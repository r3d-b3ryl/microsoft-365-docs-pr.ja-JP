---
title: PowerShell Microsoft 365グループを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: この記事では、PowerShell のグループに対して一般的な管理Microsoft 365する方法について説明します。
ms.openlocfilehash: 82617a33695135a8ad2fa6cce65c60d435d7d180
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221045"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>PowerShell Microsoft 365グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事では、Microsoft PowerShell でグループの一般的な管理タスクを行うための手順について説明します。 また、グループの PowerShell コマンドレットを示します。 SharePoint サイトを管理する方法の詳細については、「[PowerShell を使用して SharePoint Online サイトを管理する](/sharepoint/manage-team-and-communication-sites-in-powershell)」を参照してください。

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>グループの使用Microsoft 365へのリンク
<a name="BK_LinkToGuideLines"> </a>

ユーザーが [Outlook でグループを作成または編集](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)するときに、組織での使用に関するガイドラインへのリンクをそのユーザーに表示することができます。 たとえば、グループ名に特定のプレフィックスまたはサフィックスを追加する必要がある場合があります。

ユーザーをAzure Active Directory (Azure AD) PowerShell を使用して、ユーザーが組織のグループの使用ガイドラインをMicrosoft 365します。 「[グループの設定を構成するための Azure Active Directory コマンドレット](/azure/active-directory/enterprise-users/groups-settings-cmdlets)」の「**ディレクトリ レベルでの設定の作成**」の手順に従って、使用ガイドラインのハイパーリンクを定義します。 AAD コマンドレットを実行すると、ユーザーがグループを作成または編集するときにガイドラインへのリンクが表示Outlook。

