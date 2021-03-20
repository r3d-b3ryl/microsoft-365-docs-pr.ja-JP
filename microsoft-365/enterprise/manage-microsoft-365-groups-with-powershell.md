---
title: PowerShell を使用して Microsoft 365 グループを管理する
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
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: この記事では、PowerShell で Microsoft 365 グループの一般的な管理タスクを実行する方法について説明します。
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911052"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a>PowerShell を使用して Microsoft 365 グループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事では、Microsoft PowerShell でグループの一般的な管理タスクを行うための手順について説明します。 また、グループの PowerShell コマンドレットを示します。 SharePoint サイトを管理する方法の詳細については、「[PowerShell を使用して SharePoint Online サイトを管理する](/sharepoint/manage-team-and-communication-sites-in-powershell)」を参照してください。

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Microsoft 365 グループの使用ガイドラインへのリンク
<a name="BK_LinkToGuideLines"> </a>

ユーザーが [Outlook でグループを作成または編集](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)するときに、組織での使用に関するガイドラインへのリンクをそのユーザーに表示することができます。 たとえば、グループ名に特定のプレフィックスまたはサフィックスを追加する必要がある場合があります。

Azure Active Directory (Azure AD) PowerShell を使用して、Microsoft 365 グループの組織の使用ガイドラインをユーザーに示します。 「[グループの設定を構成するための Azure Active Directory コマンドレット](/azure/active-directory/enterprise-users/groups-settings-cmdlets)」の「**ディレクトリ レベルでの設定の作成**」の手順に従って、使用ガイドラインのハイパーリンクを定義します。 AAD コマンドレットを実行すると、ユーザーが Outlook でグループを作成または編集するときに、ガイドラインへのリンクが表示されます。

