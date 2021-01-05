---
title: Advance eDiscovery での検索統計
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
description: Advanced eDiscovery でコレクション検索を実行した後に生成される統計情報を表示して、検索結果を検証します。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750778"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="23008-103">Advanced eDiscovery の検索統計</span><span class="sxs-lookup"><span data-stu-id="23008-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="23008-104">検索結果を検証する 1 つの方法は、結果に関する統計情報を確認して、期待に沿った結果を確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="23008-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="23008-105">検索が完了すると、検索の詳細のフライアウトに高レベルの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="23008-106">検索によって取得されたアイテムの数と量</span><span class="sxs-lookup"><span data-stu-id="23008-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="23008-107">検索場所で見つかった、部分的にインデックスが作成されたアイテムまたはインデックスのないアイテムの数と量</span><span class="sxs-lookup"><span data-stu-id="23008-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="23008-108">検索されたメールボックスと場所の数。</span><span class="sxs-lookup"><span data-stu-id="23008-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="23008-109">より詳細な統計情報を表示するには、検索の詳細のフライアウトから [統計情報] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23008-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="23008-110">概要ビュー</span><span class="sxs-lookup"><span data-stu-id="23008-110">Summary view</span></span>

<span data-ttu-id="23008-111">[概要] ビューでは、場所の種類 (Exchange など) 別に検索結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="23008-112">場所の種類ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-112">For each location type, you can see:</span></span>

- <span data-ttu-id="23008-113">検索条件に一致するアイテムを含む場所の数</span><span class="sxs-lookup"><span data-stu-id="23008-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="23008-114">検索条件に一致したこれらの場所からのアイテムの数</span><span class="sxs-lookup"><span data-stu-id="23008-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="23008-115">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="23008-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="23008-116">[上位の場所] ビュー</span><span class="sxs-lookup"><span data-stu-id="23008-116">Top locations view</span></span>

<span data-ttu-id="23008-117">[上位の場所] ビューには、最も一致する場所が個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="23008-118">場所ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-118">For each location, you will see:</span></span>

- <span data-ttu-id="23008-119">場所名 (例: SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="23008-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="23008-120">場所の種類</span><span class="sxs-lookup"><span data-stu-id="23008-120">Location type</span></span>

- <span data-ttu-id="23008-121">検索条件に一致したアイテムの数</span><span class="sxs-lookup"><span data-stu-id="23008-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="23008-122">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="23008-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="23008-123">クエリ ビュー</span><span class="sxs-lookup"><span data-stu-id="23008-123">Queries view</span></span>

<span data-ttu-id="23008-124">クエリで (c:s) キーワードまたはキーワード行を使用した場合は、場所の種類ごとにクエリ ビューでクエリの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="23008-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="23008-125">場所の種類ごとに、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-125">For each location type, you will see:</span></span>

- <span data-ttu-id="23008-126">パート: この列には、単語 "Primary" または "Keyword" が含まれる。</span><span class="sxs-lookup"><span data-stu-id="23008-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="23008-127">"Primary" は、行がクエリ全体に統計情報を表示し、"キーワード" はクエリ コンポーネントの 1 つを意味します。</span><span class="sxs-lookup"><span data-stu-id="23008-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="23008-128">クエリ: 行が参照する実際のクエリ コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="23008-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="23008-129">Part が "Primary" の場合、これはクエリ全体です。Part が "Keyword" の場合、クエリ コンポーネントの 1 つがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="23008-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="23008-130">(キーワードを指定しない) すべてのコンテンツ イン メールボックスを検索する場合、実際のクエリは (サイズ >= 0) なので、すべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="23008-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="23008-131">SharePoint Online と OneDrive for Business サイトを検索すると、次の 2 つのコンポーネントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="23008-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="23008-132">NOT IsExternalContent:1 - オンプレミスの SharePoint 組織からコンテンツを除外します</span><span class="sxs-lookup"><span data-stu-id="23008-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="23008-133">NOT isOneNotePage: 1 - 検索クエリに一致するドキュメントが重複する可能性がある OneNote ファイルはすべて除外されます。</span><span class="sxs-lookup"><span data-stu-id="23008-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="23008-134">検索条件と一致するアイテムを含む場所の数。</span><span class="sxs-lookup"><span data-stu-id="23008-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="23008-135">検索条件に一致したこれらの場所からのアイテムの数。</span><span class="sxs-lookup"><span data-stu-id="23008-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="23008-136">検索条件に一致したアイテムの合計量。</span><span class="sxs-lookup"><span data-stu-id="23008-136">Total volume of items that matched the search conditions.</span></span>
