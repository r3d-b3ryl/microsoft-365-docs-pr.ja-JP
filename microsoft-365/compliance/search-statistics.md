---
title: 検索の統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 検索統計は、検索結果を検証する効果的な方法で、[検索の詳細] ポップアップページの [状態] の下に表示されます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 24de99cf0a7ae21b5966811b988c93d64abd5148
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286093"
---
# <a name="search-statistics-in-data-investigations-preview"></a><span data-ttu-id="6742d-103">データ調査での検索統計 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6742d-103">Search statistics in Data Investigations (preview)</span></span>

<span data-ttu-id="6742d-104">データインシデントの調査時に検索結果を検証する効果的な方法は、検索結果に関する統計情報を表示して、期待どおりに配置されていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="6742d-104">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="6742d-105">検索の実行が完了すると、[検索の詳細] ポップアップページの [ **状態** ] の下に、次のような高レベルの統計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-105">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![検索 statisics 上の検索の詳細ポップアップページ](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="6742d-107">検索条件に一致したアイテムの推定数とサイズ。</span><span class="sxs-lookup"><span data-stu-id="6742d-107">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="6742d-108">検索可能ではないが、検索に含まれていたコンテンツの場所にある、部分的にインデックスが作成されたアイテムの数とサイズ (非 *インデックスアイテム*とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="6742d-108">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="6742d-109">検索されたメールボックスとサイトの数。</span><span class="sxs-lookup"><span data-stu-id="6742d-109">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="6742d-110">詳細な統計情報を表示するには、[検索の詳細] ポップアップページの [ **統計** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6742d-110">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="6742d-111">[ **検索統計** ] ページでは、検索の概要、検索結果に一致したアイテムを含む上位の場所、および検索クエリに関する詳細な統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6742d-111">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![検索の統計ドロップダウンリスト](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="6742d-113">要約</span><span class="sxs-lookup"><span data-stu-id="6742d-113">Summary</span></span>

<span data-ttu-id="6742d-114">**概要**ビューでは、検索結果が場所の種類別に分類されて表示されます (たとえば、場所には Exchange メールボックスと SharePoint サイトが含まれています)。</span><span class="sxs-lookup"><span data-stu-id="6742d-114">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="6742d-115">場所の種類ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-115">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="6742d-116">検索条件に一致したアイテムがある場所の数。</span><span class="sxs-lookup"><span data-stu-id="6742d-116">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="6742d-117">検索条件に一致した各場所の種類からのアイテムの合計数。</span><span class="sxs-lookup"><span data-stu-id="6742d-117">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="6742d-118">検索条件に一致した各場所の種類からのアイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="6742d-118">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="6742d-119">トップの場所</span><span class="sxs-lookup"><span data-stu-id="6742d-119">Top locations</span></span>

<span data-ttu-id="6742d-120">上部の [ **場所** ] ビューには、検索条件に一致したアイテムが最も多い各コンテンツの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-120">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="6742d-121">コンテンツの場所ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-121">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="6742d-122">場所の名前。メールボックスの電子メールアドレスと SharePoint サイトの URL</span><span class="sxs-lookup"><span data-stu-id="6742d-122">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="6742d-123">場所の種類</span><span class="sxs-lookup"><span data-stu-id="6742d-123">The location type</span></span>

- <span data-ttu-id="6742d-124">検索条件に一致したアイテムの数</span><span class="sxs-lookup"><span data-stu-id="6742d-124">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="6742d-125">検索条件に一致したすべてのアイテムの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="6742d-125">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="6742d-126">クエリ</span><span class="sxs-lookup"><span data-stu-id="6742d-126">Queries</span></span>

<span data-ttu-id="6742d-127">[ **クエリ** ] ビューには、検索クエリの各コンポーネントの詳細な統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-127">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="6742d-128">検索クエリでキーワードリストを使用した場合は、各キーワードまたはキーワードフレーズに一致するアイテムの数を示す、[ **クエリ** ] ビューで拡張された統計を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6742d-128">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="6742d-129">これにより、クエリの最も多い部分 (最も少ないもの) をすばやく識別することができます。</span><span class="sxs-lookup"><span data-stu-id="6742d-129">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="6742d-130">**クエリ**ビューに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-130">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="6742d-131">**場所の種類** -行に表示される統計のコンテンツの場所の種類。</span><span class="sxs-lookup"><span data-stu-id="6742d-131">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="6742d-132">**Part** -この列には、次のいずれかの値が表示されます: **Primary** または **Keyword**。</span><span class="sxs-lookup"><span data-stu-id="6742d-132">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="6742d-133">**Primary** は、クエリ全体の統計を示す行を表します。 **キーワード** は、1つのクエリコンポーネントの行の統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6742d-133">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="6742d-134">**条件** -行が参照する検索クエリの実際のクエリコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="6742d-134">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="6742d-135">**Part**列の値が**Primary**の場合は、検索クエリ全体の統計が表示されます。値が**Keyword**の場合、[**クエリ**] 列に表示されているクエリのコンポーネントの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-135">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="6742d-136">たとえば、キーワードリストが使用されている場合、キーワードの1つの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-136">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="6742d-137">[ **クエリ** ] 列に表示される統計情報に関するその他の事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6742d-137">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="6742d-138">メールボックス内のすべてのコンテンツ (キーワードを指定せず) を検索すると、実際のクエリは **(size >= 0)** 、すべてのアイテムが返されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6742d-138">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="6742d-139">SharePoint および OneDrive サイトを検索すると、次の2つのコンポーネントが検索クエリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6742d-139">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="6742d-140">**NOT IsExternalContent: 1** -オンプレミスの SharePoint 組織からのコンテンツを除外する</span><span class="sxs-lookup"><span data-stu-id="6742d-140">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="6742d-141">**NOT isOneNotePage: 1** -すべての OneNote ファイルを除外します。これは、検索クエリに一致するドキュメントと重複するためです。</span><span class="sxs-lookup"><span data-stu-id="6742d-141">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="6742d-142">**検索の場所** 行に表示されているパーツまたは条件に対して検索クエリと一致したアイテムがあるコンテンツの場所の数。</span><span class="sxs-lookup"><span data-stu-id="6742d-142">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="6742d-143">アーカイブメールボックスには、検索条件に一致するアイテムが含まれている場合は、別の場所としてカウントされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6742d-143">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="6742d-144">**Items** -行に表示されているパーツまたは条件の検索条件に一致したアイテムの合計数。</span><span class="sxs-lookup"><span data-stu-id="6742d-144">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="6742d-145">**Size** -行に表示されるパーツまたは条件の検索条件に一致したアイテムの合計数。</span><span class="sxs-lookup"><span data-stu-id="6742d-145">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

