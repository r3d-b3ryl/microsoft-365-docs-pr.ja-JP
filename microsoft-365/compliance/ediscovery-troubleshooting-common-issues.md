---
title: Troublshooting の一般的な電子情報開示の問題
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 365 eDiscovery の一般的な問題を調査、トラブルシューティング、解決します。
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207296"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="2730a-103">一般的な電子情報開示の問題を調査、トラブルシューティング、および解決する</span><span class="sxs-lookup"><span data-stu-id="2730a-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="2730a-104">このトピックでは、電子情報開示の検索中に発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2730a-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="2730a-105">これらのシナリオのいくつかを解決するには、カスタマーサポートサービス (CSS) のヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="2730a-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="2730a-106">CSS に連絡するタイミングの詳細については、「解決手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730a-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="2730a-107">エラー/問題のあいまいな場所</span><span class="sxs-lookup"><span data-stu-id="2730a-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="2730a-108">このエラーメッセージが表示されるのは、Exchange Online Protection ( `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` EOP) で、ユーザーのメールボックスの場所を検索に追加しようとしたときに、重複した、または競合しているオブジェクトが存在する場合です。名簿.</span><span class="sxs-lookup"><span data-stu-id="2730a-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="2730a-109">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-109">Resolution</span></span>

<span data-ttu-id="2730a-110">同じユーザー ID を持つ重複したユーザーまたは配布リストをチェックします。</span><span class="sxs-lookup"><span data-stu-id="2730a-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="2730a-111">[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) に接続する</span><span class="sxs-lookup"><span data-stu-id="2730a-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="2730a-112">ユーザー名のすべてのインスタンスを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2730a-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="2730a-113">' Useralias@contoso.com ' の出力は、</span><span class="sxs-lookup"><span data-stu-id="2730a-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="2730a-114">名前</span><span class="sxs-lookup"><span data-stu-id="2730a-114">Name</span></span>  |<span data-ttu-id="2730a-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2730a-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="2730a-116">Alias、User</span><span class="sxs-lookup"><span data-stu-id="2730a-116">Alias, User</span></span>     |<span data-ttu-id="2730a-117">Enable-mailuser</span><span class="sxs-lookup"><span data-stu-id="2730a-117">MailUser</span></span>         |
> |<span data-ttu-id="2730a-118">Alias、User</span><span class="sxs-lookup"><span data-stu-id="2730a-118">Alias, User</span></span>     |<span data-ttu-id="2730a-119">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2730a-119">User</span></span>         |

