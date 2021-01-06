---
title: コア電子情報開示ケースからコンテンツをエクスポートしてダウンロードする
f1.keywords:
- NOCSH
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、コア電子情報開示ケースからコンテンツをエクスポートおよびダウンロードする方法について説明します。
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760301"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="079a8-103">コア電子情報開示ケースからコンテンツをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="079a8-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="079a8-104">検索が正常に実行された後、検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="079a8-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="079a8-105">検索結果をエクスポートすると、メールボックス アイテムは PST ファイルまたは個々のメッセージとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="079a8-106">SharePoint サイトと OneDrive for Business サイトからコンテンツをエクスポートすると、ネイティブ Officeドキュメントおよび他のドキュメントのコピーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="079a8-107">エクスポートResults.csv情報を含むファイルと、すべての検索結果に関する情報を含むマニフェスト ファイル (XML 形式) もエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="079a8-108">[ケースに関連付けられている 1 つの検索](#export-the-results-of-a-single-search)の結果をエクスポートすることも、[ケースに関連付けられている複数の検索](#export-the-results-of-multiple-searches)の結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="079a8-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="079a8-109">1 つの検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="079a8-109">Export the results of a single search</span></span>

1. <span data-ttu-id="079a8-110">適切な [https://compliance.microsoft.com](https://compliance.microsoft.com) 電子情報開示のアクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="079a8-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="079a8-111">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[すべて表示] をクリックし、[電子情報開示とコア>**します**。</span><span class="sxs-lookup"><span data-stu-id="079a8-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="079a8-112">[コア **電子情報開示** ] ページで、検索結果をエクスポートするケースを選択し、[ケースを開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="079a8-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="079a8-113">ケースの **ホーム** ページで、[検索] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="079a8-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="079a8-114">ケースの検索の一覧で、検索結果をエクスポートする検索をクリックし、フライアウトで [結果のエクスポート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="079a8-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="079a8-115">[**結果のエクスポート**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-115">The **Export results** page is displayed.</span></span> 

    ![[結果のエクスポート] ページ](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="079a8-117">コア電子情報開示ケースに関連付けられた検索の結果をエクスポートするワークフローは、[コンテンツ検索] ページで検索の検索結果をエクスポートする場合 **と同** じです。</span><span class="sxs-lookup"><span data-stu-id="079a8-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="079a8-118">詳細な手順については、「コンテンツ検索結果をエクスポート [する」を参照してください](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="079a8-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="079a8-p103">検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="079a8-p103">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="079a8-121">エクスポートを開始すると、検索結果はダウンロードする準備が完了します。つまり、検索結果は Microsoft クラウド内の Microsoft 提供の Azure Storage の場所にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="079a8-122">ケースの **エクスポート ジョブ** の一覧を表示するには、[エクスポート] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="079a8-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="079a8-123">[最新の情報に更新] **をクリック** してエクスポート ジョブの一覧を更新し、作成したエクスポート ジョブが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="079a8-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="079a8-124">エクスポート ジョブの名前は、対応する検索と同じ名前で、検索 **_Export** に追加されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="079a8-125">作成したエクスポート ジョブをクリックして、状態情報をフライアウト ページに表示します。</span><span class="sxs-lookup"><span data-stu-id="079a8-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="079a8-126">この情報には、Azure Storage の場所に転送されたアイテムの割合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="079a8-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="079a8-127">すべてのアイテムが転送された後、[結果のダウンロード] をクリックして、検索結果をローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="079a8-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="079a8-128">検索結果のダウンロードの詳細については、「コンテンツ検索結果をエクスポートする」の手順 2 [を参照してください。](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="079a8-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="079a8-129">複数の検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="079a8-129">Export the results of multiple searches</span></span>

<span data-ttu-id="079a8-130">ケースに関連付けられた 1 つの検索の結果をエクスポートする代わりに、1 つのエクスポート ジョブで同じケースから複数の検索の結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="079a8-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="079a8-131">複数の検索の結果をエクスポートする方が、一度に 1 つの検索をエクスポートするよりも高速で簡単です。</span><span class="sxs-lookup"><span data-stu-id="079a8-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="079a8-132">これらの検索の 1 つが保留の場所を検索するように構成されている場合は、複数の検索の結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="079a8-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="079a8-133">適切な [https://compliance.microsoft.com](https://compliance.microsoft.com) 電子情報開示のアクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="079a8-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="079a8-134">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[すべて表示] をクリックし、[電子情報開示とコア>**します**。</span><span class="sxs-lookup"><span data-stu-id="079a8-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="079a8-135">[コア **電子情報開示** ] ページで、検索結果をエクスポートするケースを選択し、[ケースを開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="079a8-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="079a8-136">ケースの **ホーム** ページで、[検索] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="079a8-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="079a8-137">ケースの検索の一覧で、検索結果をエクスポートする 2 つ以上の検索の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="079a8-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="079a8-138">[ **一括操作]** フライアウト ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-138">The **Bulk actions** flyout page appears.</span></span> 

    ![[一括操作] ページで、[結果のエクスポート] をクリックする](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="079a8-140">[結果 **のエクスポート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="079a8-140">Click **Export results**.</span></span>

   <span data-ttu-id="079a8-141">[**結果のエクスポート**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-141">The **Export results** page is displayed.</span></span> 

    ![[結果のエクスポート] ページ](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="079a8-143">この時点で、コア電子情報開示ケースに関連付けられた複数の検索の結果をエクスポートするワークフローは、1 つの検索の検索結果をエクスポートするのと同じです。</span><span class="sxs-lookup"><span data-stu-id="079a8-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="079a8-144">前のセクションの手順 5 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="079a8-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="079a8-145">複数の検索の結果のエクスポートに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="079a8-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="079a8-146">複数の検索の結果をエクスポートすると、すべての検索からの検索クエリが **OR** 演算子を使用して結合され、結合された検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="079a8-147">結合された検索の推定結果は、選択したエクスポート ジョブのフライアウト ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="079a8-148">検索結果は、Microsoft クラウド内の Azure Storage の場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="079a8-149">コピー ジョブの状態は、フライアウト ページにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="079a8-150">前に説明したように、すべての検索結果がコピーされた後は、ローカル コンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="079a8-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="079a8-151">エクスポートする全検索のクエリからのキーワードの最大数は 500 です。</span><span class="sxs-lookup"><span data-stu-id="079a8-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="079a8-152">これは、1 つの検索で同じ制限です。</span><span class="sxs-lookup"><span data-stu-id="079a8-152">This is the same limit for a single search.</span></span> <span data-ttu-id="079a8-153">これは、エクスポート ジョブが OR 演算子を使用してすべての検索クエリを結合 **するから** です。</span><span class="sxs-lookup"><span data-stu-id="079a8-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="079a8-154">この制限を超えると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="079a8-155">この場合は、少ない検索からの結果をエクスポートするか、エクスポートする元の検索の検索クエリを簡略化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="079a8-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="079a8-156">エクスポートされる検索結果は、アイテムが見つかったコンテンツの場所ごとに整理されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="079a8-157">つまり、エクスポート結果内のコンテンツの場所に、異なる検索によって返されるアイテムがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="079a8-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="079a8-158">たとえば、メールボックスごとに 1 つの PST ファイルでメール メッセージをエクスポートする場合、PST ファイルには複数の検索の結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="079a8-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="079a8-159">同じコンテンツの場所の同じメール アイテムまたはドキュメントが、エクスポートする複数の検索によって返される場合、アイテムの 1 つのコピーだけがエクスポートされます。 </span><span class="sxs-lookup"><span data-stu-id="079a8-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="079a8-160">作成後に複数の検索のエクスポートを編集できない。</span><span class="sxs-lookup"><span data-stu-id="079a8-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="079a8-161">たとえば、エクスポート ジョブに対して検索の追加や削除を行えなとします。</span><span class="sxs-lookup"><span data-stu-id="079a8-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="079a8-162">エクスポート ジョブを作成して、エクスポートする検索結果を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="079a8-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="079a8-163">エクスポート ジョブを作成した後は、コンピューターへの結果のダウンロード、エクスポートの再開、またはエクスポート ジョブの削除のみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="079a8-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="079a8-164">エクスポートを再開しても、エクスポート ジョブを構成する検索のクエリに対する変更は、取得される検索結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="079a8-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="079a8-165">エクスポートを再開すると、エクスポート ジョブの作成時に実行されたのと同じ検索クエリ ジョブが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="079a8-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="079a8-166">また、エクスポートを再開すると、Azure Storage の場所にコピーされた検索結果によって以前の結果が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="079a8-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="079a8-167">コピーされた以前の結果はダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="079a8-167">The previous results that were copied won't be available to be downloaded.</span></span>
