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
ms.custom:
- seo-marvel-apr2020
description: 検索結果またはこれらの検索結果のサンプルを Advanced eDiscovery ケース レビュー セットに追加する方法について説明します。
ms.openlocfilehash: 687cc33c0e7e6a09fb352e9c13058a6fcac30053
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814529"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="61f18-103">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="61f18-103">Add search results to a review set</span></span>

<span data-ttu-id="61f18-104">検索結果に問題がなければ、それらの検索結果をレビューおよび分析する準備ができたら、ケース内のレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="61f18-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="61f18-105">元のデータをレビュー セットにコピーすると、テーマの検出、重複データの検出、メールのスレッド識別などの高度な分析ツールが提供され、レビューと分析プロセスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="61f18-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="61f18-106">Microsoft 365 以外のデータ ソースからレビュー セットにデータを追加して、Microsoft 365 から収集したデータだけでなく、そのデータを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="61f18-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span> 

<span data-ttu-id="61f18-107">検索結果をレビュー セットに追加すると (ケースのレビュー セットは [レビュー セット **] タブに一** 覧表示されます)、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="61f18-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="61f18-108">検索が再び実行されます。</span><span class="sxs-lookup"><span data-stu-id="61f18-108">The search is run again.</span></span> <span data-ttu-id="61f18-109">つまり、レビュー セットにコピーされた実際の検索結果は、検索が最後に実行されたときに返された推定結果とは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61f18-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="61f18-110">検索結果内のすべてのアイテムはライブ サービス内の元のデータ ソースからコピーされ、Microsoft クラウドのセキュリティで保護された Azure Storage の場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="61f18-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="61f18-111">(コンテンツおよびメタデータを含む) すべてのアイテムには、レビュー セット内のすべてのデータは、ケース データのレビュー中に完全に検索できるように、すべてのアイテムのインデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="61f18-111">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="61f18-112">データのインデックスを再作成すると、調査セット中にデータを検索するときに、データのインデックスを詳細かつ速く検索できます。</span><span class="sxs-lookup"><span data-stu-id="61f18-112">Re-indexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="61f18-113">レビュー セットにデータを追加するには、[検索] タブ **で検索を** クリックし、[ **結果を追加]** をクリックしてポップアップ ページでセットを確認します。</span><span class="sxs-lookup"><span data-stu-id="61f18-113">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

