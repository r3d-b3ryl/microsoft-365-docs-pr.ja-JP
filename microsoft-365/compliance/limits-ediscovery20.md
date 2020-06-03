---
title: Advanced eDiscovery の制限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の高度な電子情報開示ソリューションに適用される制限について説明します。 検索ツールを使用してケースデータを収集する場合、大文字と小文字の制限、インデックスの制限、および検索の制限が含まれます。
ms.openlocfilehash: babc05cc5c74f435f0be6fbc8eafd80f09a77b75
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520149"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="4d598-104">Advanced eDiscovery を制限する</span><span class="sxs-lookup"><span data-stu-id="4d598-104">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="4d598-105">この記事では、Microsoft 365 の高度な電子情報開示ソリューションの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d598-105">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="4d598-106">ケースおよびレビュー設定の制限</span><span class="sxs-lookup"><span data-stu-id="4d598-106">Case and review set limits</span></span>

<span data-ttu-id="4d598-107">次の表に、上級電子情報開示のケースおよびレビューセットの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="4d598-107">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="4d598-108">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="4d598-108">**Description of limit**</span></span>|<span data-ttu-id="4d598-109">**制限**</span><span class="sxs-lookup"><span data-stu-id="4d598-109">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d598-110">ケースに追加できるドキュメントの合計数 (ケース内のすべてのレビューセットに対して)。</span><span class="sxs-lookup"><span data-stu-id="4d598-110">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="4d598-111">100 万個</span><span class="sxs-lookup"><span data-stu-id="4d598-111">1 million</span></span>  <br/> |
|<span data-ttu-id="4d598-112">ロードセットあたりのファイルサイズの合計。</span><span class="sxs-lookup"><span data-stu-id="4d598-112">Total file size per load set.</span></span> <span data-ttu-id="4d598-113">これには、Office 以外の365をレビューセットに読み込むことが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d598-113">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="4d598-114">100 GB</span><span class="sxs-lookup"><span data-stu-id="4d598-114">100 GB</span></span>  <br/> |
|<span data-ttu-id="4d598-115">組織内の1日あたりのすべてのレビューセットにロードされたデータの合計量。</span><span class="sxs-lookup"><span data-stu-id="4d598-115">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="4d598-116">2 TB</span><span class="sxs-lookup"><span data-stu-id="4d598-116">2 TB</span></span> <br/> |
|<span data-ttu-id="4d598-117">ケースごとの負荷セットの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-117">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="4d598-118">約</span><span class="sxs-lookup"><span data-stu-id="4d598-118">15</span></span> <br/> |
|<span data-ttu-id="4d598-119">ケースごとのレビューセットの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-119">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="4d598-120">1280</span><span class="sxs-lookup"><span data-stu-id="4d598-120">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="4d598-121">インデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="4d598-121">Indexing limits</span></span>

<span data-ttu-id="4d598-122">次の表に、Advanced 電子情報開示のインデックスの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="4d598-122">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="4d598-123">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="4d598-123">**Description of limit**</span></span>|<span data-ttu-id="4d598-124">**制限**</span><span class="sxs-lookup"><span data-stu-id="4d598-124">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="4d598-125">1つのファイルから抽出する最大文字数。</span><span class="sxs-lookup"><span data-stu-id="4d598-125">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="4d598-126">1000万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-126">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="4d598-127">1つのファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="4d598-127">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="4d598-128">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-128">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="4d598-129">文書内の埋め込みアイテムの最大の深さ。</span><span class="sxs-lookup"><span data-stu-id="4d598-129">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="4d598-130">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-130">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="4d598-131">光学式文字認識 (OCR) によって処理されたファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="4d598-131">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="4d598-132">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-132">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="4d598-133">検索の制限</span><span class="sxs-lookup"><span data-stu-id="4d598-133">Search limits</span></span>

