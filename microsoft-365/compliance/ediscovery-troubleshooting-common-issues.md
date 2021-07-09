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
ms.openlocfilehash: 0b118a97df765321704a995905de797e06a60108
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339420"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="5abfa-103">一般的な電子情報開示の問題を調査、トラブルシューティング、解決する</span><span class="sxs-lookup"><span data-stu-id="5abfa-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="5abfa-104">このトピックでは、電子情報開示検索中または電子情報開示プロセスの他の場所で発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="5abfa-105">これらのシナリオの一部を解決するには、Microsoft サポートのヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="5abfa-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="5abfa-106">Microsoft サポートに問い合わせする場合の情報は、解決手順に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5abfa-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="5abfa-107">エラー/問題: あいまいな場所</span><span class="sxs-lookup"><span data-stu-id="5abfa-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="5abfa-108">ユーザーのメールボックスの場所を検索に追加しようとして、Exchange Online Protection (EOP) ディレクトリに同じ userID を持つオブジェクトが重複または競合している場合は、次のエラーが表示されます。 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`</span><span class="sxs-lookup"><span data-stu-id="5abfa-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-109">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-109">Resolution</span></span>

<span data-ttu-id="5abfa-110">同じユーザー ID を持つ重複ユーザーまたは配布リストを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="5abfa-111">Connect[コンプライアンス センター PowerShell &にアクセスします](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5abfa-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="5abfa-112">次のコマンドを実行して、ユーザー名のすべてのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="5abfa-113">'useralias@contoso.com' の出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="5abfa-114">名前</span><span class="sxs-lookup"><span data-stu-id="5abfa-114">Name</span></span>|<span data-ttu-id="5abfa-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="5abfa-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="5abfa-116">エイリアス、ユーザー</span><span class="sxs-lookup"><span data-stu-id="5abfa-116">Alias, User</span></span>|<span data-ttu-id="5abfa-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="5abfa-117">MailUser</span></span>|
   > |<span data-ttu-id="5abfa-118">エイリアス、ユーザー</span><span class="sxs-lookup"><span data-stu-id="5abfa-118">Alias, User</span></span>|<span data-ttu-id="5abfa-119">User</span><span class="sxs-lookup"><span data-stu-id="5abfa-119">User</span></span>|

3. <span data-ttu-id="5abfa-120">複数のユーザーが返された場合は、競合するオブジェクトを見つけて修正します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="5abfa-121">エラー/問題: 特定の場所で検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="5abfa-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="5abfa-122">電子情報開示またはコンテンツ検索では、次のエラーが発生する可能性があります。 `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="5abfa-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![検索固有の場所でエラー のスクリーンショットが失敗する](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="5abfa-124">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-124">Resolution</span></span>

<span data-ttu-id="5abfa-125">このエラーが表示された場合は、検索で失敗した場所を確認してから、失敗した場所でのみ検索を再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5abfa-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="5abfa-126">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="5abfa-127">PowerShell 出力から、エラー フィールドまたは検索出力からのエラーの状態の詳細から、失敗した場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="5abfa-128">失敗した場所でのみ電子情報開示検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="5abfa-129">これらのエラーを引き続き受け取る場合は、「失敗した場所を再試行する」を参照 [して](/Office365/SecurityCompliance/retry-failed-content-search) 、トラブルシューティングの手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="5abfa-130">エラー/問題: ファイルが見つかりません</span><span class="sxs-lookup"><span data-stu-id="5abfa-130">Error/issue: File not found</span></span>

<span data-ttu-id="5abfa-131">オンラインとビジネス向け 1 つのドライブの場所SharePoint含む電子情報開示検索を実行すると、ファイルがサイト上にありますが、エラー `File Not Found` が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="5abfa-132">このエラーは、エクスポートの警告に表示され、errors.csvまたはスキップitems.csv。</span><span class="sxs-lookup"><span data-stu-id="5abfa-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="5abfa-133">これは、サイトでファイルが見つからない場合、またはインデックスが最新の日付でなかった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="5abfa-134">実際のエラーのテキストを次に示します (強調が追加されています)。</span><span class="sxs-lookup"><span data-stu-id="5abfa-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="5abfa-135">28.06.2019 10:02:19_FailedToExportItem_Failedダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5abfa-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="5abfa-136">その他の診断情報 : Microsoft。Office。Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Document 型のコンテンツ 6ea52149-91cd-4965-b5bb-82ca6a3ec9be からのダウンロードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5abfa-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="5abfa-137">相関 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="5abfa-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="5abfa-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint。Client.ServerException:***ファイルが見つかりません***。</span><span class="sxs-lookup"><span data-stu-id="5abfa-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="5abfa-139">at Microsoft.SharePoint。Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint。Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="5abfa-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-140">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-140">Resolution</span></span>

