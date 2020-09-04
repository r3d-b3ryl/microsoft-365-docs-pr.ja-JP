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
ms.openlocfilehash: c139480f18e0e6d94aae5a38d5fd636fbc62b2dc
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358475"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="3bfce-103">Advanced eDiscovery を制限する</span><span class="sxs-lookup"><span data-stu-id="3bfce-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="3bfce-104">この記事では、Microsoft 365 の高度な電子情報開示ソリューションの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="3bfce-105">ケースおよびレビュー設定の制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-105">Case and review set limits</span></span>

<span data-ttu-id="3bfce-106">次の表に、上級電子情報開示のケースおよびレビューセットの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="3bfce-107">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3bfce-107">**Description of limit**</span></span>|<span data-ttu-id="3bfce-108">**制限**</span><span class="sxs-lookup"><span data-stu-id="3bfce-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3bfce-109">ケースに追加できるドキュメントの合計数 (ケース内のすべてのレビューセットに対して)。</span><span class="sxs-lookup"><span data-stu-id="3bfce-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="3bfce-110">300 万</span><span class="sxs-lookup"><span data-stu-id="3bfce-110">3 million</span></span> <br/> |
|<span data-ttu-id="3bfce-111">ロードセットあたりのファイルサイズの合計。</span><span class="sxs-lookup"><span data-stu-id="3bfce-111">Total file size per load set.</span></span> <span data-ttu-id="3bfce-112">これには、Office 以外の365をレビューセットに読み込むことが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="3bfce-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="3bfce-113">300 GB</span></span> <br/> |
|<span data-ttu-id="3bfce-114">組織内の1日あたりのすべてのレビューセットにロードされたデータの合計量。</span><span class="sxs-lookup"><span data-stu-id="3bfce-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="3bfce-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="3bfce-115">2 TB</span></span> <br/> |
|<span data-ttu-id="3bfce-116">ケースごとの負荷セットの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="3bfce-117">200</span><span class="sxs-lookup"><span data-stu-id="3bfce-117">200</span></span> <br/> |
|<span data-ttu-id="3bfce-118">ケースごとのレビューセットの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="3bfce-119">1280</span><span class="sxs-lookup"><span data-stu-id="3bfce-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="3bfce-120">インデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-120">Indexing limits</span></span>

<span data-ttu-id="3bfce-121">次の表に、Advanced 電子情報開示のインデックスの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="3bfce-122">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3bfce-122">**Description of limit**</span></span>|<span data-ttu-id="3bfce-123">**制限**</span><span class="sxs-lookup"><span data-stu-id="3bfce-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="3bfce-124">1つのファイルから抽出する最大文字数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="3bfce-125">1000万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="3bfce-126">1つのファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3bfce-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="3bfce-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="3bfce-128">文書内の埋め込みアイテムの最大の深さ。</span><span class="sxs-lookup"><span data-stu-id="3bfce-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="3bfce-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="3bfce-130">光学式文字認識 (OCR) によって処理されたファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3bfce-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="3bfce-131">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="3bfce-132">検索の制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-132">Search limits</span></span>

