---
title: 予測コーディング (Advanced eDiscovery - クイック スタート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 予測コーディング モジュールの使用を開始する方法については、Advanced eDiscovery。 この記事では、予測コーディングを使用して、調査に最も関連性の高いレビュー セット内のコンテンツを識別するエンドツーエンドのプロセスについて説明します。
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822559"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="73edf-104">クイック スタート: クイック スタートでの予測Advanced eDiscovery (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="73edf-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="73edf-105">この記事では、予測コーディングを使用する方法のクイック スタートをAdvanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="73edf-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="73edf-106">予測コーディング モジュールは、Advanced eDiscoveryのインテリジェントな機械学習機能をAdvanced eDiscovery、レビューするコンテンツの量を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73edf-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="73edf-107">予測コーディングを使用すると、大量のケース コンテンツを、レビューに優先順位付けできる関連する一連のアイテムに対して削減し、調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="73edf-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="73edf-108">これは、レビュー セット内の最も関連性の高いアイテムのレビューに優先順位を付けるのに役立つ、独自の予測コーディング モデルを作成してトレーニングすることで実現されます。</span><span class="sxs-lookup"><span data-stu-id="73edf-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="73edf-109">予測コーディング プロセスの概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="73edf-109">Here's an a quick overview of the predictive coding process:</span></span>

![予測コーディングのクイック スタート プロセス](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="73edf-111">開始するには、モデルを作成し、関連性の高いアイテムまたは関連性の高いアイテムを 50 アイテムまでラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="73edf-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="73edf-112">次に、システムはこのトレーニングを使用して、レビュー セット内のすべてのアイテムに予測スコアを適用します。</span><span class="sxs-lookup"><span data-stu-id="73edf-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="73edf-113">これにより、予測スコアに基づいてアイテムをフィルター処理できます。これにより、最も関連性の高い (または関連性の低い) アイテムを最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="73edf-114">より高い読み上げ率とリコール率を持つモデルをトレーニングする場合は、モデルが安定するまで、後続のトレーニング ラウンドでアイテムのラベル付けを続行できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="73edf-115">モデルが安定化したら、最終的な予測フィルターを適用して、確認する項目の優先順位を設定できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="73edf-116">予測コーディングの詳細な概要については、「[予測](predictive-coding-overview.md)コーディングの概要」を参照Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="73edf-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="73edf-117">手順 1: 新しい予測コーディング モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="73edf-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="73edf-118">最初の手順は、レビュー セットに新しい予測コーディング モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="73edf-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="73edf-119">コンプライアンス センターでMicrosoft 365ケースを開Advanced eDiscovery、[レビュー セット]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="73edf-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="73edf-120">レビュー セットを開き **、[Analytics 予測** コーディングの  >  **管理 (プレビュー) ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![レビュー セットの [分析] ドロップダウン メニューをクリックして、[予測コーディング] ページに移動します。](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="73edf-122">[予測 **コーディング モデル (プレビュー)]** ページで、[新しいモデル] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="73edf-123">[フライアウト] ページで、モデルの名前とオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="73edf-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="73edf-124">[保存 **] を** クリックしてモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="73edf-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="73edf-125">システムがモデルを準備するには数分かかります。</span><span class="sxs-lookup"><span data-stu-id="73edf-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="73edf-126">準備ができたら、トレーニングの第 1 ラウンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="73edf-127">詳細な手順については、「予測コーディング モデルの [作成」を参照してください](predictive-coding-create-model.md)。</span><span class="sxs-lookup"><span data-stu-id="73edf-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="73edf-128">手順 2: 最初のトレーニング ラウンドを実行する</span><span class="sxs-lookup"><span data-stu-id="73edf-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="73edf-129">モデルを作成した後、次の手順では、関連するアイテムまたは関連性のないラベルを付け、最初のトレーニング ラウンドを完了します。</span><span class="sxs-lookup"><span data-stu-id="73edf-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="73edf-130">レビュー セットを開き **、[Analytics 予測** コーディングの  >  **管理 (プレビュー) ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="73edf-131">[予測 **コーディング モデル (プレビュー)] ページ** で、トレーニングするモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="73edf-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="73edf-132">[概要] **タブの** [ラウンド **1] で**、[次のトレーニング ラウンドの開始 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="73edf-133">[ **トレーニング]** タブが表示され、ラベル付けするアイテムが 50 件含まれています。</span><span class="sxs-lookup"><span data-stu-id="73edf-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="73edf-134">各ドキュメントを確認し、閲覧 **ウィンドウ** の下部にある [関連する] または [関連しない] ボタンを選択してラベルを付きます。</span><span class="sxs-lookup"><span data-stu-id="73edf-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![各ドキュメントに関連性の高いラベルを付け、関連性の高いラベルを付けない](..\media\TrainModel1.png)

5. <span data-ttu-id="73edf-136">50 アイテムのラベルを付け終わったら、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="73edf-137">システムがラベル付けから "学習" し、モデルを更新するには数分かかります。</span><span class="sxs-lookup"><span data-stu-id="73edf-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="73edf-138">このプロセスが完了すると、[予測コーディングモデル (プレビュー)] ページにモデルの状態が [準備完了 **] と表示** されます。</span><span class="sxs-lookup"><span data-stu-id="73edf-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="73edf-139">詳細な手順については、「予測コーディング モデルの [トレーニング」を参照してください](predictive-coding-train-model.md)。</span><span class="sxs-lookup"><span data-stu-id="73edf-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="73edf-140">手順 3: レビュー セット内のアイテムに予測スコア フィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="73edf-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="73edf-141">1 回のトレーニング ラウンドをリースで実行した後、レビュー セット内のアイテムに予測スコア フィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="73edf-142">これにより、モデルが予測したアイテムを関連性の高いアイテムまたは関連性の高いアイテムとして確認できます。</span><span class="sxs-lookup"><span data-stu-id="73edf-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="73edf-143">レビュー セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="73edf-143">Open the review set.</span></span>

   ![[フィルター] をクリックして [フィルター] フライアウト ページを表示します。](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="73edf-145">事前に読み込まれた既定のフィルターは、レビュー セット ページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="73edf-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="73edf-146">これらの設定は Any のままに **できます**。</span><span class="sxs-lookup"><span data-stu-id="73edf-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="73edf-147">[フィルター **] を** クリックして 、[ **フィルター] フライアウト** ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="73edf-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="73edf-148">**[Analytics &予測コーディング] セクションを展開** して、一連のフィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="73edf-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![[Analytics &コーディング] セクションの予測スコア フィルター](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="73edf-150">予測スコア フィルターの名前付け規則は、 **予測スコア (モデル名) です**。</span><span class="sxs-lookup"><span data-stu-id="73edf-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="73edf-151">たとえば、モデル **A** という名前のモデルの予測スコア フィルター名は **、予測スコア (モデル A) です**。</span><span class="sxs-lookup"><span data-stu-id="73edf-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="73edf-152">使用する予測スコア フィルターを選択し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="73edf-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="73edf-153">[レビュー セット] ページで、予測スコア フィルターのドロップダウンをクリックし、予測スコア範囲の最小値と最大値を入力します。</span><span class="sxs-lookup"><span data-stu-id="73edf-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="73edf-154">たとえば、次のスクリーンショットは、.5 ~ **1.0** の予測スコア **範囲を示しています**。</span><span class="sxs-lookup"><span data-stu-id="73edf-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![予測スコア フィルターの最小値と最大値](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="73edf-156">フィルターの外側をクリックすると、自動的にレビュー セットにフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="73edf-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="73edf-157">指定した範囲内の予測スコアを持つドキュメントの一覧が、レビュー セット ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="73edf-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="73edf-158">詳細な手順については、「予測フィルターを [レビュー セットに適用する」を参照してください](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="73edf-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="73edf-159">手順 4: より多くのトレーニング ラウンドを実行する</span><span class="sxs-lookup"><span data-stu-id="73edf-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="73edf-160">多くの場合、モジュールをトレーニングするために、より多くのトレーニング ラウンドを実行して、レビュー セット内の関連性の高いアイテムや関連性の低いアイテムをより適切に予測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73edf-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="73edf-161">一般に、要件を満たすのに十分に安定するまで、モデルを十分な時間トレーニングします。</span><span class="sxs-lookup"><span data-stu-id="73edf-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="73edf-162">詳細については、「追加のトレーニング [ラウンドを実行する」を参照してください。](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="73edf-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="73edf-163">手順 5: 最終的な予測スコア フィルターを適用してレビューの優先順位を設定する</span><span class="sxs-lookup"><span data-stu-id="73edf-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="73edf-164">手順 3 の手順を繰り返して、最終的な予測スコアをレビュー セットに適用し、すべてのトレーニング ラウンドを完了し、モデルを安定化した後、関連するアイテムと関連性の低いアイテムのレビューに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="73edf-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
