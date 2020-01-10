---
title: レビュー セット内のデータをクエリする
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
ms.assetid: ''
description: ''
ms.openlocfilehash: 140ccc3984dc09a794d822eb3ff02f139d87fcd5
ms.sourcegitcommit: ef658406da9d081e5e7a5f3aac8290c2f03f7aff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004824"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="a41f6-102">レビュー セット内のデータをクエリする</span><span class="sxs-lookup"><span data-stu-id="a41f6-102">Query the data in a review set</span></span>

<span data-ttu-id="a41f6-103">ほとんどの場合、レビューセット内のデータをさらに深く掘り下げて、そのデータを整理して、より効率的なレビューを促進できるようにするのが便利です。</span><span class="sxs-lookup"><span data-stu-id="a41f6-103">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="a41f6-104">レビューセットでクエリを使用すると、レビューの基準を満たすドキュメントのサブセットに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-104">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="a41f6-105">レビューセットにクエリを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="a41f6-105">Creating and running a query in a review set</span></span>

<span data-ttu-id="a41f6-106">校閲セット内のドキュメントに対してクエリを作成して実行するには、確認セットの [**新しいクエリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a41f6-106">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="a41f6-107">クエリの名前を指定して条件を定義した後、[**保存**] をクリックしてクエリを保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="a41f6-107">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="a41f6-108">以前に保存したクエリを実行するには、保存されているクエリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a41f6-108">To run a query that has been previously saved, click a saved query.</span></span>

![Set クエリを確認する](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="a41f6-110">レビューセットクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="a41f6-110">Building a review set query</span></span>

<span data-ttu-id="a41f6-111">クエリを作成するには、キーワード条件カードで条件カードとクエリ言語を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="a41f6-111">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="a41f6-112">また、より複雑なクエリを作成するには、条件カードをブロック (*条件グループ*と呼ばれる) としてグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-112">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="a41f6-113">検索できるメタデータプロパティの一覧と説明については、「 [Advanced eDiscovery のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f6-113">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="a41f6-114">条件カード</span><span class="sxs-lookup"><span data-stu-id="a41f6-114">Condition cards</span></span>

<span data-ttu-id="a41f6-115">レビューセット内のすべての検索可能なフィールドには、クエリの作成に使用できる対応する条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="a41f6-115">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="a41f6-116">複数の種類の条件カードがあります。</span><span class="sxs-lookup"><span data-stu-id="a41f6-116">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="a41f6-117">Freetext: freetext 条件カードは、subject などのテキストフィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-117">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="a41f6-118">複数の検索用語をコンマで区切ってリストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-118">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="a41f6-119">日付: 日付条件カードは、最終更新日などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-119">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="a41f6-120">検索オプション: 検索オプション条件カードは、レビューセットの特定のフィールドに使用可能な値の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="a41f6-120">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="a41f6-121">これは、[送信者] などのフィールドに対して使用されます。これは、レビューセットに指定できる値が限定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="a41f6-121">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="a41f6-122">キーワード: キーワード条件カードは、用語を検索したり、で KQL のようなクエリ言語を使用したりするために使用できる、freetext 条件カードの特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a41f6-122">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="a41f6-123">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f6-123">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="a41f6-124">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="a41f6-124">Query language</span></span>

<span data-ttu-id="a41f6-125">条件カードに加えて、キーワードカードで KQL のようなクエリ言語を使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-125">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="a41f6-126">レビューセットクエリのクエリ言語は、 **AND**、 **OR**、 **NOT**、 **NEAR**などの標準ブール演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a41f6-126">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="a41f6-127">また、1文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a41f6-127">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="a41f6-128">フィルターの使用</span><span class="sxs-lookup"><span data-stu-id="a41f6-128">Using filters</span></span>

<span data-ttu-id="a41f6-129">保存できるクエリに加えて、レビューセットフィルターを使用して、追加の条件をレビューセットクエリにすばやく適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-129">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="a41f6-130">これにより、レビューセットクエリによって表示される結果をさらに絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-130">This helps you further refine the results displayed by a review set query.</span></span>

![設定フィルターを確認する](media/AeDReviewSetFilters.png)

<span data-ttu-id="a41f6-132">フィルターは、次の2つの重要な方法でクエリとは異なります。</span><span class="sxs-lookup"><span data-stu-id="a41f6-132">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="a41f6-133">フィルターは一時的なものです。</span><span class="sxs-lookup"><span data-stu-id="a41f6-133">Filters are transient.</span></span> <span data-ttu-id="a41f6-134">既存のセッションを超えて保持されません。</span><span class="sxs-lookup"><span data-stu-id="a41f6-134">They don't persist beyond the existing session.</span></span> <span data-ttu-id="a41f6-135">つまり、フィルターを保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="a41f6-135">In other words, you can't save a filter.</span></span> <span data-ttu-id="a41f6-136">クエリはレビューセットに保存され、レビューセットを開くたびにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-136">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="a41f6-137">フィルターは常に付加的です。</span><span class="sxs-lookup"><span data-stu-id="a41f6-137">Filters are always additive.</span></span> <span data-ttu-id="a41f6-138">フィルターは、現在のレビューセットクエリに加えて適用されます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-138">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="a41f6-139">別のクエリを適用すると、現在のクエリによって返された結果が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a41f6-139">Applying a different query will replace the results returned by the current query.</span></span>
