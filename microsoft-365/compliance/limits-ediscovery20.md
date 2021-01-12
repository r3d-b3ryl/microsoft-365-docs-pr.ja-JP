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
description: Microsoft 365 の Advanced eDiscovery ソリューションに対して有効なケースの制限、インデックス作成の制限、および検索の制限について説明します。
ms.openlocfilehash: 051c1ce916fcb59ade19120bc25496101d501138
ms.sourcegitcommit: f40378013757d560d5566a11ad4e6f527c018cc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49796175"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="0b28c-103">Advanced eDiscovery を制限する</span><span class="sxs-lookup"><span data-stu-id="0b28c-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="0b28c-104">この記事では、Microsoft 365 の Advanced eDiscovery ソリューションの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b28c-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="0b28c-105">ケースとレビュー セットの制限</span><span class="sxs-lookup"><span data-stu-id="0b28c-105">Case and review set limits</span></span>

<span data-ttu-id="0b28c-106">次の表に、Advanced eDiscovery のケースとレビュー セットの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="0b28c-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="0b28c-107">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-107">**Description of limit**</span></span>|<span data-ttu-id="0b28c-108">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b28c-109">ケースに追加できるドキュメントの総数 (ケース内のすべてのレビュー セットに対して)。</span><span class="sxs-lookup"><span data-stu-id="0b28c-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="0b28c-110">300 万</span><span class="sxs-lookup"><span data-stu-id="0b28c-110">3 million</span></span> <br/> |
|<span data-ttu-id="0b28c-111">読み込みセットごとの合計ファイル サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-111">Total file size per load set.</span></span> <span data-ttu-id="0b28c-112">これには、レビュー セットへの Office 365 以外の読み込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="0b28c-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="0b28c-113">300 GB</span></span> <br/> |
|<span data-ttu-id="0b28c-114">組織内のすべてのレビュー セットに読み込まれる 1 日あたりのデータの合計量。</span><span class="sxs-lookup"><span data-stu-id="0b28c-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="0b28c-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="0b28c-115">2 TB</span></span> <br/> |
|<span data-ttu-id="0b28c-116">1 ケースあたりの読み込みセットの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="0b28c-117">200</span><span class="sxs-lookup"><span data-stu-id="0b28c-117">200</span></span> <br/> |
|<span data-ttu-id="0b28c-118">1 ケースあたりのレビュー セットの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="0b28c-119">20</span><span class="sxs-lookup"><span data-stu-id="0b28c-119">20</span></span> <br/> |
|<span data-ttu-id="0b28c-120">1 ケースあたりのタグ グループの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="0b28c-121">1000</span><span class="sxs-lookup"><span data-stu-id="0b28c-121">1000</span></span> <br/> |
|<span data-ttu-id="0b28c-122">1 ケースあたりのタグの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="0b28c-123">1000</span><span class="sxs-lookup"><span data-stu-id="0b28c-123">1000</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="0b28c-124">インデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="0b28c-124">Indexing limits</span></span>

<span data-ttu-id="0b28c-125">次の表に、Advanced eDiscovery のインデックス作成の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="0b28c-125">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="0b28c-126">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-126">**Description of limit**</span></span>|<span data-ttu-id="0b28c-127">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-127">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="0b28c-128">1 つのファイルから抽出された最大文字数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-128">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="0b28c-129">1,000 万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-129">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="0b28c-130">1 つのファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-130">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="0b28c-131">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-131">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="0b28c-132">文書内の埋め込みアイテムの最大深度。</span><span class="sxs-lookup"><span data-stu-id="0b28c-132">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="0b28c-133">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-133">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="0b28c-134">光学式文字認識 (OCR) によって処理されるファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-134">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="0b28c-135">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-135">24 MB<sup>1</sup></span></span> <br/> 
  |<span data-ttu-id="0b28c-136">1 日あたりの組織ごとのインデックス作成ジョブの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-136">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="0b28c-137">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-137">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="0b28c-138">検索の制限</span><span class="sxs-lookup"><span data-stu-id="0b28c-138">Search limits</span></span>

