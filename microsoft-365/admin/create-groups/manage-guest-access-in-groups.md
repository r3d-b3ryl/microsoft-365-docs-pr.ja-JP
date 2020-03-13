---
title: Office 365 グループでゲスト アクセスを管理する
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Office 365 グループへのゲストの追加、ゲスト ユーザーの表示、PowerShell を使用したゲスト アクセスの制御を行う方法について説明します。
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610615"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Office 365 グループでゲスト アクセスを管理する

既定では、組織で Office 365 グループのゲスト アクセスが有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

有効になっている場合、グループ メンバーは Outlook on the Web を使用して、ゲスト ユーザーを Office 365 グループに招待できます。 招待状が承認のためにグループの所有者に送信されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Office 365 接続 Yammer グループは、現在ゲスト アクセスをサポートしていません。ただし、接続されていない外部グループを Yammer ネットワークに作成することはできます。 手順については。「[Yammer の外部グループを作成して管理する](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx)」を参照してください。

### <a name="edit-guest-information"></a>ゲスト情報を編集する

承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。

1. 管理センターで、 [**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービスとアドイン</a>] ページの順に移動します。

2. [**Office 365 グループ**] を選択します。
  
3. [**Office 365 グループ**] ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、またはグループ所有者が組織外のユーザーをグループに追加できるようにするかを選択します。

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>管理センターから Office 365 グループにゲストを追加する

ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。
  
1. 管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。
  
2. ゲストを追加するグループを選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。 
  
4. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。
    
5. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。
  
## <a name="block-guest-users-from-a-specific-group"></a>特定のグループに対してゲスト ユーザーをブロックする

ほとんどのグループへのゲスト アクセスを許可したいが、ゲスト アクセスを防止する必要がある場合は、Microsoft PowerShell を使用して個々のグループのゲスト アクセスをブロックすることができます。

グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

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
    
![ゲスト グループのアクセスが False に設定されていることを示す PowerShell ウィンドウのスクリーンショット。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
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

[グループ メンバーシップを Microsoft 365 管理センターから管理する](add-or-remove-members-from-groups.md)
  
[Azure Active Directory アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
