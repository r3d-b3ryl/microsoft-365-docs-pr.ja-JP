---
title: 特定のグループにゲストが追加されるのを防ぐ
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 特定のグループにゲストが追加されるのを防ぐ方法について説明します。
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660050"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>特定の Microsoft 365 グループまたは Microsoft Teams チームにゲストが追加されるのを防ぐ

ほとんどのグループやチームへのゲスト アクセスを許可するが、ゲスト アクセスを防止する必要がある場合は、個々のグループとチームのゲスト アクセスをブロックできます。 (チームへのゲスト アクセスをブロックするには、関連付けられているグループへのゲスト アクセスをブロックします)。これにより、新しいゲストは追加されませんが、グループまたはチームに既に存在するゲストは削除されません。

組織で感度ラベルを使用する場合は、グループごとにゲスト アクセスを制御するために使用することをお勧めします。 これを行う方法については [、Microsoft Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用します。 これが推奨アプローチです。

## <a name="change-group-settings-using-microsoft-powershell"></a>Microsoft PowerShell を使用してグループ設定を変更する

PowerShell を使用して、個々のグループへの新しいゲストの追加を防止することもできます。 (チームに関連付けられた SharePoint サイトには、個別の [ゲスト共有コントロールがある点に注意してください](https://docs.microsoft.com/sharepoint/change-external-sharing-site))。

グループ レベルのゲスト アクセス設定を変更するには、Graph 用 [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) のプレビュー バージョン (モジュール名 **AzureADPreview)** を使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview` を実行しそれがこのモジュールの最新バージョンであることを確認します。

> [!NOTE]
> これらのコマンドを実行するには、全体管理者権限が必要です。 

*/<GroupName/>* をゲスト アクセスをブロックするグループの名前に変更し、次のスクリプトを実行します。

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
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>ゲストのドメインに応じてゲスト アクセスを許可またはブロックする

特定のドメインを使用しているゲストを許可またはブロックできます。 たとえば、会社 (Contoso) が別のビジネス (Fabrikam) とパートナーシップを持っている場合は、許可リストに Fabrikam を追加して、ユーザーがそれらのゲストを自分のグループに追加できます。

詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。

## <a name="add-guests-to-the-global-address-list"></a>グローバル アドレス一覧にゲストを追加する

既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。 グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。

次のコマンドを実行して、ゲストの ObjectID を検索します。

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>関連項目

[グループコラボレーション ガバナンスの計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[グループ メンバーシップを Microsoft 365 管理センターから管理する](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
