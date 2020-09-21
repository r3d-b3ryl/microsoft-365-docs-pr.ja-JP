---
title: '[方法] コンテンツエクスプローラーで分類子を再トレーニングする (プレビュー)'
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンテンツエクスプローラーで trainable 分類子にフィードバックを提供する方法について説明します。
ms.openlocfilehash: 0fbce595894cbbf2a017fc1bf657b14a5b812e29
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132362"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="7d002-103">[方法] コンテンツエクスプローラーで分類子を再トレーニングする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7d002-103">How to retrain a classifier in content explorer (preview)</span></span>

<span data-ttu-id="7d002-104">Microsoft 365 trainable クラシファイアは、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。このツールを使用して、さまざまな種類のコンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7d002-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="7d002-105">トレーニングを受けた後、それを使用して、Office の秘密度ラベル、通信コンプライアンスポリシー、および保持ラベルポリシーのアプリケーションの項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="7d002-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="7d002-106">この記事では、カスタムの trainable 分類子のパフォーマンスを向上させる方法、およびその他のフィードバックを提供することによって事前に学習した分類子について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d002-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="7d002-107">分類子のさまざまな種類の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d002-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="7d002-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7d002-108">Permissions</span></span>

<span data-ttu-id="7d002-109">Microsoft 365 コンプライアンスセンターで分類子にアクセスするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7d002-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="7d002-110">分類子を教育するには、コンプライアンス管理者ロールまたはコンプライアンスデータ管理者が必要です。</span><span class="sxs-lookup"><span data-stu-id="7d002-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="7d002-111">次のシナリオでは、分類子を使用するために、以下のアクセス許可を持つアカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="7d002-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="7d002-112">保持ラベルポリシーシナリオ: レコード管理および保持管理の役割</span><span class="sxs-lookup"><span data-stu-id="7d002-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="7d002-113">全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="7d002-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d002-114">コンテンツエクスプローラーで、Exchange アイテムに対して自動適用される保持ラベルポリシーのフィードバックを提供し、分類子を条件として使用します。</span><span class="sxs-lookup"><span data-stu-id="7d002-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="7d002-115">**アイテム保持ラベルを Exchange アイテムに自動適用し、分類子を条件として使用するアイテム保持ポリシーがない場合は、ここで停止します。**</span><span class="sxs-lookup"><span data-stu-id="7d002-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="7d002-116">分類子を使用する際には、作成する分類の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="7d002-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="7d002-117">これを行うには、一致していると判断されたアイテムに対して行われた分類の品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="7d002-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="7d002-118">分類子に対して30の評価を行うと、そのフィードバックが取得され、自動的に retrains ます。</span><span class="sxs-lookup"><span data-stu-id="7d002-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="7d002-119">分類子の再トレーニングの全体的なワークフローの詳細については、「分類の再 [トレーニングのプロセスフロー](classifier-learn-about.md#retraining-classifiers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d002-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="7d002-120">分類子は、retrained する前に、既に公開され、使用中である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d002-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer-preview"></a><span data-ttu-id="7d002-121">[方法] コンテンツエクスプローラーで分類子を再トレーニングする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7d002-121">How to retrain a classifier in content explorer (preview)</span></span>

1. <span data-ttu-id="7d002-122">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**の  >  **データ分類**  >  **コンテンツエクスプローラー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d002-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="7d002-123">[ **ラベルのフィルター]、[情報の種類]、または [カテゴリ** ] の一覧で、[ **Trainable 分類子**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="7d002-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d002-124">Trainable 分類子の見出しの下に集計アイテムが表示されるまで、最大8日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7d002-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="7d002-125">自動適用の保持ラベルポリシーで使用した trainable 分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d002-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="7d002-126">フィードバックを提供する trainable 分類子です。</span><span class="sxs-lookup"><span data-stu-id="7d002-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="7d002-127">アイテムの [ **保持ラベル** ] 列にエントリがある場合は、アイテムがとして分類されたことを意味し `match` ます。</span><span class="sxs-lookup"><span data-stu-id="7d002-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="7d002-128">アイテムの [ **保持ラベル** ] 列にエントリがない場合は、として分類されたことを意味 `close match` します。</span><span class="sxs-lookup"><span data-stu-id="7d002-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="7d002-129">アイテムに関するフィードバックを提供することによって、分類子の精度を向上させることができ `close match` ます。</span><span class="sxs-lookup"><span data-stu-id="7d002-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="7d002-130">アイテムを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="7d002-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="7d002-131">複数のアイテムを選択して、コマンドバーの [ **分類の強化** ] を選択することによって、同時に複数のアイテムに関するフィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="7d002-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="7d002-132">[ **フィードバックの提供**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d002-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="7d002-133">[ **詳細なフィードバック** ] ウィンドウで、アイテムが真陽性の場合は、[ **一致**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d002-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="7d002-134">アイテムが誤検知の場合は、そのアイテムが誤ってカテゴリに含まれている場合は、[ **一致しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d002-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="7d002-135">アイテムにより適した別の分類子がある場合は、[ **その他の trainable 分類子の候補** リスト] から選択できます。</span><span class="sxs-lookup"><span data-stu-id="7d002-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="7d002-136">これにより、他の分類子がアイテムを評価するようになります。</span><span class="sxs-lookup"><span data-stu-id="7d002-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="7d002-137">[ **フィードバックの送信** ] を選択して、の評価を送信し、 `match` 分類された `not a match` 他の trainable 分類子を提案します。</span><span class="sxs-lookup"><span data-stu-id="7d002-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="7d002-138">フィードバックの30個のインスタンスを分類子に提供した場合、その結果は自動的に再トレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="7d002-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="7d002-139">再トレーニングには、1 ~ 4 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7d002-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="7d002-140">分類子は、1日に2回だけ retrained することができます。</span><span class="sxs-lookup"><span data-stu-id="7d002-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d002-141">この情報は、テナント内の分類子に送られるので、 **Microsoft には戻りません**。</span><span class="sxs-lookup"><span data-stu-id="7d002-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="7d002-142">**Trainable 分類子 (プレビュー)** を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d002-142">Open **Trainable classifiers (preview)**.</span></span>
10. <span data-ttu-id="7d002-143">コミュニケーションコンプライアンスポリシーで使用されていた分類子が、[ **トレーニング** ] の見出しの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d002-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![再トレーニングの状態の分類子](../media/classifier-retraining.png)

11. <span data-ttu-id="7d002-145">再トレーニングが完了したら、分類子を選択して、[再トレーニングの概要] を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d002-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類子の再トレーニング結果の概要](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="7d002-147">推奨されるアクションと、分類子の retrained および現在公開されているバージョンの予測比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="7d002-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="7d002-148">再トレーニングの結果に問題がなければ、[ **再公開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d002-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="7d002-149">再トレーニングの結果に満足できない場合は、コミュニケーションコンプライアンスインターフェイスの分類子に対して追加のフィードバックを提供し、別の再トレーニングサイクルを開始するか、または何も実行しないで、現在公開されている分類子の現在のバージョンを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d002-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="7d002-150">おすすめ候補の再発行の詳細</span><span class="sxs-lookup"><span data-stu-id="7d002-150">Details on republishing recommendations</span></span>

<span data-ttu-id="7d002-151">Retrained 分類子を再発行したり、さらに再トレーニングを提案したりする際の推奨事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7d002-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="7d002-152">これには、trainable 分類子のしくみについて、さらに深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d002-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="7d002-153">再トレーニングの後は、フィードバック付きのアイテムと、分類子の学習に使用されたアイテムの両方で、分類子のパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="7d002-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="7d002-154">組み込みモデルでは、分類子のトレーニングに使用されるアイテムは、モデルを構築するために Microsoft によって使用されるアイテムです。</span><span class="sxs-lookup"><span data-stu-id="7d002-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="7d002-155">カスタムモデルの場合、分類子の元のトレーニングで使用されたアイテムは、テストおよびレビュー用に追加したサイトのものです。</span><span class="sxs-lookup"><span data-stu-id="7d002-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="7d002-156">Retrained と発行された分類子の両方のアイテムセットのパフォーマンス番号を比較して、再発行が改善されたかどうかに関する推奨事項を提示します。</span><span class="sxs-lookup"><span data-stu-id="7d002-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7d002-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d002-157">See also</span></span>

- [<span data-ttu-id="7d002-158">Trainable 分類子 (プレビュー) について</span><span class="sxs-lookup"><span data-stu-id="7d002-158">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="7d002-159">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="7d002-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
