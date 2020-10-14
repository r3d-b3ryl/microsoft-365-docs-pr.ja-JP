---
title: Advanced eDiscovery の制限
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
description: Microsoft 365 の高度な電子情報開示ソリューションに適用される大文字と小文字の制限、インデックスの制限、および検索の制限について説明します。
ms.openlocfilehash: 7d676b568c7e4cddedeff02c62b4645619d53357
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446254"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="d7f1f-103">Advanced eDiscovery を制限する</span><span class="sxs-lookup"><span data-stu-id="d7f1f-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="d7f1f-104">この記事では、Microsoft 365 の高度な電子情報開示ソリューションの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="d7f1f-105">ケースおよびレビュー設定の制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-105">Case and review set limits</span></span>

<span data-ttu-id="d7f1f-106">次の表に、上級電子情報開示のケースおよびレビューセットの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="d7f1f-107">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-107">**Description of limit**</span></span>|<span data-ttu-id="d7f1f-108">**制限**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7f1f-109">ケースに追加できるドキュメントの合計数 (ケース内のすべてのレビューセットに対して)。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="d7f1f-110">300 万</span><span class="sxs-lookup"><span data-stu-id="d7f1f-110">3 million</span></span> <br/> |
|<span data-ttu-id="d7f1f-111">ロードセットあたりのファイルサイズの合計。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-111">Total file size per load set.</span></span> <span data-ttu-id="d7f1f-112">これには、Office 以外の365をレビューセットに読み込むことが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="d7f1f-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="d7f1f-113">300 GB</span></span> <br/> |
|<span data-ttu-id="d7f1f-114">組織内の1日あたりのすべてのレビューセットにロードされたデータの合計量。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="d7f1f-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="d7f1f-115">2 TB</span></span> <br/> |
|<span data-ttu-id="d7f1f-116">ケースごとの負荷セットの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="d7f1f-117">200</span><span class="sxs-lookup"><span data-stu-id="d7f1f-117">200</span></span> <br/> |
|<span data-ttu-id="d7f1f-118">ケースごとのレビューセットの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="d7f1f-119">1280</span><span class="sxs-lookup"><span data-stu-id="d7f1f-119">20</span></span> <br/> |
|<span data-ttu-id="d7f1f-120">ケースごとのタググループの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="d7f1f-121">1000</span><span class="sxs-lookup"><span data-stu-id="d7f1f-121">1000</span></span> <br/> |
|<span data-ttu-id="d7f1f-122">ケースごとのタグの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="d7f1f-123">1000</span><span class="sxs-lookup"><span data-stu-id="d7f1f-123">1000</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="d7f1f-124">インデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-124">Indexing limits</span></span>

<span data-ttu-id="d7f1f-125">次の表に、Advanced 電子情報開示のインデックスの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-125">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="d7f1f-126">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-126">**Description of limit**</span></span>|<span data-ttu-id="d7f1f-127">**制限**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-127">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="d7f1f-128">1つのファイルから抽出する最大文字数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-128">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="d7f1f-129">1000万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-129">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="d7f1f-130">1つのファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-130">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="d7f1f-131">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-131">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="d7f1f-132">文書内の埋め込みアイテムの最大の深さ。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-132">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="d7f1f-133">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-133">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="d7f1f-134">光学式文字認識 (OCR) によって処理されたファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-134">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="d7f1f-135">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-135">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="d7f1f-136">検索の制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-136">Search limits</span></span>

