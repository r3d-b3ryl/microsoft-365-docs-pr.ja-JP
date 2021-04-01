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
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の高度な電子情報開示ソリューションで有効なケースの制限、インデックス作成の制限、および検索の制限について説明します。
ms.openlocfilehash: 145d5de5027a9d6171215c0602a733ced5265657
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445323"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="1c65f-103">Advanced eDiscovery を制限する</span><span class="sxs-lookup"><span data-stu-id="1c65f-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="1c65f-104">この記事では、Microsoft 365 の高度な電子情報開示ソリューションの制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="1c65f-105">ケースとレビューセットの制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-105">Case and review set limits</span></span>

<span data-ttu-id="1c65f-106">次の表に、Advanced eDiscovery のケースとレビュー セットの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="1c65f-107">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-107">Description of limit</span></span> | <span data-ttu-id="1c65f-108">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-109">ケースに追加できるドキュメントの総数 (ケース内のすべてのレビュー セットに対して)。</span><span class="sxs-lookup"><span data-stu-id="1c65f-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="1c65f-110">300 万</span><span class="sxs-lookup"><span data-stu-id="1c65f-110">3 million</span></span> <br/> |
|<span data-ttu-id="1c65f-111">読み込みセットごとのファイル サイズの合計。</span><span class="sxs-lookup"><span data-stu-id="1c65f-111">Total file size per load set.</span></span> <span data-ttu-id="1c65f-112">これには、レビュー セットに 365 以外Office 365 を読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c65f-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="1c65f-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="1c65f-113">300 GB</span></span> <br/> |
|<span data-ttu-id="1c65f-114">1 日に組織内のすべてのレビュー セットに読み込まれるデータの合計量。</span><span class="sxs-lookup"><span data-stu-id="1c65f-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="1c65f-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="1c65f-115">2 TB</span></span> <br/> |
|<span data-ttu-id="1c65f-116">1 ケースあたりの最大読み込みセット数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-116">Maximum number of load sets per case.</span></span>  <br/> |<span data-ttu-id="1c65f-117">200</span><span class="sxs-lookup"><span data-stu-id="1c65f-117">200</span></span> <br/> |
|<span data-ttu-id="1c65f-118">ケースごとのレビュー セットの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="1c65f-119">20</span><span class="sxs-lookup"><span data-stu-id="1c65f-119">20</span></span> <br/> |
|<span data-ttu-id="1c65f-120">ケースごとのタグ グループの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="1c65f-121">1000</span><span class="sxs-lookup"><span data-stu-id="1c65f-121">1000</span></span> <br/> |
|<span data-ttu-id="1c65f-122">1 ケースあたりのタグの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="1c65f-123">1000</span><span class="sxs-lookup"><span data-stu-id="1c65f-123">1000</span></span> <br/> |
|<span data-ttu-id="1c65f-124">レビュー セットにコンテンツを追加する組織内の最大同時ジョブ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-124">Maximum concurrent jobs in your organization to add content to a review set.</span></span> <span data-ttu-id="1c65f-125">これらのジョブの名前は **[レビュー セットにデータを追加** する] という名前で、ケースの [ **ジョブ** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-125">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span>| <span data-ttu-id="1c65f-126">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-126">10 <sup>4</sup></span></span> |
|<span data-ttu-id="1c65f-127">ユーザーごとのレビュー セットにコンテンツを追加する最大同時ジョブ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-127">Maximum concurrent jobs to add content to a review set per user.</span></span> <span data-ttu-id="1c65f-128">これらのジョブの名前は **[レビュー セットにデータを追加** する] という名前で、ケースの [ **ジョブ** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-128">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span> | <span data-ttu-id="1c65f-129">3</span><span class="sxs-lookup"><span data-stu-id="1c65f-129">3</span></span> |
|||

## <a name="hold-limits"></a><span data-ttu-id="1c65f-130">ホールド制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-130">Hold limits</span></span>

<span data-ttu-id="1c65f-131">次の表に、高度な電子情報開示ケースに関連付けられている保留リストの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-131">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="1c65f-132">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-132">Description of limit</span></span> | <span data-ttu-id="1c65f-133">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-133">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-134">1 つのケースホールド内のメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-134">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="1c65f-135">この制限には、ユーザー メールボックスの合計と、Microsoft 365 グループ、Microsoft Teams、およびグループグループに関連付けられたメールボックスYammer含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-135">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="1c65f-136">1,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-136">1,000</span></span>  <br/> |
|<span data-ttu-id="1c65f-137">1 つのケースホールド内のサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-137">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="1c65f-138">この制限には、OneDrive for Business サイト、SharePoint サイト、および Microsoft 365 グループ、Microsoft Teams、および Yammer グループに関連付けられたサイトの合計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-138">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="1c65f-139">100</span><span class="sxs-lookup"><span data-stu-id="1c65f-139">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="1c65f-140">インデックス作成の制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-140">Indexing limits</span></span>

