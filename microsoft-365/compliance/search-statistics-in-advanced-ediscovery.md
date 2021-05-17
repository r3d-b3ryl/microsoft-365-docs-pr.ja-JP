---
title: 事前電子情報開示の検索統計
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: コレクション検索を実行した後に生成される統計情報を表示して、検索結果を検証Advanced eDiscovery。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750778"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="c192d-103">[検索] で統計情報をAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c192d-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="c192d-104">検索結果を検証する方法の 1 つは、結果に関する統計情報を確認して、期待に沿った結果を得る方法です。</span><span class="sxs-lookup"><span data-stu-id="c192d-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="c192d-105">検索が完了すると、検索の詳細フライアウトに高レベルの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="c192d-106">検索によって取得されたアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="c192d-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="c192d-107">検索場所で見つかった部分的にインデックス付きまたはインデックスのないアイテムの数とボリューム</span><span class="sxs-lookup"><span data-stu-id="c192d-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="c192d-108">検索されたメールボックスと場所の数。</span><span class="sxs-lookup"><span data-stu-id="c192d-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="c192d-109">より詳細な統計情報を表示するには、検索の詳細フライアウトから [統計情報] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c192d-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="c192d-110">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="c192d-110">Summary view</span></span>

<span data-ttu-id="c192d-111">[概要] ビューでは、検索結果を場所の種類 (例: Exchange) で表示できます。</span><span class="sxs-lookup"><span data-stu-id="c192d-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="c192d-112">場所の種類ごとに、次の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c192d-112">For each location type, you can see:</span></span>

- <span data-ttu-id="c192d-113">検索条件に一致するアイテムがあった場所の数</span><span class="sxs-lookup"><span data-stu-id="c192d-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="c192d-114">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="c192d-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="c192d-115">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="c192d-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="c192d-116">[上位の場所] ビュー</span><span class="sxs-lookup"><span data-stu-id="c192d-116">Top locations view</span></span>

<span data-ttu-id="c192d-117">[上位の場所] ビューには、一致が最も多い個々の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="c192d-118">場所ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-118">For each location, you will see:</span></span>

- <span data-ttu-id="c192d-119">場所名 (URL などSharePoint)</span><span class="sxs-lookup"><span data-stu-id="c192d-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="c192d-120">場所の種類</span><span class="sxs-lookup"><span data-stu-id="c192d-120">Location type</span></span>

- <span data-ttu-id="c192d-121">検索条件に一致したアイテムの数</span><span class="sxs-lookup"><span data-stu-id="c192d-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="c192d-122">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="c192d-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="c192d-123">クエリ ビュー</span><span class="sxs-lookup"><span data-stu-id="c192d-123">Queries view</span></span>

<span data-ttu-id="c192d-124">クエリで (c:s) キーワードまたはキーワード行を使用している場合は、場所の種類ごとのクエリ ビューでクエリの内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c192d-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="c192d-125">場所の種類ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-125">For each location type, you will see:</span></span>

- <span data-ttu-id="c192d-126">パート: この列には、"Primary" または "Keyword" という単語があります。</span><span class="sxs-lookup"><span data-stu-id="c192d-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="c192d-127">"Primary" は、行がクエリ全体の統計情報を表示するのに対し、"Keyword" はクエリ コンポーネントの 1 つを意味します。</span><span class="sxs-lookup"><span data-stu-id="c192d-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="c192d-128">クエリ: 行が参照する実際のクエリ コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="c192d-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="c192d-129">Part が "Primary" の場合、これはクエリ全体です。Part が "Keyword" の場合は、クエリ コンポーネントの 1 つがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="c192d-130">(キーワードを指定しない) すべての contentin メールボックスを検索すると、実際のクエリは (サイズ >= 0) なので、すべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="c192d-131">SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c192d-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="c192d-132">NOT IsExternalContent:1 - オンプレミスの組織からコンテンツをSharePointします</span><span class="sxs-lookup"><span data-stu-id="c192d-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="c192d-133">NOT isOneNotePage: 1 - 検索クエリに一致するドキュメントOneNote重複するファイルなので、すべてのファイルを除外します。</span><span class="sxs-lookup"><span data-stu-id="c192d-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="c192d-134">検索条件に一致するアイテムを含む場所の数。</span><span class="sxs-lookup"><span data-stu-id="c192d-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="c192d-135">検索条件に一致したこれらの場所からのアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="c192d-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="c192d-136">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="c192d-136">Total volume of items that matched the search conditions.</span></span>
