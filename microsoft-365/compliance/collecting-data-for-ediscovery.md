---
title: 高度な電子情報開示でケースのデータを収集する
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
description: 詳細な電子情報開示の検索ツールを使用して、調査のためにドキュメントセットを特定する方法について説明します。
ms.custom: seo-marvel-2020
ms.openlocfilehash: 725c289324a8e4d5bd4d7a7b9ddd9e091b6d6241
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956200"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="cfe6b-103">高度な電子情報開示でケースのデータを収集する</span><span class="sxs-lookup"><span data-stu-id="cfe6b-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="cfe6b-104">ケースに関係のある保管担当者およびデータソースを特定したら、詳細についてのドキュメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="cfe6b-105">上級電子情報開示の検索ツールを使用して、Microsoft 365 の custodial および非 wi-fi ダイヤルの場所から関連するドキュメントを識別できます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="cfe6b-106">検索を実行すると、検索クエリに一致したアイテムが最も多い場所など、取得したアイテムの統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="cfe6b-107">結果のサブセットをプレビューすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="cfe6b-108">さらに調査するドキュメントのセットを特定したら、検索結果をレビューセットに追加して、収集して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="cfe6b-109">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="cfe6b-109">Create a search</span></span>

<span data-ttu-id="cfe6b-110">[**検索] タブの [** **新しい検索**] を選択すると、検索を作成するためのガイドとなるウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="cfe6b-111">検索を作成する方法の詳細については、「 [データを収集するための検索を作成する](create-search-to-collect-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="cfe6b-112">検索が作成されると、詳細情報を含むフライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="cfe6b-113">検索がまだ完了していないため、[ **統計** ] および [ **プレビュー** ] ボタンは最初は使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="cfe6b-114">検索の進行状況を追跡するには、[ **検索** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="cfe6b-115">検索結果と統計情報を表示する</span><span class="sxs-lookup"><span data-stu-id="cfe6b-115">View search results and statistics</span></span>

<span data-ttu-id="cfe6b-116">コンテンツ検索には、統計 (見積り) とプレビューという2つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="cfe6b-117">これらの各コンポーネントが完了すると、[**検索**] タブの対応する列に [**送信\*\*\*\*済み**] から [**進行**中] に変更された状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="cfe6b-118">検索の推定が完了したら、検索を選択すると、検索結果に関する大まかな統計情報が表示される、フライアウトページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="cfe6b-119">この時点で、[ **統計** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="cfe6b-120">このチェックボックスをオンにすると、次のような検索統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="cfe6b-121">要約</span><span class="sxs-lookup"><span data-stu-id="cfe6b-121">Summary</span></span>
- <span data-ttu-id="cfe6b-122">トップの場所</span><span class="sxs-lookup"><span data-stu-id="cfe6b-122">Top locations</span></span>
- <span data-ttu-id="cfe6b-123">クエリ</span><span class="sxs-lookup"><span data-stu-id="cfe6b-123">Queries</span></span>

<span data-ttu-id="cfe6b-124">検索統計の詳細については、「 [検索統計](search-statistics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="cfe6b-125">プレビューが完了すると、[ **プレビュー** ] ボタンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="cfe6b-126">このチェックボックスをオンにして、抽出された結果のサブセットをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="cfe6b-127">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="cfe6b-127">Add search results to a review set</span></span>

<span data-ttu-id="cfe6b-128">検索結果全体を収集して処理する準備ができたら、それをレビューセットに追加することで、それを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="cfe6b-129">詳細については、「 [レビューセットにデータを追加する](add-data-to-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="cfe6b-130">Microsoft 以外の365データをレビューセットに追加する</span><span class="sxs-lookup"><span data-stu-id="cfe6b-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="cfe6b-131">ケースのコレクションプロセスの一部として、Office 以外の365データをレビューセットに追加し、検索ツールを使用して収集した Office 365 データと一緒に確認して分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="cfe6b-132">Office 以外の365を追加する場合は、そのようなを特定の保管担当者に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="cfe6b-133">詳細については、「 [Microsoft 以外の365データをレビューセットに読み込む](load-non-Office-365-data-into-a-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6b-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