1. <span data-ttu-id="5abfa-141">検索で識別された場所を確認して、ファイルの場所が正しく、検索場所に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="5abfa-142">サイト、ライブラリ、または[](/sharepoint/crawl-site-content)リストのクロールと再インデックスの手動要求の手順を使用して、サイトのインデックスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="5abfa-143">エラー/問題: このファイルは存在しなくなったためエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="5abfa-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="5abfa-144">このファイルは、インデックスに引き続き一覧表示されたため、推定検索結果の数に含まれていました。</span><span class="sxs-lookup"><span data-stu-id="5abfa-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="5abfa-145">ファイルは最終的にインデックスから削除され、将来エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="5abfa-146">オンラインおよびビジネス向け One Drive For Business の場所を含む電子情報開示SharePointを実行すると、このエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="5abfa-147">電子情報開示は、SPO インデックスを使用してファイルの場所を識別します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-147">eDiscovery relies on the SPO index to identify the file locations.</span></span> <span data-ttu-id="5abfa-148">ファイルが削除されたが、SPO インデックスがまだ更新されていない場合、このエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-149">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-149">Resolution</span></span> 
<span data-ttu-id="5abfa-150">SPO の場所を開き、このファイルが実際に開いていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="5abfa-151">推奨される解決策は、サイトのインデックスを手動で再作成するか、サイトが自動的なバックグラウンド プロセスによってインデックスを再作成するまで待機することです。</span><span class="sxs-lookup"><span data-stu-id="5abfa-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artifact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="5abfa-152">エラー/問題: この検索結果は、それ自体ではダウンロードできないフォルダーまたは他の成果物である場合はダウンロードされません。フォルダーまたはライブラリ内のアイテムはダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="5abfa-152">Error/issue: This search result was not downloaded as it is a folder or other artifact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="5abfa-153">オンラインおよびビジネス向け One Drive For Business の場所を含む電子情報開示SharePointを実行すると、このエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="5abfa-154">これは、インデックスで報告されたアイテムをエクスポートしようとしていたが、フォルダーなのでエクスポートしなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="5abfa-155">エラーで説明したように、フォルダー アイテムはエクスポートされますが、その内容はエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="5abfa-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="5abfa-156">エラー/問題: 受信者が見つからないため、検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="5abfa-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="5abfa-157">電子情報開示の検索が失敗し、エラーが発生しました `recipient not found` 。</span><span class="sxs-lookup"><span data-stu-id="5abfa-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="5abfa-158">このエラーは、オブジェクトが同期されていないので、Exchange Online Protection (EOP) でユーザー オブジェクトが見つからない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-159">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-159">Resolution</span></span>

