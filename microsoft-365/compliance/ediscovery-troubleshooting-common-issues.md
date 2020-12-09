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
description: Office 365 電子情報開示の一般的な問題を解決するために実行できる基本的なトラブルシューティング手順について説明します。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4f1bad23705729c15976959a3902501f05da7600
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602038"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="6d3bd-103">一般的な電子情報開示の問題を調査、トラブルシューティング、および解決する</span><span class="sxs-lookup"><span data-stu-id="6d3bd-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="6d3bd-104">このトピックでは、電子情報開示の検索中に発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="6d3bd-105">これらのシナリオのいくつかを解決するには、Microsoft サポートのヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="6d3bd-106">Microsoft サポートに連絡するタイミングについては、「解決手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="6d3bd-107">エラー/問題: あいまいな場所</span><span class="sxs-lookup"><span data-stu-id="6d3bd-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="6d3bd-108">ユーザーのメールボックスの場所を検索に追加しようとしたときに、Exchange Online Protection (EOP) ディレクトリに同じ userID を持つオブジェクトが重複しているか競合している場合、次のエラーが表示され `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-109">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-109">Resolution</span></span>

<span data-ttu-id="6d3bd-110">同じユーザー ID を持つ重複したユーザーまたは配布リストをチェックします。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="6d3bd-111">[セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)に接続します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-111">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="6d3bd-112">ユーザー名のすべてのインスタンスを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="6d3bd-113">' Useralias@contoso.com ' の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="6d3bd-114">名前</span><span class="sxs-lookup"><span data-stu-id="6d3bd-114">Name</span></span>|<span data-ttu-id="6d3bd-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="6d3bd-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="6d3bd-116">Alias、User</span><span class="sxs-lookup"><span data-stu-id="6d3bd-116">Alias, User</span></span>|<span data-ttu-id="6d3bd-117">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="6d3bd-117">MailUser</span></span>|
   > |<span data-ttu-id="6d3bd-118">Alias、User</span><span class="sxs-lookup"><span data-stu-id="6d3bd-118">Alias, User</span></span>|<span data-ttu-id="6d3bd-119">User</span><span class="sxs-lookup"><span data-stu-id="6d3bd-119">User</span></span>|

