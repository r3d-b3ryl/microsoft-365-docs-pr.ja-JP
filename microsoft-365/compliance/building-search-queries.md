---
title: Advanced eDiscovery で検索クエリを作成する
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
description: Microsoft 365 の Advanced eDiscovery を使用してデータを検索する場合は、キーワードと条件を使用して検索範囲を絞り込む。
ms.openlocfilehash: 8ec1e099625bb081f8a915f08ac818fddcc2b60d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751114"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a><span data-ttu-id="d5154-103">Advanced eDiscovery で検索コレクション クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="d5154-103">Build search collection queries in Advanced eDiscovery</span></span>

<span data-ttu-id="d5154-104">Advanced eDiscovery ケースでデータを収集する検索クエリを作成する場合、キーワードを使用して特定のコンテンツと条件を検索し、検索範囲を絞り込み、法的調査に最も関連するアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="d5154-104">When building search queries to collect data in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![キーワードと条件を使用して検索の結果を絞り込む](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="d5154-106">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="d5154-106">Keyword searches</span></span>

<span data-ttu-id="d5154-107">検索クエリの [キーワード] **ボックス** にキーワード クエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5154-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="d5154-108">キーワード、電子メール メッセージのプロパティ (送信日と受信日など)、またはドキュメントのプロパティ (ファイル名やドキュメントが最後に変更された日付など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="d5154-109">**AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="d5154-110">また、SharePoint と OneDrive のドキュメント (電子メール メッセージではなく) で機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5154-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="d5154-111">この **キーワード** ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。</span><span class="sxs-lookup"><span data-stu-id="d5154-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>

## <a name="keyword-list"></a><span data-ttu-id="d5154-112">キーワード リスト</span><span class="sxs-lookup"><span data-stu-id="d5154-112">Keyword list</span></span>

<span data-ttu-id="d5154-113">または、[キーワード リストを表示する] チェック ボックス **をオンにして** 、各行にキーワードまたはキーワード フレーズを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5154-113">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="d5154-114">各行のキーワードは、作成される検索クエリの **OR** 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:s* として表されます) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="d5154-114">The keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="d5154-115">つまり、任意の行にキーワードを含むアイテムが検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5154-115">This means items that contain any keyword in any row are in the search results.</span></span> <span data-ttu-id="d5154-116">Advanced eDiscovery 検索クエリでは、キーワード リストに最大 180 行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-116">You can add up to 180 rows in the keyword list in Advanced eDiscovery search queries.</span></span>

![キーワード リストを使用してクエリ内の各キーワードの統計情報を取得する](../media/KeywordListSearch.png)

<span data-ttu-id="d5154-118">キーワード リストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="d5154-118">Why use the keyword list?</span></span> <span data-ttu-id="d5154-119">キーワード リスト内の各キーワードに一致するアイテムの数を示す統計情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-119">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="d5154-120">これにより、最も効果的な (かつ最も少ない) キーワードをすばやく識別できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-120">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="d5154-121">キーワード リスト内の行でキーワード フレーズ (かっこで囲む) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5154-121">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="d5154-122">検索統計の詳細については、「検索統計」 [を参照してください](search-statistics-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d5154-122">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="d5154-123">条件</span><span class="sxs-lookup"><span data-stu-id="d5154-123">Conditions</span></span>

<span data-ttu-id="d5154-124">検索条件を追加して検索範囲を絞り込み、より絞り込みされた結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="d5154-124">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="d5154-125">各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5154-125">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="d5154-126">条件は、AND 演算子と同様の機能を持つ論理演算子 (検索クエリ構文では *c:c* として表されます) によって、キーワード ボックスで指定されたキーワード クエリに論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="d5154-126">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="d5154-127">つまり、アイテムはキーワード クエリと検索結果に含まれる 1 つ以上の条件の両方を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5154-127">That means items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="d5154-128">このように、条件を使用して結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d5154-128">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="d5154-129">検索クエリで使用できる条件の一覧と説明については、キーワード クエリと検索条件の「検索条件」セクション [を参照してください](keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="d5154-129">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
