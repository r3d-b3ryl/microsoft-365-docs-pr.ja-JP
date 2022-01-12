---
title: Microsoft 365 グループを作成できるユーザーを管理する
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: ユーザーがグループを作成できるユーザーを制御Microsoft 365します。
ms.openlocfilehash: 4280b6859358580547302ccf9497e8cd1e7ed752
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61939407"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Microsoft 365 グループを作成できるユーザーを管理する

既定では、すべてのユーザーがグループMicrosoft 365できます。 IT の支援を必要とせずにユーザーが共同作業を開始できるので、この方法をお勧めします。

ビジネスでグループを作成できるユーザーを制限する必要がある場合は、Microsoft 365グループの作成を特定のグループまたはセキュリティ グループのMicrosoft 365制限できます。

ビジネス標準に準拠しないチームまたはグループを作成するユーザーが気になる場合は、ユーザーにトレーニング コースを完了し、許可されたユーザーのグループに追加する必要があります。

グループを作成できるユーザーを制限すると、グループに依存してアクセスを行うすべてのサービスに影響します。

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (クラシック)
- Projectの詳細 / ロードマップ

この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。 Office 365管理者は、[オンライン] 、Microsoft 365 管理センター、Exchange、および SharePointをSharePointできます。 他の役割は、以下のような制限付きの方法でグループを作成できます。

- Exchange管理者: Exchange管理センター、Azure AD
- パートナー層 1 のサポート: Microsoft 365 管理センター、Exchange管理センター、Azure AD
- パートナー層 2 のサポート: Microsoft 365 管理センター、Exchange管理センター、Azure AD
- ディレクトリ製作者: Azure AD
- SharePoint管理者: SharePoint管理センター、Azure AD
- Teams サービス管理者: Teams管理センター、Azure AD
- ユーザー管理者: Microsoft 365 管理センター、Azure AD

これらの役割の 1 つのメンバーである場合は、制限付きユーザー Microsoft 365グループを作成し、そのユーザーをグループの所有者として割り当てることができます。

## <a name="licensing-requirements"></a>ライセンスの要件

グループを作成するユーザーを管理するには、次のユーザーに割りAzure AD Premiumライセンスを割り当てる必要があります。

- これらのグループ作成の設定を管理している管理者
- グループの作成が許可されているグループのメンバー

> [!NOTE]
> Azure[ライセンスの割り当て方法の詳細については、「Azure Active Directory ポータル](/azure/active-directory/fundamentals/license-users-groups)でライセンスを割り当てるまたは削除する」を参照してください。

次のユーザーは、割り当Azure AD Premiumライセンスを必要としません。

- グループのメンバー Microsoft 365他のグループを作成できないユーザー。

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>手順 1: グループを作成する必要があるユーザーのグループをMicrosoft 365する

グループを作成できるユーザーを制御するには、組織内の 1 つのグループのみを使用できます。 ただし、他のグループをこのグループのメンバーとして入れ子にすることもできます。

上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。

1. 管理センターで、[グループ] ページ [に移動します](https://admin.microsoft.com/adminportal/home#/groups)。

2. [**グループの追加**] をクリックします。

3. 必要なグループの種類を選択します。 グループの名前は覚えておいてください。 後で必要になります。

4. グループの設定を完了し、組織でグループを作成できるユーザーまたは他のグループを追加します。

詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](../admin/email/create-edit-or-delete-a-security-group.md)」を参照してください。

## <a name="step-2-run-powershell-commands"></a>手順 2: PowerShell コマンドを実行する

グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。

下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。

作成 *\<GroupName\>* したグループの名前に置き換える。 例:

`$GroupName = "Group Creators"`

GroupCreators.ps1 としてファイルを保存します。

PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD \<FileLocation\>" と入力)。

次のように入力してスクリプトを実行します。

`.\GroupCreators.ps1`

サインインを求められたら、[管理者アカウントでサインイン](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)します。

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
    $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
  $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
} else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

スクリプトの最後の行に、更新された設定が表示されます。

![PowerShell スクリプト出力のスクリーンショット。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

今後、使用するグループを変更する場合は、新しいグループの名前でスクリプトを再実行できます。

グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。

## <a name="step-3-verify-that-it-works"></a>手順 3: 動作することを確認する

変更を有効にするには、30 分以上かかる場合があります。 新しい設定を確認するには、次の手順を実行します。

1. グループを作成Microsoft 365する必要があるユーザーのユーザー アカウントを使用して、グループにサインインします。 つまり、作成したグループまたは管理者のメンバーではありません。

2. [**Planner**] タイルを選択します。

3. Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。

4. プランとグループの作成が無効になっていることを示すメッセージが表示されます。

グループのメンバーと同じ手順を再度実行します。

> [!NOTE]
> グループのメンバーがグループを作成できない場合は、OWA メールボックス ポリシーによってブロックされていない [か確認します](/powershell/module/exchange/set-owamailboxpolicy)。

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画の推奨事項](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[Office 365 PowerShell の概要](../enterprise/getting-started-with-microsoft-365-powershell.md)

[セルフサービス グループ管理に必要な Azure Active Directory の設定](/azure/active-directory/users-groups-roles/groups-self-service-management)

[ExecutionPolicy の設定](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[グループ設定を構成するための Azure Active Directory コマンドレット](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