<span data-ttu-id="1c65f-141">次の表に、Advanced eDiscovery のインデックスの制限を示します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-141">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="1c65f-142">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-142">Description of limit</span></span> | <span data-ttu-id="1c65f-143">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-143">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-144">1 つのファイルから抽出された最大文字数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-144">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="1c65f-145">1,000 万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-145">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1c65f-146">1 つのファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-146">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="1c65f-147">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-147">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1c65f-148">ドキュメントに埋め込まれたアイテムの最大深度。</span><span class="sxs-lookup"><span data-stu-id="1c65f-148">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="1c65f-149">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-149">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="1c65f-150">光学式文字認識 (OCR) によって処理されるファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-150">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="1c65f-151">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-151">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="1c65f-152">1 日あたりの組織ごとのインデックス ジョブの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-152">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="1c65f-153">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-153">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="1c65f-154">検索の制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-154">Search limits</span></span>

<span data-ttu-id="1c65f-155">このセクションで説明する制限は、[検索] タブの検索ツールを使用してケースのデータを収集する場合に関連しています。</span><span class="sxs-lookup"><span data-stu-id="1c65f-155">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="1c65f-156">詳細については、「Advanced [eDiscovery でケースのデータを収集する」を参照してください](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="1c65f-156">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="1c65f-157">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-157">Description of limit</span></span> | <span data-ttu-id="1c65f-158">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-158">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-159">1 つの検索で検索できるメールボックスまたはサイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-159">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="1c65f-160">制限なし</span><span class="sxs-lookup"><span data-stu-id="1c65f-160">No limit</span></span>|
|<span data-ttu-id="1c65f-161">同時に実行できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-161">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="1c65f-162">制限なし</span><span class="sxs-lookup"><span data-stu-id="1c65f-162">No limit</span></span> |
|<span data-ttu-id="1c65f-163">1 人のユーザーが同時に開始できる検索の最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-163">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="1c65f-164">10</span><span class="sxs-lookup"><span data-stu-id="1c65f-164">10</span></span> | 
|<span data-ttu-id="1c65f-165">検索クエリの最大文字数 (演算子と条件を含む)。</span><span class="sxs-lookup"><span data-stu-id="1c65f-165">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="1c65f-166">10,000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-166">10,000&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="1c65f-167">プレフィックス ワイルドカードのアルファ文字の最小数。たとえば **、1 つの _ または \* *_* セットです \***。</span><span class="sxs-lookup"><span data-stu-id="1c65f-167">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="1c65f-168">3</span><span class="sxs-lookup"><span data-stu-id="1c65f-168">3</span></span> |  
|<span data-ttu-id="1c65f-169">プレフィックス ワイルドカードを使用して正確な語句を検索する場合、またはプレフィックス ワイルドカードと NEAR Boolean 演算子を使用する場合に返される最大 **バリアント** 。</span><span class="sxs-lookup"><span data-stu-id="1c65f-169">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="1c65f-170">10,000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-170">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="1c65f-171">検索のプレビュー ページに表示されるユーザー メールボックスごとのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-171">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="1c65f-172">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-172">The newest items are displayed.</span></span> |<span data-ttu-id="1c65f-173">100</span><span class="sxs-lookup"><span data-stu-id="1c65f-173">100</span></span>|
|<span data-ttu-id="1c65f-174">検索のプレビュー ページに表示されるすべてのメールボックスのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-174">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="1c65f-175">1,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-175">1,000</span></span>|
|<span data-ttu-id="1c65f-176">検索結果をプレビューできるメールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-176">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="1c65f-177">検索クエリに一致するアイテムを含むメールボックスが 1000 を超える場合は、結果が最も多い上位 1,000 メールボックスだけがプレビューで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-177">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="1c65f-178">1,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-178">1,000</span></span>|
|<span data-ttu-id="1c65f-179">検索のプレビュー ページに表示される SharePoint サイトと OneDrive for Business サイトのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-179">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="1c65f-180">最新のアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-180">The newest items are displayed.</span></span> |<span data-ttu-id="1c65f-181">200</span><span class="sxs-lookup"><span data-stu-id="1c65f-181">200</span></span>|
|<span data-ttu-id="1c65f-182">検索結果をプレビューできる SharePoint サイトと OneDrive for Business サイトの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-182">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="1c65f-183">検索クエリに一致するアイテムを含むサイトが 200 を超える場合は、結果が最も多い上位 200 サイトだけがプレビューに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-183">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="1c65f-184">200</span><span class="sxs-lookup"><span data-stu-id="1c65f-184">200</span></span>|
|<span data-ttu-id="1c65f-185">検索のプレビュー ページに表示されるパブリック フォルダー メールボックスごとのアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-185">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="1c65f-186">100</span><span class="sxs-lookup"><span data-stu-id="1c65f-186">100</span></span>|
|<span data-ttu-id="1c65f-187">検索のプレビュー ページに表示されるパブリック フォルダーメールボックスアイテムの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-187">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="1c65f-188">200</span><span class="sxs-lookup"><span data-stu-id="1c65f-188">200</span></span>|
|<span data-ttu-id="1c65f-189">検索結果をプレビューできるパブリック フォルダー メールボックスの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-189">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="1c65f-190">検索クエリに一致するアイテムを含むパブリック フォルダー メールボックスが 500 を超える場合は、結果が最も多い上位 500 メールボックスだけがプレビューで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-190">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="1c65f-191">500</span><span class="sxs-lookup"><span data-stu-id="1c65f-191">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="1c65f-192">検索時間</span><span class="sxs-lookup"><span data-stu-id="1c65f-192">Search times</span></span>

<span data-ttu-id="1c65f-193">Microsoft は、すべての組織が実行する検索のパフォーマンス情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-193">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="1c65f-194">検索クエリが複雑になると、検索時間が長くなる可能性がありますが、検索時間が長くなる最も大きな要因は、検索するメールボックスの数です。</span><span class="sxs-lookup"><span data-stu-id="1c65f-194">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="1c65f-195">Microsoft では検索時間に関するサービス レベル契約は提供されませんが、次の表に、検索に含まれるメールボックスの数に基づくコレクション検索の平均検索時間を示します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-195">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="1c65f-196">**メールボックスの数**</span><span class="sxs-lookup"><span data-stu-id="1c65f-196">**Number of mailboxes**</span></span>|<span data-ttu-id="1c65f-197">**検索平均時間**</span><span class="sxs-lookup"><span data-stu-id="1c65f-197">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="1c65f-198">100</span><span class="sxs-lookup"><span data-stu-id="1c65f-198">100</span></span>  <br/> |<span data-ttu-id="1c65f-199">30 秒</span><span class="sxs-lookup"><span data-stu-id="1c65f-199">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="1c65f-200">1,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-200">1,000</span></span>  <br/> |<span data-ttu-id="1c65f-201">45 秒</span><span class="sxs-lookup"><span data-stu-id="1c65f-201">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="1c65f-202">10,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-202">10,000</span></span>  <br/> |<span data-ttu-id="1c65f-203">4 分</span><span class="sxs-lookup"><span data-stu-id="1c65f-203">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="1c65f-204">25,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-204">25,000</span></span>  <br/> |<span data-ttu-id="1c65f-205">10 分</span><span class="sxs-lookup"><span data-stu-id="1c65f-205">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="1c65f-206">50,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-206">50,000</span></span>  <br/> |<span data-ttu-id="1c65f-207">20 分</span><span class="sxs-lookup"><span data-stu-id="1c65f-207">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="1c65f-208">100,000</span><span class="sxs-lookup"><span data-stu-id="1c65f-208">100,000</span></span>  <br/> |<span data-ttu-id="1c65f-209">25 分</span><span class="sxs-lookup"><span data-stu-id="1c65f-209">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="1c65f-210">ビューアーの制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-210">Viewer limits</span></span>

| <span data-ttu-id="1c65f-211">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-211">Description of limit</span></span> | <span data-ttu-id="1c65f-212">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-212">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-213">ネイティブ ビューアーで表示できる Excel ファイルの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-213">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="1c65f-214">4 MB</span><span class="sxs-lookup"><span data-stu-id="1c65f-214">4 MB</span></span>  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a><span data-ttu-id="1c65f-215">エクスポートの制限 - レビュー セットから最終的にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="1c65f-215">Export limits - Final export out of Review Set</span></span>

<span data-ttu-id="1c65f-216">このセクションで説明する制限は、レビュー セットからドキュメントをエクスポートする方法に関連しています。</span><span class="sxs-lookup"><span data-stu-id="1c65f-216">The limits described in this section are related to exporting documents out of a review set.</span></span>

| <span data-ttu-id="1c65f-217">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-217">Description of limit</span></span> | <span data-ttu-id="1c65f-218">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-218">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-219">1 つのエクスポートの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="1c65f-219">Maximum size of a single export.</span></span>|<span data-ttu-id="1c65f-220">300 万ドキュメントまたは 100 GB、どちらが小さいか</span><span class="sxs-lookup"><span data-stu-id="1c65f-220">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="1c65f-221">レビュー セットごとの最大同時エクスポート数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-221">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="1c65f-222">1</span><span class="sxs-lookup"><span data-stu-id="1c65f-222">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="1c65f-223">ダウンロード制限の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="1c65f-223">Review set download limits</span></span>

| <span data-ttu-id="1c65f-224">制限の説明</span><span class="sxs-lookup"><span data-stu-id="1c65f-224">Description of limit</span></span> | <span data-ttu-id="1c65f-225">制限</span><span class="sxs-lookup"><span data-stu-id="1c65f-225">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="1c65f-226">レビュー セットからダウンロードされたファイルの合計サイズまたはドキュメントの最大数。</span><span class="sxs-lookup"><span data-stu-id="1c65f-226">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="1c65f-227">3 MB または 50 ドキュメント <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="1c65f-227">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="1c65f-228"><sup>1 1</sup> つのファイル制限を超えたアイテムは、処理エラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-228"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="1c65f-229"><sup>2</sup> SharePoint と OneDrive for Business の場所を検索する場合、検索するサイトの URL の文字は、この制限に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-229"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span>
>
> <span data-ttu-id="1c65f-230"><sup>3</sup> 語句以外のクエリ (二重引用符を使用しないキーワード値) では、特別なプレフィックス インデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c65f-230"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="1c65f-231">これにより、文書内で単語が発生しますが、文書内で発生する場所は示しません。</span><span class="sxs-lookup"><span data-stu-id="1c65f-231">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="1c65f-232">語句クエリ (二重引用符付きキーワード値) を実行するには、文書内の語句の位置を比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c65f-232">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="1c65f-233">つまり、語句クエリにプレフィックス インデックスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c65f-233">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="1c65f-234">この場合、プレフィックスが展開される可能性のあるすべての単語を含むクエリを内部的に展開します。たとえば **、time _ は \* *_*"time OR timer OR times OR timex OR timeboxed OR ..." に展開できます。**</span><span class="sxs-lookup"><span data-stu-id="1c65f-234">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="1c65f-235">10,000 の制限は、クエリに一致するドキュメントの数ではなく、単語が展開できるバリアントの最大数です。</span><span class="sxs-lookup"><span data-stu-id="1c65f-235">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="1c65f-236">語句以外の用語には、上限がありません。</span><span class="sxs-lookup"><span data-stu-id="1c65f-236">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="1c65f-237"><sup>4 この</sup> 制限は、他の電子情報開示ツールのコンテンツのエクスポートと共有されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-237"><sup>4</sup> This limit is shared with exporting content in other eDiscovery tools.</span></span> <span data-ttu-id="1c65f-238">つまり、コンテンツ検索と Core 電子情報開示での同時エクスポート (および Advanced eDiscovery のレビュー セットにコンテンツを追加する) はすべて、この制限に対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-238">This means that concurrent exports in Content search and Core eDiscovery (and adding content to review sets in Advanced eDiscovery) are all applied against this limit.</span></span>
>
> <span data-ttu-id="1c65f-239"><sup>5</sup> この制限は、選択したドキュメントをレビュー セットからダウンロードする場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-239"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="1c65f-240">レビュー セットからドキュメントをエクスポートする場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1c65f-240">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="1c65f-241">ドキュメントのダウンロードとエクスポートの詳細については、「Advanced eDiscovery でのケース データのエクスポート [」を参照してください](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="1c65f-241">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="1c65f-242"><sup>6</sup> 1 日あたりの組織ごとのインデックスの制限。</span><span class="sxs-lookup"><span data-stu-id="1c65f-242"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="1c65f-243">回避策として、ケースの [データ ソース] タブで複数の保管担当者を選択し、[インデックスの更新] をクリックして、保管担当者ごとに個別のインデックス ジョブを作成しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c65f-243">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