![使用ガイドラインのリンクがある新しいグループを作成する](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![グループ使用ガイドラインをクリックして、組織の Office 365 グループのガイドラインを参照する](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>ユーザーが Microsoft 365 グループとして送信を許可する
<a name="BK_LinkToGuideLines"> </a>

Microsoft 365 グループで "Send As" を有効にする場合は [、Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) コマンドレットと [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) コマンドレットを使用してこれを構成します。 この設定を有効にすると、Microsoft 365 グループ ユーザーは Outlook または Outlook on the web を使用して、Microsoft 365 グループとして電子メールを送信および返信できます。 ユーザーはグループに移動し、新しいメールを作成して、「メールボックス所有者として送信する」フィールドをグループのメール アドレスに変更することができます。

([Exchange 管理センターでもこれを行うことができます](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)。)

次のスクリプトを使用して、更新するグループのエイリアスと、アクセス許可を付与するユーザーのエイリアスに *\<GroupAlias\>* *\<UserAlias\>* 置き換える。 [Exchange Online PowerShell に接続し](/powershell/exchange/connect-to-exchange-online-powershell)、このスクリプトを実行します。

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

コマンドレットが実行されると、**From** フィールドにグループ メール アドレスを追加することにより、ユーザーが Outlook または Outlook on the web に移動して、グループとして送信することができます。

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>組織内の Microsoft 365 グループの分類を作成する

組織内のユーザーが Microsoft 365 グループを作成するときに設定できる感度ラベルを作成できます。 グループを分類する場合は、以前のグループ分類機能ではなく、感度ラベルを使用することをお勧めします。 感度ラベルの使用の詳細については、「感度ラベルを使用して [Microsoft Teams、Microsoft 365](../compliance/sensitivity-labels-teams-groups-sites.md)グループ、および SharePoint サイトのコンテンツを保護する」を参照してください。

> [!IMPORTANT]
> 現在分類ラベルを使用している場合、感度ラベルが有効になると、グループを作成するユーザーは使用できなくなりました。

以前のグループ分類機能は引き続き使用できます。 組織内のユーザーが Microsoft 365 グループを作成するときに設定できる分類を作成できます。 たとえば、作成するグループにユーザーが「標準」、「機密」、「極秘」といった分類を設定できるようにすることができます。 グループの分類は既定では設定されていないので、ユーザーに分類を設定させるには、分類を作成する必要があります。 Azure Active Directory PowerShell を使用して、Microsoft 365 グループの組織の使用ガイドラインをユーザーに示します。

グループ設定[を構成するための Azure Active Directory](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)コマンドレットを確認し、「ディレクトリレベルで設定を作成する」の手順に従って、Microsoft 365 グループの分類を定義します。

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

![Microsoft 365 グループ分類の選択](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>グローバル アドレス一覧から Microsoft 365 グループを非表示にする。
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 グループを組織のグローバル アドレス一覧 (GAL) および他のリストに表示するかどうかを指定できます。 たとえば、住所一覧に表示しない法務部門グループがある場合は、そのグループが GAL に表示されるのを停止できます。 次のようにSet-Unifiedグループコマンドレットを実行して、グループをアドレス一覧から非表示にします。

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>内部ユーザーだけが Microsoft 365 グループにメッセージを送信できる
<a name="BKMK_CreateClassification"> </a>

他の組織のユーザーが Microsoft 365 グループにメールを送信したくない場合は、そのグループの設定を変更できます。 これにより、内部のユーザーのみがグループにメールを送信できるようになります。 外部ユーザーがメッセージをそのグループに送信しようとすると、そのメッセージは拒否されます。

この設定を更新するには、次のように Set-UnifiedGroup コマンドレットを実行します。

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>Microsoft 365 グループへのメール ヒントの追加
<a name="BKMK_CreateClassification"> </a>

送信者が Microsoft 365 グループに電子メールを送信しようとするたびに、メール ヒントを表示できます。

グループにメール ヒントを追加するには、Set-UnifiedGroup コマンドレットを実行します。

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

メール ヒントと共に、MailTipTranslations を設定することもできます。これは、メール ヒントの追加言語を指定します。 スペイン語の翻訳を追加するとします。この場合は、次のコマンドを実行します。

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>Microsoft 365 グループの表示名を変更する

表示名は、Microsoft 365 グループの名前を指定します。 この名前は、Exchange 管理センターまたは Microsoft 365 管理センターで確認できます。 グループの表示名を編集するか、既存の Microsoft 365 グループに表示名を割り当てるには、次のコマンドSet-UnifiedGroupします。

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>Outlook 用 Microsoft 365 グループの既定の設定をパブリックまたはプライベートに変更する
<a name="BKMK_CreateClassification"> </a>

Outlook の Microsoft 365 グループは、既定でプライベートとして作成されます。 組織で Microsoft 365 グループを既定でパブリック (またはプライベートに戻す) として作成する場合は、次の PowerShell コマンドレット構文を使用します。

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

非公開に設定するには:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

設定を確認するには:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

詳細については、「[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)」および「[Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)」を参照してください。

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 グループのコマンドレット

次のコマンドレットは、Microsoft 365 グループと一緒に使用できます。

|**コマンドレット名**|**Description**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |このコマンドレットを使用して、既存の Microsoft 365 グループを参照し、グループ オブジェクトのプロパティを表示する  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |特定の Microsoft 365 グループのプロパティを更新する  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |新しい Microsoft 365 グループを作成します。 このコマンドレットは、最小限のパラメーター セットを提供します。 拡張プロパティの値を設定するには、新しいSet-UnifiedGroup後にプロパティを使用します。  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |既存の Microsoft 365 グループを削除する  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Microsoft 365 グループのメンバーシップと所有者の情報を取得する  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |既存の Microsoft 365 グループにメンバー、所有者、およびサブスクライバーを追加する <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |既存の Microsoft 365 グループから所有者とメンバーを削除する  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |アカウントと関連付けられたユーザーの写真について情報を表示します。 パスワードは Active Directory に格納されます。  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |ユーザーの写真をアカウントに関連付けるために使用します。 パスワードは Active Directory に格納されます。  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |Microsoft 365 グループの写真を削除する  <br/> |

## <a name="related-topics"></a>関連項目

[配布リストを Microsoft 365 グループにアップグレードする](/office365/admin/manage/upgrade-distribution-lists)

[Microsoft 365 グループを作成できるユーザーを管理する](/office365/admin/create-groups/manage-creation-of-groups)

[Microsoft 365 グループへのゲスト アクセスを管理する](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[静的なグループメンバーシップを動的に変更する](/azure/active-directory/users-groups-roles/groups-change-type)