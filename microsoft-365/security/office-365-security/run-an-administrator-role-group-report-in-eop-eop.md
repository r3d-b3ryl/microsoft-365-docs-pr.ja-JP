---
title: スタンドアロン EOP で管理者役割グループ レポートを実行する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者の役割グループ レポートを実行する方法を学習できます。 このレポートは、管理者が管理者役割グループのメンバーを追加または削除すると、それぞれの発生箇度をログに取り示します。
ms.openlocfilehash: db1934c7865209d358d164ff5165bb23026589cc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827507"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="45e3b-104">スタンドアロン EOP で管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="45e3b-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="45e3b-105">Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織では、管理者が管理役割グループのメンバーの追加または削除を行えると、そのサービスによってそれぞれの発生をログに格納します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="45e3b-106">スタンドアロン EOP の役割グループの詳細については、「スタンドアロン EOP の [アクセス許可」を参照してください](feature-permissions-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="45e3b-107">Exchange 管理センター (EAC) で管理者の役割グループ レポートを実行すると、エントリが検索結果として表示されます。各エントリには、影響を受ける役割グループ、役割グループのメンバーシップを変更したユーザー、およびメンバーシップの更新が実行された日時が含まれます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="45e3b-108">このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="45e3b-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="45e3b-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="45e3b-110">Exchange 管理センターを開くには、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="45e3b-111">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="45e3b-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="45e3b-112">具体的には、既定で ComplianceManagement、OrganizationManagement (グローバル管理者)、および SecurityAdministrator 役割グループに割り当てる "Audit Logs/監査ログ" 役割または "View-Only Audit Logs/監査ログ収集のみ" 役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="45e3b-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="45e3b-113">詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="45e3b-114">このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="45e3b-115">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="45e3b-115">Having problems?</span></span> <span data-ttu-id="45e3b-116">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="45e3b-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="45e3b-117">EAC を使用して管理者役割グループ レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="45e3b-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="45e3b-118">管理者役割グループ レポートを実行して、特定の期間に組織の管理役割グループに加えられた変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="45e3b-119">EAC で、コンプライアンス管理 **の監査に** \> **移動し、** 管理者の役割 **グループ レポートの実行を選択します**。</span><span class="sxs-lookup"><span data-stu-id="45e3b-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="45e3b-120">表示された **管理者の役割グループに対する変更の** 検索で、以下の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="45e3b-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="45e3b-121">**[開始日** ] **と [終了日**] : 日付範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="45e3b-122">既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="45e3b-123">**役割グループの選択**: 既定では、すべての役割グループが検索されます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="45e3b-124">特定の役割グループに対して結果をフィルター処理するには、[ **役割グループの選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="45e3b-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="45e3b-125">表示されるダイアログで、役割グループを選択して [Add ->]\*\*をクリック>。 \*\*</span><span class="sxs-lookup"><span data-stu-id="45e3b-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="45e3b-126">必要な回数だけこの手順を繰り返し、完了したら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45e3b-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="45e3b-127">完了したら、[検索] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="45e3b-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="45e3b-p108">指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="45e3b-130">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="45e3b-130">How do you know this worked?</span></span>

<span data-ttu-id="45e3b-p109">管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="45e3b-134">役割グループのメンバーシップに対する変更の監視</span><span class="sxs-lookup"><span data-stu-id="45e3b-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="45e3b-p110">役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="45e3b-p111">ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="45e3b-139">2018/1/27 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="45e3b-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="45e3b-140">管理者</span><span class="sxs-lookup"><span data-stu-id="45e3b-140">Administrator</span></span> <br> <span data-ttu-id="45e3b-141">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="45e3b-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="45e3b-142">2018/2/06 午前 10:09</span><span class="sxs-lookup"><span data-stu-id="45e3b-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="45e3b-143">管理者</span><span class="sxs-lookup"><span data-stu-id="45e3b-143">Administrator</span></span> <br> <span data-ttu-id="45e3b-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="45e3b-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="45e3b-145">2018/2/19 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="45e3b-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="45e3b-146">管理者</span><span class="sxs-lookup"><span data-stu-id="45e3b-146">Administrator</span></span> <br> <span data-ttu-id="45e3b-147">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="45e3b-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="45e3b-148">この例では、管理者ユーザー アカウントによって次の変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="45e3b-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="45e3b-149">2018 年 2 月 6 日に、ユーザー tonip が追加されました。</span><span class="sxs-lookup"><span data-stu-id="45e3b-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="45e3b-150">2018 年 2 月 19 日に、ユーザー pilarp が削除されました。</span><span class="sxs-lookup"><span data-stu-id="45e3b-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="45e3b-151">スタンドアロンの Exchange Online PowerShell を使用して監査ログ エントリを検索する</span><span class="sxs-lookup"><span data-stu-id="45e3b-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="45e3b-152">Exchange Online PowerShell を使用して、指定した条件に合う監査ログ エントリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="45e3b-153">検索条件の一覧については [、「Search-AdminAuditLog 検索条件」を参照してください](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-153">For a list of search criteria, see [Search-AdminAuditLog search criteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet).</span></span> <span data-ttu-id="45e3b-154">この手順では **Search-AdminAuditLog コマンドレットを使用** し、Exchange Online PowerShell に検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="45e3b-155">このコマンドレットは、 **New-AdminAuditLogSearch** コマンドレットまたは EAC 監査レポートのレポートで定義されている制限値を超える結果セットを返す必要がある場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="45e3b-156">指定した条件で監査ログを検索するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="45e3b-157">**Search-AdminAuditLog** コマンドレットを実行すると、既定で最大 1,000 個のログ エントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="45e3b-158">_ResultSize パラメーターを使用_して、最大 250,000 のログ エントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="45e3b-159">または、この値を使用 `Unlimited` してすべてのエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="45e3b-160">この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="45e3b-161">**開始日**: 2018 年 8 月 4 日</span><span class="sxs-lookup"><span data-stu-id="45e3b-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="45e3b-162">**終了日**: 2018 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="45e3b-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="45e3b-163">**ユーザー ID**: davids、chrisd、kima</span><span class="sxs-lookup"><span data-stu-id="45e3b-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="45e3b-164">**コマンドレット**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="45e3b-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="45e3b-165">**パラメーター**: ProhibitSendQuota、ProhibitSendReceiveQuota、IssueWarningQuota、MaxSendSize _、MaxReceiveSize_ _ProhibitSendQuota_ _ProhibitSendReceiveQuota_ _IssueWarningQuota_ _MaxSendSize_</span><span class="sxs-lookup"><span data-stu-id="45e3b-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="45e3b-p114">この例では、特定のメールボックスの変更を検索します。これは、トラブルシューティングを実行している場合や、調査のために情報を入手する必要がある場合に便利です。次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="45e3b-169">**開始日**: 2018 年 5 月 1 日</span><span class="sxs-lookup"><span data-stu-id="45e3b-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="45e3b-170">**終了日**: 2018 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="45e3b-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="45e3b-171">**オブジェクト ID**: contoso.com/Users/DavidS</span><span class="sxs-lookup"><span data-stu-id="45e3b-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="45e3b-172">検索の結果返されるログ エントリが多い場合は **、Exchange Online PowerShell を使用して監査** ログ エントリを検索し、その結果を受信者に送信する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45e3b-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="45e3b-173">その手順を実行すると、指定した受信者に XML ファイルが電子メールの添付ファイルとして送信されるため、目的のデータをより簡単に抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="45e3b-174">構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45e3b-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="45e3b-175">監査ログ エントリの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="45e3b-175">View details of audit log entries</span></span>

<span data-ttu-id="45e3b-176">**Search-AdminAuditLog コマンドレットは**、監査ログの内容に記述されている[フィールドを返します](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)。</span><span class="sxs-lookup"><span data-stu-id="45e3b-176">The **Search-AdminAuditLog** cmdlet returns the fields described in [Audit log contents](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents).</span></span> <span data-ttu-id="45e3b-177">コマンドレットによって返されるフィールドのうち、 **CmdletParameters** と **ModifiedProperties** の 2 つのフィールドには、既定では表示できない追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-177">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="45e3b-178">**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="45e3b-179">または **、Exchange Online PowerShell を使用して監査** ログ エントリを検索し、結果を受信者に送信できます。この操作を行うには、このトピックの後半で説明した XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="45e3b-180">この手順では、次の概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="45e3b-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="45e3b-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="45e3b-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="45e3b-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="45e3b-183">検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="45e3b-184">各監査ログ エントリは、変数に配列要素として格納されます `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="45e3b-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="45e3b-185">配列要素のインデックスを指定することで、配列要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45e3b-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="45e3b-186">配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。</span><span class="sxs-lookup"><span data-stu-id="45e3b-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="45e3b-187">たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="45e3b-p119">上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="45e3b-190">**CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="45e3b-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>
