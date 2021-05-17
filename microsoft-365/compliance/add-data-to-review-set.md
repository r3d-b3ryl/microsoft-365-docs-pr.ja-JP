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
description: これらの検索結果の検索結果またはサンプルをケース レビュー セットにAdvanced eDiscoveryする方法について学習します。
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919979"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="58eae-103">検索結果をレビュー セットに追加する</span><span class="sxs-lookup"><span data-stu-id="58eae-103">Add search results to a review set</span></span>

<span data-ttu-id="58eae-104">検索の結果に満足し、それらの検索結果を確認して分析する準備ができたら、ケース内のレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="58eae-104">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="58eae-105">元のデータをレビュー セットにコピーすると、テーマの検出、重複に近い検出、電子メール スレッドの識別などの高度な分析ツールを提供することで、レビューと分析プロセスも容易になります。</span><span class="sxs-lookup"><span data-stu-id="58eae-105">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="58eae-106">また、ユーザー以外のデータ ソースMicrosoft 365レビュー セットにデータを追加して、データをレビューセットから収集したデータに加えて確認Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="58eae-106">You can also add data from non-Microsoft 365 data sources to a review set so that you can review that data in addition to the data you collect from Microsoft 365.</span></span>

<span data-ttu-id="58eae-107">検索の結果をレビュー セットに追加すると (ケース内のレビュー セットが [レビュー セット] タブに **表示** されます)、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="58eae-107">When you add the results of a search to a review set (the review sets in a case are listed on the **Review sets** tab), the following things occur:</span></span>

- <span data-ttu-id="58eae-108">検索が再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="58eae-108">The search is run again.</span></span> <span data-ttu-id="58eae-109">つまり、レビュー セットにコピーされた実際の検索結果は、検索が最後に実行された時点で返された推定結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58eae-109">This means the actual search results copied to the review set may be different than the estimated results that were returned when the search was last run.</span></span>

- <span data-ttu-id="58eae-110">検索結果のすべてのアイテムは、ライブ サービスの元のデータ ソースからコピーされ、Microsoft クラウド内Azure Storageにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="58eae-110">All items in the search results are copied from the original data source in the live services, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="58eae-111">すべてのアイテム (コンテンツとメタデータを含む) が再インデックス化され、ケース データのレビュー中にレビュー セット内のすべてのデータが完全に検索可能になります。</span><span class="sxs-lookup"><span data-stu-id="58eae-111">All items (including the content and metadata) are reindexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="58eae-112">ケース調査中にレビュー セット内のデータを検索すると、データのインデックスを再作成すると、徹底的かつ高速な検索が行ないます。</span><span class="sxs-lookup"><span data-stu-id="58eae-112">Reindexing the data results in thorough and fast searches when you search the data in the review set during the case investigation.</span></span>

- <span data-ttu-id="58eae-113">[Microsoft](encryption.md)暗号化テクノロジで暗号化されたファイルで、検索結果に返される電子メール メッセージに添付されているファイルは、電子メール メッセージと添付ファイルがレビュー セットに追加された場合に復号化されます。</span><span class="sxs-lookup"><span data-stu-id="58eae-113">A file encrypted with a [Microsoft encryption technology](encryption.md) and is attached to an email message that's returned in the search results is decrypted when the email message and attached file are added to the review set.</span></span> <span data-ttu-id="58eae-114">復号化されたファイルは、レビュー セットで確認およびクエリできます。</span><span class="sxs-lookup"><span data-stu-id="58eae-114">You can review and query the decrypted file in the review set.</span></span> <span data-ttu-id="58eae-115">復号化されたメール添付ファイルをレビュー セットに追加するには、RMS Decrypt ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="58eae-115">You have to be assigned the RMS Decrypt role to add decrypted email attachments to a review set.</span></span> <span data-ttu-id="58eae-116">詳細については、「電子情報開示ツール[の復号化」Microsoft 365参照してください](ediscovery-decryption.md)。</span><span class="sxs-lookup"><span data-stu-id="58eae-116">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

<span data-ttu-id="58eae-117">レビュー セットにデータを追加するには、[検索] タブで検索をクリックし、[結果の追加] をクリックして、フライアウト ページで [レビュー セット] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58eae-117">To add data to a review set, click a search on the **Searches** tab, and then click **Add results to review set** on the flyout page.</span></span>

<span data-ttu-id="58eae-118">既存のレビュー セットに追加するか、新しいレビュー セットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="58eae-118">You can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="58eae-119">新しいレビュー セットに追加する場合は、名前を指定し、[追加] をクリック **して** 、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="58eae-119">If adding to a new review set, specify the name and then click **Add** to display the flyout page.</span></span>

![レビュー セットを選択し、コレクション オプションを構成する](../media/AeD_AddToReviewSet.png)

