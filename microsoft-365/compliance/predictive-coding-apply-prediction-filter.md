---
title: レビュー セット内のアイテムに予測スコア フィルターを適用する
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
description: 予測スコア フィルターを使用して、予測コーディング モデルが関連性がある、または関連性が低いと予測されるアイテムを表示します。
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822527"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="2e210-103">予測スコア フィルターをレビュー セットに適用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2e210-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="2e210-104">Advanced eDiscovery で予測コーディング モデルを作成し、それが安定している位置までトレーニングした後、予測スコア フィルターを適用して、モデルが関連性が高い (または関連性が低い) と判断したレビュー セットアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2e210-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="2e210-105">モデルを作成すると、対応する予測スコア フィルターも作成されます。</span><span class="sxs-lookup"><span data-stu-id="2e210-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="2e210-106">このフィルターを使用すると、指定した範囲内に予測スコアが割り当てられたアイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2e210-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="2e210-107">一般に **、0** ~ **.5** の予測スコアは、モデルが予測したアイテムには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="2e210-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="2e210-108">予測スコアが .5 ~ **1.0** **の** 間に割り当てられたアイテムは、モデルが予測したアイテムが関連しています。</span><span class="sxs-lookup"><span data-stu-id="2e210-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="2e210-109">予測スコア フィルターを使用する 2 つの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2e210-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="2e210-110">モデルが関連すると予測したレビュー セット内のアイテムのレビューに優先順位を付ける。</span><span class="sxs-lookup"><span data-stu-id="2e210-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="2e210-111">モデルが予測したレビュー セットのアイテムは関連付けされません。</span><span class="sxs-lookup"><span data-stu-id="2e210-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="2e210-112">または、予測スコア フィルターを使用して、関連性の低いアイテムのレビューの優先順位を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2e210-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="2e210-113">予測スコア フィルターを適用する前に</span><span class="sxs-lookup"><span data-stu-id="2e210-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="2e210-114">対応する予測スコア フィルターが作成される予測コーディング モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e210-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="2e210-115">トレーニング ラウンドの後に予測スコア フィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="2e210-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="2e210-116">ただし、複数のラウンドを実行した後、または予測スコア フィルターを使用する前に、モデルが安定するまで待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e210-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="2e210-117">予測スコア フィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="2e210-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="2e210-118">コンプライアンス センター Microsoft 365ケースを開Advanced eDiscovery、[レビュー セット] タブを選択し、レビュー セットを開きます。</span><span class="sxs-lookup"><span data-stu-id="2e210-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![[フィルター] をクリックして [フィルター] フライアウト ページを表示します。](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="2e210-120">事前に読み込まれた既定のフィルターは、レビュー セット ページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e210-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="2e210-121">これらの設定は Any のままに **できます**。</span><span class="sxs-lookup"><span data-stu-id="2e210-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="2e210-122">[フィルター **] を** クリックして 、[ **フィルター] フライアウト** ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="2e210-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="2e210-123">**[Analytics &予測コーディング] セクションを展開** して、一連のフィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="2e210-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![[Analytics &コーディング] セクションの予測スコア フィルター](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="2e210-125">予測スコア フィルターの名前付け規則は、 **予測スコア (モデル名) です**。</span><span class="sxs-lookup"><span data-stu-id="2e210-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="2e210-126">たとえば、モデル **A** という名前のモデルの予測スコア フィルター名は **、予測スコア (モデル A) です**。</span><span class="sxs-lookup"><span data-stu-id="2e210-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="2e210-127">使用する予測スコア フィルターを選択し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2e210-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="2e210-128">[レビュー セット] ページで、予測スコア フィルターのドロップダウンをクリックし、予測スコア範囲の最小値と最大値を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e210-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="2e210-129">たとえば、次のスクリーンショットは、.5 ~ **1.0** の予測スコア **範囲を示しています**。</span><span class="sxs-lookup"><span data-stu-id="2e210-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![予測スコア フィルターの最小値と最大値](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="2e210-131">フィルターの外側をクリックすると、自動的にレビュー セットにフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e210-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="2e210-132">指定した範囲内の予測スコアを持つドキュメントの一覧が、レビュー セット ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e210-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="2e210-133">ドキュメントに割り当てる実際の予測スコアを表示するには、閲覧ウィンドウの **[メタデータ** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e210-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="2e210-134">レビュー セット内のすべてのモデルの予測スコアは **、RelevanceScores メタデータ** プロパティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e210-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="2e210-135">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2e210-135">More information</span></span>

- <span data-ttu-id="2e210-136">フィルターの使用の詳細については、「レビュー セットの [コンテンツのクエリとフィルター」を参照してください](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="2e210-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