![レビュー セットへのデータの追加](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="61f18-115">既存のレビュー セットに追加するか、新しいレビュー セットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61f18-115">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="61f18-116">新しいレビュー セットに追加する場合は、名前を指定してから [追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61f18-116">If adding to a new review set, specify the name and then click **Add**.</span></span>

![レビュー セットの選択](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="61f18-118">コレクションのレビューの範囲を設定するオプションの定義</span><span class="sxs-lookup"><span data-stu-id="61f18-118">Define options to scope your collection for review</span></span>

<span data-ttu-id="61f18-119">検索のコンテンツを既存のレビュー セットに追加したり、新しいレビュー セットを作成したりする場合、レビュー用のコンテンツの収集方法があります。</span><span class="sxs-lookup"><span data-stu-id="61f18-119">As you add the content of a search to an existing review set or create a new one you have options for how to collect the content for review:</span></span>

- <span data-ttu-id="61f18-120">**会話レビュー セット** に追加された項目はスレッド形式の会話に対して有効になり、スレッド形式の会話に対して有効になり、この記事の [会話レビュー セット] の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61f18-120">**Conversational review set** - the items added to the review set will be enabled for threaded conversations to help review content in context of the back and forth conversation, see more in this article [conversation review sets]</span></span>

- <span data-ttu-id="61f18-121">**最新の添付ファイルの取得を有効** にする - このコントロールを使用して、最新の添付ファイルやリンク ファイルをコレクションに含め、詳細なレビューを行います。このコンテンツをグループ化できる新しい検索可能なフィールド名の詳細については、「[advanced eDiscovery のドキュメント メタデータ フィールド] を参照してください</span><span class="sxs-lookup"><span data-stu-id="61f18-121">**Enable retrieval for modern attachment** - use this control to include modern attachments or linked files in the collection for further review; read more about the new searchable field names that are available to group this content, see [document metadata fields in advanced ediscovery]</span></span>

- <span data-ttu-id="61f18-122">**SharePoint のバージョン (ベータ版) を含** む: このコントロールによって、コレクションのバージョン制限および検索パラメーターに関して、すべてのバージョンの SharePoint ファイルのコレクションを有効にします注: このコントロールによってコレクションのサイズが大幅に増加します</span><span class="sxs-lookup"><span data-stu-id="61f18-122">**Include versions from SharePoint (beta)** - this control enables collection of all version of a SharePoint file per the version limits and search parameters of the collection; note: this control will increase the size of the collection significantly</span></span>

<span data-ttu-id="61f18-123">レビューセットへのデータの追加は、時間のかかるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="61f18-123">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="61f18-124">このプロセスには、Microsoft 365 の元のデータ ソースから (たとえば、メールボックスやサイトから) アイテムを収集し、Azure Storage の場所にコピーします (このコピー プロセスは「インジェク *ション*」とも呼ばれる)、アイテムのインデックスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="61f18-124">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="61f18-125">[ジョブ] タブまたは [検索]**タブで進**行状況を追跡するには、[追加データ] 内の状態**を監視して、設定値の列を確認**します。 **Searches**</span><span class="sxs-lookup"><span data-stu-id="61f18-125">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="61f18-126">レビュー セットの処理が完了した後、 **ケースの [レ** ビュー セット] タブをクリックし、レビュー セットをクリックして、レビュー セット内のデータのフィルター処理、レビュー、タグ付け、エクスポートのプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="61f18-126">After the review set processing is completed, click the **Review sets** tab in the case, and click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="61f18-127">レビュー セットにサンプルを追加する</span><span class="sxs-lookup"><span data-stu-id="61f18-127">Add a sample to a review set</span></span>

<span data-ttu-id="61f18-128">検索結果をすべてレビュー セットに追加する前に、検索結果をさらに詳しく検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビュー セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="61f18-128">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="61f18-129">レビュー セットにサンプルを追加するには、[検索] タブの **検索をクリック** し、ポップアップ ページの [ **サンプル** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61f18-129">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="61f18-130">[サ **ンプリング パラメーター] ページ** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61f18-130">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="61f18-131">**信頼度 =% と** 信頼度の間隔 **は %** と -レビュー セットに追加される項目は、設定した統計パラメーターによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="61f18-131">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="61f18-132">通常、結果をサンプリングするときに信頼度と間隔を使用する場合は、ドロップダウン ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="61f18-132">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="61f18-133">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f18-133">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="61f18-134">**サンプル % - レ** ビュー セットに追加されるアイテムは、検索によって返されたアイテムの総数の指定した割合に対するランダムな選択に基づいています。</span><span class="sxs-lookup"><span data-stu-id="61f18-134">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="61f18-135">上記のいずれかのオプションを選択して構成した後、レビュー セットを選択して、サンプルを追加し、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61f18-135">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="61f18-136">繰り返しますが、[ジョブ]**Jobs**タブまたは [検索]**Searches**タブで進行状況を追跡し、設定された列**の [追加データ] 内の状態を監視して、設定列を確認**します。</span><span class="sxs-lookup"><span data-stu-id="61f18-136">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="61f18-137">光学式文字認識</span><span class="sxs-lookup"><span data-stu-id="61f18-137">Optical character recognition</span></span>

<span data-ttu-id="61f18-138">レビュー セットに検索結果を追加すると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって、画像からテキストが自動的に抽出され、レビュー セットに追加されるデータとイメージ テキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61f18-138">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="61f18-139">抽出したテキストは、レビュー セット内で選択したイメージ ファイルのテキスト ビューアーで確認できます。</span><span class="sxs-lookup"><span data-stu-id="61f18-139">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="61f18-140">これにより、画像内のテキストをさらにレビューおよび分析できます。</span><span class="sxs-lookup"><span data-stu-id="61f18-140">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="61f18-141">OCR は、圧縮されていないファイル、電子メールの添付ファイル、および埋め込み画像の場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="61f18-141">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="61f18-142">OCRでサポートされている画像ファイル形式のリストについては、[「高度なeDiscoveryでサポートされているファイルタイプ」](supported-filetypes-ediscovery20.md#image)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61f18-142">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="61f18-143">Advanced eDiscovery で作成するケースごとにOCR機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61f18-143">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="61f18-144">詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="61f18-144">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
