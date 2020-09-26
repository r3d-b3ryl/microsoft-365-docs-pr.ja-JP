---
title: 高度電子情報開示の検索統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 高度な電子情報開示でコレクション検索を実行した後に生成された統計情報を表示して、検索結果を検証します。
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286083"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="47acc-103">高度な電子情報開示の検索統計</span><span class="sxs-lookup"><span data-stu-id="47acc-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="47acc-104">検索結果を検証する方法の1つは、結果に関する統計を調べて、期待どおりに配置されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="47acc-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="47acc-105">検索が完了すると、高度な統計情報が検索の詳細ポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="47acc-106">検索によって取得されたアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="47acc-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="47acc-107">検索場所で見つかった、部分的にインデックスまたはインデックス付けされていないアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="47acc-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="47acc-108">検索されたメールボックスと場所の数。</span><span class="sxs-lookup"><span data-stu-id="47acc-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="47acc-109">詳細な統計情報を表示するには、検索の詳細ポップアップから [統計] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47acc-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="47acc-110">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="47acc-110">Summary view</span></span>

<span data-ttu-id="47acc-111">概要ビューでは、検索結果が場所の種類 (例: Exchange) ごとに分類されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="47acc-112">場所の種類ごとに、次の情報が表示できます。</span><span class="sxs-lookup"><span data-stu-id="47acc-112">For each location type, you can see:</span></span>

- <span data-ttu-id="47acc-113">検索条件に一致したアイテムがある場所の数</span><span class="sxs-lookup"><span data-stu-id="47acc-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="47acc-114">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="47acc-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="47acc-115">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="47acc-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="47acc-116">トップの場所ビュー</span><span class="sxs-lookup"><span data-stu-id="47acc-116">Top locations view</span></span>

<span data-ttu-id="47acc-117">上部の [場所] ビューには、最も一致がある個々の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="47acc-118">場所ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-118">For each location, you will see:</span></span>

- <span data-ttu-id="47acc-119">場所の名前 (例: SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="47acc-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="47acc-120">場所の種類</span><span class="sxs-lookup"><span data-stu-id="47acc-120">Location type</span></span>

- <span data-ttu-id="47acc-121">検索条件に一致したアイテムの数</span><span class="sxs-lookup"><span data-stu-id="47acc-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="47acc-122">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="47acc-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="47acc-123">クエリビュー</span><span class="sxs-lookup"><span data-stu-id="47acc-123">Queries view</span></span>

<span data-ttu-id="47acc-124">クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリビューにクエリのブレークダウンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="47acc-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="47acc-125">場所の種類ごとに、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-125">For each location type, you will see:</span></span>

- <span data-ttu-id="47acc-126">Part: この列には、"Primary" または "Keyword" という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="47acc-127">"Primary" は、クエリ全体に対して行が統計情報を表示することを意味し、"Keyword" は1つのクエリコンポーネントを表します。</span><span class="sxs-lookup"><span data-stu-id="47acc-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="47acc-128">クエリ: 行が参照している実際のクエリコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="47acc-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="47acc-129">Part が "Primary" の場合、これはクエリ全体になります。Part が "Keyword" であった場合は、クエリコンポーネントのいずれかがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="47acc-130">キーワードを指定せずにすべての contentin メールボックスを検索すると、実際のクエリは (size >= 0)、すべてのアイテムが返されるようになります。</span><span class="sxs-lookup"><span data-stu-id="47acc-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="47acc-131">SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="47acc-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="47acc-132">NOT IsExternalContent: 1-オンプレミスの SharePoint 組織からコンテンツを除外する</span><span class="sxs-lookup"><span data-stu-id="47acc-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="47acc-133">NOT isOneNotePage: 1-すべての OneNote ファイルを除外します。これは、検索クエリに一致するドキュメントと重複する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="47acc-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="47acc-134">検索条件に一致したアイテムがある場所の数。</span><span class="sxs-lookup"><span data-stu-id="47acc-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="47acc-135">検索条件に一致したこれらの場所からのアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="47acc-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="47acc-136">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="47acc-136">Total volume of items that matched the search conditions.</span></span>
