---
title: 検索結果をレビュー セットに追加する
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
description: 高度な電子情報開示ケースに関連付けられた検索結果を追加します。 アイテムは元の場所からコピーされ、Microsoft によって提供される Azure ストレージの場所にコピーされます。 また、アイテムもインデックスが再作成され、高度な電子情報開示によって画像ファイルの OCR が実行され、レビューと分析のための画像テキストがアップロードされます。
ms.openlocfilehash: 5e4eaa5e83bbca3a80abe0026f3880ce8d3c85c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080157"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="6c81d-105">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="6c81d-105">Add search results to a review set</span></span>

<span data-ttu-id="6c81d-106">検索結果に問題がなければ、検索結果を確認して分析する準備ができたら、それらをレビューセットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-106">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="6c81d-107">元のデータをレビューセットにコピーすると、テーマの検出、ほぼ重複した検出、電子メールスレッドの識別などの高度な分析ツールを提供することにより、レビューと分析のプロセスも容易になります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-107">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="6c81d-108">また、office 365 から収集したデータに加えてデータを確認できるように、Office 以外の365データソースのデータをレビューセットに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-108">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span> 

<span data-ttu-id="6c81d-109">検索結果をレビューセットに追加すると (ケースのレビューセットが [**レビューセット**] タブに一覧表示されます)、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-109">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="6c81d-110">検索が再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-110">The search is run again.</span></span> <span data-ttu-id="6c81d-111">つまり、レビューセットにコピーされる実際の検索結果は、検索が最後に実行されたときに返された推定結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-111">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="6c81d-112">検索結果内のすべてのアイテムは、live Office 365 サービスの元のデータソースからコピーされ、Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-112">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="6c81d-113">すべてのアイテム (コンテンツとメタデータを含む) が再インデックス化され、ケースデータの確認時にレビューセット内のすべてのデータが完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-113">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="6c81d-114">ケース調査時にレビューセット内のデータを検索するときに、データのインデックスを完全検索と高速検索で再インデックス化します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-114">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="6c81d-115">レビューセットにデータを追加するには、[**検索**] タブで検索をクリックしてから、ポップアップページの [**レビューセットに結果を追加**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c81d-115">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![レビューセットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="6c81d-117">既存のレビューセットに追加したり、新しいレビューセットを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-117">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="6c81d-118">新しいレビューセットにを追加する場合は、名前を指定して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c81d-118">If adding to a new review set, specify the name and then click **Add**.</span></span>

![レビューセットを選択する](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="6c81d-120">レビューセットへのデータの追加は、長時間実行されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6c81d-120">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="6c81d-121">このプロセスには、Office 365 の元のデータソース (たとえば、メールボックスやサイトから) のアイテムを収集し、それらを Azure ストレージの場所 (このコピープロセスは*取り込み*とも呼ばれます) にコピーして、アイテムのインデックスを再作成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-121">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="6c81d-122">[**ジョブ**] タブまたは [**検索**] タブで進行状況を追跡するには、[[**レビューするデータを確認セットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-122">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="6c81d-123">レビューセット処理が完了した後で、ケースの [**検査セット**] タブをクリックし、[レビュー] セットをクリックして、レビューセットのデータのフィルター、確認、タグ付け、エクスポートのプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-123">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="6c81d-124">レビューセットにサンプルを追加する</span><span class="sxs-lookup"><span data-stu-id="6c81d-124">Add a sample to a review set</span></span>

<span data-ttu-id="6c81d-125">すべてをレビューセットに追加する前に、検索結果をより詳細に検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビューセットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-125">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="6c81d-126">サンプルをレビューセットに追加するには、[**検索**] タブで検索をクリックして、フライアウトページの [**サンプル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c81d-126">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="6c81d-127">[**サンプリングパラメーター** ] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-127">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="6c81d-128">[**信頼度レベル%** と**信頼区間%** ]-レビューセットに追加されるアイテムは、設定した統計パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-128">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="6c81d-129">通常、結果のサンプリング時に信頼度と間隔を使用する場合は、ドロップダウンボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-129">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="6c81d-130">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-130">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="6c81d-131">**ランダムサンプル%** -レビューセットに追加されるアイテムは、検索によって返されるアイテムの総数に対する、指定されたパーセンテージのランダムな選択に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6c81d-131">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="6c81d-132">前のオプションの1つを選択して構成した後、そのサンプルを追加するレビューセットを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c81d-132">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="6c81d-133">この場合も、[**ジョブ**] タブまたは [**検索**] タブで進捗状況を追跡するには、[[**レビューするデータをレビューセットに追加しまし**た] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="6c81d-133">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="6c81d-134">光学式文字認識</span><span class="sxs-lookup"><span data-stu-id="6c81d-134">Optical character recognition</span></span>

<span data-ttu-id="6c81d-135">検索結果をレビューセットに追加すると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって画像からテキストが自動的に抽出されます。また、画像テキストには、校閲セットに追加されるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c81d-135">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="6c81d-136">抽出されたテキストは、校閲セットの選択したイメージファイルのテキストビューアーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-136">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="6c81d-137">これにより、画像内のテキストに対してさらにレビューと分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c81d-137">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="6c81d-138">OCR は、ルースファイル、電子メールの添付ファイル、および埋め込み画像に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c81d-138">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="6c81d-139">OCR でサポートされている画像ファイル形式の一覧については、「 [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md#image)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c81d-139">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="6c81d-140">詳細な電子情報開示で作成するケースごとに OCR 機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c81d-140">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="6c81d-141">詳細については、「 [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c81d-141">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
