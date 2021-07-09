---
title: PowerShell スクリプトを使用して監査ログを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: PowerShell スクリプトを使用して、Exchange Online で Search-UnifiedAuditLog コマンドレットを実行し、監査ログを検索します。 このスクリプトは、大規模なセット (最大 50,000 件) の監査レコードを返すように最適化されています。 これらのレコードはスクリプトによって CSV ファイルにエクスポートされ、ユーザーは Excel の Power Query を使用して表示および変換することができます。
ms.openlocfilehash: 8abea51bb1e7e1fa7bd513bea78708b06da62def
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341010"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="9673a-105">PowerShell スクリプトを使用して監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="9673a-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="9673a-106">今日の世界では、セキュリティ、コンプライアンス、および監査は、IT 管理者にとって最優先事項になっています。</span><span class="sxs-lookup"><span data-stu-id="9673a-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="9673a-107">Microsoft 365 には、組織がセキュリティ、コンプライアンス、および監査を管理するのに役立ついくつかの組み込みの機能があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="9673a-108">特に、統合監査ログは、セキュリティ インシデントとコンプライアンスの問題を調査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9673a-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="9673a-109">次の方法を使用して、監査ログを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9673a-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="9673a-110">Office 365 マネージメント アクティビティ API</span><span class="sxs-lookup"><span data-stu-id="9673a-110">The Office 365 Management Activity API</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="9673a-111">Microsoft 365 コンプライアンス センターの[監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="9673a-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="9673a-112">Exchange Online PowerShell の [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="9673a-112">The [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="9673a-113">監査ログを定期的に取得する必要がある場合は、Office 365 マネージメント アクティビティ API を使用するソリューションを検討する必要があります。これは、その API が大規模な組織に対して、継続的に数百万の監査レコードを取得するためのスケーラビリティとパフォーマンスを提供できるためです。</span><span class="sxs-lookup"><span data-stu-id="9673a-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="9673a-114">Microsoft 365 コンプライアンス センターの監査ログ検索ツールを使用すると、より短い時間範囲で発生する特定の操作の監査レコードをすばやく見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="9673a-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="9673a-115">特に大規模な組織の場合、監査ログ検索ツールでより長い時間範囲を使用すると、返されるレコードが多すぎて簡単に管理またはエクスポートできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="9673a-116">特定の調査またはインシデントの監査データを手動で取得する必要がある場合、特に大規模な組織で日付範囲が長い場合は、**Search-UnifiedAuditLog** コマンドレットを使用するのが最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="9673a-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="9673a-117">この記事には、そのコマンドレットを使用して最大 50,000 件の監査レコードを取得し、それらを CSV ファイルにエクスポートする PowerShell スクリプトが含まれています。その CSV ファイルを Excel の Power Query を使用して書式設定し、レビューに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="9673a-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="9673a-118">この記事のスクリプトを使用すると、大規模な監査ログ検索がそのサービスでタイムアウトになる可能性を最小限に抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="9673a-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="9673a-119">スクリプトを実行する前に</span><span class="sxs-lookup"><span data-stu-id="9673a-119">Before you run the script</span></span>

- <span data-ttu-id="9673a-120">スクリプトを正常に使用して監査レコードを返すようにするには、組織で監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="9673a-121">Microsoft 365 および Office 365 Enterprise 組織では、監査ログは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9673a-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="9673a-122">組織で監査ログ検索が有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9673a-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  <span data-ttu-id="9673a-123">**UnifiedAuditLogIngestionEnabled** プロパティの値 `True`は、監査ログ検索が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9673a-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="9673a-124">スクリプトを正常に実行するには、Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="9673a-125">既定では、これらの役割は Exchange 管理センターの [アクセス許可] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9673a-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="9673a-126">詳細については、「[コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)」の「監査ログを検索するための要件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span>

- <span data-ttu-id="9673a-127">スクリプトが完了するまでに長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="9673a-128">実行にかかる時間は、スクリプトで監査レコードを取得するために構成する日付範囲と間隔のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9673a-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="9673a-129">日付範囲を大きくして間隔を短くすると、実行時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="9673a-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="9673a-130">日付範囲と間隔の詳細については、手順 2 の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="9673a-p108">この記事で提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="9673a-p108">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="9673a-136">手順 1: Exchange Online PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="9673a-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="9673a-137">最初の手順は、Exchange Online PowerShell へ接続することです。</span><span class="sxs-lookup"><span data-stu-id="9673a-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9673a-138">最新の認証、多要素認証 (MFA) を使用して接続できます。</span><span class="sxs-lookup"><span data-stu-id="9673a-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="9673a-139">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="9673a-140">手順 2: スクリプトを変更して実行し、監査レコードを取得する</span><span class="sxs-lookup"><span data-stu-id="9673a-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="9673a-141">Exchange Online PowerShell に接続した後、次の手順は、スクリプトを作成、変更、および実行して、監査データを取得することです。</span><span class="sxs-lookup"><span data-stu-id="9673a-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="9673a-142">監査ログ検索スクリプトの最初の 7 行には、検索を構成するために変更できる次の変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9673a-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="9673a-143">これらの変数の説明については、手順 2 の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="9673a-p111">ファイル拡張子 ps1 の Windows PowerShell スクリプトに以下のテキストを保存します。たとえば、SearchAuditLog.ps1 などという名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="9673a-p111">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1. For example, SearchAuditLog.ps1.</span></span>

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. <span data-ttu-id="9673a-146">次の表にリストされている変数を変更して、検索条件を構成します。</span><span class="sxs-lookup"><span data-stu-id="9673a-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="9673a-147">スクリプトにはこれらの変数のサンプル値が含まれていますが、ユーザーの特定の要件を満たすために (特に明記されていない限り) 変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   <br>

   ****

   |<span data-ttu-id="9673a-148">変数</span><span class="sxs-lookup"><span data-stu-id="9673a-148">Variable</span></span>|<span data-ttu-id="9673a-149">サンプル値</span><span class="sxs-lookup"><span data-stu-id="9673a-149">Sample value</span></span>|<span data-ttu-id="9673a-150">説明</span><span class="sxs-lookup"><span data-stu-id="9673a-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="9673a-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="9673a-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="9673a-p113">スクリプトによって実行された監査ログ検索の進行状況に関する情報を含むログ ファイルの名前と場所を指定します。スクリプトは UTC タイムスタンプをログ ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9673a-p113">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script. The script writes UTC timestamps to the log file.</span></span>|
   |`$outputFile`|<span data-ttu-id="9673a-154">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="9673a-154">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="9673a-155">スクリプトによって返される監査レコードを含む CSV ファイルの名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9673a-155">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="9673a-156">`[DateTime]$start` と `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="9673a-156">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="9673a-159">監査ログ検索の日付範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="9673a-159">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="9673a-160">スクリプトは、指定された日付範囲内に発生した監査アクティビティのレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="9673a-160">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="9673a-161">たとえば、2021 年 1 月に実行されたアクティビティを返すには、開始日を `"2021-01-01"`、終了日を `"2021-01-31"` と指定します (値は必ず二重引用符で囲んでください)。スクリプトのサンプル値は、24 時間前に実行されたアクティビティのレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="9673a-161">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="9673a-162">値にタイムスタンプを含めない場合、既定のタイムスタンプは指定された日付の午前 0 時 (深夜) です。</span><span class="sxs-lookup"><span data-stu-id="9673a-162">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="9673a-163">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="9673a-163">"AzureActiveDirectory"</span></span>|<span data-ttu-id="9673a-164">検索する監査アクティビティ (*操作* とも呼ばれます) のレコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9673a-164">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="9673a-165">このプロパティは、アクティビティがトリガーされたサービスまたは機能を示します。</span><span class="sxs-lookup"><span data-stu-id="9673a-165">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="9673a-166">この変数に使用できるレコードの種類の一覧については、「[監査ログ レコードの種類](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-166">For a list of record types that you can use for this variable, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="9673a-167">レコードの種類の名前または ENUM 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9673a-167">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="9673a-168">**ヒント:** すべてのレコードの種類の監査レコードを返すには、値 `$null` (二重引用符なし) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9673a-168">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="9673a-169">5000</span><span class="sxs-lookup"><span data-stu-id="9673a-169">5000</span></span>|<span data-ttu-id="9673a-170">**Search-UnifiedAuditLog** コマンドレットがスクリプトによって呼び出されるたびに返される結果の数を指定します (*結果セット* と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="9673a-170">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="9673a-171">5,000 の値は、コマンドレットでサポートされている最大値です。</span><span class="sxs-lookup"><span data-stu-id="9673a-171">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="9673a-172">この値はそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="9673a-172">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="9673a-173">60</span><span class="sxs-lookup"><span data-stu-id="9673a-173">60</span></span>|<span data-ttu-id="9673a-174">返されるレコード数 5000 の制限を克服するために、この変数は指定されたデータ範囲を取得し、それをより小さな時間間隔に切り分けます。</span><span class="sxs-lookup"><span data-stu-id="9673a-174">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="9673a-175">これで、日付範囲全体ではなく各間隔が、コマンドの 5000 レコード出力制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="9673a-175">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="9673a-176">ほとんどの組織では、日付範囲内の 60 分間隔あたり 5000 レコードの既定値で十分です。</span><span class="sxs-lookup"><span data-stu-id="9673a-176">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="9673a-177">ただし、スクリプトが `maximum results limitation reached` (最大結果制限に達しました) というエラーを返した場合は、時間間隔を短くして (たとえば、30 分または 15 分にして) スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="9673a-177">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="9673a-178">前の表にリストされている変数のほとんどは、**Search-UnifiedAuditLog** コマンドレットのパラメーターに対応しています。</span><span class="sxs-lookup"><span data-stu-id="9673a-178">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="9673a-179">これらのパラメーターの詳細については、「[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-179">For more information about these parameters, see [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="9673a-180">ローカル コンピューターで Windows PowerShell を開き、変更したスクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9673a-180">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="9673a-181">Exchange Online PowerShell でコマンドレットを実行します。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9673a-181">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="9673a-182">スクリプトの実行中は、進行状況メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9673a-182">The script displays progress messages while it's running.</span></span> <span data-ttu-id="9673a-183">スクリプトの実行が終了すると、監査レコードを含むログ ファイルと CSV ファイルが作成され、`$logFile` 変数と `$outputFile` 変数で定義されたフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9673a-183">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9673a-184">このスクリプトを実行するたびに返される監査レコードの最大数には、50,000 の制限があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-184">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="9673a-185">このスクリプトを実行して 50,000 件の結果が返される場合は、日付範囲内に発生したアクティビティの監査レコードが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9673a-185">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="9673a-186">その場合は、日付範囲をより短い期間に分割してから、日付範囲ごとにスクリプトを再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9673a-186">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="9673a-187">たとえば、90 日間の日付範囲で 50,000 件の結果が返される場合、スクリプトを 2 回再実行できます。1 回目は日付範囲の最初の 45 日間、2 回目は残りの 45 日間です。</span><span class="sxs-lookup"><span data-stu-id="9673a-187">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="9673a-188">手順 3: 監査レコードを書式設定して表示する</span><span class="sxs-lookup"><span data-stu-id="9673a-188">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="9673a-189">スクリプトを実行して監査レコードを CSV ファイルにエクスポートした後、監査レコードの確認と分析を容易にするために CSV ファイルを書式設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9673a-189">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="9673a-190">1 つの方法として、Excel の Power Query に含まれる JSON 変換機能を使用して、**[AuditData]** 列の JSON オブジェクトの各プロパティを、独自の列に分割することができます。</span><span class="sxs-lookup"><span data-stu-id="9673a-190">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="9673a-191">詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9673a-191">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
