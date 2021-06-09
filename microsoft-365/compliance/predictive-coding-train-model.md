---
title: 予測コーディング モデルをトレーニングAdvanced eDiscovery
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
description: ''
ms.openlocfilehash: ef6d1cf23d6cca58f4226696bc63c1dea5816cc1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822551"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="6504b-102">予測コーディング モデルのトレーニング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="6504b-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="6504b-103">Advanced eDiscovery で予測コーディング モデルを作成した後、次の手順では、最初のトレーニング ラウンドを実行して、レビュー セット内の関連性と関連性の高いコンテンツについてモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="6504b-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="6504b-104">トレーニングの最初のラウンドを完了したら、後続のトレーニング ラウンドを実行して、関連するコンテンツと関連性のないコンテンツを予測するモデルの能力を向上できます。</span><span class="sxs-lookup"><span data-stu-id="6504b-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="6504b-105">予測コーディング ワークフローを確認するには、「[](predictive-coding-overview.md#the-predictive-coding-workflow)予測コーディングの概要」を参照Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6504b-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery ](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="6504b-106">モデルをトレーニングする前に</span><span class="sxs-lookup"><span data-stu-id="6504b-106">Before you train a model</span></span>

- <span data-ttu-id="6504b-107">トレーニングラウンド中に、ドキュメント内の **コンテンツの関連性** に基づいて、アイテムに関連または関連性のないラベルを付けします。 </span><span class="sxs-lookup"><span data-stu-id="6504b-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="6504b-108">メタデータ フィールドの値を基に決定を下す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6504b-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="6504b-109">たとえば、電子メール メッセージや電子メール Teamsの場合は、メッセージ参加者にラベル付け決定を基にしません。</span><span class="sxs-lookup"><span data-stu-id="6504b-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span> 

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="6504b-110">モデルを初めてトレーニングする</span><span class="sxs-lookup"><span data-stu-id="6504b-110">Train a model for the first time</span></span>

1. <span data-ttu-id="6504b-111">コンプライアンス センターでMicrosoft 365ケースを開Advanced eDiscovery、[レビュー セット]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="6504b-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="6504b-112">レビュー セットを開き **、[Analytics 予測** コーディングの  >  **管理 (プレビュー) ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6504b-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="6504b-113">[予測 **コーディング モデル (プレビュー)] ページ** で、トレーニングするモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6504b-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="6504b-114">[概要] **タブの** [ラウンド **1] で**、[次のトレーニング ラウンドの開始 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6504b-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="6504b-115">[ **トレーニング]** タブが表示され、ラベル付けするアイテムが 50 件含まれています。</span><span class="sxs-lookup"><span data-stu-id="6504b-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="6504b-116">各ドキュメントを確認し、閲覧 **ウィンドウ** の下部にある [関連する] または [関連しない] ボタンを選択してラベルを付きます。</span><span class="sxs-lookup"><span data-stu-id="6504b-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![各ドキュメントに関連性の高いラベルを付け、関連性の高いラベルを付けない](..\media\TrainModel1.png)

6. <span data-ttu-id="6504b-118">50 アイテムのラベルを付け終わったら、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6504b-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="6504b-119">システムがラベル付けから "学習" し、モデルを更新するには数分かかります。</span><span class="sxs-lookup"><span data-stu-id="6504b-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="6504b-120">このプロセスが完了すると、[予測コーディングモデル (プレビュー)] ページにモデルの状態が [準備完了 **] と表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="6504b-121">追加のトレーニング ラウンドを実行する</span><span class="sxs-lookup"><span data-stu-id="6504b-121">Perform additional training rounds</span></span>

<span data-ttu-id="6504b-122">トレーニングの最初のラウンドを実行した後、前のセクションの手順に従って、後続のトレーニング ラウンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6504b-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="6504b-123">唯一の違いは、モデルの [概要] タブで更新されるトレーニング **ラウンドの数** です。たとえば、最初のトレーニング ラウンドを実行した後、[次のトレーニング ラウンドの開始] をクリックして、トレーニングの第 2 ラウンドを開始できます。</span><span class="sxs-lookup"><span data-stu-id="6504b-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="6504b-124">などなど。</span><span class="sxs-lookup"><span data-stu-id="6504b-124">And so on.</span></span>

<span data-ttu-id="6504b-125">トレーニングの各ラウンド (進行中のトレーニングと完了したトレーニングの両方) が、モデルの **[トレーニング** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="6504b-126">トレーニング ラウンドを選択すると、ラウンドの情報と指標を含むフライアウト ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="6504b-127">トレーニング ラウンドを実行した後の処理</span><span class="sxs-lookup"><span data-stu-id="6504b-127">What happens after you perform a training round</span></span>

<span data-ttu-id="6504b-128">最初のトレーニング ラウンドを実行すると、次の処理を実行するジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="6504b-129">トレーニング セット内の 40 項目のラベル付け方法に基づいて、モデルはラベル付けから学習し、より正確に更新します。</span><span class="sxs-lookup"><span data-stu-id="6504b-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="6504b-130">次に、モデルはレビュー セット全体の各アイテムを処理し **、0** (関連しない) から **1** (関連しない) の間の予測スコアを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6504b-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>  

- <span data-ttu-id="6504b-131">モデルは、トレーニング ラウンド中にラベル付けしたコントロール セット内の 10 項目に予測スコアを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6504b-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="6504b-132">モデルは、これらの 10 アイテムの予測スコアと、トレーニング ラウンド中にアイテムに割り当てた実際のラベルを比較します。</span><span class="sxs-lookup"><span data-stu-id="6504b-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="6504b-133">この比較に基づいて、モデルは次の分類 (コントロール セットの混同 *行列と呼* ばれる) を識別して、モデルの予測パフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="6504b-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>
  
  |          |<span data-ttu-id="6504b-134">モデルは、アイテムが関連すると予測します</span><span class="sxs-lookup"><span data-stu-id="6504b-134">Model predicts item is relevant</span></span> |<span data-ttu-id="6504b-135">モデルはアイテムが関連しないと予測します</span><span class="sxs-lookup"><span data-stu-id="6504b-135">Model predicts item is not relevant</span></span> |
  |:---------|:---------|:---------|
  |<span data-ttu-id="6504b-136">**レビューアーのラベルアイテムを関連付け**</span><span class="sxs-lookup"><span data-stu-id="6504b-136">**Reviewer labels item as relevant**</span></span>| <span data-ttu-id="6504b-137">正の正の値</span><span class="sxs-lookup"><span data-stu-id="6504b-137">True positive</span></span>| <span data-ttu-id="6504b-138">誤検知</span><span class="sxs-lookup"><span data-stu-id="6504b-138">False positive</span></span> |
  |<span data-ttu-id="6504b-139">**レビューアーがアイテムに関連性の高いラベルを付け**</span><span class="sxs-lookup"><span data-stu-id="6504b-139">**Reviewer labels item as not relevant**</span></span>| <span data-ttu-id="6504b-140">False 負</span><span class="sxs-lookup"><span data-stu-id="6504b-140">False negative</span></span> |<span data-ttu-id="6504b-141">True 負</span><span class="sxs-lookup"><span data-stu-id="6504b-141">True negative</span></span> |
  ||||

  <span data-ttu-id="6504b-142">これらの比較に基づいて、モデルは、F スコア、精度、および呼び出しメトリックの値と、それぞれの誤差幅を導き出します。</span><span class="sxs-lookup"><span data-stu-id="6504b-142">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="6504b-143">これらのモデルのパフォーマンス 指標のスコアは、トレーニング ラウンドのフライアウト ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-143">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="6504b-144">これらの指標の説明については、「予測コーディングリファレンス [」を参照してください](predictive-coding-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="6504b-144">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="6504b-145">最後に、モデルは、次のトレーニング ラウンドに使用される次の 50 項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="6504b-145">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="6504b-146">今回は、コントロール セットから 20 アイテム、レビュー セットから 30 の新しいアイテムを選択し、次のラウンドのトレーニング セットとして指定します。</span><span class="sxs-lookup"><span data-stu-id="6504b-146">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="6504b-147">次のトレーニング ラウンドのサンプリングは、一様にサンプリングされません。</span><span class="sxs-lookup"><span data-stu-id="6504b-147">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="6504b-148">モデルは、レビュー セットからアイテムのサンプリング選択を最適化し、予測があいまいなアイテムを選択します。つまり、予測スコアは 0.5 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="6504b-148">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="6504b-149">このプロセスは、バイアス選択 *と呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="6504b-149">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="6504b-150">後続のトレーニング ラウンドを実行した後の処理</span><span class="sxs-lookup"><span data-stu-id="6504b-150">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="6504b-151">後続のトレーニング ラウンド (最初のトレーニング ラウンドの後) を実行した後、モデルは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="6504b-151">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="6504b-152">モデルは、そのトレーニング のラウンドでトレーニング セットに適用したラベルに基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-152">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="6504b-153">システムは、コントロール セット内のアイテムに対するモデルの予測スコアを評価し、スコアがコントロール セット内のアイテムのラベル付け方法と一致するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6504b-153">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="6504b-154">評価は、すべてのトレーニング ラウンドのコントロール セットのすべてのラベル付きアイテムに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="6504b-154">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="6504b-155">この評価の結果は、モデルの [概要] タブ **のダッシュボードに** 組み込まれる。</span><span class="sxs-lookup"><span data-stu-id="6504b-155">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="6504b-156">更新されたモデルは、レビュー セット内のすべてのアイテムを再処理し、更新された予測スコアを各アイテムに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6504b-156">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6504b-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="6504b-157">Next steps</span></span>

<span data-ttu-id="6504b-158">最初のトレーニング ラウンドを実行した後、より多くのトレーニング ラウンドを実行するか、モデルの予測スコア フィルターをレビュー セットに適用して、モデルが予測したアイテムを関連性の高いまたは関連性の低いアイテムとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="6504b-158">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="6504b-159">詳細については、「予測スコア フィルター [をレビュー セットに適用する」を参照してください](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="6504b-159">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
