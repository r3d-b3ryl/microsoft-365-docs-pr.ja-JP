---
title: 管理者監査ログをスタンドアロン EOP で表示する
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
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、管理者監査ログをスタンドアロンの Exchange Online Protection (EOP) で表示および検索する方法を学習できます。
ms.openlocfilehash: 171f3ec531b232ca796232ab26caefbee8afc75c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653499"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="8a16c-103">管理者監査ログをスタンドアロン EOP で表示する</span><span class="sxs-lookup"><span data-stu-id="8a16c-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="8a16c-104">Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell を使用して、管理者監査ログのエントリを検索して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="8a16c-105">管理者監査ログには、管理者や管理者特権が割り当てられているユーザーが実行したスタンドアロンの EOP PowerShell コマンドレットに基づいて、特定の操作が記録されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="8a16c-106">管理者監査ログのエントリは、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8a16c-107">管理者監査ログは既定で有効になっており、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a16c-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="8a16c-108">管理者監査ログには、 **Get**、 **Search**、または**Test**という動詞で始まるコマンドレットに基づいてアクションが記録されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8a16c-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="8a16c-109">監査ログのエントリは 90 日間維持されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="8a16c-110">エントリが90日よりも古い場合は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8a16c-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="8a16c-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8a16c-112">Exchange 管理センターを開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="8a16c-113">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8a16c-114">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a16c-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8a16c-115">具体的には、ComplianceManagement、組織の管理 (グローバル管理者)、および SecurityAdministrator の役割グループに既定で割り当てられている監査ログまたは表示専用の監査ログの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="8a16c-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="8a16c-116">詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="8a16c-117">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="8a16c-118">問題がある場合は、</span><span class="sxs-lookup"><span data-stu-id="8a16c-118">Having problems?</span></span> <span data-ttu-id="8a16c-119">[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="8a16c-120">EAC を使用して管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="8a16c-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="8a16c-121">EAC で、[**コンプライアンス管理** \> ] [**監査**] に移動し、[**管理者監査ログレポートを実行**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="8a16c-122">[**管理者の役割グループへの変更の検索**] ページが開いたら、**開始日**と**終了日**(既定の範囲は過去2週間) を選択し、[**検索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="8a16c-123">指定した期間内に行われたすべての構成の変更が表示され、次の情報を使用して並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="8a16c-124">**日付**: 構成の変更が行われた日時。</span><span class="sxs-lookup"><span data-stu-id="8a16c-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="8a16c-125">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="8a16c-126">**コマンドレット**: 構成変更を行うために使用されたコマンドレットの名前。</span><span class="sxs-lookup"><span data-stu-id="8a16c-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="8a16c-127">**User**: 構成の変更を行ったユーザーのユーザーアカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="8a16c-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="8a16c-p107">最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="8a16c-131">**変更**されたオブジェクト: コマンドレットによって変更されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8a16c-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="8a16c-132">**パラメーター (パラメーター: 値)**: 使用されたコマンドレットパラメーターと、パラメーターで指定された値。</span><span class="sxs-lookup"><span data-stu-id="8a16c-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="8a16c-133">特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="8a16c-134">スタンドアロンの EOP PowerShell を使用して管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="8a16c-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="8a16c-135">スタンドアロンの EOP PowerShell を使用して、指定した条件に一致する監査ログエントリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="8a16c-136">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="8a16c-137">**注**:</span><span class="sxs-lookup"><span data-stu-id="8a16c-137">**Notes**:</span></span>

- <span data-ttu-id="8a16c-138">_Parameters_パラメーターは、_コマンドレット_パラメーターと共にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="8a16c-139">_Objectid_パラメーターは、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="8a16c-140">有効な値は、監査ログでのオブジェクトの表現方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8a16c-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="8a16c-141">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-141">For example:</span></span>

  - <span data-ttu-id="8a16c-142">Name</span><span class="sxs-lookup"><span data-stu-id="8a16c-142">Name</span></span>
  - <span data-ttu-id="8a16c-143">標準識別名 (たとえば、contoso.com/Users/Akia Al-Al-zuhairi)</span><span class="sxs-lookup"><span data-stu-id="8a16c-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="8a16c-144">結果を絞り込んで、対象のオブジェクトの種類を特定するには、このコマンドレットの他のフィルター処理パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a16c-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="8a16c-145">_UserIds_パラメーターは、変更を行ったユーザー (コマンドレットを実行したユーザー) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="8a16c-146">_StartDate_パラメーターと_EndDate_パラメーターに対して、タイムゾーンを指定せずに日付/時刻値を指定すると、値は協定世界時 (UTC) になります。</span><span class="sxs-lookup"><span data-stu-id="8a16c-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="8a16c-147">このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="8a16c-148">UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z</span><span class="sxs-lookup"><span data-stu-id="8a16c-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="8a16c-149">日付/時刻値を、ローカルタイムゾーンの日付/時刻を UTC に変換する数式として指定します (例:) `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="8a16c-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="8a16c-150">詳細については、「[Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="8a16c-151">コマンドレットは、既定で最大1000個のログエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="8a16c-152">_Resultsize_パラメーターを使用して、最大25万のログエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="8a16c-153">または、値を使用して `Unlimited` すべてのエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="8a16c-154">この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="8a16c-155">**開始日**: 2019 年8月4日</span><span class="sxs-lookup"><span data-stu-id="8a16c-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="8a16c-156">**終了日**: 2019 年10月3日</span><span class="sxs-lookup"><span data-stu-id="8a16c-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="8a16c-157">**コマンドレット**: add-rolegroupmember</span><span class="sxs-lookup"><span data-stu-id="8a16c-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="8a16c-158">構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a16c-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="8a16c-159">監査ログ エントリの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="8a16c-159">View details of audit log entries</span></span>

<span data-ttu-id="8a16c-160">**検索-Adminauditlog**コマンドレットは、このトピックで後述する「[監査ログの内容](#audit-log-contents)」セクションで説明されているフィールドを返します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="8a16c-161">コマンドレットによって返されるフィールドの2つのフィールド、 **ModifiedProperties** **parameters**およびには、既定では返されない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a16c-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="8a16c-162">**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="8a16c-163">検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="8a16c-164">各監査ログエントリは、変数に配列要素として格納され `$Results` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="8a16c-165">配列要素のインデックスを指定することで、配列要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="8a16c-166">配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。</span><span class="sxs-lookup"><span data-stu-id="8a16c-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="8a16c-167">たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="8a16c-p115">上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="8a16c-170">**CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="8a16c-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="8a16c-171">監査ログの内容</span><span class="sxs-lookup"><span data-stu-id="8a16c-171">Audit log contents</span></span>

<span data-ttu-id="8a16c-172">それぞれの監査ログ エントリには、次の表に記載されている情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="8a16c-173">監査ログには、1 つまたは複数の監査ログ エントリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a16c-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="8a16c-174">フィールド</span><span class="sxs-lookup"><span data-stu-id="8a16c-174">Field</span></span>|<span data-ttu-id="8a16c-175">説明</span><span class="sxs-lookup"><span data-stu-id="8a16c-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="8a16c-176">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="8a16c-177">このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含まれてい `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="8a16c-178">このフィールドには、フィールド内のユーザーによって実行されたコマンドレットの名前が含まれてい `Caller` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="8a16c-179">このフィールドには、フィールドのコマンドレットの実行時に指定されたパラメーターが含まれてい `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="8a16c-180">パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="8a16c-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="8a16c-181">このフィールドには、フィールドのオブジェクトで変更されたプロパティが含まれてい `ObjectModified` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="8a16c-182">プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="8a16c-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="8a16c-183">このフィールドには、フィールドでコマンドレットを実行したユーザーのユーザーアカウントが含まれてい `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="8a16c-184">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="8a16c-185">このフィールドでは、フィールドのコマンドレットが正常に実行されたかどうかを指定し `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="8a16c-186">値はまたはのいずれか `True` `False` です。</span><span class="sxs-lookup"><span data-stu-id="8a16c-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="8a16c-187">このフィールドには、フィールドのコマンドレットが正常に完了しなかった場合に生成されるエラーメッセージが含まれてい `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="8a16c-188">このフィールドには、フィールドのコマンドレットが実行された日付と時刻が含まれてい `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="8a16c-189">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="8a16c-190">このフィールドは、フィールドに指定されたコマンドレットが実行されたサーバーを示し `CmdletName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="8a16c-191">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="8a16c-192">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="8a16c-193">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="8a16c-194">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="8a16c-195">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="8a16c-196">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="8a16c-197">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a16c-197">This field is used internally by EOP.</span></span>|
|
