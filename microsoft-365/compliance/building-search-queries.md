---
title: 高度な電子情報開示で検索クエリを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Microsoft 365 の高度な電子情報開示を使用してデータを検索する場合は、キーワードと条件を使用して検索範囲を絞り込む。
ms.openlocfilehash: e0df319257776d3995a4b8e37781d7b5dad54d82
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838483"
---
# <a name="build-search-queries-for-collections-in-advanced-ediscovery"></a><span data-ttu-id="147cd-103">Advanced eDiscovery でコレクションの検索クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="147cd-103">Build search queries for collections in Advanced eDiscovery</span></span>

<span data-ttu-id="147cd-104">Advanced eDiscovery ケースでコレクションを[](collections-overview.md)作成するときに検索クエリを構成する場合、キーワードを使用して特定のコンテンツと条件を検索し、検索範囲を絞り込み、法的調査に最も関連のあるアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="147cd-104">When configuring the search query when creating a [collection](collections-overview.md) in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![キーワードと条件を使用して検索の結果を絞り込む](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="147cd-106">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="147cd-106">Keyword searches</span></span>

<span data-ttu-id="147cd-107">検索クエリの [キーワード] **ボックスに** キーワード クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="147cd-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="147cd-108">キーワード、電子メール メッセージのプロパティ (送信日と受信日など)、またはファイル名やドキュメントが最後に変更された日付などのドキュメント プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="147cd-109">**AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="147cd-110">SharePoint および OneDrive のドキュメント (電子メール メッセージではなく) で機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="147cd-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="147cd-111">この **キーワード** ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。</span><span class="sxs-lookup"><span data-stu-id="147cd-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>

## <a name="keyword-list"></a><span data-ttu-id="147cd-112">キーワード リスト</span><span class="sxs-lookup"><span data-stu-id="147cd-112">Keyword list</span></span>

<span data-ttu-id="147cd-113">または、[キーワード 一 **覧を表示** する] チェック ボックスをオンにして、各行にキーワードまたはキーワード 語句を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="147cd-113">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="147cd-114">各行のキーワードは、作成された検索クエリの **OR** 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:s* として表されます) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="147cd-114">The keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="147cd-115">つまり、任意の行にキーワードを含むアイテムが検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="147cd-115">This means items that contain any keyword in any row are in the search results.</span></span> <span data-ttu-id="147cd-116">高度な電子情報開示検索クエリでは、キーワード リストに最大 180 行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-116">You can add up to 180 rows in the keyword list in Advanced eDiscovery search queries.</span></span>

![キーワード リストを使用して、クエリ内の各キーワードの統計情報を取得する](../media/KeywordListSearch.png)

<span data-ttu-id="147cd-118">キーワード リストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="147cd-118">Why use the keyword list?</span></span> <span data-ttu-id="147cd-119">キーワード リスト内の各キーワードに一致するアイテムの数を示す統計情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-119">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="147cd-120">これにより、最も効果的な (および最も少ない) キーワードをすばやく特定できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-120">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="147cd-121">キーワード リストの行にキーワード 語句 (かっこで囲む) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="147cd-121">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="147cd-122">検索統計の詳細については、「検索統計」 [を参照してください](search-statistics-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="147cd-122">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="147cd-123">条件</span><span class="sxs-lookup"><span data-stu-id="147cd-123">Conditions</span></span>

<span data-ttu-id="147cd-124">検索条件を追加して、検索範囲を絞り込み、より絞り込みされた結果のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="147cd-124">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="147cd-125">各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="147cd-125">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="147cd-126">条件は **、AND** 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:c* として表される) によって、キーワード ボックスで指定されたキーワード クエリに論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="147cd-126">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="147cd-127">つまり、アイテムはキーワード クエリと検索結果に含める 1 つ以上の条件の両方を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="147cd-127">That means items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="147cd-128">このように、条件を使用して結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="147cd-128">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="147cd-129">検索クエリで使用できる条件の一覧と説明については、「キーワード クエリと検索条件」の「検索条件」 [セクションを参照してください](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="147cd-129">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