<span data-ttu-id="58eae-121">レビューセットへのデータの追加は、時間のかかるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="58eae-121">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="58eae-122">このプロセスには、Microsoft 365 の元のデータ ソース (メールボックスやサイトなど) からアイテムを収集し、Azure Storage の場所 (このコピー プロセスは取り込みとも呼ばれる) にコピーしてから、アイテムのインデックスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="58eae-122">This process includes gathering items from the original data sources in Microsoft 365 (for example, from mailboxes and sites), copying them to the Azure Storage location (this copying process is also called *ingestion*), and then reindexing the items.</span></span> <span data-ttu-id="58eae-123">[ジョブ] タブまたは[検索] タブで進行状況を追跡するには、[データを確認するデータを確認する] 列の状態 **を監視** します。</span><span class="sxs-lookup"><span data-stu-id="58eae-123">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="58eae-124">レビュー セットの処理が完了したら、ケースの[レビュー セット] タブをクリックし、レビュー セットをクリックして、レビュー セット内のデータのフィルター処理、レビュー、タグ付け、エクスポートのプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="58eae-124">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process of filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="define-options-to-scope-your-collection-for-review"></a><span data-ttu-id="58eae-125">コレクションのレビュー対象範囲を設定するオプションを定義する</span><span class="sxs-lookup"><span data-stu-id="58eae-125">Define options to scope your collection for review</span></span>

<span data-ttu-id="58eae-126">検索のコンテンツを既存のレビュー セットまたは新しいレビュー セットに追加する場合、レビュー用にコンテンツを収集する方法について、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="58eae-126">When you add the content of a search to an existing or new review set, you have the following options for how to collect the content for review:</span></span>

- <span data-ttu-id="58eae-127">**SharePoint (ベータ) の** バージョンを含める: このオプションを使用して、コレクションのバージョン制限と検索パラメーターごとに SharePoint ドキュメントのすべてのバージョンのコレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="58eae-127">**Include versions from SharePoint (beta)**: Use this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="58eae-128">このオプションを選択すると、レビュー セットに追加されるアイテムのサイズが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="58eae-128">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

- <span data-ttu-id="58eae-129">**会話の取得オプション**: レビュー セットに追加されたアイテムは、スレッド会話で有効にされ、前後の会話のコンテキストでコンテンツを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58eae-129">**Conversation retrieval options**: Items added to the review set are enabled for threaded conversations to help review content in context of the back and forth conversation.</span></span> <span data-ttu-id="58eae-130">詳細については、「Review [conversations in Advanced eDiscovery」 を参照してください](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="58eae-130">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

- <span data-ttu-id="58eae-131">**最新の添付ファイルの取得を** 有効にする: このオプションを使用して、最新の添付ファイルまたはリンク されたファイルをコレクションに含め、詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="58eae-131">**Enable retrieval for modern attachments**: Use this option to include modern attachments or linked files in the collection for further review.</span></span> <span data-ttu-id="58eae-132">最新の添付ファイルに関連する検索可能なプロパティの詳細については、「[ドキュメント](document-metadata-fields-in-Advanced-eDiscovery.md)のメタデータ フィールド」を参照Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="58eae-132">For more information about the searchable properties related to modern attachments, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="58eae-133">レビュー セットにサンプルを追加する</span><span class="sxs-lookup"><span data-stu-id="58eae-133">Add a sample to a review set</span></span>

<span data-ttu-id="58eae-134">すべての検索結果をレビュー セットに追加する前に、検索の結果を詳細に検証する場合は、検索結果のサンプルをレビュー セットに追加する代わりに、レビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="58eae-134">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="58eae-135">レビュー セットにサンプルを追加するには、[検索] タブで検索をクリックし、フライアウト ページの [**サンプル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58eae-135">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="58eae-136">[サンプリング **パラメーター] ページ** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="58eae-136">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="58eae-137">**信頼レベル % と\*\*\*\*信頼区間 %** - レビュー セットに追加されるアイテムは、設定した統計パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="58eae-137">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="58eae-138">結果をサンプリングするときに通常信頼度と間隔を使用する場合は、ドロップダウン ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="58eae-138">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="58eae-139">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58eae-139">Otherwise, use the default settings.</span></span>

- <span data-ttu-id="58eae-140">**ランダム サンプル %** - レビュー セットに追加されるアイテムは、検索によって返されるアイテムの総数に対する指定された割合のランダムな選択に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="58eae-140">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="58eae-141">前のオプションのいずれかを選択して構成したら、レビュー セットを選択してサンプルを追加し、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="58eae-141">After selecting and configuring one of the previous options, choose a review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="58eae-142">繰り返しますが、[ジョブ]タブまたは [検索] タブの進行状況を追跡するには、[データを確認するデータを確認する] 列の状態 **を監視** します。</span><span class="sxs-lookup"><span data-stu-id="58eae-142">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="58eae-143">光学式文字認識</span><span class="sxs-lookup"><span data-stu-id="58eae-143">Optical character recognition</span></span>

<span data-ttu-id="58eae-144">検索結果をレビュー セットに追加すると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって画像からテキストが自動的に抽出され、レビュー セットに追加されたデータが含まれる画像テキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="58eae-144">When you add search results to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the data that's added to a review set.</span></span> <span data-ttu-id="58eae-145">抽出されたテキストは、レビュー セットで選択したイメージ ファイルのテキスト ビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="58eae-145">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="58eae-146">これにより、画像内のテキストをさらにレビューおよび分析できます。</span><span class="sxs-lookup"><span data-stu-id="58eae-146">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="58eae-147">OCR は、圧縮されていないファイル、電子メールの添付ファイル、および埋め込み画像の場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="58eae-147">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="58eae-148">OCRでサポートされている画像ファイル形式のリストについては、[「高度なeDiscoveryでサポートされているファイルタイプ」](supported-filetypes-ediscovery20.md#image)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="58eae-148">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="58eae-149">Advanced eDiscovery で作成するケースごとにOCR機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58eae-149">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="58eae-150">詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="58eae-150">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
