---
title: CJK/Double Byte のサポートは、Advanced eDiscovery
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
description: 2 Advanced eDiscovery文字セットMicrosoft 365使用する中国語、日本語、韓国語 (CJK) 言語をサポートする方法について学習します。
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926603"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="7786c-103">CJK 言語サポートのAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7786c-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="7786c-104">Advanced eDiscoveryでは、レビュー セットで次の高度なシナリオに対応する 2 バイト文字セット言語 (簡体字中国語、繁体字中国語、日本語、韓国語を総称して *CJK* 言語と呼ばれる) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7786c-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="7786c-105">レビュー セット [のデータをクエリする場合](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="7786c-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="7786c-106">レビュー セット [内のドキュメントにタグを付けするときに使用します](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="7786c-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="7786c-107">レビュー セット [内のケース データを、](analyzing-data-in-review-set.md) ほぼ重複検出、電子メール スレッド、テーマ分析を使用して分析する場合。</span><span class="sxs-lookup"><span data-stu-id="7786c-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7786c-108">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7786c-108">Frequently asked questions</span></span>

<span data-ttu-id="7786c-109">**CJK 文字を含むアイテムを収集する検索を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="7786c-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="7786c-110">CJK 文字は、キーワード[](building-search-queries.md#keyword-searches)検索、キーワード[](keyword-queries-and-search-conditions.md)クエリ、および検索条件に Advanced eDiscovery使用できます。</span><span class="sxs-lookup"><span data-stu-id="7786c-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="7786c-111">コア電子情報開示とコンテンツ検索でコンテンツを検索する場合は、CJK 文字の検索もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7786c-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="7786c-112">ブール演算子 AND  [](keyword-queries-and-search-conditions.md#search-operators) **、OR、NOT、NEAR** など、すべての検索演算子と検索条件に対して CJK サポートを **提供します**。 [](keyword-queries-and-search-conditions.md#search-conditions)</span><span class="sxs-lookup"><span data-stu-id="7786c-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="7786c-113">コンテンツの場所またはアイテムに CJK 文字が含まれているが、検索で結果が返されない場合は、クエリ言語の国/地域アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7786c-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![コンテンツ検索のクエリ言語 -国/地域アイコン](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="7786c-115">をクリックし、検索に対応する言語と国のカルチャ コードの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="7786c-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="7786c-116">デフォルトの言語/地域はニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="7786c-116">The default language/region is neutral.</span></span>

<span data-ttu-id="7786c-117">**複数の言語を一度に検索できますか?**</span><span class="sxs-lookup"><span data-stu-id="7786c-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="7786c-118">検索シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7786c-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="7786c-119">レビュー セット[内のデータをクエリ](review-set-search.md)するときに、Advanced eDiscovery言語を検索できます。</span><span class="sxs-lookup"><span data-stu-id="7786c-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="7786c-120">データを [収集する検索を作成する場合](create-search-to-collect-data.md)は、ターゲットとする言語ごとに個別の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="7786c-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="7786c-121">たとえば、中国語と韓国語の両方を含むドキュメントを検索する場合は、最初のクエリで [中国語] を選択し、2 番目のクエリに [韓国語] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7786c-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="7786c-122">**レビュー セット内のクエリの言語を選択するクエリ言語と国/地域のアイコンが表示されます。レビュー セット検索でクエリ言語を指定する方法**</span><span class="sxs-lookup"><span data-stu-id="7786c-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="7786c-123">レビュー セットのクエリでは、ドキュメント言語を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7786c-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="7786c-124">Advanced eDiscoveryにコンテンツを追加すると、ドキュメント言語が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="7786c-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="7786c-125">これにより、レビュー セットでクエリ結果を最適化できます。</span><span class="sxs-lookup"><span data-stu-id="7786c-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="7786c-126">**ファイル メタデータで検出された言語を [確認できますか](view-documents-in-review-set.md#file-metadata)?**</span><span class="sxs-lookup"><span data-stu-id="7786c-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="7786c-127">いいえ、ファイル メタデータに検出された言語は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7786c-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="7786c-128">**レビュー セット内のドキュメント言語でフィルター処理できますか**。</span><span class="sxs-lookup"><span data-stu-id="7786c-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="7786c-129">いいえ、レビュー セット内のドキュメント言語でフィルター処理、並べ替え、または検索を行う方法はありません。</span><span class="sxs-lookup"><span data-stu-id="7786c-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="7786c-130">**レビュー セットシナリオ用のこの CJK リリースは、既存の検索セットとレビュー セットに影響しますか?**</span><span class="sxs-lookup"><span data-stu-id="7786c-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="7786c-131">いいえ、既存の検索セットとレビュー セットは変更されません。</span><span class="sxs-lookup"><span data-stu-id="7786c-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="7786c-132">既存のデータのインデックスを再作成する必要はなく、英語のテキストの検索結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="7786c-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="7786c-133">**表示言語を中国語、日本語、韓国語に変更する方法**</span><span class="sxs-lookup"><span data-stu-id="7786c-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="7786c-134">表示言語とタイム ゾーンを変更する方法については、「言語と地域の設定を設定する方法」を参照[Office 365。](/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="7786c-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="7786c-135">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7786c-135">Known issues</span></span>

- <span data-ttu-id="7786c-136">OCR はイメージ ファイルからの CJK 文字をサポートしません</span><span class="sxs-lookup"><span data-stu-id="7786c-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="7786c-137">注釈ビューの電子メール ファイル (*.eml や[](view-documents-in-review-set.md#annotate-view)*.msg など) は、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7786c-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="7786c-138">テキスト ビューでの検索ヒット [の](view-documents-in-review-set.md#text-view) 強調表示は、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7786c-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="7786c-139">データ [の分析に](using-relevance.md) 使用される関連性モジュールは、CJK 言語をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7786c-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="7786c-140">[クエリ ベースの保留は](managing-holds.md#manage-non-custodial-holds) 、CJK 言語ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7786c-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span>