---
title: Advanced eDiscovery のケースのデータを収集する
f1.keywords:
- NOCSH
ms.author: markjjo
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
description: Advanced eDiscovery の検索ツールを使用して、調査でレビューするドキュメント セットを識別する方法について説明します。
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751271"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="69f47-103">Advanced eDiscovery のケースのデータを収集する</span><span class="sxs-lookup"><span data-stu-id="69f47-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="69f47-104">ケースに関心のあるカストディアンとデータ ソースを特定したら、次に、詳細を確認するドキュメントのセットを特定します。</span><span class="sxs-lookup"><span data-stu-id="69f47-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="69f47-105">Advanced eDiscovery の検索ツールを使用して、Microsoft 365 の保管場所と保管場所以外の場所から関連するドキュメントを識別できます。</span><span class="sxs-lookup"><span data-stu-id="69f47-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="69f47-106">検索を実行すると、検索クエリに一致したアイテムが最も多かった場所など、取得したアイテムの統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="69f47-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="69f47-107">結果のサブセットをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="69f47-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="69f47-108">さらに調べるドキュメントのセットを特定した後、検索結果をレビュー セットに追加して、収集と処理を行います。</span><span class="sxs-lookup"><span data-stu-id="69f47-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="69f47-109">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="69f47-109">Create a search</span></span>

<span data-ttu-id="69f47-110">[検索 **] タブで**[新しい検索] を選択すると、検索を作成するためのウィザードが開始されます。 </span><span class="sxs-lookup"><span data-stu-id="69f47-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="69f47-111">検索を作成する方法の詳細については、「データを収集する検索を作成 [する」を参照してください](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="69f47-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="69f47-112">検索が作成されると、詳細を含むフライアウト ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69f47-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="69f47-113">[**統計情報]\*\*\*\*ボタンと**[プレビュー] ボタンは、検索がまだ完了していないので、最初は使用できません。</span><span class="sxs-lookup"><span data-stu-id="69f47-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="69f47-114">[検索] タブでは、検索の進行状況 **を追跡** できます。</span><span class="sxs-lookup"><span data-stu-id="69f47-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="69f47-115">検索結果と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="69f47-115">View search results and statistics</span></span>

<span data-ttu-id="69f47-116">コンテンツ検索には、統計情報 (推定値) とプレビューの 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="69f47-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="69f47-117">これらの各コンポーネントが完了すると、[検索] タブの対応する列に状態が表示され、[送信済み]から[進行中] から [完了] に変 **わります**。</span><span class="sxs-lookup"><span data-stu-id="69f47-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="69f47-118">検索の推定が完了したら、検索を選択してフライアウト ページを表示します。このページには、検索の結果に関する高レベルの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69f47-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="69f47-119">この時点で、[統計情報 **] ボタン** がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="69f47-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="69f47-120">このオプションを選択すると、次のような検索統計を表示できます。</span><span class="sxs-lookup"><span data-stu-id="69f47-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="69f47-121">概要</span><span class="sxs-lookup"><span data-stu-id="69f47-121">Summary</span></span>
- <span data-ttu-id="69f47-122">トップの場所</span><span class="sxs-lookup"><span data-stu-id="69f47-122">Top locations</span></span>
- <span data-ttu-id="69f47-123">クエリ</span><span class="sxs-lookup"><span data-stu-id="69f47-123">Queries</span></span>

<span data-ttu-id="69f47-124">検索統計の詳細については、「検索統計」 [を参照してください](search-statistics-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="69f47-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="69f47-125">プレビューが完了すると、[プレビュー] **ボタン** がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="69f47-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="69f47-126">結果のサンプリングされたサブセットをプレビューするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="69f47-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="69f47-127">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="69f47-127">Add search results to a review set</span></span>

<span data-ttu-id="69f47-128">検索の結果全体を収集して処理する準備ができたら、それをレビュー セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="69f47-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="69f47-129">詳細については、「レビュー セット [にデータを追加する」を参照してください](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="69f47-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="69f47-130">Microsoft 365 以外のデータをレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="69f47-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="69f47-131">ケースの収集プロセスの一環として、Office 365 以外のデータをレビュー セットに追加し、検索ツールを使用して収集した Office 365 データと共にレビューおよび分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="69f47-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="69f47-132">365 以外Office追加する場合は、ケース内の特定のカストディアンに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="69f47-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="69f47-133">詳細については [、「Microsoft 365 以外のデータをレビュー セットに読み込む」を参照してください](load-non-Office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="69f47-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