3. <span data-ttu-id="6d3bd-120">複数のユーザーが返された場合は、競合しているオブジェクトを見つけて修正します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="6d3bd-121">エラー/問題: 特定の場所で検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="6d3bd-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="6d3bd-122">電子情報開示またはコンテンツの検索では、次のエラーが発生することがあります。 `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="6d3bd-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![検索固有の場所が失敗するエラーのスクリーンショット](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="6d3bd-124">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-124">Resolution</span></span>

<span data-ttu-id="6d3bd-125">このエラーが表示された場合は、検索で失敗した場所を確認し、失敗した場所でのみ検索を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="6d3bd-126">[セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-126">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="6d3bd-127">PowerShell 出力から、失敗した場所を [エラー] フィールドに表示するか、または検索出力からエラーが発生した状態の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="6d3bd-128">失敗した場所のみで電子情報開示検索を再試行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="6d3bd-129">引き続きこれらのエラーが表示される場合は、「その他のトラブルシューティング手順のために [失敗した場所を再試行](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-129">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="6d3bd-130">エラー/問題: ファイルが見つかりません</span><span class="sxs-lookup"><span data-stu-id="6d3bd-130">Error/issue: File not found</span></span>

<span data-ttu-id="6d3bd-131">SharePoint Online を含む電子情報開示検索を実行する際に、ビジネスの場所として1つのドライブを使用すると、 `File Not Found` ファイルがサイトに配置されていてもエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="6d3bd-132">このエラーは、エクスポート時に警告が表示され、items.csv errors.csv またはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="6d3bd-133">これは、サイトでファイルが見つからない場合、またはインデックスが古くなっている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="6d3bd-134">実際のエラーのテキストを次に示します (強調が追加されています)。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="6d3bd-135">28.06.2019 10:02: コンテンツをダウンロードするには19_FailedToExportItem_Failed します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="6d3bd-136">その他の診断情報: 6ea52149-91cd-コンテンツのダウンロードに失敗しました。 b5bb-82ca6a3ec9be Document of the be of the of the type of Document。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="6d3bd-137">関連付け Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="6d3bd-138">ServerErrorCode:-2147024894 >---例外: ***ファイルが見つかりません***。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="6d3bd-139">ProcessResponseStream (Stream responseStream) () で、内部例外スタックトレース---の最後に (Stream) を呼び出します。の場合は、内部例外スタックトレースの末尾に---します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-140">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-140">Resolution</span></span>

1. <span data-ttu-id="6d3bd-141">検索で特定された場所を調べて、ファイルの場所が正しいことと、検索場所に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="6d3bd-142">サイト [、ライブラリ、またはリストのインデックスを再作成するための、手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content) の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="6d3bd-143">エラー/問題: 受信者が見つからないため、検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="6d3bd-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="6d3bd-144">電子情報開示の検索が失敗し、エラーが発生し `recipient not found` ます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="6d3bd-145">このエラーは、オブジェクトが同期されていないために、Exchange Online Protection (EOP) でユーザーオブジェクトが見つからない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-146">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-146">Resolution</span></span>

1. <span data-ttu-id="6d3bd-147">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) に接続する</span><span class="sxs-lookup"><span data-stu-id="6d3bd-147">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6d3bd-148">ユーザーが Exchange Online Protection と同期されているかどうかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="6d3bd-149">ユーザーに質問するメールユーザーオブジェクトが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="6d3bd-150">何も返されない場合は、user オブジェクトを調査します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="6d3bd-151">オブジェクトを同期できない場合は、Microsoft サポートに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="6d3bd-152">エラー/問題: 検索結果のエクスポートが遅くなっています</span><span class="sxs-lookup"><span data-stu-id="6d3bd-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="6d3bd-153">セキュリティ/コンプライアンスセンターの電子情報開示またはコンテンツ検索からの検索結果をエクスポートする場合、ダウンロードには予想より時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="6d3bd-154">ダウンロードするデータの量を確認して、エクスポートの速度を上げることができます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-155">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-155">Resolution</span></span>

1. <span data-ttu-id="6d3bd-156">[セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-156">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="6d3bd-157">SearchResults パラメーターと Searchresults パラメーターにダウンロードされるデータの量を検索します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="6d3bd-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="6d3bd-159">[結果] フィールドに、エクスポートされたデータを検索し、発生したエラーがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="6d3bd-160">エラーが発生した場合に、コンテンツをエクスポートしたディレクトリにある、トレースログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="6d3bd-161">それでも問題が解決しない場合は、大規模な結果セットを返す検索を小さな検索に分割することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="6d3bd-162">たとえば、検索クエリで日付範囲を使用して、より短時間でダウンロードできる結果セットを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="6d3bd-163">エラー/問題: "内部サーバーエラー (500) が発生しました"</span><span class="sxs-lookup"><span data-stu-id="6d3bd-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="6d3bd-164">電子情報開示検索を実行するときに、"内部サーバーエラー (500) が発生しました" と同様のエラーで検索が引き続き失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部サーバーエラー500スクリーンショット](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="6d3bd-166">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-166">Resolution</span></span>

1. <span data-ttu-id="6d3bd-167">検索を小さな検索に分割して、検索を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="6d3bd-168">短い日付範囲を使用するか、検索する場所の数を制限してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="6d3bd-169">[セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-169">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="6d3bd-170">結果とエラーの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="6d3bd-171">トレースログファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-171">Examine the trace.log file.</span></span> <span data-ttu-id="6d3bd-172">これは、検索結果をエクスポートしたのと同じフォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="6d3bd-173">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="6d3bd-174">エラー/問題: 保留が同期しない</span><span class="sxs-lookup"><span data-stu-id="6d3bd-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="6d3bd-175">電子情報開示ケース保持ポリシー同期の配布エラー。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="6d3bd-176">エラーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-176">The error reads:</span></span>

> <span data-ttu-id="6d3bd-177">リソース: ポリシーの展開に予想よりも時間がかかっています。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="6d3bd-178">最終的な展開状態を更新するのに2時間かかる場合があります。そのため、しばらくしてから数時間後にもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-179">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-179">Resolution</span></span>

1. <span data-ttu-id="6d3bd-180">[セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)に接続し、電子情報開示ケースホールドに対して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-180">Connect to [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="6d3bd-181">アイテム保持ポリシーの場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="6d3bd-182">次のようなエラーが発生した場合は、"指定した値を入力してください" というエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="6d3bd-183">エラー: リソース: ポリシーの展開に予想よりも時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="6d3bd-184">最終的な展開状態を更新するのに2時間かかる場合があります。そのため、しばらくしてから数時間後にもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="6d3bd-185">対象のポリシーで、RetryDistribution パラメーターを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="6d3bd-186">電子情報開示ケース保持の場合:</span><span class="sxs-lookup"><span data-stu-id="6d3bd-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="6d3bd-187">アイテム保持ポリシーの場合:</span><span class="sxs-lookup"><span data-stu-id="6d3bd-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="6d3bd-188">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="6d3bd-189">エラー: "HTTP 条件付きヘッダーを使用して指定された条件は満たされていません"</span><span class="sxs-lookup"><span data-stu-id="6d3bd-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="6d3bd-190">電子情報開示エクスポートツールを使用して検索結果をダウンロードする場合、次のエラーが表示されることがあります。 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` これは、通常、Azure ストレージの場所で発生する一時的なエラーです。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="6d3bd-191">解決方法</span><span class="sxs-lookup"><span data-stu-id="6d3bd-191">Resolution</span></span>

<span data-ttu-id="6d3bd-192">この問題を解決するには、 [検索結果のダウンロード](export-search-results.md#step-2-download-the-search-results)を再試行します。これにより、電子情報開示エクスポートツールが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="6d3bd-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d3bd-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d3bd-193">See Also</span></span>

- [<span data-ttu-id="6d3bd-194">コンテンツの場所エラーを回避するためのヒント</span><span class="sxs-lookup"><span data-stu-id="6d3bd-194">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
