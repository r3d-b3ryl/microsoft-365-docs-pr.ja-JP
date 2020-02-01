---
title: 高度な電子情報開示でケースのデータを収集する
f1.keywords:
- NOCSH
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a6b86d9f86edc427e10c02a99e3cda3e5e79db66
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595854"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="697ef-102">高度な電子情報開示でケースのデータを収集する</span><span class="sxs-lookup"><span data-stu-id="697ef-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="697ef-103">ケースに関係のある保管担当者およびデータソースを特定したら、詳細についてのドキュメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="697ef-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="697ef-104">上級電子情報開示の検索ツールを使用して、Office 365 の custodial および非 wi-fi ダイヤルの場所からこれらを識別することができます。</span><span class="sxs-lookup"><span data-stu-id="697ef-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="697ef-105">検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="697ef-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="697ef-106">結果のサブセットをプレビューすることもできます。</span><span class="sxs-lookup"><span data-stu-id="697ef-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="697ef-107">さらに調査するドキュメントのセットを特定したら、検索結果をレビューセットに追加して、収集して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="697ef-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="697ef-108">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="697ef-108">Create a search</span></span>

<span data-ttu-id="697ef-109">[**検索] タブの [** **新しい検索**] を選択すると、検索を作成するためのガイドとなるウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="697ef-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="697ef-110">検索を作成する方法の詳細については、「[データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="697ef-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="697ef-111">検索が作成されると、詳細情報を含むフライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="697ef-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="697ef-112">検索がまだ完了していないため、[**統計**] および [**プレビュー** ] ボタンは最初は使用できません。</span><span class="sxs-lookup"><span data-stu-id="697ef-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="697ef-113">検索の進行状況を追跡するには、[**検索**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="697ef-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="697ef-114">検索結果と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="697ef-114">View search results and statistics</span></span>

<span data-ttu-id="697ef-115">コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="697ef-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="697ef-116">これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に [**送信\*\*\*\*済み**] から [**進行**中] に変更された状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="697ef-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="697ef-117">検索の推定が完了したら、検索を選択すると、検索結果に関する大まかな統計情報が表示される、フライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="697ef-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="697ef-118">この時点で、[**統計**] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="697ef-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="697ef-119">このチェックボックスをオンにすると、次のような検索統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="697ef-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="697ef-120">概要</span><span class="sxs-lookup"><span data-stu-id="697ef-120">Summary</span></span>
- <span data-ttu-id="697ef-121">トップの場所</span><span class="sxs-lookup"><span data-stu-id="697ef-121">Top locations</span></span>
- <span data-ttu-id="697ef-122">クエリ</span><span class="sxs-lookup"><span data-stu-id="697ef-122">Queries</span></span>

<span data-ttu-id="697ef-123">検索統計の詳細については、「[検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="697ef-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="697ef-124">プレビューが完了すると、[**プレビュー** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="697ef-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="697ef-125">このチェックボックスをオンにして、抽出された結果のサブセットをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="697ef-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="697ef-126">検索結果をレビューセットに追加する</span><span class="sxs-lookup"><span data-stu-id="697ef-126">Adding search results to a review set</span></span>

<span data-ttu-id="697ef-127">検索結果全体を収集して処理する準備ができたら、それをレビューセットに追加することで、それを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="697ef-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="697ef-128">詳細については、「[レビューセットにデータを追加する](add-data-to-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="697ef-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