3. <span data-ttu-id="2730a-120">複数のユーザーが返された場合は、競合しているオブジェクトを見つけて修正します。</span><span class="sxs-lookup"><span data-stu-id="2730a-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="2730a-121">特定の場所でエラー/問題の検索が失敗する</span><span class="sxs-lookup"><span data-stu-id="2730a-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="2730a-122">電子情報開示またはコンテンツの検索では、次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2730a-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="2730a-123">この検索は (#) エラーで完了しました。</span><span class="sxs-lookup"><span data-stu-id="2730a-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="2730a-124">失敗した場所で検索を再試行しますか?</span><span class="sxs-lookup"><span data-stu-id="2730a-124">Would you like to retry the search on the failed locations?</span></span>

![検索の特定の場所が失敗するエラーのスクリーンショット]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="2730a-126">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-126">Resolution</span></span>

<span data-ttu-id="2730a-127">このエラーが表示された場合は、検索で失敗した場所を確認し、失敗した場所でのみ検索を再実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2730a-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="2730a-128">[Exchange Online Protection の Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続します。</span><span class="sxs-lookup"><span data-stu-id="2730a-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="2730a-129">種類:</span><span class="sxs-lookup"><span data-stu-id="2730a-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="2730a-130">PowerShell 出力から、失敗した場所を [エラー] フィールドに表示するか、または検索出力からエラーが発生した状態の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="2730a-131">失敗した場所のみで電子情報開示検索を再試行します。</span><span class="sxs-lookup"><span data-stu-id="2730a-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="2730a-132">引き続きこれらのエラーが表示される場合は、「その他のトラブルシューティング手順で[失敗した場所を再試行](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730a-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="2730a-133">エラー/問題ファイルが見つかりません</span><span class="sxs-lookup"><span data-stu-id="2730a-133">Error/issue file not found</span></span>

<span data-ttu-id="2730a-134">SharePoint Online を含む電子情報開示検索を実行する際に、ビジネスの場所として 1 `File Not Found`つのドライブを使用すると、ファイルがサイトに配置されていてもエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2730a-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="2730a-135">このエラーは、エクスポートの警告とエラー .csv またはスキップされたアイテムです。これは、ファイルがサイトに存在しないか、インデックスが古くなっている場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2730a-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="2730a-136">強調が追加された実際のエラーのテキストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2730a-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="2730a-137">28.06.2019 10:02: 19_FailedToExportItem_Failed をダウンロードしてコンテンツをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2730a-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="2730a-138">その他の診断情報: 6ea52149-91cd-コンテンツのダウンロードに失敗しました。 b5bb-82ca6a3ec9be Document of the be of the of the type of Document。</span><span class="sxs-lookup"><span data-stu-id="2730a-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="2730a-139">関連付け Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="2730a-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="2730a-140">ServerErrorCode:-2147024894 >---例外:***ファイルが見つかりません***。</span><span class="sxs-lookup"><span data-stu-id="2730a-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="2730a-141">ProcessResponseStream (Stream responseStream) () で、内部例外スタックトレース---の最後に (Stream) を呼び出します。の場合は、内部例外スタックトレースの末尾に---します。</span><span class="sxs-lookup"><span data-stu-id="2730a-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="2730a-142">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-142">Resolution</span></span>

1. <span data-ttu-id="2730a-143">検索で特定された場所を調べて、ファイルの場所が正しいことと、検索場所に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="2730a-144">サイト[、ライブラリ、またはリストの](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)インデックスを再作成するための手動要求の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2730a-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="2730a-145">エラー/問題の検索で受信者が見つからない</span><span class="sxs-lookup"><span data-stu-id="2730a-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="2730a-146">電子情報開示の検索`recipient not found`がエラーで失敗する。</span><span class="sxs-lookup"><span data-stu-id="2730a-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="2730a-147">このエラーは、オブジェクトが同期されていないために、Exchange Online Protection (EOP) でユーザーオブジェクトが見つからない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2730a-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="2730a-148">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-148">Resolution</span></span>

1. <span data-ttu-id="2730a-149">[Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続します。</span><span class="sxs-lookup"><span data-stu-id="2730a-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="2730a-150">ユーザーオブジェクトが Exchange Online Protection の種類と同期されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="2730a-151">ユーザーの質問には enable-mailuser オブジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="2730a-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="2730a-152">何も返されない場合は、user オブジェクトを調査します。</span><span class="sxs-lookup"><span data-stu-id="2730a-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="2730a-153">オブジェクトを同期できない場合は、CSS に接続します。</span><span class="sxs-lookup"><span data-stu-id="2730a-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="2730a-154">検索結果のエクスポートに時間がかかるエラー/問題</span><span class="sxs-lookup"><span data-stu-id="2730a-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="2730a-155">セキュリティ/コンプライアンスセンターの電子情報開示またはコンテンツ検索からの検索結果をエクスポートする場合、ダウンロードには予想より時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="2730a-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="2730a-156">ダウンロードするデータの量を確認して、エクスポートの速度を上げることができます。</span><span class="sxs-lookup"><span data-stu-id="2730a-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="2730a-157">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-157">Resolution</span></span>

1.  <span data-ttu-id="2730a-158">この記事に記載されている手順を使用して、[ダウンロード速度を上げ](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)ます。</span><span class="sxs-lookup"><span data-stu-id="2730a-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="2730a-159">それでも問題が解決しない場合は、 [Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2730a-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="2730a-160">SearchResults パラメーターと Searchresults パラメーターにダウンロードされるデータの量を検索します。</span><span class="sxs-lookup"><span data-stu-id="2730a-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="2730a-161">種類:</span><span class="sxs-lookup"><span data-stu-id="2730a-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="2730a-162">[結果] フィールドに、エクスポートされたデータを検索し、発生したエラーがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="2730a-163">エラーが発生した場合に、コンテンツをエクスポートしたディレクトリにある、トレースログファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="2730a-164">エラー/問題 "内部サーバーエラー (500) が発生しました"</span><span class="sxs-lookup"><span data-stu-id="2730a-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="2730a-165">電子情報開示検索を実行するときに、"内部サーバーエラー (500) が発生しました" と同様のエラーで検索が繰り返し失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2730a-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![内部サーバーエラー500スクリーンショット](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="2730a-167">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-167">Resolution</span></span>

1. <span data-ttu-id="2730a-168">検索を小さな検索に分割して、検索を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="2730a-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="2730a-169">短い日付範囲を使用するか、検索する場所の数を制限してください。</span><span class="sxs-lookup"><span data-stu-id="2730a-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="2730a-170">[Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2730a-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="2730a-171">結果とエラーの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="2730a-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="2730a-172">トレースログファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="2730a-172">Examine the trace.log file.</span></span> <span data-ttu-id="2730a-173">エクスポートをに送信したのと同じフォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2730a-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="2730a-174">サポートの CSS に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2730a-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="2730a-175">エラー/問題保持が同期しない</span><span class="sxs-lookup"><span data-stu-id="2730a-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="2730a-176">電子情報開示ケース保持ポリシー同期の配布エラー。</span><span class="sxs-lookup"><span data-stu-id="2730a-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="2730a-177">エラーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2730a-177">The error reads:</span></span>

> <span data-ttu-id="2730a-178">リソース: ポリシーの展開に予想よりも時間がかかっています。</span><span class="sxs-lookup"><span data-stu-id="2730a-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="2730a-179">最終的な展開状態を更新するには2時間かかることがあります。そのため、数時間後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="2730a-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="2730a-180">解決策</span><span class="sxs-lookup"><span data-stu-id="2730a-180">Resolution</span></span>

1.  <span data-ttu-id="2730a-181">[Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2730a-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="2730a-182">次のようなエラーが発生した場合は、"指定した値を入力してください" というエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="2730a-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="2730a-183">エラーが存在する場合は、PG へのエスカレーションを作成して、手動による強制的な再同期をポリシーに適用します。</span><span class="sxs-lookup"><span data-stu-id="2730a-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="2730a-184">連絡先 CSS。</span><span class="sxs-lookup"><span data-stu-id="2730a-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="2730a-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="2730a-185">See Also</span></span>
- [<span data-ttu-id="2730a-186">コンテンツの場所エラーを回避するためのヒント</span><span class="sxs-lookup"><span data-stu-id="2730a-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)