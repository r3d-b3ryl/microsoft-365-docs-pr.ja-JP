---
title: ドラフト コレクションをレビュー セットにコミットする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 下書きコレクションを作成して反復処理した後、そのコレクションをレビュー セットにコミットできます。 下書きコレクションをコミットすると、収集されたアイテムがケースのレビュー セットに追加されます。 収集したアイテムがレビュー セットに含められたら、それらを分析、確認、およびエクスポートできます。
ms.openlocfilehash: dceb661d9586e324482dc4f56bce12fafaf9b251
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276979"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="98f10-105">下書きコレクションをレビュー セットにコミットAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="98f10-105">Commit a draft collection to a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="98f10-106">下書きコレクションで収集したアイテムに満足し、それらを分析、タグ付け、レビューする準備ができたら、ケース内のレビュー セットにコレクションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="98f10-106">When you're satisfied with the items you've collected in a draft collection and are ready to analyze, tag, and review them, you can add a collection to a review set in the case.</span></span> <span data-ttu-id="98f10-107">下書きコレクションをレビュー セットにコミットすると、収集されたアイテムは、レビュー セット内の元のコンテンツMicrosoft 365にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="98f10-107">When you commit a draft collection to a review set, collected items are copied from their original content location in Microsoft 365 to a review set.</span></span> <span data-ttu-id="98f10-108">レビュー セットは、Microsoft クラウド内の安全Azure Storageな場所です。</span><span class="sxs-lookup"><span data-stu-id="98f10-108">A review set is a secure, Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>

## <a name="commit-a-draft-collection-to-a-review-set"></a><span data-ttu-id="98f10-109">ドラフト コレクションをレビュー セットにコミットする</span><span class="sxs-lookup"><span data-stu-id="98f10-109">Commit a draft collection to a review set</span></span>

1. <span data-ttu-id="98f10-110">[コレクション] Microsoft 365 コンプライアンス センターケースを開Advanced eDiscoveryし、[コレクション] タブを選択して、ケース内のコレクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="98f10-110">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, and then select the **Collections** tab to display a list of the collections in the case.</span></span>

   ![ケース内のコレクションの一覧](../media/CommitDraftCollections1.png)

   > [!TIP]
   > <span data-ttu-id="98f10-112">[状態] `Estimated` 列の **値** は、レビュー セットに追加できる下書きコレクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="98f10-112">A value of `Estimated` in the **Status** column identifies the draft collections that can be added to a review set.</span></span> <span data-ttu-id="98f10-113">状態は `Committed` 、コレクションが既にレビュー セットに追加済みかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98f10-113">A status of `Committed` indicates that a collection has already been added to a review set.</span></span>

2. <span data-ttu-id="98f10-114">[コレクション **] ページ** で、レビュー セットにコミットする下書きコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-114">On the **Collections** page, select the draft collection that you want to commit to a review set.</span></span>

3. <span data-ttu-id="98f10-115">フライアウト ページの下部で、[アクションの編集]**コレクション**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98f10-115">On the bottom of the flyout page, select **Actions** > **Edit collection**.</span></span>

