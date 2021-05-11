---
title: 電子情報開示検索結果の統計情報を表示する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 検索統計機能を使用して、コア電子情報開示ケースに関連付けられたコンテンツ検索と検索の統計をコンプライアンス センターで表示するMicrosoft 365説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311115"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="39c7f-103">電子情報開示検索結果の統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="39c7f-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="39c7f-104">コンテンツ検索または Core 電子情報開示ケースに関連付けられた検索を作成して実行した後、推定検索結果に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="39c7f-105">これには、検索結果の概要 (検索フライアウト ページに表示される推定検索結果の概要と同様)、検索クエリに一致するアイテムを含むコンテンツの場所の数、最も一致するアイテムがあるコンテンツの場所の ID などのクエリ統計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="39c7f-106">さらに、キーワード リストを使用して、検索クエリ内の各キーワードの統計情報を返す検索を構成できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="39c7f-107">これにより、クエリ内の各キーワードによって返される結果の数を比較できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="39c7f-108">検索統計を CSV ファイルにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="39c7f-109">これにより、フィルター処理と並べ替え機能を使用して、Excelを比較し、検索結果のレポートを準備できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="39c7f-110">検索の統計情報を取得する</span><span class="sxs-lookup"><span data-stu-id="39c7f-110">Get statistics for searches</span></span>

