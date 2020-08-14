---
title: 特定のグループに対してゲスト ユーザーをブロックする
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 特定のグループに対してゲスト ユーザーをブロックする
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662715"
---
# <a name="block-guest-users-from-a-specific-group"></a>特定のグループに対してゲスト ユーザーをブロックする

ほとんどのグループへのゲストアクセスを許可し、ゲストアクセスを禁止する場所がある場合は、個々のグループのゲストアクセスをブロックすることができます。

組織で機密ラベルを使用する場合は、グループごとのゲストアクセスを制御するためにそれらを使用することをお勧めします。 これを行う方法については、「 [機密ラベルを使用して Microsoft Teams、microsoft 365 グループ、および SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」を参照してください。 これが推奨アプローチです。

Microsoft PowerShell を使用して個々のグループへのゲストアクセスをブロックすることもできます。

グループレベルのゲストアクセス設定を変更するには、 [Graph 用の Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビューバージョンを使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Installing the Azure AD Module (Azure AD モジュールのインストール)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

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

特定のドメインを使用しているゲスト ユーザーを許可またはブロックできます。たとえば、自分の会社 (Contoso) が他の会社 (Fabrikam) とパートナーシップを結んでいる場合、許可リストに Fabrikam を追加し、ユーザーが自分のグループにそれらのゲストを追加できるようにすることができます。

詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。

## <a name="add-guests-to-the-global-address-list"></a>グローバル アドレス一覧にゲストを追加する

既定では、ゲストは Exchange グローバル アドレス一覧に表示されません。 グローバル アドレス一覧にゲストを表示するには、次の手順を使用します。

ゲスト ユーザーの ObjectID を検索するには、次を実行します。

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

次に、ObjectID、GivenName、Surname、DisplayName、TelephoneNumber の適切な値を使用して以下を実行します。

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>関連記事

[グループ メンバーシップを Microsoft 365 管理センターから管理する](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)