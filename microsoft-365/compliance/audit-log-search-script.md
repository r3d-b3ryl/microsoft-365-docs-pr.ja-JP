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
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164183"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>PowerShell スクリプトを使用して監査ログを検索する

今日の世界では、セキュリティ、コンプライアンス、および監査は、IT 管理者にとって最優先事項になっています。 Microsoft 365 には、組織がセキュリティ、コンプライアンス、および監査を管理するのに役立ついくつかの組み込みの機能があります。 特に、統合監査ログは、セキュリティ インシデントとコンプライアンスの問題を調査するのに役立ちます。 次の方法を使用して、監査ログを取得できます。

- [Office 365 マネージメント アクティビティ API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Microsoft 365 コンプライアンス センターの[監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)

- Exchange Online PowerShell の [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) コマンドレット

監査ログを定期的に取得する必要がある場合は、Office 365 マネージメント アクティビティ API を使用するソリューションを検討する必要があります。これは、その API が大規模な組織に対して、継続的に数百万の監査レコードを取得するためのスケーラビリティとパフォーマンスを提供できるためです。 Microsoft 365 コンプライアンス センターの監査ログ検索ツールを使用すると、より短い時間範囲で発生する特定の操作の監査レコードをすばやく見つけることができます。 特に大規模な組織の場合、監査ログ検索ツールでより長い時間範囲を使用すると、返されるレコードが多すぎて簡単に管理またはエクスポートできない場合があります。

特定の調査またはインシデントの監査データを手動で取得する必要がある場合、特に大規模な組織で日付範囲が長い場合は、**Search-UnifiedAuditLog** コマンドレットを使用するのが最適なオプションです。 この記事には、そのコマンドレットを使用して最大 50,000 件の監査レコードを取得し、それらを CSV ファイルにエクスポートする PowerShell スクリプトが含まれています。その CSV ファイルを Excel の Power Query を使用して書式設定し、レビューに役立てることができます。 この記事のスクリプトを使用すると、大規模な監査ログ検索がそのサービスでタイムアウトになる可能性を最小限に抑えることもできます。

## <a name="before-you-run-the-script"></a>スクリプトを実行する前に

- スクリプトを正常に使用して監査レコードを返すようにするには、組織で監査ログを有効にする必要があります。 Microsoft 365 および Office 365 Enterprise 組織では、監査ログは既定でオンになっています。 組織で監査ログ検索が有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  **UnifiedAuditLogIngestionEnabled** プロパティの値 `True`は、監査ログ検索が有効になっていることを示します。

- スクリプトを正常に実行するには、Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。 既定では、これらの役割は Exchange 管理センターの [アクセス許可] ページでコンプライアンス管理役割グループまたは組織管理役割グループに割り当てられています。 詳細については、「[コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)」の「監査ログを検索するための要件」セクションを参照してください。

- スクリプトが完了するまでに長い時間がかかる場合があります。 実行にかかる時間は、スクリプトで監査レコードを取得するために構成する日付範囲と間隔のサイズによって異なります。 日付範囲を大きくして間隔を短くすると、実行時間が長くなります。 日付範囲と間隔の詳細については、手順 2 の表を参照してください。

- この記事で提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-connect-to-exchange-online-powershell"></a>手順 1: Exchange Online PowerShell に接続する

最初の手順は、Exchange Online PowerShell へ接続することです。 最新の認証、多要素認証 (MFA) を使用して接続できます。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>手順 2: スクリプトを変更して実行し、監査レコードを取得する

Exchange Online PowerShell に接続した後、次の手順は、スクリプトを作成、変更、および実行して、監査データを取得することです。 監査ログ検索スクリプトの最初の 7 行には、検索を構成するために変更できる次の変数が含まれています。 これらの変数の説明については、手順 2 の表を参照してください。

1. ファイル拡張子 ps1 の Windows PowerShell スクリプトに以下のテキストを保存します。たとえば、SearchAuditLog.ps1 などという名前のファイルに保存します。

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

2. 次の表にリストされている変数を変更して、検索条件を構成します。 スクリプトにはこれらの変数のサンプル値が含まれていますが、ユーザーの特定の要件を満たすために (特に明記されていない限り) 変更する必要があります。

   <br>

   ****

   |変数|サンプル値|説明|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|スクリプトによって実行された監査ログ検索の進行状況に関する情報を含むログ ファイルの名前と場所を指定します。スクリプトは UTC タイムスタンプをログ ファイルに書き込みます。|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|スクリプトによって返される監査レコードを含む CSV ファイルの名前と場所を指定します。|
   |`[DateTime]$start` と `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|監査ログ検索の日付範囲を指定します。 スクリプトは、指定された日付範囲内に発生した監査アクティビティのレコードを返します。 たとえば、2021 年 1 月に実行されたアクティビティを返すには、開始日を `"2021-01-01"`、終了日を `"2021-01-31"` と指定します (値は必ず二重引用符で囲んでください)。スクリプトのサンプル値は、24 時間前に実行されたアクティビティのレコードを返します。 値にタイムスタンプを含めない場合、既定のタイムスタンプは指定された日付の午前 0 時 (深夜) です。|
   |`$record`|"AzureActiveDirectory"|検索する監査アクティビティ (*操作* とも呼ばれます) のレコードの種類を指定します。 このプロパティは、アクティビティがトリガーされたサービスまたは機能を示します。 この変数に使用できるレコードの種類の一覧については、「[監査ログ レコードの種類](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)」を参照してください。 レコードの種類の名前または ENUM 値を使用できます。 <br/><br/>**ヒント:** すべてのレコードの種類の監査レコードを返すには、値 `$null` (二重引用符なし) を使用します。|
   |`$resultSize`|5000|**Search-UnifiedAuditLog** コマンドレットがスクリプトによって呼び出されるたびに返される結果の数を指定します (*結果セット* と呼ばれます)。 5,000 の値は、コマンドレットでサポートされている最大値です。 この値はそのままにしておきます。|
   |`$intervalMinutes`|60|返されるレコード数 5000 の制限を克服するために、この変数は指定されたデータ範囲を取得し、それをより小さな時間間隔に切り分けます。 これで、日付範囲全体ではなく各間隔が、コマンドの 5000 レコード出力制限の対象になります。 ほとんどの組織では、日付範囲内の 60 分間隔あたり 5000 レコードの既定値で十分です。 ただし、スクリプトが `maximum results limitation reached` (最大結果制限に達しました) というエラーを返した場合は、時間間隔を短くして (たとえば、30 分または 15 分にして) スクリプトを再実行します。|
   ||||

   前の表にリストされている変数のほとんどは、**Search-UnifiedAuditLog** コマンドレットのパラメーターに対応しています。 これらのパラメーターの詳細については、「[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)」を参照してください。

3. ローカル コンピューターで Windows PowerShell を開き、変更したスクリプトを保存したフォルダーに移動します。

4. Exchange Online PowerShell でコマンドレットを実行します。以下に例を示します。

   ```powershell
   .\SearchAuditLog.ps1
   ```

スクリプトの実行中は、進行状況メッセージが表示されます。 スクリプトの実行が終了すると、監査レコードを含むログ ファイルと CSV ファイルが作成され、`$logFile` 変数と `$outputFile` 変数で定義されたフォルダーに保存されます。

> [!IMPORTANT]
> このスクリプトを実行するたびに返される監査レコードの最大数には、50,000 の制限があります。 このスクリプトを実行して 50,000 件の結果が返される場合は、日付範囲内に発生したアクティビティの監査レコードが含まれていない可能性があります。 その場合は、日付範囲をより短い期間に分割してから、日付範囲ごとにスクリプトを再実行することをお勧めします。 たとえば、90 日間の日付範囲で 50,000 件の結果が返される場合、スクリプトを 2 回再実行できます。1 回目は日付範囲の最初の 45 日間、2 回目は残りの 45 日間です。

## <a name="step-3-format-and-view-the-audit-records"></a>手順 3: 監査レコードを書式設定して表示する

スクリプトを実行して監査レコードを CSV ファイルにエクスポートした後、監査レコードの確認と分析を容易にするために CSV ファイルを書式設定することをお勧めします。 1 つの方法として、Excel の Power Query に含まれる JSON 変換機能を使用して、**[AuditData]** 列の JSON オブジェクトの各プロパティを、独自の列に分割することができます。 詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する」を参照してください。