4. <span data-ttu-id="98f10-116">コレクションの編集ウィザードで、[下書きまたは収集 **の** 保存] **ページが表示** されるまで [次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98f10-116">In the edit collection wizard, click **Next** until the **Save draft or collect** page is displayed.</span></span>

5. <span data-ttu-id="98f10-117">以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="98f10-117">Configure the following settings:</span></span>

   1. <span data-ttu-id="98f10-118">[アイテム **の収集と追加] を選択して、レビュー セットを確認します**。</span><span class="sxs-lookup"><span data-stu-id="98f10-118">Select **Collect items and add to review set**.</span></span>

   2. <span data-ttu-id="98f10-119">コレクションを新しいレビュー セット (コレクションの送信後に作成) に追加するか、既存のレビュー セットに追加するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="98f10-119">Decide whether to add the collection to a new review set (which is created after you submit the collection) or add it to an existing review set.</span></span> <span data-ttu-id="98f10-120">決定に基づいてこのセクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="98f10-120">Complete this section based on your decision.</span></span>

   3. <span data-ttu-id="98f10-121">追加のコレクション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="98f10-121">Configure the additional collection settings:</span></span>

       - <span data-ttu-id="98f10-122">**TeamsメッセージYammerする**: 検索クエリによって返されるチャット アイテムをコレクションに追加するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-122">**Teams and Yammer messages**: Select this option to add conversation threads to the collection that include the chat items returned by the search query in the collection.</span></span> <span data-ttu-id="98f10-123">つまり、検索条件に一致するアイテムを含むチャット会話が再構築されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-123">This means that the chat conversation that contains items that match the search criteria is reconstructed.</span></span> <span data-ttu-id="98f10-124">これにより、前後の会話のコンテキストでチャット アイテムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="98f10-124">This lets you review chat items in the context of the back and forth conversation.</span></span> <span data-ttu-id="98f10-125">詳細については、「スレッドの[スレッド化」を参照Advanced eDiscovery。](conversation-review-sets.md)</span><span class="sxs-lookup"><span data-stu-id="98f10-125">For more information, see [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).</span></span>

       - <span data-ttu-id="98f10-126">**クラウド添付** ファイル: コレクションの結果がレビュー セットに追加された場合に、最新の添付ファイルまたはリンク されたファイルを含める場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-126">**Cloud attachments**: Select this option to include modern attachments or linked files when the collection results are added to the review set.</span></span> <span data-ttu-id="98f10-127">つまり、最新の添付ファイルまたはリンク されたファイルのターゲット ファイルがレビュー セットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-127">This means that the target file of a modern attachment or linked file is added to the review set.</span></span>

       - <span data-ttu-id="98f10-128">**SharePointバージョン**: コレクションのバージョン制限と検索パラメーターに基SharePoint ドキュメントのすべてのバージョンのコレクションを有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-128">**SharePoint versions**: Select this option to enable the collection of all version of a SharePoint document per the version limits and search parameters of the collection.</span></span> <span data-ttu-id="98f10-129">このオプションを選択すると、レビュー セットに追加されるアイテムのサイズが大幅に増加します。</span><span class="sxs-lookup"><span data-stu-id="98f10-129">Selecting this option will significantly increase the size of items that are added to the review set.</span></span>

   4. <span data-ttu-id="98f10-130">レビュー セットに追加するコレクションのスケールを定義する設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="98f10-130">Configure the settings to define the scale of the collection to add to the review set:</span></span>

      - <span data-ttu-id="98f10-131">**[すべてのコレクション結果を追加** する]: コレクションの検索条件に一致するアイテムをレビュー セットに追加するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-131">**Add all collection results**: Select this option to add all the items that match the search criteria of the collection to the review set.</span></span>

      - <span data-ttu-id="98f10-132">**コレクション結果のサンプルを追加** する: すべての結果を追加する代わりに、コレクション結果のサンプルをレビュー セットに追加するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-132">**Add a sample of the collection results**: Select this option to add a sample of the collection results to the review set instead of adding all results.</span></span> <span data-ttu-id="98f10-133">このオプションを選択した場合は、[サンプル パラメーターの編集] **をクリックし** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98f10-133">If you select this option, click **Edit sample parameters** and choose one of the following options:</span></span>

         - <span data-ttu-id="98f10-134">**信頼度に基づく** サンプル: コレクションのアイテムがレビュー セットに追加される場合は、設定した統計パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="98f10-134">**Sample based on confidence**: Items from the collection are added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="98f10-135">結果をサンプリングするときに通常信頼度と間隔を使用する場合は、ドロップダウン ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="98f10-135">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="98f10-136">それ以外の場合は、既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="98f10-136">Otherwise, use the default settings.</span></span>

         - <span data-ttu-id="98f10-137">**ランダムサンプル**: コレクションのアイテムは、検索によって返されたアイテムの総数に対する指定された割合のランダムな選択に基づいてレビュー セットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-137">**Randomly sample**: Items from the collection are added to the review set based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

6. <span data-ttu-id="98f10-138">[コレクション **の確認] ページ** で、前のページで構成したコレクション設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="98f10-138">On the **Review your collection** page, you can review the collection settings that you configured on the previous page.</span></span> <span data-ttu-id="98f10-139">変更 **する場合** は、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98f10-139">Click **Edit** if you want to change them.</span></span>

7. <span data-ttu-id="98f10-140">[送信 **] を** クリックして下書きコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="98f10-140">Click **Submit** to create the draft collection.</span></span> <span data-ttu-id="98f10-141">コレクションが作成されたという確認ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-141">A page is displayed confirming that the collection was created.</span></span>

## <a name="what-happens-after-you-commit-a-draft-collection"></a><span data-ttu-id="98f10-142">下書きコレクションをコミットした後の操作</span><span class="sxs-lookup"><span data-stu-id="98f10-142">What happens after you commit a draft collection</span></span>

<span data-ttu-id="98f10-143">下書きコレクションをレビュー セットにコミットすると、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="98f10-143">When you commit a draft collection to a review set, the following things happen:</span></span>

- <span data-ttu-id="98f10-144">コレクションをコミットする新しいレビュー セットを作成した場合、レビュー セットが作成され、ケースの **[** レビュー セット] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-144">If you created a new review set to commit the collection to, the review set is created and displayed on the **Review sets** tab in the case.</span></span> <span data-ttu-id="98f10-145">新しいレビュー セットの状態は [準備完了] **です**。</span><span class="sxs-lookup"><span data-stu-id="98f10-145">The status of the new review set is **Ready**.</span></span> <span data-ttu-id="98f10-146">この状態の値は、レビュー セットが作成された状態を意味します。コレクションがレビュー セットに追加されたという意味ではない。</span><span class="sxs-lookup"><span data-stu-id="98f10-146">This status value means the review set has been created; it doesn't mean that the collection has been added to the review set.</span></span> <span data-ttu-id="98f10-147">コレクション内のアイテムをレビュー セットに追加する状態が [コレクション] タブ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-147">The status of adding items in the collection to the review set is displayed on the **Collections** tab.</span></span>

- <span data-ttu-id="98f10-148">コレクション検索クエリが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-148">The collection search query is run again.</span></span> <span data-ttu-id="98f10-149">つまり、レビュー セットにコピーされた実際の検索結果は、コレクションの検索が最後に実行された時点で返された推定結果とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="98f10-149">This means the actual search results copied to the review set may be different than the estimated results that were returned when the collection search was last run.</span></span>

- <span data-ttu-id="98f10-150">検索結果のすべてのアイテムは、ライブ サービスの元のデータ ソースからコピーされ、Microsoft クラウド内Azure Storageにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="98f10-150">All items in the search results are copied from the original data source in the live service, and copied to a secure Azure Storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="98f10-151">保管担当者または保管担当者以外のデータ ソースに含められないすべてのアイテム (コンテンツとメタデータを含 *む)* は、ケース データのレビュー中にレビュー セット内のすべてのデータが完全に検索可能な (ディープ インデックスと呼ばれるプロセスで) インデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-151">All items (including the content and metadata) that aren't located in custodian or non-custodian data sources are reindexed (in a process called *deep indexing*) so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="98f10-152">コレクション内のコンテンツのインデックスを再作成すると、ケース調査中にレビュー セット内のコンテンツを検索またはフィルター処理すると、完全かつ迅速に検索されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-152">Reindexing the content in a collection results in thorough and fast searches when you search or filter the content in the review set during the case investigation.</span></span>

- <span data-ttu-id="98f10-153">検索結果SharePoint返されるOneDriveドキュメントおよび暗号化されたファイル、および暗号化されたファイルは、コレクションをレビュー セットにコミットすると復号化されます。</span><span class="sxs-lookup"><span data-stu-id="98f10-153">Encrypted SharePoint and OneDrive documents and encrypted files attached email messages that's returned in the search results are decrypted when you commit the collection to a review set.</span></span> <span data-ttu-id="98f10-154">復号化されたファイルは、レビュー セットで確認およびクエリできます。</span><span class="sxs-lookup"><span data-stu-id="98f10-154">You can review and query the decrypted files in the review set.</span></span> <span data-ttu-id="98f10-155">詳細については、「電子情報開示ツール[の復号化」Microsoft 365参照してください](ediscovery-decryption.md)。</span><span class="sxs-lookup"><span data-stu-id="98f10-155">For more information, see [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).</span></span>

- <span data-ttu-id="98f10-156">光学式文字認識 (OCR) 機能は、画像からテキストを抽出し、レビュー セットに追加されたコンテンツを含む画像テキストを含みます。</span><span class="sxs-lookup"><span data-stu-id="98f10-156">Optical character recognition (OCR) functionality extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="98f10-157">詳細については、この記事の「 [光学式文字認識」](#optical-character-recognition) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98f10-157">For more information, see the [Optical character recognition](#optical-character-recognition) section in this article.</span></span>

- <span data-ttu-id="98f10-158">コミットが正常に完了すると、[コレクション] タブの状態列の **値が** に変更されます `Committed` 。</span><span class="sxs-lookup"><span data-stu-id="98f10-158">After the commit is successfully completed, the value of the status column of on the **Collections** tab is changed to `Committed`.</span></span>

## <a name="optical-character-recognition"></a><span data-ttu-id="98f10-159">光学式文字認識</span><span class="sxs-lookup"><span data-stu-id="98f10-159">Optical character recognition</span></span>

<span data-ttu-id="98f10-160">コレクションをレビュー セットにコミットすると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって画像からテキストが自動的に抽出され、レビュー セットに追加されたコンテンツが含まれる画像テキストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98f10-160">When you commit a collection to a review set, optical character recognition (OCR) functionality in Advanced eDiscovery automatically extracts text from images, and includes the image text with the content that's added to a review set.</span></span> <span data-ttu-id="98f10-161">抽出されたテキストは、レビュー セットで選択したイメージ ファイルのテキスト ビューアーで表示できます。</span><span class="sxs-lookup"><span data-stu-id="98f10-161">You can view the extracted text in the Text viewer of the selected image file in the review set.</span></span> <span data-ttu-id="98f10-162">これにより、画像内のテキストをさらにレビューおよび分析できます。</span><span class="sxs-lookup"><span data-stu-id="98f10-162">This lets you conduct further review and analysis on text in images.</span></span> <span data-ttu-id="98f10-163">OCR は、圧縮されていないファイル、電子メールの添付ファイル、および埋め込み画像の場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="98f10-163">OCR is supported for loose files, email attachments, and embedded images.</span></span> <span data-ttu-id="98f10-164">OCRでサポートされている画像ファイル形式のリストについては、[「高度なeDiscoveryでサポートされているファイルタイプ」](supported-filetypes-ediscovery20.md#image)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98f10-164">For a list of image file formats that are supported for OCR, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).</span></span>

<span data-ttu-id="98f10-165">Advanced eDiscovery で作成するケースごとにOCR機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98f10-165">You have to enable OCR functionality for each case that you create in Advanced eDiscovery.</span></span> <span data-ttu-id="98f10-166">詳細については、「検索と分析 [の設定を構成する」を参照してください](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)。</span><span class="sxs-lookup"><span data-stu-id="98f10-166">For more information, see [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).</span></span>