1. <span data-ttu-id="5abfa-160">[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する</span><span class="sxs-lookup"><span data-stu-id="5abfa-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5abfa-161">次のコマンドを実行して、ユーザーが同期されている場所を確認Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="5abfa-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="5abfa-162">ユーザーの質問のメール ユーザー オブジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="5abfa-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="5abfa-163">何も返されなかった場合は、ユーザー オブジェクトを調査します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="5abfa-164">オブジェクトを同期できない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="5abfa-165">エラー/問題: 検索結果のエクスポートが遅い</span><span class="sxs-lookup"><span data-stu-id="5abfa-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="5abfa-166">コア電子情報開示検索またはコンテンツ検索から検索結果をエクスポートする場合、Microsoft 365 コンプライアンス センター予想より長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-166">When exporting search results from Core eDiscovery or Content search in the Microsoft 365 compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="5abfa-167">ダウンロードするデータの量を確認し、エクスポート速度を上げすることができます。</span><span class="sxs-lookup"><span data-stu-id="5abfa-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-168">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-168">Resolution</span></span>

1. <span data-ttu-id="5abfa-169">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="5abfa-170">SearchResults パラメーターと SearchStatistics パラメーターで、ダウンロードするデータの量を検索します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="5abfa-171">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="5abfa-172">結果フィールドで、エクスポートされたデータを検索し、発生したエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="5abfa-173">コンテンツをエクスポートしたディレクトリにある trace.log ファイルで、エラーが発生した場合はチェックします。</span><span class="sxs-lookup"><span data-stu-id="5abfa-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="5abfa-174">それでも問題が発生する場合は、結果の大きなセットを返す検索を小さな検索に分割する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="5abfa-175">たとえば、検索クエリで日付範囲を使用して、より速くダウンロードできる結果の小さなセットを返します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-export-process-not-progressing-or-is-stuck"></a><span data-ttu-id="5abfa-176">エラー/問題: エクスポート プロセスが進行していないか、スタックしている</span><span class="sxs-lookup"><span data-stu-id="5abfa-176">Error/issue: Export process not progressing or is stuck</span></span>

<span data-ttu-id="5abfa-177">コア電子情報開示検索またはコンテンツ検索から検索結果をエクスポートする場合、Microsoft 365 コンプライアンス センタープロセスが進行していないか、スタックしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-177">When exporting search results from Core eDiscovery or Content search in the Microsoft 365 compliance center, the export process is not progressing or appears to be stuck.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-178">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-178">Resolution</span></span>

1. <span data-ttu-id="5abfa-179">必要に応じて、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-179">If necessary, rerun the search.</span></span> <span data-ttu-id="5abfa-180">検索が 7 日以上前に実行された場合は、検索を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-180">If the search was last ran more than 7 days ago, you have to rerun the search.</span></span>

2. <span data-ttu-id="5abfa-181">エクスポートを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-181">Restart the export.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="5abfa-182">エラー/問題: "内部サーバー エラー (500) が発生しました"</span><span class="sxs-lookup"><span data-stu-id="5abfa-182">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="5abfa-183">電子情報開示検索を実行する場合、"内部サーバー エラー (500) が発生しました"のようなエラーで検索が継続的に失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-183">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部サーバー エラー 500 スクリーンショット](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="5abfa-185">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-185">Resolution</span></span>

1. <span data-ttu-id="5abfa-186">検索を小さな検索に分割し、もう一度検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-186">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="5abfa-187">日付範囲を小さくするか、検索する場所の数を制限してみてください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-187">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="5abfa-188">Connectコンプライアンス センター [powerShell &に移動し、](/powershell/exchange/connect-to-scc-powershell)次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-188">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="5abfa-189">結果とエラーの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-189">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="5abfa-190">trace.log ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-190">Examine the trace.log file.</span></span> <span data-ttu-id="5abfa-191">検索結果をエクスポートしたフォルダーと同じフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-191">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="5abfa-192">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-192">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="5abfa-193">エラー/問題: 保留は同期されません</span><span class="sxs-lookup"><span data-stu-id="5abfa-193">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="5abfa-194">電子情報開示ケースホールド ポリシー同期配布エラー。</span><span class="sxs-lookup"><span data-stu-id="5abfa-194">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="5abfa-195">エラーは次のように読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-195">The error reads:</span></span>

> <span data-ttu-id="5abfa-196">"リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-196">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="5abfa-197">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-198">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-198">Resolution</span></span>

1. <span data-ttu-id="5abfa-199">Connectコンプライアンス センター [powerShell &に](/powershell/exchange/connect-to-scc-powershell)移動し、電子情報開示ケースホールドに対して次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-199">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="5abfa-200">アイテム保持ポリシーの場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-200">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="5abfa-201">DistributionDetail パラメーターの値を調べて、次のようなエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-201">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="5abfa-202">エラー: リソース: ポリシーの展開に予想以上に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="5abfa-202">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="5abfa-203">最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-203">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="5abfa-204">問題のポリシーで RetryDistribution パラメーターを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-204">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="5abfa-205">電子情報開示ケースホールドの場合:</span><span class="sxs-lookup"><span data-stu-id="5abfa-205">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="5abfa-206">アイテム保持ポリシーの場合:</span><span class="sxs-lookup"><span data-stu-id="5abfa-206">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="5abfa-207">Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-207">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="5abfa-208">エラー: "HTTP 条件付きヘッダーを使用して指定された条件が満たされていません"</span><span class="sxs-lookup"><span data-stu-id="5abfa-208">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="5abfa-209">電子情報開示エクスポート ツールを使用して検索結果をダウンロードすると、次のエラーが表示される可能性があります。これは一時的なエラーで、通常は電子情報開示の場所Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` です。</span><span class="sxs-lookup"><span data-stu-id="5abfa-209">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-210">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-210">Resolution</span></span>

<span data-ttu-id="5abfa-211">この問題を解決するには、検索結果の [ダウンロードを](export-search-results.md#step-2-download-the-search-results)再試行し、電子情報開示エクスポート ツールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-211">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="5abfa-212">エラー/問題: ダウンロードしたエクスポートに結果が表示されません</span><span class="sxs-lookup"><span data-stu-id="5abfa-212">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="5abfa-213">エクスポートが正常に完了すると、エクスポート ツールを介したダウンロードが完了すると、結果にファイルが 0 件表示されます。</span><span class="sxs-lookup"><span data-stu-id="5abfa-213">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="5abfa-214">解決方法</span><span class="sxs-lookup"><span data-stu-id="5abfa-214">Resolution</span></span>

<span data-ttu-id="5abfa-215">これはクライアント側の問題です。</span><span class="sxs-lookup"><span data-stu-id="5abfa-215">This is a client-side issue.</span></span> <span data-ttu-id="5abfa-216">修復するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-216">To remediate it, follow these steps:</span></span>

1. <span data-ttu-id="5abfa-217">別のクライアント/コンピューターを使用してダウンロードしてみてください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-217">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="5abfa-218">[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch)コマンドレットを使用して不要になった古い検索を削除します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-218">Remove old searches that are no longer needed using [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet.</span></span>

3. <span data-ttu-id="5abfa-219">必ずローカル ドライブにダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="5abfa-219">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="5abfa-220">ウイルス スキャナーが実行されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-220">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="5abfa-221">同じフォルダーまたは任意の親フォルダーに他のエクスポートがダウンロードしなかからなことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-221">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="5abfa-222">前の手順が機能しない場合は、zipping と重複除外を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5abfa-222">If the previous steps don't work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="5abfa-223">これが機能する場合は、ローカル ウイルス スキャナーまたはディスクの問題が原因で問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="5abfa-223">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