![[使用ガイドライン] リンクを使用して新しいグループを作成します。](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![[グループの使用ガイドライン] をクリックして、組織とOffice 365ガイドラインを確認します。](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>ユーザーがグループとして送信Microsoft 365する
<a name="BK_LinkToGuideLines"> </a>

グループを "送信者" にMicrosoft 365する場合は[、Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)コマンドレットと[Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission)コマンドレットを使用してこれを構成します。 この設定を有効にすると、Microsoft 365 ユーザーは Outlook または Outlook on the web を使用して電子メールを送信および返信Microsoft 365できます。 ユーザーはグループに移動し、新しいメールを作成して、「メールボックス所有者として送信する」フィールドをグループのメール アドレスに変更することができます。

([Exchange 管理センターでもこれを行うことができます](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)。)

次のスクリプトを使用して、更新するグループのエイリアスと、アクセス許可を付与するユーザーのエイリアスに *\<GroupAlias\>* *\<UserAlias\>* 置き換える。 [Exchange Online PowerShell に接続し](/powershell/exchange/connect-to-exchange-online-powershell)、このスクリプトを実行します。

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

コマンドレットが実行されると、**From** フィールドにグループ メール アドレスを追加することにより、ユーザーが Outlook または Outlook on the web に移動して、グループとして送信することができます。

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>組織内のグループMicrosoft 365分類を作成する

組織内のユーザーがグループを作成するときに設定できる感度ラベルをMicrosoft 365できます。 グループを分類する場合は、以前のグループ分類機能ではなく、感度ラベルを使用することをお勧めします。 感度ラベルの使用の詳細については、「感度ラベルを使用して、Microsoft Teams、Microsoft 365、およびサイトのコンテンツを保護する」[をSharePointしてください](../compliance/sensitivity-labels-teams-groups-sites.md)。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、感度ラベルが有効になると、グループを作成するユーザーは使用できなくなりました。

以前のグループ分類機能は引き続き使用できます。 組織のユーザーがグループを作成するときに設定できる分類をMicrosoft 365できます。 たとえば、作成するグループにユーザーが「標準」、「機密」、「極秘」といった分類を設定できるようにすることができます。 グループの分類は既定では設定されていないので、ユーザーに分類を設定させるには、分類を作成する必要があります。 PowerShell Azure Active Directoryを使用して、ユーザーに組織のグループの使用ガイドラインをMicrosoft 365します。

グループ設定[Azure Active Directoryする](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)コマンドレットを確認し、「ディレクトリ レベルで設定を作成する」の手順に従って、グループグループのMicrosoft 365してください。

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

各分類に説明を関連付けるために、定義する設定属性 *ClassificationDescriptions* を使用できます。

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

ここで、Classification は ClassificationList の文字列と一致します。

例:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

上の Azure Active Directory コマンドレットを実行して分類を設定した後、特定のグループに分類を設定する場合は、[Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) コマンドレットを実行します。

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

または、分類を使用して新しいグループを作成します。

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Exchange Online PowerShell の使用の詳細については、「[Exchange Online による PowerShell の使用](/powershell/exchange/exchange-online-powershell)」および「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

これらの設定を有効にした後、グループの所有者は、Outlook on the web および Outlook​​ のドロップダウン メニューから分類を選択し、[**編集**] グループ ページから分類を保存できるようになります。

![[グループMicrosoft 365] を選択します。](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>グローバル アドレスMicrosoft 365グループを非表示にする。
<a name="BKMK_CreateClassification"> </a>

組織のグローバル アドレス一Microsoft 365 (GAL) および他のリストにグループを表示するかどうかを指定できます。 たとえば、住所一覧に表示しない法務部門グループがある場合は、そのグループが GAL に表示されるのを停止できます。 次のようにSet-Unifiedグループコマンドレットを実行して、グループをアドレス一覧から非表示にします。

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>内部ユーザーだけがグループにメッセージを送信Microsoft 365する
<a name="BKMK_CreateClassification"> </a>

他の組織のユーザーがグループにメールを送信Microsoft 365場合は、そのグループの設定を変更できます。 これにより、内部のユーザーのみがグループにメールを送信できるようになります。 外部ユーザーがメッセージをそのグループに送信しようとすると、そのメッセージは拒否されます。

この設定を更新するには、次のように Set-UnifiedGroup コマンドレットを実行します。

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>メール ヒントをグループにMicrosoft 365する
<a name="BKMK_CreateClassification"> </a>

送信者がグループに電子メールを送信Microsoft 365、メール ヒントを表示できます。

グループにメール ヒントを追加するには、Set-UnifiedGroup コマンドレットを実行します。

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

メール ヒントと共に、MailTipTranslations を設定することもできます。これは、メール ヒントの追加言語を指定します。 スペイン語の翻訳を追加するとします。この場合は、次のコマンドを実行します。

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>グループの表示名をMicrosoft 365する

表示名は、グループの名前Microsoft 365します。 この名前は、Exchange 管理センターまたは exchange 管理センターで確認<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター。</a> 次のコマンドを実行して、グループの表示名を編集したり、既存のグループに表示Microsoft 365割り当Set-UnifiedGroupできます。

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>グループのグループの既定Microsoft 365を [パブリックOutlookプライベート] に変更する
<a name="BKMK_CreateClassification"> </a>

Microsoft 365既定では、Outlookグループは Private として作成されます。 組織で既定で Microsoft 365として作成する (またはプライベートに戻す) 場合は、次の PowerShell コマンドレット構文を使用します。

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

非公開に設定するには:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

設定を確認するには:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

詳細については、「[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)」および「[Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)」を参照してください。

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365グループコマンドレット

次のコマンドレットは、グループとMicrosoft 365できます。

|**コマンドレット名**|**Description**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |このコマンドレットを使用して、グループの既存Microsoft 365を参照し、グループ オブジェクトのプロパティを表示します。  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |特定のグループのプロパティをMicrosoft 365する  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |グループに新しいMicrosoft 365します。 このコマンドレットは、最小限のパラメーター セットを提供します。 拡張プロパティの値を設定するには、新しいSet-UnifiedGroup後にプロパティを使用します。  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |既存のグループをMicrosoft 365する  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |グループのメンバーシップと所有者情報をMicrosoft 365する  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |メンバー、所有者、およびサブスクライバーを既存のグループにMicrosoft 365する <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |既存のグループから所有者とメンバーをMicrosoft 365する  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |アカウントと関連付けられたユーザーの写真について情報を表示します。 パスワードは Active Directory に格納されます。  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |ユーザーの写真をアカウントに関連付けるために使用します。 パスワードは Active Directory に格納されます。  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |グループの写真をMicrosoft 365する  <br/> |

## <a name="related-topics"></a>関連項目

[配布リストをグループにMicrosoft 365する](/office365/admin/manage/upgrade-distribution-lists)

[Microsoft 365 グループを作成できるユーザーを管理する](/office365/admin/create-groups/manage-creation-of-groups)

[グループへのゲスト アクセスMicrosoft 365する](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[静的なグループメンバーシップを動的に変更する](/azure/active-directory/users-groups-roles/groups-change-type)
