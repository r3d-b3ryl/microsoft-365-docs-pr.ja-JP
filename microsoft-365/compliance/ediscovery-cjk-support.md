---
title: 高度な電子情報開示のための CJK/ダブルバイトのサポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の Advanced eDiscovery が、2バイト文字セットを使用する中国、日本語、および韓国語 (CJK) の言語をサポートする方法について説明します。
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626937"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="ffb1b-103">高度な電子情報開示のための CJK 言語サポート</span><span class="sxs-lookup"><span data-stu-id="ffb1b-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="ffb1b-104">高度な電子情報開示では、2バイト文字セットの言語がサポートされています (これらには、簡体字中国語、繁体字中国語、日本語、韓国語が含まれています)。レビューセットの次の高度なシナリオについては、次 *のように* なります。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="ffb1b-105">[レビューセット内のデータに対してクエリ](review-set-search.md)を実行する場合。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="ffb1b-106">[レビューセット内のドキュメントにタグ付け](tagging-documents.md)するとき。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="ffb1b-107">近い重複検出、電子メールスレッド、およびテーマ分析を使用して、 [レビューセット内のケースデータを分析](analyzing-data-in-review-set.md) する場合。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ffb1b-108">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ffb1b-108">Frequently asked questions</span></span>

<span data-ttu-id="ffb1b-109">**CJK 文字を含むアイテムを収集するために検索を作成するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="ffb1b-110">高度な電子情報開示のコンテンツを検索するときに、 [キーワード検索](building-search-queries.md#keyword-searches)、 [キーワードクエリ、および検索条件](keyword-queries-and-search-conditions.md) に CJK 文字を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="ffb1b-111">主な電子情報開示とコンテンツ検索でコンテンツを検索する場合も、CJK 文字の検索がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="ffb1b-112">すべての [検索演算子](keyword-queries-and-search-conditions.md#search-operators) と [検索条件](keyword-queries-and-search-conditions.md#search-conditions)(ブール演算子 **and**、 **OR**、 **NOT**、 **NEAR**など) に対して、CJK サポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="ffb1b-113">コンテンツの場所またはアイテムに CJK 文字が含まれているが、検索結果が返されない場合は、[クエリ言語-国/地域] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![クエリ言語-コンテンツ検索の国/地域アイコン](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="ffb1b-115">を選択して、検索に対応する言語-国のカルチャコード値を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="ffb1b-116">デフォルトの言語/地域はニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-116">The default language/region is neutral.</span></span>

<span data-ttu-id="ffb1b-117">**一度に複数の言語を検索できますか。**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="ffb1b-118">検索シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="ffb1b-119">高度な電子情報開示の [レビューセットのデータ](review-set-search.md) に対してクエリを実行すると、複数の言語を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="ffb1b-120">データを [収集する](create-search-to-collect-data.md)ための検索を作成するときは、対象とする言語ごとに個別の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="ffb1b-121">たとえば、中国語と韓国語の両方を含むドキュメントを検索する場合は、最初のクエリで中国語を選択し、2番目のクエリに対して [韓国語] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="ffb1b-122">**[クエリ言語-国/地域] アイコンが表示されないので、レビューセット内のクエリの言語を選択できます。レビューセットの検索でクエリ言語を指定するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="ffb1b-123">レビューセットのクエリの場合は、ドキュメントの言語を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="ffb1b-124">コンテンツをレビューセットに追加すると、高度な電子情報開示によってドキュメント言語が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="ffb1b-125">これにより、クエリ結果をレビューセットで最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="ffb1b-126">**検出された言語が [ファイルメタデータ](view-documents-in-review-set.md#file-metadata)に表示されますか。**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="ffb1b-127">いいえ、ファイルメタデータに検出された言語は表示できません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="ffb1b-128">**校閲セットでドキュメントの言語によってフィルター**を適用できますか。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="ffb1b-129">いいえ。校閲セットでドキュメントの言語によるフィルター、並べ替え、または検索を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="ffb1b-130">**この CJK リリースをレビューセットシナリオで既存の検索およびレビューセットに影響を与えるかどうか。**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="ffb1b-131">いいえ。既存の検索と校閲セットは変更されません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="ffb1b-132">既存のデータのインデックスを再作成する必要はありません。また、英語のテキストの検索結果も同じになります。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="ffb1b-133">**表示言語を中国語、日本語、または韓国語に変更するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ffb1b-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="ffb1b-134">表示言語とタイムゾーンを変更する方法については、「 [Office 365 の言語と地域の設定を設定する方法](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="ffb1b-135">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ffb1b-135">Known issues</span></span>

- <span data-ttu-id="ffb1b-136">OCR では、画像ファイルの CJK 文字はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ffb1b-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="ffb1b-137">[注釈ビュー](view-documents-in-review-set.md#annotate-view)での電子メールファイル (\* .eml、\* .msg など) は、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="ffb1b-138">[テキストビュー](view-documents-in-review-set.md#text-view)での検索の検索は、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="ffb1b-139">データの分析に使用される [関連性モジュール](using-relevance.md) は、CJK 言語をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="ffb1b-140">[クエリベースの保持](managing-holds.md#manage-non-custodial-holds) は、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ffb1b-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
