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
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551420"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="dc686-103">コア電子情報開示ケースからコンテンツをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc686-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="dc686-104">検索が正常に実行されたら、検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="dc686-104">After a search is successfully run, you can export the search results.</span></span> <span data-ttu-id="dc686-105">検索結果をエクスポートすると、メールボックスアイテムは PST ファイルまたは個別のメッセージとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="dc686-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="dc686-106">SharePoint と OneDrive for Business サイトからコンテンツをエクスポートすると、ネイティブな Office ドキュメントとその他のドキュメントのコピーがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="dc686-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="dc686-107">エクスポートされたすべてのアイテムに関する情報と、すべての検索結果に関する情報を含むマニフェストファイル (XML 形式) がエクスポートされた結果の .csv ファイル。</span><span class="sxs-lookup"><span data-stu-id="dc686-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="dc686-108">[ケースに関連付けられている 1 つの検索](#export-the-results-of-a-single-search)の結果をエクスポートすることも、[ケースに関連付けられている複数の検索](#export-the-results-of-multiple-searches)の結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dc686-108">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches).</span></span>
  
## <a name="export-the-results-of-a-single-search"></a><span data-ttu-id="dc686-109">単一の検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc686-109">Export the results of a single search</span></span>

1. <span data-ttu-id="dc686-110">に[https://compliance.microsoft.com](https://compliance.microsoft.com)移動し、適切な電子情報開示のアクセス許可が割り当てられているユーザーアカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc686-110">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="dc686-111">Microsoft 365 コンプライアンスセンターの左側のナビゲーションウィンドウで、[**すべて表示**] をクリックし、[**電子情報開示 > Core**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-111">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="dc686-112">[**コア電子情報開示**] ページで、検索結果をエクスポートするケースを選択し、[ **case を開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-112">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="dc686-113">ケースの**ホーム**ページで、[**検索**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-113">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="dc686-114">ケースの検索の一覧で、検索結果のエクスポート元となる検索をクリックし、ポップアップで [結果の**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-114">In the list of searches for the case, click the search that you want to export search results from, and then click **Export results** on the flyout.</span></span>

    <span data-ttu-id="dc686-115">[**結果のエクスポート**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-115">The **Export results** page is displayed.</span></span> 

    ![[結果のエクスポート] ページ](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="dc686-117">コア電子情報開示ケースに関連付けられた検索結果をエクスポートするワークフローは、**コンテンツ検索**ページで検索の検索結果をエクスポートするのと同じです。</span><span class="sxs-lookup"><span data-stu-id="dc686-117">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="dc686-118">詳細な手順については、「[コンテンツ検索の結果をエクスポート](export-search-results.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc686-118">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc686-p103">検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc686-p103">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

    <span data-ttu-id="dc686-121">エクスポートを開始すると、検索結果のダウンロードが準備されます。これは、microsoft が提供する microsoft クラウド内の Azure ストレージの場所にアップロードされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dc686-121">After you start the export, the search results are prepared for downloading, which means they are uploaded to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="dc686-122">ケースのエクスポートジョブの一覧を表示するには、[**エクスポート**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-122">Click the **Export** tab to display the list of export jobs for the case.</span></span>
  
    <span data-ttu-id="dc686-123">作成したエクスポートジョブが表示されるように、[**更新**] をクリックしてエクスポートジョブのリストを更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc686-123">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="dc686-124">エクスポートジョブの名前は、検索名に **_Export**が追加された対応する検索と同じです。</span><span class="sxs-lookup"><span data-stu-id="dc686-124">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="dc686-125">作成したエクスポートジョブをクリックして、フライアウトページに状態情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc686-125">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="dc686-126">この情報には、Azure ストレージの場所に転送されたアイテムの割合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc686-126">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="dc686-127">すべてのアイテムが転送されたら、[**結果のダウンロード**] をクリックして、検索結果をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="dc686-127">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="dc686-128">検索結果のダウンロードの詳細については、「[コンテンツ検索結果のエクスポート](export-search-results.md#step-2-download-the-search-results)」のステップ2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc686-128">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

## <a name="export-the-results-of-multiple-searches"></a><span data-ttu-id="dc686-129">複数の検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="dc686-129">Export the results of multiple searches</span></span>

<span data-ttu-id="dc686-130">ケースに関連付けられた1つの検索結果をエクスポートする代わりに、1つのエクスポートジョブで同じケースから複数の検索結果をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc686-130">As an alternative to exporting the results of a single search associated with a case, you can export the results of multiple searches from the same case in a single export job.</span></span> <span data-ttu-id="dc686-131">複数の検索結果をエクスポートすることは、一度に1回の検索で結果をエクスポートするよりも速く、簡単です。</span><span class="sxs-lookup"><span data-stu-id="dc686-131">Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc686-132">保留中の場所を検索するようにこれらの検索のいずれかが構成されている場合、複数の検索の結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dc686-132">You can't export the results of multiple searches if one of those searches was configured to search locations on hold.</span></span>

1. <span data-ttu-id="dc686-133">に[https://compliance.microsoft.com](https://compliance.microsoft.com)移動し、適切な電子情報開示のアクセス許可が割り当てられているユーザーアカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc686-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="dc686-134">Microsoft 365 コンプライアンスセンターの左側のナビゲーションウィンドウで、[**すべて表示**] をクリックし、[**電子情報開示 > Core**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-134">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="dc686-135">[**コア電子情報開示**] ページで、検索結果をエクスポートするケースを選択し、[ **case を開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-135">On the **Core eDiscovery** page, select the case that you want to export search results from, and then click **Open case**.</span></span>

4. <span data-ttu-id="dc686-136">ケースの**ホーム**ページで、[**検索**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-136">On the **Home** page for the case, click the **Searches** tab.</span></span>
    
5. <span data-ttu-id="dc686-137">ケースの検索の一覧で、検索結果をエクスポートする2つ以上の検索の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dc686-137">In the list of searches for the case, select the checkbox next to two or more searches you want to export search results from.</span></span> 

   <span data-ttu-id="dc686-138">[**一括アクション**のポップアップ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-138">The **Bulk actions** flyout page appears.</span></span> 

    ![[一括操作] ページで、[結果のエクスポート] をクリックする](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. <span data-ttu-id="dc686-140">[**結果のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc686-140">Click **Export results**.</span></span>

   <span data-ttu-id="dc686-141">[**結果のエクスポート**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-141">The **Export results** page is displayed.</span></span> 

    ![[結果のエクスポート] ページ](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="dc686-143">この時点で、コア電子情報開示ケースに関連付けられた複数の検索結果をエクスポートするワークフローは、単一の検索の検索結果をエクスポートするのと同じです。</span><span class="sxs-lookup"><span data-stu-id="dc686-143">At this point, the workflow to export the results of multiple searches associated with a Core eDiscovery case is that same as exporting the search results for a single search.</span></span> <span data-ttu-id="dc686-144">前のセクションのステップ5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc686-144">See step 5 in the previous section.</span></span>

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="dc686-145">複数の検索の結果のエクスポートに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="dc686-145">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="dc686-146">複数の検索の結果をエクスポートすると、すべての検索からの検索クエリが**or**演算子を使用して結合され、その後の検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-146">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started.</span></span> <span data-ttu-id="dc686-147">組み合わせた検索の推定結果は、選択したエクスポートジョブのフライアウトページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-147">The estimated results of the combined search are displayed in the flyout page of the selected export job.</span></span> <span data-ttu-id="dc686-148">検索結果は、Microsoft クラウド内の Azure ストレージの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="dc686-148">The search results are then copied to the Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="dc686-149">コピージョブの状態も、フライアウトページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-149">The status of the copy job is also displayed on the flyout page.</span></span> <span data-ttu-id="dc686-150">前述したように、すべての検索結果がコピーされたら、それらをローカルコンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="dc686-150">As previously stated, after all the search results have been copied, you can download them to a local computer.</span></span>

- <span data-ttu-id="dc686-151">エクスポートするすべての検索のクエリからの最大キーワード数は500です。</span><span class="sxs-lookup"><span data-stu-id="dc686-151">The maximum number of keywords from queries for all searches that you want to export is 500.</span></span> <span data-ttu-id="dc686-152">これは、1つの検索に対して同じ制限があります。</span><span class="sxs-lookup"><span data-stu-id="dc686-152">This is the same limit for a single search.</span></span> <span data-ttu-id="dc686-153">これは、エクスポートジョブで**or**演算子を使用してすべての検索クエリが結合されるためです。</span><span class="sxs-lookup"><span data-stu-id="dc686-153">That's because the export job combines all the search queries by using the **OR** operator.</span></span> <span data-ttu-id="dc686-154">この制限を超えると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-154">If you exceed this limit, an error will be returned.</span></span> <span data-ttu-id="dc686-155">この場合、より少ない検索から結果をエクスポートするか、エクスポートする元の検索の検索クエリを簡略化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc686-155">In this case, you have to export the results from fewer searches or simplify the search queries of the original searches that you want to export.</span></span>

- <span data-ttu-id="dc686-156">エクスポートされる検索結果は、アイテムが検出されたコンテンツの場所によって整理されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-156">The search results that are exported are organized by the content location the item was found in.</span></span> <span data-ttu-id="dc686-157">つまり、エクスポート結果のコンテンツの場所には、さまざまな検索によって返されるアイテムが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc686-157">That means a content location in the export results may have items returned by different searches.</span></span> <span data-ttu-id="dc686-158">たとえば、メールボックスごとに1つの PST ファイルに電子メールメッセージをエクスポートする場合、PST ファイルに複数の検索の結果が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc686-158">For example, if you choose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>

- <span data-ttu-id="dc686-159">同じコンテンツの場所の同じメール アイテムまたはドキュメントが、エクスポートする複数の検索によって返される場合、アイテムの 1 つのコピーだけがエクスポートされます。 </span><span class="sxs-lookup"><span data-stu-id="dc686-159">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>

- <span data-ttu-id="dc686-160">作成した後で、複数の検索のエクスポートを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc686-160">You can't edit an export for multiple searches after you create it.</span></span> <span data-ttu-id="dc686-161">たとえば、エクスポートジョブから検索を追加または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc686-161">For example, you can't add or remove searches from the export job.</span></span> <span data-ttu-id="dc686-162">エクスポートジョブを作成して、エクスポートする検索結果を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc686-162">You have to create an export job to change which search results are exported.</span></span> <span data-ttu-id="dc686-163">エクスポートジョブを作成した後は、結果をコンピューターにダウンロードするか、エクスポートを再起動するか、またはエクスポートジョブを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc686-163">After an export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>

- <span data-ttu-id="dc686-164">エクスポートを再起動すると、エクスポートジョブを実行する検索のクエリを変更しても、取得した検索結果には影響しません。</span><span class="sxs-lookup"><span data-stu-id="dc686-164">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="dc686-165">エクスポートを再起動すると、エクスポートジョブの作成時に実行されたのと同じ組み合わせの検索クエリジョブが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc686-165">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="dc686-166">また、エクスポートを再起動すると、Azure ストレージの場所にコピーされた検索結果によって、以前の結果が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dc686-166">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="dc686-167">以前にコピーされた結果をダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dc686-167">The previous results that were copied won't be available to be downloaded.</span></span>

- <span data-ttu-id="dc686-168">高度な電子情報開示 (クラシック) での分析のために複数の検索結果を準備することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc686-168">Preparing the results of multiple searches for analysis in Advanced eDiscovery (classic) isn't available.</span></span> <span data-ttu-id="dc686-169">高度な電子情報開示 (クラシック) では、1回の検索の結果のみを準備できます。</span><span class="sxs-lookup"><span data-stu-id="dc686-169">You can only prepare the results of a single search for analysis in Advanced eDiscovery (classic).</span></span>