<span data-ttu-id="d7f1f-137">このセクションで説明する制限は、検索ツールを [ **検索] タブ** で使用して、ケースのデータを収集することに関連しています。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-137">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="d7f1f-138">詳細については、「 [Advanced 電子情報開示のケースのデータを収集する](collecting-data-for-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-138">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="d7f1f-139">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-139">**Description of limit**</span></span>|<span data-ttu-id="d7f1f-140">**制限**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-140">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7f1f-141">1回の検索で検索できるメールボックスまたはサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-141">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="d7f1f-142">無制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-142">No limit</span></span>  <br/> |
|<span data-ttu-id="d7f1f-143">一度に実行できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-143">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="d7f1f-144">無制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-144">No limit</span></span>  <br/> | 
|<span data-ttu-id="d7f1f-145">一度に1人のユーザーが同時に開始できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-145">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="d7f1f-146">10  </span><span class="sxs-lookup"><span data-stu-id="d7f1f-146">10</span></span>  <br/> | 
|<span data-ttu-id="d7f1f-147">検索クエリの最大文字数 (演算子と条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-147">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="d7f1f-148">**メールボックス**: 1万</span><span class="sxs-lookup"><span data-stu-id="d7f1f-148">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="d7f1f-149">**サイト**: すべてのサイトを検索する場合は4000、最大20件のサイト<sup>2</sup>を検索する場合は2000</span><span class="sxs-lookup"><span data-stu-id="d7f1f-149">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="d7f1f-150">プレフィックスワイルドカードの最小文字数。たとえば、 **1 \* **また**は \* セットを設定**します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-150">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="d7f1f-151">1/3</span><span class="sxs-lookup"><span data-stu-id="d7f1f-151">3</span></span>  <br/> |  
|<span data-ttu-id="d7f1f-152">プレフィックスワイルドカードを使用して完全に一致する語句を検索する場合、またはプレフィックスワイルドカードおよび **NEAR** ブール演算子を使用する場合に返される最大のバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-152">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="d7f1f-153">1万 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-153">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="d7f1f-154">検索のプレビューページに表示される、ユーザーごとのメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-154">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="d7f1f-155">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-155">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="d7f1f-156">100</span><span class="sxs-lookup"><span data-stu-id="d7f1f-156">100</span></span>  <br/> |
|<span data-ttu-id="d7f1f-157">検索のプレビューページに表示されるすべてのメールボックスからのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-157">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="d7f1f-158">1,000</span><span class="sxs-lookup"><span data-stu-id="d7f1f-158">1,000</span></span>  <br/> |
|<span data-ttu-id="d7f1f-159">検索結果としてプレビューできるメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-159">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="d7f1f-160">検索クエリに一致するアイテムを含む1000個を超えるメールボックスがある場合は、最も多くの結果がある上位1000のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-160">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="d7f1f-161">1,000</span><span class="sxs-lookup"><span data-stu-id="d7f1f-161">1,000</span></span>  <br/> |
|<span data-ttu-id="d7f1f-162">検索のプレビューページに表示される SharePoint および OneDrive for business サイトのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-162">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="d7f1f-163">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-163">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="d7f1f-164">200</span><span class="sxs-lookup"><span data-stu-id="d7f1f-164">200</span></span>  <br/> |
|<span data-ttu-id="d7f1f-165">検索結果としてプレビューできる SharePoint および OneDrive for Business サイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-165">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="d7f1f-166">検索クエリと一致するアイテムが含まれる200を超えるサイトがある場合は、最も多くの結果がある上位200サイトのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-166">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="d7f1f-167">200</span><span class="sxs-lookup"><span data-stu-id="d7f1f-167">200</span></span>  <br/> |
|<span data-ttu-id="d7f1f-168">検索用にプレビューページに表示されるパブリックフォルダーメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-168">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="d7f1f-169">100</span><span class="sxs-lookup"><span data-stu-id="d7f1f-169">100</span></span>  <br/> |
|<span data-ttu-id="d7f1f-170">検索用にプレビューページに表示されるすべてのパブリックフォルダーメールボックスアイテムに含まれるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-170">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="d7f1f-171">200</span><span class="sxs-lookup"><span data-stu-id="d7f1f-171">200</span></span>  <br/> |
|<span data-ttu-id="d7f1f-172">検索結果としてプレビューできるパブリックフォルダーメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-172">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="d7f1f-173">検索クエリと一致するアイテムが含まれている500以上のパブリックフォルダーメールボックスがある場合は、最も多くの結果がある上位500のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-173">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="d7f1f-174">500</span><span class="sxs-lookup"><span data-stu-id="d7f1f-174">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="d7f1f-175">ビューアーの制限</span><span class="sxs-lookup"><span data-stu-id="d7f1f-175">Viewer limits</span></span>

|<span data-ttu-id="d7f1f-176">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-176">**Description of limit**</span></span>|<span data-ttu-id="d7f1f-177">**制限**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-177">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="d7f1f-178">ネイティブビューアーで表示できる Excel ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-178">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="d7f1f-179">4 MB</span><span class="sxs-lookup"><span data-stu-id="d7f1f-179">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="d7f1f-180">設定ダウンロードの制限を確認する</span><span class="sxs-lookup"><span data-stu-id="d7f1f-180">Review set download limits</span></span>

|<span data-ttu-id="d7f1f-181">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-181">**Description of limit**</span></span>|<span data-ttu-id="d7f1f-182">**制限**</span><span class="sxs-lookup"><span data-stu-id="d7f1f-182">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7f1f-183">校閲セットからダウンロードされたファイルの合計サイズまたはドキュメントの最大数。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-183">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="d7f1f-184">3 MB または50のドキュメント <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d7f1f-184">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="d7f1f-185"><sup>1</sup> 1 つのファイル制限を超えるアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-185"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="d7f1f-186"><sup>2</sup> SharePoint および OneDrive for business の場所を検索するとき、検索対象のサイトの url 内の文字数がこの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-186"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="d7f1f-187"><sup>3</sup> 語句以外のクエリ (二重引用符を使用しないキーワード値) の場合は、特別なプレフィックスインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-187"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="d7f1f-188">これにより、文書内で単語が発生しても、文書内のどこにも存在しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-188">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="d7f1f-189">語句のクエリ (二重引用符で囲まれたキーワード値) を処理するには、ドキュメント内の位置を語句内の単語と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-189">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="d7f1f-190">これは、語句のクエリにプレフィックスインデックスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-190">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="d7f1f-191">この場合は、プレフィックスが展開される可能性のあるすべての単語を含むクエリを内部で展開します。たとえば、 \*\*time \* \*\* **は "time/timer or TIMES/timex or timeboxed or..."** に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-191">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="d7f1f-192">上限は1万で、クエリに一致するドキュメントの数ではなく、単語が拡張できるバリエーションの最大数です。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-192">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="d7f1f-193">語句以外の用語には、上限がありません。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-193">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="d7f1f-194"><sup>4</sup> この制限は、校閲セットから選択したドキュメントをダウンロードする場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-194"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="d7f1f-195">校閲セットからドキュメントをエクスポートする場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-195">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="d7f1f-196">ドキュメントのダウンロードとエクスポートの詳細については、「 [Advanced eDiscovery でケースデータをエクスポート](exporting-data-ediscover20.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7f1f-196">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