<span data-ttu-id="39c7f-111">コンテンツ検索またはコア電子情報開示ケースに関連付けられた検索の統計情報を表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="39c7f-112">[コンプライアンス センター Microsoft 365で、[すべて **表示]** をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="39c7f-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="39c7f-113">[ **コンテンツ検索] を** クリックし、検索を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="39c7f-114">OR</span><span class="sxs-lookup"><span data-stu-id="39c7f-114">OR</span></span>

   - <span data-ttu-id="39c7f-115">[**電子情報開示**  >  **コア]** をクリックし、ケースを選択し、[検索] タブで検索を **選択** して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="39c7f-116">選択した検索のフライアウト ページで、[検索の統計情報] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![[検索の統計情報] タブ](../media/SearchStatistics1.png)

<span data-ttu-id="39c7f-118">[ **検索の統計情報]** タブには、検索に関するさまざまな種類の統計情報を含む次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="39c7f-119">検索コンテンツ</span><span class="sxs-lookup"><span data-stu-id="39c7f-119">Search content</span></span>

<span data-ttu-id="39c7f-120">このセクションでは、検索によって返される推定アイテムの概要をグラフィカルに表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="39c7f-121">これは、検索条件に一致するアイテムの数を示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="39c7f-122">この情報は、検索によって返されるアイテムの推定数に関するアイデアを提供します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![検索の見積もりを検索する](../media/SearchContentReport.png)

- <span data-ttu-id="39c7f-124">**場所別の推定アイテム**: 検索によって返される推定アイテムの総数。</span><span class="sxs-lookup"><span data-stu-id="39c7f-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="39c7f-125">メールボックスとサイト内にあるアイテムの特定の数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="39c7f-126">**ヒットの推定場所**: 検索によって返されるアイテムを含むコンテンツの場所の総数。</span><span class="sxs-lookup"><span data-stu-id="39c7f-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="39c7f-127">メールボックスとサイトの場所の特定の数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="39c7f-128">**場所別のデータボリューム (MB 単位)**: 検索によって返される推定アイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="39c7f-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="39c7f-129">メールボックス アイテムとサイト アイテムの特定のサイズも表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="39c7f-130">条件レポート</span><span class="sxs-lookup"><span data-stu-id="39c7f-130">Condition report</span></span>

<span data-ttu-id="39c7f-131">このセクションでは、検索クエリに関する統計情報と、検索クエリの異なる部分に一致した推定アイテムの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="39c7f-132">これらの統計を使用して、検索クエリの各コンポーネントに一致するアイテムの数を分析できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="39c7f-133">これにより、検索条件を絞り込み、必要に応じて範囲を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="39c7f-134">このレポートのコピーを CSV 形式でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-134">You can also download a copy of this report in CSV format.</span></span>

![条件レポート](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="39c7f-136">**場所の** 種類: クエリ統計が適用されるコンテンツの場所の種類。</span><span class="sxs-lookup"><span data-stu-id="39c7f-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="39c7f-137">この値は **Exchange** メールボックスの場所を示します。サイトの場所 **SharePoint** 値を指定します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="39c7f-138">**Part**: 統計が適用される検索クエリの一部。</span><span class="sxs-lookup"><span data-stu-id="39c7f-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="39c7f-139">**Primary は** 、検索クエリ全体を示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="39c7f-140">**キーワード** は、行内の統計情報が特定のキーワードに対する値を示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="39c7f-141">検索クエリにキーワード リストを使用する場合は、クエリの各コンポーネントの統計情報が次の表に含まれます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="39c7f-142">詳細については、「検索の [キーワード統計を取得する」を参照してください](#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="39c7f-143">**Condition**: 対応する行に表示される統計情報を返した検索クエリの実際のコンポーネント (キーワードまたは条件)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="39c7f-144">**ヒットのある場所**: [条件] 列にリストされているプライマリクエリまたはキーワード クエリに一致するアイテムを含むコンテンツの場所 ([場所の種類] 列で指定) の **数**。</span><span class="sxs-lookup"><span data-stu-id="39c7f-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="39c7f-145">**アイテム**: [条件] 列に一覧表示されているクエリに一致するアイテムの数 (指定したコンテンツの場所 **から** )。</span><span class="sxs-lookup"><span data-stu-id="39c7f-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="39c7f-146">前に説明したように、検索中のキーワードの複数のインスタンスがアイテムに含まれている場合、この列には 1 回だけカウントされます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="39c7f-147">**サイズ (MB)**: [条件] 列の検索クエリに一致する (指定したコンテンツの場所で) 見つかったすべてのアイテムの **合計サイズ。**</span><span class="sxs-lookup"><span data-stu-id="39c7f-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="39c7f-148">トップの場所</span><span class="sxs-lookup"><span data-stu-id="39c7f-148">Top locations</span></span>

<span data-ttu-id="39c7f-149">このセクションでは、検索によって返されるアイテムが最も多い特定のコンテンツの場所に関する統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="39c7f-150">上位 1,000 の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="39c7f-151">このレポートのコピーを CSV 形式でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="39c7f-152">場所名 (メールボックスの電子メール アドレスとサイトの URL) の名前。</span><span class="sxs-lookup"><span data-stu-id="39c7f-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="39c7f-153">場所の種類 (メールボックスまたはサイト)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="39c7f-154">検索によって返されるコンテンツの場所のアイテムの推定数。</span><span class="sxs-lookup"><span data-stu-id="39c7f-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="39c7f-155">各コンテンツの場所の推定アイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="39c7f-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="39c7f-156">検索のキーワード統計を取得する</span><span class="sxs-lookup"><span data-stu-id="39c7f-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="39c7f-157">前に説明したように、[ **条件] レポート** セクションには、検索クエリと、クエリに一致するアイテムの数 (およびサイズ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="39c7f-158">検索クエリを作成または編集するときにキーワード リストを使用する場合は、各キーワードまたはキーワード フレーズに一致するアイテムの数を示す拡張統計情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="39c7f-159">これにより、クエリの最も有効な部分 (および最も少ない) を迅速に特定できます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="39c7f-160">たとえば、キーワードが多数のアイテムを返す場合は、キーワード クエリを絞り込んで検索結果を絞り込む場合があります。</span><span class="sxs-lookup"><span data-stu-id="39c7f-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="39c7f-161">キーワード リストを作成し、検索のキーワード統計を表示するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="39c7f-162">コンプライアンス センター Microsoft 365、新しいコンテンツ検索または Core 電子情報開示ケースに関連付けられた検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="39c7f-163">検索ウィザード **の [** 条件] ページで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="39c7f-164">[キーワード リスト **の表示] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="39c7f-164">select the **Show keyword list** checkbox.</span></span>

   ![[キーワード一覧を表示する] チェック ボックス](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="39c7f-166">キーワード テーブルの行にキーワードまたはキーワード フェーズを入力します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="39c7f-167">たとえば、最初の行 **に「budget」** と入力し、2 行目に **「security」** と入力し、3 行目に **「FY2021」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![リストに最大 20 のキーワードまたはキーワード フレーズを入力する](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="39c7f-169">大規模なキーワード リストによって発生する問題を軽減するために、検索クエリのキーワード リストの最大 20 行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="39c7f-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="39c7f-170">検索して統計情報を取得するキーワードをリストに追加した後、検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="39c7f-171">検索が完了したら、それを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="39c7f-172">[検索の **統計情報] タブ** で、[条件] レポート **をクリックして** 、検索のキーワード統計を表示します。</span><span class="sxs-lookup"><span data-stu-id="39c7f-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![各キーワードの統計情報が表示されます](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="39c7f-174">前のスクリーンショットで示したように、各キーワードの統計情報が表示されます。次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39c7f-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="39c7f-175">検索に含まれるコンテンツの場所の各種類に対するキーワード統計。</span><span class="sxs-lookup"><span data-stu-id="39c7f-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="39c7f-176">インデックスが作成されていないメールボックス アイテムの数。</span><span class="sxs-lookup"><span data-stu-id="39c7f-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="39c7f-177">各キーワードの実際の検索クエリと結果 ([パーツ] 列の **[** キーワード] として識別されます) (検索クエリの条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="39c7f-178">完全な検索クエリ ([パーツ] 列 **でプライマリ** として識別) と、場所の種類ごとに完全なクエリの統計情報。</span><span class="sxs-lookup"><span data-stu-id="39c7f-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="39c7f-179">これらは、[概要] タブに表示される統計 **と同じ点に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="39c7f-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