<span data-ttu-id="0b28c-139">このセクションで説明する制限は、[検索] タブの検索ツールを使用してケースのデータを収集する方法に関連しています。</span><span class="sxs-lookup"><span data-stu-id="0b28c-139">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="0b28c-140">詳細については [、「Advanced eDiscovery でケースのデータを収集する」を参照してください](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0b28c-140">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="0b28c-141">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-141">**Description of limit**</span></span>|<span data-ttu-id="0b28c-142">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-142">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b28c-143">1 つの検索で検索できるメールボックスまたはサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-143">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="0b28c-144">制限なし</span><span class="sxs-lookup"><span data-stu-id="0b28c-144">No limit</span></span>  <br/> |
|<span data-ttu-id="0b28c-145">同時に実行できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-145">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="0b28c-146">制限なし</span><span class="sxs-lookup"><span data-stu-id="0b28c-146">No limit</span></span>  <br/> | 
|<span data-ttu-id="0b28c-147">1 人のユーザーが同時に開始できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-147">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="0b28c-148">10 </span><span class="sxs-lookup"><span data-stu-id="0b28c-148">10</span></span>  <br/> | 
|<span data-ttu-id="0b28c-149">検索クエリの最大文字数 (演算子と条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="0b28c-149">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="0b28c-150">**メールボックス**: 10,000</span><span class="sxs-lookup"><span data-stu-id="0b28c-150">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="0b28c-151">**サイト**: すべてのサイトを検索する場合は 4,000、最大 20 サイトを検索する場合は 2,000 <sup></sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-151">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="0b28c-152">プレフィックス ワイルドカードのアルファ文字の最小数。たとえば、 **\* 1* _ または _*set . \*\*_</span><span class="sxs-lookup"><span data-stu-id="0b28c-152">Minimum number of alpha characters for prefix wildcards; for example **one\** _ or _*set\*\*_.</span></span> <br/> |<span data-ttu-id="0b28c-153">3 </span><span class="sxs-lookup"><span data-stu-id="0b28c-153">3</span></span>  <br/> |  
|<span data-ttu-id="0b28c-154">完全一致する語句を検索するためにプレフィックス ワイルドカードを使用する場合、またはプレフィックス ワイルドカードと _ *NEAR*\* ブール演算子を使用する場合に返される最大バリアント。</span><span class="sxs-lookup"><span data-stu-id="0b28c-154">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the _ *NEAR*\* Boolean operator.</span></span>  <br/> |<span data-ttu-id="0b28c-155">10,000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-155">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="0b28c-156">検索のプレビュー ページに表示されるユーザーごとのメールボックスごとのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-156">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="0b28c-157">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-157">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="0b28c-158">100</span><span class="sxs-lookup"><span data-stu-id="0b28c-158">100</span></span>  <br/> |
|<span data-ttu-id="0b28c-159">検索のプレビュー ページに表示される、すべてのメールボックスからのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-159">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="0b28c-160">1,000</span><span class="sxs-lookup"><span data-stu-id="0b28c-160">1,000</span></span>  <br/> |
|<span data-ttu-id="0b28c-161">検索結果をプレビューできるメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-161">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="0b28c-162">検索クエリに一致するアイテムを含むメールボックスが 1000 を超える場合、最も多くの結果を持つ上位 1,000 のメールボックスのみをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-162">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="0b28c-163">1,000</span><span class="sxs-lookup"><span data-stu-id="0b28c-163">1,000</span></span>  <br/> |
|<span data-ttu-id="0b28c-164">検索のプレビュー ページに表示される SharePoint サイトと OneDrive for Business サイトのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-164">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="0b28c-165">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-165">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="0b28c-166">200</span><span class="sxs-lookup"><span data-stu-id="0b28c-166">200</span></span>  <br/> |
|<span data-ttu-id="0b28c-167">検索結果をプレビューできる SharePoint サイトと OneDrive for Business サイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-167">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="0b28c-168">検索クエリに一致するアイテムを含むサイトが 200 を超える場合、最も多くの結果を持つ上位 200 のサイトのみをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-168">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="0b28c-169">200</span><span class="sxs-lookup"><span data-stu-id="0b28c-169">200</span></span>  <br/> |
|<span data-ttu-id="0b28c-170">検索のプレビュー ページに表示されるパブリック フォルダー メールボックスごとのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-170">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="0b28c-171">100</span><span class="sxs-lookup"><span data-stu-id="0b28c-171">100</span></span>  <br/> |
|<span data-ttu-id="0b28c-172">検索のプレビュー ページに表示される、すべてのパブリック フォルダー メールボックス アイテムで見つかったアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-172">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="0b28c-173">200</span><span class="sxs-lookup"><span data-stu-id="0b28c-173">200</span></span>  <br/> |
|<span data-ttu-id="0b28c-174">検索結果をプレビューできるパブリック フォルダー メールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-174">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="0b28c-175">検索クエリに一致するアイテムを含むパブリック フォルダー メールボックスが 500 を超える場合、最も多くの結果を持つ上位 500 のメールボックスのみをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-175">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="0b28c-176">500</span><span class="sxs-lookup"><span data-stu-id="0b28c-176">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="0b28c-177">ビューアーの制限</span><span class="sxs-lookup"><span data-stu-id="0b28c-177">Viewer limits</span></span>

|<span data-ttu-id="0b28c-178">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-178">**Description of limit**</span></span>|<span data-ttu-id="0b28c-179">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-179">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b28c-180">ネイティブ ビューアーで表示できる Excel ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-180">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="0b28c-181">4 MB</span><span class="sxs-lookup"><span data-stu-id="0b28c-181">4 MB</span></span>  <br/> |
|||

## <a name="export-limits"></a><span data-ttu-id="0b28c-182">エクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="0b28c-182">Export limits</span></span>

|<span data-ttu-id="0b28c-183">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-183">**Description of limit**</span></span>|<span data-ttu-id="0b28c-184">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-184">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b28c-185">1 つのエクスポートの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-185">Maximum size of a single export.</span></span>|<span data-ttu-id="0b28c-186">300 万ドキュメントまたは 100 GB の方が小さい</span><span class="sxs-lookup"><span data-stu-id="0b28c-186">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="0b28c-187">1 日の最大データ量。</span><span class="sxs-lookup"><span data-stu-id="0b28c-187">Maximum amount of data in a single day.</span></span> | <span data-ttu-id="0b28c-188">2 TB</span><span class="sxs-lookup"><span data-stu-id="0b28c-188">2 TB</span></span> |
|<span data-ttu-id="0b28c-189">組織内の最大同時エクスポート数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-189">Maximum concurrent exports in your organization.</span></span> | <span data-ttu-id="0b28c-190">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-190">10 <sup>4</sup></span></span> |
|<span data-ttu-id="0b28c-191">ユーザーあたりの最大同時エクスポート数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-191">Maximum concurrent exports per user.</span></span> | <span data-ttu-id="0b28c-192">3 </span><span class="sxs-lookup"><span data-stu-id="0b28c-192">3</span></span> |
|<span data-ttu-id="0b28c-193">1 つの PST ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="0b28c-193">Maximum size of a single PST file.</span></span> | <span data-ttu-id="0b28c-194">10 GB</span><span class="sxs-lookup"><span data-stu-id="0b28c-194">10 GB</span></span> |
|<span data-ttu-id="0b28c-195">レビュー セットあたりの最大同時エクスポート数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-195">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="0b28c-196">1 </span><span class="sxs-lookup"><span data-stu-id="0b28c-196">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="0b28c-197">一連のダウンロード制限を確認する</span><span class="sxs-lookup"><span data-stu-id="0b28c-197">Review set download limits</span></span>

|<span data-ttu-id="0b28c-198">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="0b28c-198">**Description of limit**</span></span>|<span data-ttu-id="0b28c-199">**制限**</span><span class="sxs-lookup"><span data-stu-id="0b28c-199">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b28c-200">レビュー セットからダウンロードした合計ファイル サイズまたはドキュメントの最大数。</span><span class="sxs-lookup"><span data-stu-id="0b28c-200">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="0b28c-201">3 MB または 50 ドキュメント <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="0b28c-201">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="0b28c-202"><sup>1</sup> 1 つのファイル制限を超えるアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-202"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="0b28c-203"><sup>2</sup> SharePoint と OneDrive for Business の場所を検索する場合、検索するサイトの URL 内の文字は、この制限に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-203"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="0b28c-204"><sup>3</sup> 語句以外のクエリ (二重引用符を使用しないキーワード値) には、特別なプレフィックス インデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b28c-204"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="0b28c-205">これにより、単語は文書内で発生しますが、文書内で発生する場所は示しません。</span><span class="sxs-lookup"><span data-stu-id="0b28c-205">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="0b28c-206">語句クエリ (二重引用符を含むキーワード値) を実行するには、ドキュメント内の位置と語句内の単語の位置を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b28c-206">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="0b28c-207">つまり、語句クエリにプレフィックス インデックスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b28c-207">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="0b28c-208">この場合、プレフィックスが展開される可能性のあるすべての単語でクエリを内部的に展開します。For example, **time _ can expand to \* *_*"time OR timer OR times OR timex OR timeboxed OR ..."**.</span><span class="sxs-lookup"><span data-stu-id="0b28c-208">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="0b28c-209">10,000 の制限は、クエリに一致するドキュメントの数ではなく、単語が展開できるバリアントの最大数です。</span><span class="sxs-lookup"><span data-stu-id="0b28c-209">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="0b28c-210">語句以外の用語には、上限がありません。</span><span class="sxs-lookup"><span data-stu-id="0b28c-210">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="0b28c-211"><sup>4</sup> この制限は、すべての電子情報開示ツールで共有されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-211"><sup>4</sup> This limit is shared across all eDiscovery tools.</span></span> <span data-ttu-id="0b28c-212">つまり、コンテンツ検索、コア電子情報開示、および Advanced eDiscovery の同時エクスポートは、この制限に対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-212">This means that concurrent exports in Content search, Core eDiscovery, and Advanced eDiscovery are applied against this limit.</span></span> <br/>
> <span data-ttu-id="0b28c-213"><sup>5</sup> この制限は、選択したドキュメントをレビュー セットからダウンロードする場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-213"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="0b28c-214">レビュー セットからドキュメントをエクスポートする場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="0b28c-214">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="0b28c-215">ドキュメントのダウンロードとエクスポートの詳細については [、「Advanced eDiscovery](exporting-data-ediscover20.md)でのケース データのエクスポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b28c-215">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>
> <span data-ttu-id="0b28c-216"><sup>1</sup> 日に 1 組織あたり 6 つのインデックス作成制限。</span><span class="sxs-lookup"><span data-stu-id="0b28c-216"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="0b28c-217">回避策として、複数の保管担当者を選択し、[インデックスの更新] をクリックすると、保管担当者ごとに個別のインデックス ジョブが作成されるのを回避できます。</span><span class="sxs-lookup"><span data-stu-id="0b28c-217">As a workaround, you can select multiple custodians and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> <br/>

