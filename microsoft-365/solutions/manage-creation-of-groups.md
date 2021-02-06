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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Microsoft 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122386"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Microsoft 365 グループを作成できるユーザーを管理する

既定では、すべてのユーザーが Microsoft 365 グループを作成できます。 IT の支援を必要とせずにユーザーが共同作業を開始できる場合、この方法をお勧めします。

ビジネスでグループを作成できるユーザーを制限する必要がある場合は、この記事の手順に従います。 グループを作成できるユーザーを制限すると、アクセスにグループに依存する次のようなすべてのサービスに影響します。

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (クラシック)
- Project for the web / Roadmap

Microsoft 365 グループの作成は、特定の Microsoft 365 グループまたはセキュリティ グループのメンバーに制限できます。 制限するには、Windows PowerShell を使用します。 この記事では、必要な手順について説明します。

この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。 Office 365 のグローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの方法でグループを作成できます。 他の役割は、以下のような制限付きの方法でグループを作成できます。

- Exchange 管理者: Exchange 管理センター、Azure AD
- パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD
- パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD
- ディレクトリ製作者: Azure AD
- SharePoint 管理者: SharePoint 管理センター、Azure AD
- Teams サービス管理者: Teams 管理センター、Azure AD
- ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD

これらの役割のメンバーである場合は、制限付きユーザー用に Microsoft 365 グループを作成し、そのユーザーをグループの所有者として割り当てることができます。

## <a name="licensing-requirements"></a>ライセンスの要件

グループを作成するユーザーを管理するには、次のユーザーに Azure AD Premium ライセンスまたは Azure AD Basic EDU ライセンスが割り当てられている必要があります。

- これらのグループ作成の設定を管理している管理者
- グループの作成が許可されているグループのメンバー

> [!NOTE]
> [Azure ライセンスを割り当てる方法](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)の詳細については、「Azure Active Directory ポータルでライセンスを割り当てるまたは削除する」を参照してください。

以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。

- Microsoft 365 グループのメンバーであり、他のグループを作成できないユーザー。

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>手順 1: Microsoft 365 グループを作成する必要があるユーザーのグループを作成する

グループを作成できるユーザーを制御するために使用できるのは、組織内の 1 つのグループのみです。 ただし、他のグループをこのグループのメンバーとして入れ子にできます。

上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。

1. 管理センターで、[グループ] ページ [に移動します](https://admin.microsoft.com/adminportal/home#/groups)。

2. [**グループの追加**] をクリックします。

3. 必要なグループの種類を選択します。 グループの名前は覚えておいてください。 後で必要になります。

4. グループの設定を完了し、組織でグループを作成できるユーザーまたは他のグループを追加します。

詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)」を参照してください。

## <a name="step-2-run-powershell-commands"></a>手順 2: PowerShell コマンドを実行する

グループレベルのゲスト アクセス設定を変更するには、[Graph 用 Azure Active Directory PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (モジュール名 **AzureADPreview**) のプレビュー バージョンを使用する必要があります。

- 以前に Azure AD PowerShell モジュールのいかなるバージョンもインストールしたことがない場合には、「[Azure AD モジュールのインストール](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)」を参照し、指示に従ってパブリック プレビュー リリースをインストールしてください。

- Azure AD PowerShell モジュール (AzureAD) の 2.0 一般提供バージョンをインストールしている場合には、PowerShell セッションで `Uninstall-Module AzureAD` を実行してアンインストールし、`Install-Module AzureADPreview` を実行してプレビュー バージョンをインストールする必要があります。

- プレビュー バージョンを既にインストールしている場合には、`Install-Module AzureADPreview`を実行しそれがこのモジュールの最新バージョンであることを確認します。

下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。

作成 *\<GroupName\>* したグループの名前に置き換える。 例:

`$GroupName = "Group Creators"`

GroupCreators.ps1 としてファイルを保存します。

PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。

次のように入力してスクリプトを実行します。

`.\GroupCreators.ps1`

サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)します。

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
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

スクリプトの最後の行に、更新された設定が表示されます。

![完了すると、設定は次のように表示されます。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

今後、使用するグループを変更する場合は、新しいグループの名前を使用してスクリプトを再実行できます。

グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。

## <a name="step-3-verify-that-it-works"></a>手順 3: 動作することを確認する

変更を有効にするには、30 分以上かかる場合があります。 新しい設定を確認するには、次の手順を実行します。

1. グループを作成できないユーザーのユーザー アカウントで Microsoft 365 にサインインします。 つまり、作成したグループのメンバーまたは管理者ではありません。

2. [**Planner**] タイルを選択します。

3. Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。

4. プランとグループの作成が無効になっていることを示すメッセージが表示されます。

グループのメンバーと同じ手順を再度実行してください。

> [!NOTE]
> グループのメンバーがグループを作成できない場合は、OWA メールボックス ポリシーによってブロックされていない [か確認します](https://go.microsoft.com/fwlink/?linkid=852135)。

## <a name="related-topics"></a>関連項目

[グループコラボレーション ガバナンスの計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[Office 365 PowerShell の概要](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[ExecutionPolicy の設定](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
