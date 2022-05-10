---
title: ゲストが特定のグループに追加されないようにする
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: ゲストが特定のグループに追加されないようにする方法について説明します
ms.openlocfilehash: f050011427ceeeff8347c2acd5b6d3fbbcf11bec
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2022
ms.locfileid: "65285316"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>ゲストが特定のMicrosoft 365 グループまたはMicrosoft Teams チームに追加されないようにする

ほとんどのグループとチームへのゲスト アクセスを許可するが、ゲスト アクセスを禁止する場所がある場合は、個々のグループとチームのゲスト アクセスをブロックできます。 (チームへのゲスト アクセスのブロックは、関連付けられているグループへのゲスト アクセスをブロックすることによって行われます)。これにより、新しいゲストが追加されるのを防ぎますが、グループまたはチームに既に参加しているゲストは削除されません。

組織内で秘密度ラベルを使用する場合は、それらを使用してグループごとにゲスト アクセスを制御することをお勧めします。 これを行う方法については、[秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、およびSharePoint サイトのコンテンツを保護](../compliance/sensitivity-labels-teams-groups-sites.md)します。 これが推奨アプローチです。

## <a name="change-group-settings-using-microsoft-powershell"></a>Microsoft PowerShell を使用してグループ設定を変更する

PowerShell を使用して、個々のグループに新しいゲストが追加されないようにすることもできます。 (チームに関連付けられているSharePoint サイトには[、個別のゲスト共有コントロール](/sharepoint/change-external-sharing-site)があることを忘れないでください)。

Azure Active Directory [PowerShell for Graph](/powershell/azure/active-directory/install-adv2)のプレビュー バージョン (モジュール名 **AzureADPreview**) を使用して、グループ レベルのゲスト アクセス設定を変更する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。

> [!NOTE]
> これらのコマンドを実行するには、全体管理者権限が必要です。 

*\<GroupName\>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

設定を検証するために、次のコマンドを実行します。

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

検証は次のようになります。
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)

設定を切り替えて特定のグループへのゲスト アクセスを許可する場合は、次のスクリプトを実行し、ゲスト アクセスを許可するグループの名前に変更 ```<GroupName>``` します。

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$True
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
$id = (get-AzureADObjectSetting -TargetType groups -TargetObjectId $groupID).id
Set-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy -id $id
```

## <a name="allow-or-block-guest-access-based-on-their-domain"></a>ゲストのドメインに応じてゲスト アクセスを許可またはブロックする

特定のドメインを使用しているゲストを許可またはブロックできます。 たとえば、ビジネス (Contoso) が別のビジネス (Fabrikam) とパートナーシップを結ぶ場合、ユーザーがそれらのゲストをグループに追加できるように、Fabrikam を許可リストに追加できます。

詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)」を参照してください。

## <a name="add-guests-to-the-global-address-list"></a>グローバル アドレス一覧にゲストを追加する

既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。 グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。

次を実行して、ゲストの ObjectID を見つけます。

```PowerShell
get-AzureADUser -all $true | ?{$_.CreationType -eq "Invitation"}
```

次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[グループ メンバーシップを Microsoft 365 管理センターから管理する](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory アクセス レビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)
