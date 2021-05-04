---
title: 一般的な電子情報開示の問題のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 電子情報開示の一般的な問題を解決するために実行できる基本的なトラブルシューティング手順Office 365説明します。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3d3d0830ac677ea812a0d09793de8214245d6b2a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060992"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="0b3dd-103">一般的な電子情報開示の問題を調査、トラブルシューティング、解決する</span><span class="sxs-lookup"><span data-stu-id="0b3dd-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="0b3dd-104">このトピックでは、電子情報開示検索中または電子情報開示プロセスの他の場所で発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="0b3dd-105">これらのシナリオの一部を解決するには、Microsoft サポートのヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="0b3dd-106">Microsoft サポートに問い合わせする場合の情報は、解決手順に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="0b3dd-107">エラー/問題: あいまいな場所</span><span class="sxs-lookup"><span data-stu-id="0b3dd-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="0b3dd-108">ユーザーのメールボックスの場所を検索に追加しようとして、Exchange Online Protection (EOP) ディレクトリに同じ userID を持つオブジェクトが重複または競合している場合は、次のエラーが表示されます。 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`</span><span class="sxs-lookup"><span data-stu-id="0b3dd-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-109">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-109">Resolution</span></span>

<span data-ttu-id="0b3dd-110">同じユーザー ID を持つ重複ユーザーまたは配布リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="0b3dd-111">Connect[コンプライアンス センター PowerShell &にアクセスします](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="0b3dd-112">次のコマンドを実行して、ユーザー名のすべてのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="0b3dd-113">'useralias@contoso.com' の出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="0b3dd-114">名前</span><span class="sxs-lookup"><span data-stu-id="0b3dd-114">Name</span></span>|<span data-ttu-id="0b3dd-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="0b3dd-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="0b3dd-116">エイリアス、ユーザー</span><span class="sxs-lookup"><span data-stu-id="0b3dd-116">Alias, User</span></span>|<span data-ttu-id="0b3dd-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="0b3dd-117">MailUser</span></span>|
   > |<span data-ttu-id="0b3dd-118">エイリアス、ユーザー</span><span class="sxs-lookup"><span data-stu-id="0b3dd-118">Alias, User</span></span>|<span data-ttu-id="0b3dd-119">User</span><span class="sxs-lookup"><span data-stu-id="0b3dd-119">User</span></span>|

3. <span data-ttu-id="0b3dd-120">複数のユーザーが返された場合は、競合するオブジェクトを見つけて修正します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="0b3dd-121">エラー/問題: 特定の場所で検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="0b3dd-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="0b3dd-122">電子情報開示またはコンテンツ検索では、次のエラーが発生する可能性があります。 `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="0b3dd-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![検索固有の場所でエラー のスクリーンショットが失敗する](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="0b3dd-124">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-124">Resolution</span></span>

<span data-ttu-id="0b3dd-125">このエラーが表示された場合は、検索で失敗した場所を確認してから、失敗した場所でのみ検索を再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="0b3dd-126">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="0b3dd-127">PowerShell 出力から、エラー フィールドまたは検索出力からのエラーの状態の詳細から、失敗した場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="0b3dd-128">失敗した場所でのみ電子情報開示検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="0b3dd-129">これらのエラーを引き続き受け取る場合は、「失敗した場所を再試行する」を参照 [して](/Office365/SecurityCompliance/retry-failed-content-search) 、トラブルシューティングの手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="0b3dd-130">エラー/問題: ファイルが見つかりません</span><span class="sxs-lookup"><span data-stu-id="0b3dd-130">Error/issue: File not found</span></span>

<span data-ttu-id="0b3dd-131">オンラインとビジネス向け 1 つのドライブの場所SharePoint含む電子情報開示検索を実行すると、ファイルがサイト上にありますが、エラー `File Not Found` が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="0b3dd-132">このエラーは、エクスポートの警告に表示され、errors.csvまたはスキップitems.csv。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="0b3dd-133">これは、サイトでファイルが見つからない場合、またはインデックスが最新の日付でなかった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="0b3dd-134">実際のエラーのテキストを次に示します (強調が追加されています)。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="0b3dd-135">28.06.2019 10:02:19_FailedToExportItem_Failedダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="0b3dd-136">その他の診断情報 : Microsoft。Office。Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Document 型のコンテンツ 6ea52149-91cd-4965-b5bb-82ca6a3ec9be からのダウンロードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="0b3dd-137">相関 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="0b3dd-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="0b3dd-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint。Client.ServerException:***ファイルが見つかりません***。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="0b3dd-139">at Microsoft.SharePoint。Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint。Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="0b3dd-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-140">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-140">Resolution</span></span>

1. <span data-ttu-id="0b3dd-141">検索で識別された場所を確認して、ファイルの場所が正しく、検索場所に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="0b3dd-142">サイト、ライブラリ、または[](/sharepoint/crawl-site-content)リストのクロールと再インデックスの手動要求の手順を使用して、サイトのインデックスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="0b3dd-143">エラー/問題: 受信者が見つからないため、検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="0b3dd-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="0b3dd-144">電子情報開示の検索が失敗し、エラーが発生しました `recipient not found` 。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="0b3dd-145">このエラーは、オブジェクトが同期されていないので、Exchange Online Protection (EOP) でユーザー オブジェクトが見つからない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-146">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-146">Resolution</span></span>

1. <span data-ttu-id="0b3dd-147">[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する</span><span class="sxs-lookup"><span data-stu-id="0b3dd-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0b3dd-148">次のコマンドを実行して、ユーザーが同期されている場所を確認Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="0b3dd-149">ユーザーの質問のメール ユーザー オブジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="0b3dd-150">何も返されなかった場合は、ユーザー オブジェクトを調査します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="0b3dd-151">オブジェクトを同期できない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="0b3dd-152">エラー/問題: 検索結果のエクスポートが遅い</span><span class="sxs-lookup"><span data-stu-id="0b3dd-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="0b3dd-153">セキュリティとコンプライアンス センターで電子情報開示またはコンテンツ検索から検索結果をエクスポートする場合、ダウンロードに予想以上の時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="0b3dd-154">ダウンロードするデータの量を確認し、エクスポート速度を上げすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-155">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-155">Resolution</span></span>

1. <span data-ttu-id="0b3dd-156">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="0b3dd-157">SearchResults パラメーターと SearchStatistics パラメーターで、ダウンロードするデータの量を検索します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="0b3dd-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="0b3dd-159">結果フィールドで、エクスポートされたデータを検索し、発生したエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="0b3dd-160">コンテンツをエクスポートしたディレクトリにある trace.log ファイルで、エラーが発生した場合はチェックします。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="0b3dd-161">それでも問題が発生する場合は、結果の大きなセットを返す検索を小さな検索に分割する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="0b3dd-162">たとえば、検索クエリで日付範囲を使用して、より速くダウンロードできる結果の小さなセットを返します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="0b3dd-163">エラー/問題: "内部サーバー エラー (500) が発生しました"</span><span class="sxs-lookup"><span data-stu-id="0b3dd-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="0b3dd-164">電子情報開示検索を実行する場合、"内部サーバー エラー (500) が発生しました"のようなエラーで検索が継続的に失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部サーバー エラー 500 スクリーンショット](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="0b3dd-166">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-166">Resolution</span></span>

1. <span data-ttu-id="0b3dd-167">検索を小さな検索に分割し、もう一度検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="0b3dd-168">日付範囲を小さくするか、検索する場所の数を制限してみてください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="0b3dd-169">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="0b3dd-170">結果とエラーの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="0b3dd-171">trace.log ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-171">Examine the trace.log file.</span></span> <span data-ttu-id="0b3dd-172">検索結果をエクスポートしたフォルダーと同じフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="0b3dd-173">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="0b3dd-174">エラー/問題: 保留は同期されません</span><span class="sxs-lookup"><span data-stu-id="0b3dd-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="0b3dd-175">電子情報開示ケースホールド ポリシー同期配布エラー。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="0b3dd-176">エラーは次のように読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-176">The error reads:</span></span>

> <span data-ttu-id="0b3dd-177">"リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="0b3dd-178">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-179">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-179">Resolution</span></span>

1. <span data-ttu-id="0b3dd-180">Connectコンプライアンス センター [powerShell &に](/powershell/exchange/connect-to-scc-powershell)移動し、電子情報開示ケースホールドに対して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="0b3dd-181">アイテム保持ポリシーの場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="0b3dd-182">DistributionDetail パラメーターの値を調べて、次のようなエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="0b3dd-183">エラー: リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="0b3dd-184">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="0b3dd-185">問題のポリシーで RetryDistribution パラメーターを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="0b3dd-186">電子情報開示ケースホールドの場合:</span><span class="sxs-lookup"><span data-stu-id="0b3dd-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="0b3dd-187">アイテム保持ポリシーの場合:</span><span class="sxs-lookup"><span data-stu-id="0b3dd-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="0b3dd-188">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="0b3dd-189">エラー: "HTTP 条件付きヘッダーを使用して指定された条件が満たされていません"</span><span class="sxs-lookup"><span data-stu-id="0b3dd-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="0b3dd-190">電子情報開示エクスポート ツールを使用して検索結果をダウンロードすると、次のエラーが表示される可能性があります。これは一時的なエラーで、通常は電子情報開示の場所Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` です。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-191">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-191">Resolution</span></span>

<span data-ttu-id="0b3dd-192">この問題を解決するには、検索結果の [ダウンロードを](export-search-results.md#step-2-download-the-search-results)再試行し、電子情報開示エクスポート ツールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="0b3dd-193">エラー/問題: ダウンロードしたエクスポートに結果が表示されません</span><span class="sxs-lookup"><span data-stu-id="0b3dd-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="0b3dd-194">エクスポートが正常に完了すると、エクスポート ツールを介したダウンロードが完了すると、結果にファイルが 0 件表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="0b3dd-195">解決方法</span><span class="sxs-lookup"><span data-stu-id="0b3dd-195">Resolution</span></span>

<span data-ttu-id="0b3dd-196">これはクライアント側の問題であり、修復するには、次の手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="0b3dd-197">別のクライアント/コンピューターを使用してダウンロードしてみてください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="0b3dd-198">[Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] コマンドレットを使用して、不要になった古い検索を削除します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-198">Remove old searches that are no longer needed using [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] cmdlet.</span></span>

3. <span data-ttu-id="0b3dd-199">必ずローカル ドライブにダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-199">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="0b3dd-200">ウイルス スキャナーが実行されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-200">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="0b3dd-201">同じフォルダーまたは任意の親フォルダーに他のエクスポートがダウンロードしなかからなことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-201">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="0b3dd-202">前の手順が機能しない場合は、zipping と重複除外を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-202">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="0b3dd-203">これが機能する場合は、ローカル ウイルス スキャナーまたはディスクの問題が原因で問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="0b3dd-203">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
