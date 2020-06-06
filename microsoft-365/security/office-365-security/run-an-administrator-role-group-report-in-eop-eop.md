---
title: スタンドアロン EOP で管理者役割グループ レポートを実行する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者の役割グループレポートを実行する方法について説明します。 このレポートは、管理者が管理者の役割グループに対してメンバーを追加または削除したときにログに記録されます。このレポートには、EOP ごとにログが記録
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587366"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="3208d-104">スタンドアロン EOP で管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="3208d-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="3208d-105">Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、管理者が管理役割グループにメンバーを追加したり、管理者の役割グループからメンバーを削除したりすると、サービスによって各発生がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3208d-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="3208d-106">スタンドアロン EOP の役割グループの詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3208d-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="3208d-107">Exchange 管理センター (EAC) で管理者の役割グループレポートを実行すると、エントリが検索結果として表示され、影響を受ける役割グループ、役割グループのメンバーシップと日時、および作成されたメンバーシップの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3208d-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="3208d-108">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視します。</span><span class="sxs-lookup"><span data-stu-id="3208d-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3208d-109">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3208d-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3208d-110">Exchange 管理センターを開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3208d-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3208d-111">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3208d-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="3208d-112">具体的には、ComplianceManagement、組織の管理 (グローバル管理者)、および SecurityAdministrator の役割グループに既定で割り当てられている監査ログまたは表示専用の監査ログの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="3208d-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="3208d-113">詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。</span><span class="sxs-lookup"><span data-stu-id="3208d-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="3208d-114">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3208d-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3208d-115">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="3208d-115">Having problems?</span></span> <span data-ttu-id="3208d-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="3208d-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="3208d-117">EAC を使用して管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="3208d-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="3208d-118">管理者の役割グループレポートを実行して、組織内の管理役割グループに対する変更を特定の時間枠で検索します。</span><span class="sxs-lookup"><span data-stu-id="3208d-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="3208d-119">EAC で、[**コンプライアンス管理**] [監査] に移動し、 \> **Auditing**[**管理者の役割グループレポートの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3208d-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="3208d-120">[**管理者の役割グループへの変更の検索**] ページが開いたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3208d-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3208d-121">**開始**日と**終了日**: 日付の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="3208d-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="3208d-122">既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3208d-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="3208d-123">**役割グループの選択**: 既定では、すべての役割グループが検索されます。</span><span class="sxs-lookup"><span data-stu-id="3208d-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="3208d-124">特定の役割グループによって結果をフィルター処理するには、[**役割グループの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3208d-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="3208d-125">表示されるダイアログで、役割グループを選択し、[**追加->**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3208d-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="3208d-126">必要な回数だけこの手順を繰り返し、完了したら [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3208d-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="3208d-127">完了したら、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3208d-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="3208d-p108">指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3208d-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3208d-130">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="3208d-130">How do you know this worked?</span></span>

<span data-ttu-id="3208d-p109">管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="3208d-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="3208d-134">役割グループのメンバーシップに対する変更の監視</span><span class="sxs-lookup"><span data-stu-id="3208d-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="3208d-p110">役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。</span><span class="sxs-lookup"><span data-stu-id="3208d-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="3208d-p111">ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3208d-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="3208d-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="3208d-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="3208d-140">管理者</span><span class="sxs-lookup"><span data-stu-id="3208d-140">Administrator</span></span> <br> <span data-ttu-id="3208d-141">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="3208d-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="3208d-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="3208d-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="3208d-143">管理者</span><span class="sxs-lookup"><span data-stu-id="3208d-143">Administrator</span></span> <br> <span data-ttu-id="3208d-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="3208d-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="3208d-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="3208d-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="3208d-146">管理者</span><span class="sxs-lookup"><span data-stu-id="3208d-146">Administrator</span></span> <br> <span data-ttu-id="3208d-147">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="3208d-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="3208d-148">この例では、管理者ユーザー アカウントによって次の変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="3208d-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="3208d-149">2/06/2018 で、ユーザー tonip を追加しました。</span><span class="sxs-lookup"><span data-stu-id="3208d-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="3208d-150">2/19/2018 で、ユーザー pilarp がが削除されました。</span><span class="sxs-lookup"><span data-stu-id="3208d-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="3208d-151">スタンドアロンの Exchange Online PowerShell を使用して監査ログエントリを検索する</span><span class="sxs-lookup"><span data-stu-id="3208d-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="3208d-152">Exchange Online の PowerShell を使用して、指定した条件に一致する監査ログエントリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3208d-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="3208d-153">検索条件の一覧については、「[検索-AdminAuditLog ログの検索条件](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3208d-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="3208d-154">この手順では、**検索-AdminAuditLog**コマンドレットを使用して、Exchange Online PowerShell で検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="3208d-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="3208d-155">このコマンドレットは、 **New-AdminAuditLogSearch** コマンドレットまたは EAC 監査レポートのレポートで定義されている制限値を超える結果セットを返す必要がある場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3208d-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="3208d-156">指定した条件で監査ログを検索するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3208d-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="3208d-157">**Search-AdminAuditLog** コマンドレットを実行すると、既定で最大 1,000 個のログ エントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="3208d-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="3208d-158">_Resultsize_パラメーターを使用して、最大25万のログエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="3208d-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="3208d-159">または、値を使用して `Unlimited` すべてのエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="3208d-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="3208d-160">この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="3208d-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="3208d-161">**開始日**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="3208d-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="3208d-162">**終了日**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="3208d-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="3208d-163">**ユーザー id**: davids、chrisd、kima</span><span class="sxs-lookup"><span data-stu-id="3208d-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="3208d-164">**コマンドレット**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="3208d-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="3208d-165">**パラメーター**: _ProhibitSendQuota_、 _ProhibitSendReceiveQuota_、 _warnings ewarnings quota_、 _maxsendsize_、 _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="3208d-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="3208d-p114">この例では、特定のメールボックスの変更を検索します。これは、トラブルシューティングを実行している場合や、調査のために情報を入手する必要がある場合に便利です。次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="3208d-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="3208d-169">**開始日**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="3208d-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="3208d-170">**終了日**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="3208d-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="3208d-171">**オブジェクト ID**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="3208d-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="3208d-172">検索に多数のログエントリが返される場合は、このトピックで後述する「 **Exchange Online PowerShell を使用して監査ログエントリを検索し、結果を受信者に送信**する」で説明されている手順を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3208d-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="3208d-173">その手順を実行すると、指定した受信者に XML ファイルが電子メールの添付ファイルとして送信されるため、目的のデータをより簡単に抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="3208d-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="3208d-174">構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3208d-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="3208d-175">監査ログ エントリの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3208d-175">View details of audit log entries</span></span>

<span data-ttu-id="3208d-176">**検索-Adminauditlog**コマンドレットは、「[監査ログの内容](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)」に記載されているフィールドを返します。</span><span class="sxs-lookup"><span data-stu-id="3208d-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="3208d-177">コマンドレットによって返されるフィールドのうち、 **CmdletParameters** と **ModifiedProperties** の 2 つのフィールドには、既定では表示できない追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3208d-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="3208d-178">**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3208d-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="3208d-179">または、「 **Exchange Online PowerShell を使用して監査ログエントリを検索し、結果を受信者に送信**する」の手順を使用して、XML ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3208d-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="3208d-180">この手順では、次の概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="3208d-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="3208d-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="3208d-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="3208d-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="3208d-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="3208d-183">検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="3208d-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="3208d-184">各監査ログエントリは、変数に配列要素として格納され `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="3208d-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="3208d-185">配列要素のインデックスを指定することで、配列要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3208d-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="3208d-186">配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。</span><span class="sxs-lookup"><span data-stu-id="3208d-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="3208d-187">たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3208d-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="3208d-p119">上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3208d-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="3208d-190">**CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="3208d-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>