<span data-ttu-id="4d598-134">このセクションで説明する制限は、検索ツールを [**検索] タブ**で使用して、ケースのデータを収集することに関連しています。</span><span class="sxs-lookup"><span data-stu-id="4d598-134">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="4d598-135">詳細については、「 [Advanced 電子情報開示のケースのデータを収集する](collecting-data-for-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d598-135">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="4d598-136">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="4d598-136">**Description of limit**</span></span>|<span data-ttu-id="4d598-137">**制限**</span><span class="sxs-lookup"><span data-stu-id="4d598-137">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d598-138">1回の検索で検索できるメールボックスまたはサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-138">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="4d598-139">無制限</span><span class="sxs-lookup"><span data-stu-id="4d598-139">No limit</span></span>  <br/> |
|<span data-ttu-id="4d598-140">一度に実行できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-140">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="4d598-141">無制限</span><span class="sxs-lookup"><span data-stu-id="4d598-141">No limit</span></span>  <br/> | 
|<span data-ttu-id="4d598-142">一度に1人のユーザーが同時に開始できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-142">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="4d598-143">10  </span><span class="sxs-lookup"><span data-stu-id="4d598-143">10</span></span>  <br/> | 
|<span data-ttu-id="4d598-144">検索クエリの最大文字数 (演算子と条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="4d598-144">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="4d598-145">**メールボックス**: 1万</span><span class="sxs-lookup"><span data-stu-id="4d598-145">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="4d598-146">**サイト**: すべてのサイトを検索する場合は4000、最大20件のサイト<sup>2</sup>を検索する場合は2000</span><span class="sxs-lookup"><span data-stu-id="4d598-146">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="4d598-147">プレフィックスワイルドカードの最小文字数。たとえば、 **1 \* **また**は \* セットを設定**します。</span><span class="sxs-lookup"><span data-stu-id="4d598-147">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="4d598-148">1/3</span><span class="sxs-lookup"><span data-stu-id="4d598-148">3</span></span>  <br/> |  
|<span data-ttu-id="4d598-149">プレフィックスワイルドカードを使用して完全に一致する語句を検索する場合、またはプレフィックスワイルドカードおよび**NEAR**ブール演算子を使用する場合に返される最大のバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="4d598-149">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="4d598-150">1万<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-150">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="4d598-151">検索のプレビューページに表示される、ユーザーごとのメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-151">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="4d598-152">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d598-152">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="4d598-153">100</span><span class="sxs-lookup"><span data-stu-id="4d598-153">100</span></span>  <br/> |
|<span data-ttu-id="4d598-154">検索のプレビューページに表示されるすべてのメールボックスからのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-154">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="4d598-155">1,000</span><span class="sxs-lookup"><span data-stu-id="4d598-155">1,000</span></span>  <br/> |
|<span data-ttu-id="4d598-156">検索結果としてプレビューできるメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-156">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="4d598-157">検索クエリに一致するアイテムを含む1000個を超えるメールボックスがある場合は、最も多くの結果がある上位1000のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d598-157">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="4d598-158">1,000</span><span class="sxs-lookup"><span data-stu-id="4d598-158">1,000</span></span>  <br/> |
|<span data-ttu-id="4d598-159">検索のプレビューページに表示される SharePoint および OneDrive for business サイトのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-159">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="4d598-160">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d598-160">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="4d598-161">200</span><span class="sxs-lookup"><span data-stu-id="4d598-161">200</span></span>  <br/> |
|<span data-ttu-id="4d598-162">検索結果としてプレビューできる SharePoint および OneDrive for Business サイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-162">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="4d598-163">検索クエリと一致するアイテムが含まれる200を超えるサイトがある場合は、最も多くの結果がある上位200サイトのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d598-163">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="4d598-164">200</span><span class="sxs-lookup"><span data-stu-id="4d598-164">200</span></span>  <br/> |
|<span data-ttu-id="4d598-165">検索用にプレビューページに表示されるパブリックフォルダーメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-165">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="4d598-166">100</span><span class="sxs-lookup"><span data-stu-id="4d598-166">100</span></span>  <br/> |
|<span data-ttu-id="4d598-167">検索用にプレビューページに表示されるすべてのパブリックフォルダーメールボックスアイテムに含まれるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-167">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="4d598-168">200</span><span class="sxs-lookup"><span data-stu-id="4d598-168">200</span></span>  <br/> |
|<span data-ttu-id="4d598-169">検索結果としてプレビューできるパブリックフォルダーメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-169">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="4d598-170">検索クエリと一致するアイテムが含まれている500以上のパブリックフォルダーメールボックスがある場合は、最も多くの結果がある上位500のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d598-170">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="4d598-171">500</span><span class="sxs-lookup"><span data-stu-id="4d598-171">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="4d598-172">ビューアーの制限</span><span class="sxs-lookup"><span data-stu-id="4d598-172">Viewer limits</span></span>

|<span data-ttu-id="4d598-173">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="4d598-173">**Description of limit**</span></span>|<span data-ttu-id="4d598-174">**制限**</span><span class="sxs-lookup"><span data-stu-id="4d598-174">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="4d598-175">ネイティブビューアーで表示できる Excel ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="4d598-175">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="4d598-176">4 MB</span><span class="sxs-lookup"><span data-stu-id="4d598-176">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="4d598-177">設定ダウンロードの制限を確認する</span><span class="sxs-lookup"><span data-stu-id="4d598-177">Review set download limits</span></span>

|<span data-ttu-id="4d598-178">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="4d598-178">**Description of limit**</span></span>|<span data-ttu-id="4d598-179">**制限**</span><span class="sxs-lookup"><span data-stu-id="4d598-179">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d598-180">校閲セットからダウンロードされたファイルの合計サイズまたはドキュメントの最大数。</span><span class="sxs-lookup"><span data-stu-id="4d598-180">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="4d598-181">3 MB または50のドキュメント<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4d598-181">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="4d598-182"><sup>1</sup> 1 つのファイル制限を超えるアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d598-182"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="4d598-183"><sup>2</sup> SharePoint および OneDrive for business の場所を検索するとき、検索対象のサイトの url 内の文字数がこの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="4d598-183"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="4d598-184"><sup>3</sup>語句以外のクエリ (二重引用符を使用しないキーワード値) の場合は、特別なプレフィックスインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d598-184"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="4d598-185">これにより、文書内で単語が発生しても、文書内のどこにも存在しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="4d598-185">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="4d598-186">語句のクエリ (二重引用符で囲まれたキーワード値) を処理するには、ドキュメント内の位置を語句内の単語と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d598-186">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="4d598-187">これは、語句のクエリにプレフィックスインデックスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4d598-187">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="4d598-188">この場合は、プレフィックスが展開される可能性のあるすべての単語を含むクエリを内部で展開します。たとえば、 \*\*time \* \*\* **は "time/timer or TIMES/timex or timeboxed or..."** に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4d598-188">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="4d598-189">上限は1万で、クエリに一致するドキュメントの数ではなく、単語が拡張できるバリエーションの最大数です。</span><span class="sxs-lookup"><span data-stu-id="4d598-189">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="4d598-190">語句以外の用語には、上限がありません。</span><span class="sxs-lookup"><span data-stu-id="4d598-190">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="4d598-191"><sup>4</sup>この制限は、校閲セットから選択したドキュメントをダウンロードする場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d598-191"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="4d598-192">校閲セットからドキュメントをエクスポートする場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="4d598-192">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="4d598-193">ドキュメントのダウンロードとエクスポートの詳細については、「 [Advanced eDiscovery でケースデータをエクスポート](exporting-data-ediscover20.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d598-193">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

