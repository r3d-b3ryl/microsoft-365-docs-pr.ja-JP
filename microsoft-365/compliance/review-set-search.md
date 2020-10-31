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
description: レビューセットでクエリを作成して実行し、高度な電子情報開示ケースにおけるより効率的なレビューのためにデータを整理する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816570"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="1b527-103">レビュー セット内のデータをクエリする</span><span class="sxs-lookup"><span data-stu-id="1b527-103">Query the data in a review set</span></span>

<span data-ttu-id="1b527-104">ほとんどの場合、レビューセット内のデータをさらに深く掘り下げて、そのデータを整理して、より効率的なレビューを促進できるようにするのが便利です。</span><span class="sxs-lookup"><span data-stu-id="1b527-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="1b527-105">レビューセットでクエリを使用すると、レビューの基準を満たすドキュメントのサブセットに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1b527-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="1b527-106">レビューセットにクエリを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="1b527-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="1b527-107">レビューセット内のドキュメントに対してクエリを作成して実行するには、レビューセットの [ **新しいクエリ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b527-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="1b527-108">クエリの名前を指定して条件を定義した後、[ **保存** ] を選択してクエリを保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="1b527-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="1b527-109">以前に保存されたクエリを実行するには、保存済みのクエリを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b527-109">To run a query that has been previously saved, select a saved query.</span></span>

![Set クエリを確認する](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="1b527-111">レビューセットクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="1b527-111">Building a review set query</span></span>

<span data-ttu-id="1b527-112">キーワード、プロパティ、および条件をキーワード条件に組み合わせて使用すると、クエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1b527-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="1b527-113">また、より複雑なクエリを作成するには、条件をブロック ( *条件グループ* と呼ばれる) としてグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b527-113">You can also group conditions as a block (called a *condition group* ) to build a more complex query.</span></span> <span data-ttu-id="1b527-114">検索できるメタデータのプロパティの一覧と説明については、「[Advanced eDiscovery のドキュメントのメタデータ フィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b527-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="1b527-115">条件</span><span class="sxs-lookup"><span data-stu-id="1b527-115">Conditions</span></span>

<span data-ttu-id="1b527-116">レビューセット内のすべての検索可能なフィールドには、クエリの作成に使用できる対応する条件があります。</span><span class="sxs-lookup"><span data-stu-id="1b527-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="1b527-117">条件には、次の複数の種類があります。</span><span class="sxs-lookup"><span data-stu-id="1b527-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="1b527-118">Freetext: freetext 条件は、subject などのテキストフィールドに対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b527-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="1b527-119">複数の検索用語をコンマで区切ってリストすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b527-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="1b527-120">日付: 日付の条件は、最終変更日などの日付フィールドに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b527-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="1b527-121">検索オプション: 検索オプションの条件には、レビューセットの特定のフィールドに指定できる値の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b527-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="1b527-122">これは、[送信者] などのフィールドに対して使用されます。これは、レビューセットに指定できる値が限定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="1b527-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="1b527-123">キーワード: キーワード条件は、用語を検索したり、で KQL のようなクエリ言語を使用したりするために使用できる freetext 条件の特定のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="1b527-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="1b527-124">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b527-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="1b527-125">クエリ言語</span><span class="sxs-lookup"><span data-stu-id="1b527-125">Query language</span></span>

<span data-ttu-id="1b527-126">条件に加えて、キーワードの条件に KQL のようなクエリ言語を使用して、クエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1b527-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="1b527-127">レビューセットクエリのクエリ言語は、 **AND** 、 **OR** 、 **NOT** 、 **NEAR** などの標準ブール演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1b527-127">The query language for review set queries supports standard Boolean operators, such as **AND** , **OR** , **NOT** , and **NEAR** .</span></span> <span data-ttu-id="1b527-128">また、1文字のワイルドカード (?) と複数文字のワイルドカード (\*) もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1b527-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="1b527-129">フィルター</span><span class="sxs-lookup"><span data-stu-id="1b527-129">Filters</span></span>

<span data-ttu-id="1b527-130">保存できるクエリに加えて、レビューセットフィルターを使用して、追加の条件をレビューセットクエリにすばやく適用することができます。</span><span class="sxs-lookup"><span data-stu-id="1b527-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="1b527-131">フィルターを使用すると、レビューセットクエリによって表示される結果をさらに絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1b527-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![設定フィルターを確認する](../media/AeDReviewSetFilters.png)

<span data-ttu-id="1b527-133">フィルターは、次の2つの重要な方法でクエリとは異なります。</span><span class="sxs-lookup"><span data-stu-id="1b527-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="1b527-134">フィルターは一時的なものです。</span><span class="sxs-lookup"><span data-stu-id="1b527-134">Filters are transient.</span></span> <span data-ttu-id="1b527-135">既存のセッションを超えて保持されません。</span><span class="sxs-lookup"><span data-stu-id="1b527-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="1b527-136">つまり、フィルターを保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b527-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="1b527-137">クエリはレビューセットに保存され、レビューセットを開くたびにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1b527-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="1b527-138">フィルターは常に付加的です。</span><span class="sxs-lookup"><span data-stu-id="1b527-138">Filters are always additive.</span></span> <span data-ttu-id="1b527-139">フィルターは、現在のレビュー セットのクエリに加えて、適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b527-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="1b527-140">別のクエリを適用すると、現在のクエリから返された結果は置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="1b527-140">Applying a different query will replace the results returned by the current query.</span></span>
