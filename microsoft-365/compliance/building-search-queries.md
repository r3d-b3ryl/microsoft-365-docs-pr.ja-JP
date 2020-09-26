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
description: Microsoft 365 で Advanced eDiscovery を使用してデータを検索するときに、検索範囲を絞るためにキーワードと条件を使用します。
ms.openlocfilehash: 3ddd9c38f16fc2dd0fcb96e5fffc79ebbacdbda4
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285803"
---
# <a name="build-search-collection-queries-in-advanced-ediscovery"></a><span data-ttu-id="bcabd-103">高度な電子情報開示での検索コレクションクエリの作成</span><span class="sxs-lookup"><span data-stu-id="bcabd-103">Build search collection queries in Advanced eDiscovery</span></span>

<span data-ttu-id="bcabd-104">高度な電子情報開示ケースでデータを収集するための検索クエリを作成する場合、キーワードを使用して特定のコンテンツと条件を見つけ、法的調査に最も関連のあるアイテムを返すために検索の範囲を絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-104">When building search queries to collect data in an Advanced eDiscovery case, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your legal investigation.</span></span>

![キーワードと条件を使用して検索結果を絞り込む](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="bcabd-106">キーワード検索</span><span class="sxs-lookup"><span data-stu-id="bcabd-106">Keyword searches</span></span>

<span data-ttu-id="bcabd-107">検索クエリの [ **キーワード** ] ボックスにキーワードクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="bcabd-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="bcabd-108">キーワード、電子メールメッセージのプロパティ ([送信日時] や [受信日時] など)、またはドキュメントのプロパティ (ファイル名、ドキュメントが最後に変更された日付など) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="bcabd-109">**AND**、**OR**、**NOT**、**NEAR** などのブール演算子を使用するより複雑なクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="bcabd-110">SharePoint および OneDrive (電子メールメッセージではない) のドキュメントで機密情報 (社会保障番号など) を検索したり、外部で共有されているドキュメントを検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="bcabd-111">この**キーワード** ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に入ります。</span><span class="sxs-lookup"><span data-stu-id="bcabd-111">If you leave the **Keywords** box empty, all content located in the specified content locations is in the search results.</span></span>
    
<span data-ttu-id="bcabd-112">または、[ **キーワードリストを表示** する] チェックボックスをオンにして、各行にキーワードまたはキーワードフレーズを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-112">Alternatively, you can select the **Show keyword list** check box and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="bcabd-113">このようにすると、各行のキーワードは、作成された検索クエリの**or**演算子の機能と類似した論理演算子 (検索クエリ構文では*c:s*で表されます) によって接続されます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-113">If you do this, the keywords in each row are connected by a logical operator (which is represented as *c:s* in the search query syntax) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="bcabd-114">これは、任意の行にキーワードを含むアイテムが検索結果に含まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bcabd-114">This means items that contain any keyword in any row are in the search results.</span></span>

![キーワードリストを使用して、クエリ内の各キーワードの統計情報を取得する](../media/KeywordListSearch.png)

<span data-ttu-id="bcabd-116">キーワードリストを使用する理由</span><span class="sxs-lookup"><span data-stu-id="bcabd-116">Why use the keyword list?</span></span> <span data-ttu-id="bcabd-117">キーワードリストの各キーワードに一致するアイテムの数を示す統計情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="bcabd-118">これは、最も頻繁に使用される (および最も少ない) キーワードをすばやく識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="bcabd-119">キーワードリストの行にキーワードフレーズ (かっこで囲む) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="bcabd-120">検索統計の詳細については、「 [検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcabd-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bcabd-121">大きなキーワードリストによって発生する問題を減らすために、キーワード一覧では最大20行に制限されています。</span><span class="sxs-lookup"><span data-stu-id="bcabd-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="bcabd-122">条件</span><span class="sxs-lookup"><span data-stu-id="bcabd-122">Conditions</span></span>
    
<span data-ttu-id="bcabd-123">検索条件を追加して検索の範囲を絞り込んだり、より洗練された結果セットを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="bcabd-124">各条件によって、作成された検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="bcabd-125">条件は、論理演算子 (検索クエリ構文で *c:c* として表されます) で指定されたキーワードクエリに論理的に接続されています。これは、 **and 演算子と** 機能が似ています。</span><span class="sxs-lookup"><span data-stu-id="bcabd-125">A condition is logically connected to the keyword query specified in the keyword box by a logical operator (which is represented as *c:c* in the search query syntax) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="bcabd-126">つまり、アイテムは、キーワードクエリと、検索結果に含まれる1つまたは複数の条件を満たす必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bcabd-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="bcabd-127">このように、条件を使用して結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bcabd-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="bcabd-128">検索クエリで使用できる条件の一覧と説明については、「 [キーワードクエリと検索条件](keyword-queries-and-search-conditions.md#search-conditions)」の「検索条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcabd-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
