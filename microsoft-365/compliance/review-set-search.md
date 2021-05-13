---
title: レビュー セット内のデータをクエリする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: レビュー セットでクエリを作成して実行し、データを整理して、より効率的なレビューを行う方法についてAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345802"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="329ac-103">レビュー セット内のデータをクエリする</span><span class="sxs-lookup"><span data-stu-id="329ac-103">Query the data in a review set</span></span>

<span data-ttu-id="329ac-104">ほとんどの場合、レビュー セット内のデータを深く掘り下げ、そのデータを整理して、より効率的なレビューを容易に行えるのが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="329ac-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="329ac-105">レビュー セットでクエリを使用すると、レビューの条件を満たすドキュメントのサブセットに集中できます。</span><span class="sxs-lookup"><span data-stu-id="329ac-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="329ac-106">レビュー セットでのクエリの作成と実行</span><span class="sxs-lookup"><span data-stu-id="329ac-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="329ac-107">レビュー セット内のドキュメントに対してクエリを作成して実行するには、レビュー セットで **[新しいクエリ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="329ac-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="329ac-108">クエリに名前を付けて条件を定義した後、[保存] **を選択して** クエリを保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="329ac-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="329ac-109">以前に保存されたクエリを実行するには、保存したクエリを選択します。</span><span class="sxs-lookup"><span data-stu-id="329ac-109">To run a query that has been previously saved, select a saved query.</span></span>

![セット クエリを確認する](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="329ac-111">レビュー セット クエリの作成</span><span class="sxs-lookup"><span data-stu-id="329ac-111">Building a review set query</span></span>

<span data-ttu-id="329ac-112">キーワード、プロパティ、および条件の組み合わせを使用して、キーワード条件でクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="329ac-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="329ac-113">条件をブロック (条件グループと呼 *ばれる)* としてグループ化して、より複雑なクエリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="329ac-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="329ac-114">検索できるメタデータのプロパティの一覧と説明については、「[Advanced eDiscovery のドキュメントのメタデータ フィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="329ac-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="329ac-115">条件</span><span class="sxs-lookup"><span data-stu-id="329ac-115">Conditions</span></span>

<span data-ttu-id="329ac-116">レビュー セット内のすべての検索可能フィールドには、クエリの作成に使用できる対応する条件があります。</span><span class="sxs-lookup"><span data-stu-id="329ac-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="329ac-117">条件には複数の種類があります。</span><span class="sxs-lookup"><span data-stu-id="329ac-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="329ac-118">フリーテキスト: 件名などのテキスト フィールドにフリーテキスト条件が使用されます。</span><span class="sxs-lookup"><span data-stu-id="329ac-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="329ac-119">複数の検索用語をコンマで区切ってリストできます。</span><span class="sxs-lookup"><span data-stu-id="329ac-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="329ac-120">日付: 日付条件は、最終変更日などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="329ac-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="329ac-121">検索オプション: 検索オプション条件は、レビュー セット内の特定のフィールドに使用できる値の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="329ac-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="329ac-122">これは、レビュー セットに指定できる値の数が有限である送信者などのフィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="329ac-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="329ac-123">キーワード: キーワード条件は、用語を検索したり、KQL のようなクエリ言語を使用したりするために使用できるフリーテキスト条件の特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="329ac-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="329ac-124">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="329ac-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="329ac-125">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="329ac-125">Query language</span></span>

<span data-ttu-id="329ac-126">条件に加えて、キーワード条件で KQL のようなクエリ言語を使用してクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="329ac-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="329ac-127">レビュー セット クエリのクエリ言語は **、AND、OR、NOT、NEAR** などの標準ブール演算子を **サポートします**。 </span><span class="sxs-lookup"><span data-stu-id="329ac-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="329ac-128">また、1 文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="329ac-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="329ac-129">フィルター</span><span class="sxs-lookup"><span data-stu-id="329ac-129">Filters</span></span>

<span data-ttu-id="329ac-130">保存できるクエリに加えて、レビュー セット フィルターを使用して、レビュー セット クエリに追加の条件をすばやく適用できます。</span><span class="sxs-lookup"><span data-stu-id="329ac-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="329ac-131">フィルターを使用すると、レビュー セット クエリによって表示される結果をさらに絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="329ac-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![セット フィルターを確認する](../media/AeDReviewSetFilters.png)

<span data-ttu-id="329ac-133">フィルターは、2 つの重要な方法でクエリと異なります。</span><span class="sxs-lookup"><span data-stu-id="329ac-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="329ac-134">フィルターは一時的なものです。</span><span class="sxs-lookup"><span data-stu-id="329ac-134">Filters are transient.</span></span> <span data-ttu-id="329ac-135">既存のセッションを超えて保持されません。</span><span class="sxs-lookup"><span data-stu-id="329ac-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="329ac-136">つまり、フィルターを保存できないのです。</span><span class="sxs-lookup"><span data-stu-id="329ac-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="329ac-137">クエリはレビュー セットに保存され、レビュー セットを開くたびにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="329ac-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="329ac-138">フィルターは常に加算されます。</span><span class="sxs-lookup"><span data-stu-id="329ac-138">Filters are always additive.</span></span> <span data-ttu-id="329ac-139">フィルターは、現在のレビュー セットのクエリに加えて、適用されます。</span><span class="sxs-lookup"><span data-stu-id="329ac-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="329ac-140">別のクエリを適用すると、現在のクエリから返された結果は置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="329ac-140">Applying a different query will replace the results returned by the current query.</span></span>
