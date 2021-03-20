---
title: スタンドアロン EOP で管理者監査ログを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者監査ログを表示および検索する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908128"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="57861-103">スタンドアロン EOP で管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="57861-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="57861-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="57861-104">**Applies to**</span></span>
- [<span data-ttu-id="57861-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="57861-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="57861-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell を使用して、管理監査ログ内のエントリを検索および表示できます。</span><span class="sxs-lookup"><span data-stu-id="57861-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="57861-107">管理者監査ログには、管理者および管理者特権が割り当てられているユーザーによって実行されるスタンドアロン EOP PowerShell コマンドレットに基づいて、特定のアクションが記録されます。</span><span class="sxs-lookup"><span data-stu-id="57861-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="57861-108">管理者監査ログのエントリには、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="57861-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="57861-109">管理者監査ログは既定で有効になっているので、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="57861-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="57861-110">管理者監査ログは、動詞 Get、Search、または Test で始まるコマンドレットに基づいてアクションを記録 **します**。</span><span class="sxs-lookup"><span data-stu-id="57861-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="57861-111">監査ログのエントリは 90 日間維持されます。</span><span class="sxs-lookup"><span data-stu-id="57861-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="57861-112">エントリが 90 日を超える場合、そのエントリは削除されます。</span><span class="sxs-lookup"><span data-stu-id="57861-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="57861-113">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="57861-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="57861-114">Exchange 管理センターを開く方法については、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="57861-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="57861-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57861-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="57861-116">この記事の手順を実行するには、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="57861-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="57861-117">具体的には、既定で組織の管理、コンプライアンス管理、およびセキュリティ管理者の役割グループに割り当てられている監査ログまたはビュー専用監査ログの役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="57861-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="57861-118">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57861-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="57861-119">この記事の手順に適用されるキーボード ショートカットの詳細については、「Exchange Online の Exchange 管理センターのキーボード ショートカット」 [を参照してください](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="57861-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="57861-120">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="57861-120">Having problems?</span></span> <span data-ttu-id="57861-121">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="57861-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="57861-122">EAC を使用して管理監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="57861-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="57861-123">EAC で、[コンプライアンス管理の監査] に移動し、[管理者監査ログ レポートの実行 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="57861-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="57861-124">開いた **[管理者役割グループ** への変更の検索] ページで、[開始日] と **[終了日**] (既定の範囲は過去 2 週間) を選択し、[検索] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="57861-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="57861-125">指定した期間中に行われた構成変更はすべて表示され、次の情報を使用して並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="57861-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="57861-126">**日付**: 構成の変更が行われた日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="57861-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="57861-127">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="57861-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="57861-128">**コマンドレット**: 構成を変更するために使用されたコマンドレットの名前。</span><span class="sxs-lookup"><span data-stu-id="57861-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="57861-129">**User**: 構成を変更したユーザーのユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="57861-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="57861-p107">最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57861-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="57861-133">**変更されたオブジェクト**: コマンドレットによって変更されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="57861-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="57861-134">**パラメーター (Parameter:Value)**: 使用されたコマンドレット パラメーターと、パラメーターで指定された任意の値。</span><span class="sxs-lookup"><span data-stu-id="57861-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="57861-135">特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="57861-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="57861-136">スタンドアロンの EOP PowerShell を使用して管理監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="57861-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="57861-137">スタンドアロン EOP PowerShell を使用して、指定した条件を満たす監査ログ エントリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="57861-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="57861-138">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="57861-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="57861-139">**注**:</span><span class="sxs-lookup"><span data-stu-id="57861-139">**Notes**:</span></span>

- <span data-ttu-id="57861-140">Parameters パラメーターは _、Cmdlets_ パラメーターと共 _にのみ使用_ できます。</span><span class="sxs-lookup"><span data-stu-id="57861-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="57861-141">_ObjectIds パラメーターは_、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="57861-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="57861-142">有効な値は、オブジェクトが監査ログでどのように表されるのかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="57861-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="57861-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57861-143">For example:</span></span>

  - <span data-ttu-id="57861-144">名前</span><span class="sxs-lookup"><span data-stu-id="57861-144">Name</span></span>
  - <span data-ttu-id="57861-145">標準の識別名 (たとえば、al-Zuhairi contoso.com/Users/Akia)</span><span class="sxs-lookup"><span data-stu-id="57861-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="57861-146">このコマンドレットで他のフィルター パラメーターを使用して結果を絞り込み、対象のオブジェクトの種類を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57861-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="57861-147">_UserIds パラメーターは_、変更を行ったユーザー (コマンドレットを実行したユーザー) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="57861-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="57861-148">_StartDate パラメーターと_ _EndDate_ パラメーターの場合、タイム ゾーンのない日付/時刻の値を指定すると、値は協定世界時 (UTC) になります。</span><span class="sxs-lookup"><span data-stu-id="57861-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="57861-149">このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="57861-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="57861-150">UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z</span><span class="sxs-lookup"><span data-stu-id="57861-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="57861-151">日付/時刻の値を、ローカル タイム ゾーンの日付/時刻を UTC に変換する数式として指定します。たとえば、 を指定します `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="57861-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="57861-152">詳細については、「[Get-Date](/powershell/module/microsoft.powershell.utility/get-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57861-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="57861-153">コマンドレットは、既定で最大 1,000 のログ エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="57861-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="57861-154">_ResultSize パラメーターを使用_ して、最大 250,000 のログ エントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="57861-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="57861-155">または、値を使用して `Unlimited` すべてのエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="57861-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="57861-156">この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="57861-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="57861-157">**開始日 :** 2019 年 8 月 4 日</span><span class="sxs-lookup"><span data-stu-id="57861-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="57861-158">**終了日 :** 2019 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="57861-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="57861-159">**コマンドレット**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="57861-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="57861-160">構文およびパラメーターの詳細については、「[Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57861-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="57861-161">監査ログ エントリの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="57861-161">View details of audit log entries</span></span>

<span data-ttu-id="57861-162">**Search-AdminAuditLog コマンドレットは**、この記事の後半の [](#audit-log-contents)「監査ログの内容」セクションで説明されているフィールドを返します。</span><span class="sxs-lookup"><span data-stu-id="57861-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="57861-163">コマンドレットによって返されるフィールドの中で **、CmdletParameters** と **ModifiedProperties** という 2 つのフィールドには、既定では返されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="57861-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="57861-164">**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="57861-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="57861-165">検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="57861-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="57861-166">各監査ログ エントリは、変数に配列要素として格納されます `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="57861-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="57861-167">配列要素のインデックスを指定することで、配列要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="57861-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="57861-168">配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。</span><span class="sxs-lookup"><span data-stu-id="57861-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="57861-169">たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="57861-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="57861-p115">上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="57861-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="57861-172">**CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="57861-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="57861-173">監査ログの内容</span><span class="sxs-lookup"><span data-stu-id="57861-173">Audit log contents</span></span>

<span data-ttu-id="57861-174">それぞれの監査ログ エントリには、次の表に記載されている情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57861-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="57861-175">監査ログには、1 つまたは複数の監査ログ エントリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57861-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="57861-176">Field</span><span class="sxs-lookup"><span data-stu-id="57861-176">Field</span></span>|<span data-ttu-id="57861-177">説明</span><span class="sxs-lookup"><span data-stu-id="57861-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="57861-178">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="57861-179">このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含 `CmdletName` まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="57861-180">このフィールドには、フィールド内のユーザーが実行したコマンドレットの名前が含 `Caller` まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="57861-181">このフィールドには、フィールド内のコマンドレットの実行時に指定された `CmdletName` パラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="57861-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="57861-182">パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="57861-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="57861-183">このフィールドには、フィールド内のオブジェクトで変更されたプロパティが含 `ObjectModified` まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="57861-184">プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="57861-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="57861-185">このフィールドには、フィールドでコマンドレットを実行したユーザーのユーザー アカウントが含 `CmdletName` まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="57861-186">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="57861-187">このフィールドは、フィールド内のコマンドレットが正常に実行 `CmdletName` されたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="57861-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="57861-188">値は、 または `True` `False` です。</span><span class="sxs-lookup"><span data-stu-id="57861-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="57861-189">このフィールドには、フィールド内のコマンドレットが正常に完了しなかった場合に生成 `CmdletName` されるエラー メッセージが含まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="57861-190">このフィールドには、フィールド内のコマンドレットが実行された日時 `CmdletName` が含まれる。</span><span class="sxs-lookup"><span data-stu-id="57861-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="57861-191">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="57861-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="57861-192">このフィールドは、フィールドで指定されたコマンドレットが実行されたサーバー `CmdletName` を示します。</span><span class="sxs-lookup"><span data-stu-id="57861-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="57861-193">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="57861-194">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="57861-195">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="57861-196">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="57861-197">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="57861-198">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="57861-199">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57861-199">This field is used internally by EOP.</span></span>|
|