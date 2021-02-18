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
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286479"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="3ea8f-103">スタンドアロン EOP で管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="3ea8f-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="3ea8f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3ea8f-104">**Applies to**</span></span>
- [<span data-ttu-id="3ea8f-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="3ea8f-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3ea8f-106">Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロンの EOP PowerShell を使用して、管理者監査ログのエントリを検索して表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="3ea8f-107">管理者監査ログには、管理者と管理者特権が割り当てられているユーザーによって実行される、スタンドアロンの EOP PowerShell コマンドレットに基づく特定の操作が記録されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="3ea8f-108">管理者監査ログのエントリには、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、影響を受けたオブジェクトに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="3ea8f-109">管理者監査ログは既定で有効になっていますが、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="3ea8f-110">管理者監査ログには、Get、Search、または Test という動詞で始まるコマンドレットに基づく操作は記録 **されます**。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="3ea8f-111">監査ログのエントリは 90 日間維持されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="3ea8f-112">90 日を超える古いエントリは削除されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ea8f-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3ea8f-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ea8f-114">Exchange 管理センターを開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3ea8f-115">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3ea8f-116">この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="3ea8f-117">具体的には、既定で組織の管理、コンプライアンス管理、およびセキュリティ管理者の役割グループに割り当てられる監査ログまたは表示専用の監査ログの役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="3ea8f-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="3ea8f-118">詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="3ea8f-119">この記事の手順に適用されるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3ea8f-120">問題が発生する場合</span><span class="sxs-lookup"><span data-stu-id="3ea8f-120">Having problems?</span></span> <span data-ttu-id="3ea8f-121">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="3ea8f-122">EAC を使用して管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="3ea8f-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="3ea8f-123">EAC で、**コンプライアンス管理の** 監査に移動し、[管理者監査ログ レポートの実行] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="3ea8f-124">In the **Search for changes to administrator role groups** page that opens, choose a Start **date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span><span class="sxs-lookup"><span data-stu-id="3ea8f-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="3ea8f-125">指定した期間中に行われたすべての構成変更が表示され、次の情報を使用して並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="3ea8f-126">**日付**: 構成の変更が行われた日時。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="3ea8f-127">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="3ea8f-128">**コマンドレット**: 構成の変更に使用されたコマンドレットの名前。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="3ea8f-129">**ユーザー**: 構成を変更したユーザーのユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="3ea8f-p107">最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="3ea8f-133">**変更された** オブジェクト : コマンドレットによって変更されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="3ea8f-134">**Parameters (Parameter:Value)**: 使用されたコマンドレット パラメーターと、パラメーターで指定された任意の値。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="3ea8f-135">特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="3ea8f-136">スタンドアロンの EOP PowerShell を使用して管理者監査ログを表示する</span><span class="sxs-lookup"><span data-stu-id="3ea8f-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="3ea8f-137">スタンドアロンの EOP PowerShell を使用して、指定した条件を満たす監査ログ エントリを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="3ea8f-138">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="3ea8f-139">**注**:</span><span class="sxs-lookup"><span data-stu-id="3ea8f-139">**Notes**:</span></span>

- <span data-ttu-id="3ea8f-140">Parameters パラメーターは _、Cmdlets_ パラメーターと共 _にのみ使用_ できます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="3ea8f-141">_ObjectIds パラメーター_ は、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="3ea8f-142">有効な値は、監査ログでのオブジェクトの表示方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="3ea8f-143">例:</span><span class="sxs-lookup"><span data-stu-id="3ea8f-143">For example:</span></span>

  - <span data-ttu-id="3ea8f-144">Name</span><span class="sxs-lookup"><span data-stu-id="3ea8f-144">Name</span></span>
  - <span data-ttu-id="3ea8f-145">正規の識別名 (たとえば、al-Zuhairi contoso.com/Users/Akia)</span><span class="sxs-lookup"><span data-stu-id="3ea8f-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="3ea8f-146">結果を絞り込み、対象のオブジェクトの種類を特定するには、このコマンドレットで他のフィルター処理パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="3ea8f-147">_UserIds パラメーター_ は、変更を行ったユーザー (コマンドレットを実行したユーザー) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="3ea8f-148">_StartDate パラメーターと_ _EndDate_ パラメーターで、タイム ゾーンを指定せずに日付/時刻の値を指定した場合、値は協定世界時 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3ea8f-149">このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="3ea8f-150">UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z</span><span class="sxs-lookup"><span data-stu-id="3ea8f-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="3ea8f-151">日付/時刻の値を、現地のタイム ゾーンの日付/時刻を UTC に変換する数式として指定します。たとえば、次のようになります `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="3ea8f-152">詳細については、「[Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="3ea8f-153">このコマンドレットは、既定で最大 1,000 のログ エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="3ea8f-154">_ResultSize パラメーターを使用_ して、最大 250,000 のログ エントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="3ea8f-155">または、値を使用して `Unlimited` すべてのエントリを返します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="3ea8f-156">この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="3ea8f-157">**開始日 :** 2019 年 8 月 4 日</span><span class="sxs-lookup"><span data-stu-id="3ea8f-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="3ea8f-158">**終了日 :** 2019 年 10 月 3 日</span><span class="sxs-lookup"><span data-stu-id="3ea8f-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="3ea8f-159">**コマンドレット**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="3ea8f-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="3ea8f-160">構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="3ea8f-161">監査ログ エントリの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3ea8f-161">View details of audit log entries</span></span>

<span data-ttu-id="3ea8f-162">**Search-AdminAuditLog** コマンドレットは、この記事で後述する「監査ログの内容」セクション [で説明されている](#audit-log-contents)フィールドを返します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="3ea8f-163">コマンドレットによって返されるフィールドの中で **、CmdletParameters** と **ModifiedProperties** という 2 つのフィールドには、既定では返されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="3ea8f-164">**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="3ea8f-165">検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="3ea8f-166">各監査ログ エントリは、変数に配列要素として格納されます `$Results` 。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="3ea8f-167">配列要素のインデックスを指定することで、配列要素を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="3ea8f-168">配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="3ea8f-169">たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="3ea8f-p115">上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="3ea8f-172">**CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="3ea8f-173">監査ログの内容</span><span class="sxs-lookup"><span data-stu-id="3ea8f-173">Audit log contents</span></span>

<span data-ttu-id="3ea8f-174">それぞれの監査ログ エントリには、次の表に記載されている情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="3ea8f-175">監査ログには、1 つまたは複数の監査ログ エントリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="3ea8f-176">フィールド</span><span class="sxs-lookup"><span data-stu-id="3ea8f-176">Field</span></span>|<span data-ttu-id="3ea8f-177">説明</span><span class="sxs-lookup"><span data-stu-id="3ea8f-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="3ea8f-178">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="3ea8f-179">このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含 `CmdletName` されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="3ea8f-180">このフィールドには、ユーザーがフィールド内で実行したコマンドレットの名前が含 `Caller` まれる。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="3ea8f-181">このフィールドには、フィールド内のコマンドレットが実行された際に指定された `CmdletName` パラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3ea8f-182">パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="3ea8f-183">このフィールドには、フィールド内のオブジェクトで変更されたプロパティが含 `ObjectModified` まれる。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="3ea8f-184">プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="3ea8f-185">このフィールドには、フィールドでコマンドレットを実行したユーザーのユーザー アカウントが含 `CmdletName` されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="3ea8f-186">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="3ea8f-187">このフィールドは、フィールド内のコマンドレットが正常に実行 `CmdletName` されたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="3ea8f-188">値は、次 `True` のいずれかまたはです `False` 。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="3ea8f-189">このフィールドには、フィールド内のコマンドレットが正常に完了できなかった場合に生成 `CmdletName` されるエラー メッセージが含まれる。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="3ea8f-190">このフィールドには、フィールド内のコマンドレットが実行された日時 `CmdletName` が含されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="3ea8f-191">日時は、世界協定時刻 (UTC) 形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="3ea8f-192">このフィールドは、フィールドで指定されたコマンドレットが実行されたサーバー `CmdletName` を示します。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="3ea8f-193">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="3ea8f-194">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="3ea8f-195">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="3ea8f-196">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="3ea8f-197">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="3ea8f-198">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="3ea8f-199">このフィールドは、EOP によって内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea8f-199">This field is used internally by EOP.</span></span>|
|