<span data-ttu-id="3bfce-133">このセクションで説明する制限は、検索ツールを [ **検索] タブ** で使用して、ケースのデータを収集することに関連しています。</span><span class="sxs-lookup"><span data-stu-id="3bfce-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="3bfce-134">詳細については、「 [Advanced 電子情報開示のケースのデータを収集する](collecting-data-for-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfce-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="3bfce-135">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3bfce-135">**Description of limit**</span></span>|<span data-ttu-id="3bfce-136">**制限**</span><span class="sxs-lookup"><span data-stu-id="3bfce-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3bfce-137">1回の検索で検索できるメールボックスまたはサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="3bfce-138">無制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-138">No limit</span></span>  <br/> |
|<span data-ttu-id="3bfce-139">一度に実行できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="3bfce-140">無制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="3bfce-141">一度に1人のユーザーが同時に開始できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="3bfce-142">10  </span><span class="sxs-lookup"><span data-stu-id="3bfce-142">10</span></span>  <br/> | 
|<span data-ttu-id="3bfce-143">検索クエリの最大文字数 (演算子と条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="3bfce-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="3bfce-144">**メールボックス**: 1万</span><span class="sxs-lookup"><span data-stu-id="3bfce-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="3bfce-145">**サイト**: すべてのサイトを検索する場合は4000、最大20件のサイト<sup>2</sup>を検索する場合は2000</span><span class="sxs-lookup"><span data-stu-id="3bfce-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="3bfce-146">プレフィックスワイルドカードの最小文字数。たとえば、 **1 \* **また**は \* セットを設定**します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="3bfce-147">3 </span><span class="sxs-lookup"><span data-stu-id="3bfce-147">3</span></span>  <br/> |  
|<span data-ttu-id="3bfce-148">プレフィックスワイルドカードを使用して完全に一致する語句を検索する場合、またはプレフィックスワイルドカードおよび **NEAR** ブール演算子を使用する場合に返される最大のバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="3bfce-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="3bfce-149">1万 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="3bfce-150">検索のプレビューページに表示される、ユーザーごとのメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="3bfce-151">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="3bfce-152">100</span><span class="sxs-lookup"><span data-stu-id="3bfce-152">100</span></span>  <br/> |
|<span data-ttu-id="3bfce-153">検索のプレビューページに表示されるすべてのメールボックスからのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="3bfce-154">1,000</span><span class="sxs-lookup"><span data-stu-id="3bfce-154">1,000</span></span>  <br/> |
|<span data-ttu-id="3bfce-155">検索結果としてプレビューできるメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="3bfce-156">検索クエリに一致するアイテムを含む1000個を超えるメールボックスがある場合は、最も多くの結果がある上位1000のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="3bfce-157">1,000</span><span class="sxs-lookup"><span data-stu-id="3bfce-157">1,000</span></span>  <br/> |
|<span data-ttu-id="3bfce-158">検索のプレビューページに表示される SharePoint および OneDrive for business サイトのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="3bfce-159">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="3bfce-160">200</span><span class="sxs-lookup"><span data-stu-id="3bfce-160">200</span></span>  <br/> |
|<span data-ttu-id="3bfce-161">検索結果としてプレビューできる SharePoint および OneDrive for Business サイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="3bfce-162">検索クエリと一致するアイテムが含まれる200を超えるサイトがある場合は、最も多くの結果がある上位200サイトのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="3bfce-163">200</span><span class="sxs-lookup"><span data-stu-id="3bfce-163">200</span></span>  <br/> |
|<span data-ttu-id="3bfce-164">検索用にプレビューページに表示されるパブリックフォルダーメールボックスあたりのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="3bfce-165">100</span><span class="sxs-lookup"><span data-stu-id="3bfce-165">100</span></span>  <br/> |
|<span data-ttu-id="3bfce-166">検索用にプレビューページに表示されるすべてのパブリックフォルダーメールボックスアイテムに含まれるアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="3bfce-167">200</span><span class="sxs-lookup"><span data-stu-id="3bfce-167">200</span></span>  <br/> |
|<span data-ttu-id="3bfce-168">検索結果としてプレビューできるパブリックフォルダーメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="3bfce-169">検索クエリと一致するアイテムが含まれている500以上のパブリックフォルダーメールボックスがある場合は、最も多くの結果がある上位500のメールボックスのみがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="3bfce-170">500</span><span class="sxs-lookup"><span data-stu-id="3bfce-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="3bfce-171">ビューアーの制限</span><span class="sxs-lookup"><span data-stu-id="3bfce-171">Viewer limits</span></span>

|<span data-ttu-id="3bfce-172">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3bfce-172">**Description of limit**</span></span>|<span data-ttu-id="3bfce-173">**制限**</span><span class="sxs-lookup"><span data-stu-id="3bfce-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="3bfce-174">ネイティブビューアーで表示できる Excel ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3bfce-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="3bfce-175">4 MB</span><span class="sxs-lookup"><span data-stu-id="3bfce-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="3bfce-176">設定ダウンロードの制限を確認する</span><span class="sxs-lookup"><span data-stu-id="3bfce-176">Review set download limits</span></span>

|<span data-ttu-id="3bfce-177">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="3bfce-177">**Description of limit**</span></span>|<span data-ttu-id="3bfce-178">**制限**</span><span class="sxs-lookup"><span data-stu-id="3bfce-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3bfce-179">校閲セットからダウンロードされたファイルの合計サイズまたはドキュメントの最大数。</span><span class="sxs-lookup"><span data-stu-id="3bfce-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="3bfce-180">3 MB または50のドキュメント <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="3bfce-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="3bfce-181"><sup>1</sup> 1 つのファイル制限を超えるアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="3bfce-182"><sup>2</sup> SharePoint および OneDrive for business の場所を検索するとき、検索対象のサイトの url 内の文字数がこの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="3bfce-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="3bfce-183"><sup>3</sup> 語句以外のクエリ (二重引用符を使用しないキーワード値) の場合は、特別なプレフィックスインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="3bfce-184">これにより、文書内で単語が発生しても、文書内のどこにも存在しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="3bfce-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="3bfce-185">語句のクエリ (二重引用符で囲まれたキーワード値) を処理するには、ドキュメント内の位置を語句内の単語と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bfce-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="3bfce-186">これは、語句のクエリにプレフィックスインデックスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3bfce-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="3bfce-187">この場合は、プレフィックスが展開される可能性のあるすべての単語を含むクエリを内部で展開します。たとえば、 \*\*time \* \*\* **は "time/timer or TIMES/timex or timeboxed or..."** に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="3bfce-188">上限は1万で、クエリに一致するドキュメントの数ではなく、単語が拡張できるバリエーションの最大数です。</span><span class="sxs-lookup"><span data-stu-id="3bfce-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="3bfce-189">語句以外の用語には、上限がありません。</span><span class="sxs-lookup"><span data-stu-id="3bfce-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="3bfce-190"><sup>4</sup> この制限は、校閲セットから選択したドキュメントをダウンロードする場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3bfce-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="3bfce-191">校閲セットからドキュメントをエクスポートする場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="3bfce-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="3bfce-192">ドキュメントのダウンロードとエクスポートの詳細については、「 [Advanced eDiscovery でケースデータをエクスポート](exporting-data-ediscover20.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfce-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

