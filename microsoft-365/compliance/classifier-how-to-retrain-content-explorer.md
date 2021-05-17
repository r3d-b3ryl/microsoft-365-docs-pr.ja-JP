---
title: コンテンツ エクスプローラーで分類子を再トレーニングする方法
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
description: コンテンツ エクスプローラーでトレーニング可能な分類子にフィードバックを提供する方法について学習します。
ms.openlocfilehash: d61437634dcad7f01a6737947b0f32f42de2818e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918103"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="67a95-103">コンテンツ エクスプローラーで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="67a95-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="67a95-104">トレーニングMicrosoft 365分類子は、さまざまな種類のコンテンツを認識するトレーニングツールです。</span><span class="sxs-lookup"><span data-stu-id="67a95-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="67a95-105">トレーニングが完了したら、このラベルを使用して、Office、通信コンプライアンス ポリシー、および保持ラベル ポリシーを適用するためのアイテムを識別できます。</span><span class="sxs-lookup"><span data-stu-id="67a95-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="67a95-106">この記事では、追加のフィードバックを提供することで、カスタムトレーニング可能な分類子といくつかの事前トレーニング済みの分類子のパフォーマンスを向上させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="67a95-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="67a95-107">分類子の種類の詳細については、「トレーニング可能な分類子について」 [を参照してください](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="67a95-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="67a95-108">チューニングと再トレーニングプロセスの概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67a95-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="67a95-109">詳細を取得するには、この記事の全文を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="67a95-110">権限</span><span class="sxs-lookup"><span data-stu-id="67a95-110">Permissions</span></span>

<span data-ttu-id="67a95-111">コンプライアンス センターで分類子にMicrosoft 365するには、次のMicrosoft 365使用します。</span><span class="sxs-lookup"><span data-stu-id="67a95-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="67a95-112">分類子をトレーニングするには、コンプライアンス管理者の役割またはコンプライアンス データ管理者が必要です</span><span class="sxs-lookup"><span data-stu-id="67a95-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="67a95-113">次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="67a95-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="67a95-114">アイテム保持ラベル ポリシーのシナリオ: レコード管理と保持管理の役割</span><span class="sxs-lookup"><span data-stu-id="67a95-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="67a95-115">全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="67a95-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67a95-116">コンテンツ エクスプローラーで、アイテムにアイテムを自動適用するアイテム保持ラベル ポリシー Exchangeフィードバックを提供し、分類子を条件として使用します。</span><span class="sxs-lookup"><span data-stu-id="67a95-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="67a95-117">**アイテム保持ラベルを Exchange アイテムに自動的に適用し、分類子を条件として使用するアイテム保持ポリシーを持ってない場合は、ここで停止します。**</span><span class="sxs-lookup"><span data-stu-id="67a95-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="67a95-118">分類子を使用する場合は、分類の精度を上げてほしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="67a95-119">これを行うには、一致または一致ではないと識別されたアイテムに対して行われた分類の品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="67a95-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="67a95-120">分類子に対して 30 の評価を行った後、そのフィードバックを受け取り、自動的に再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="67a95-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="67a95-121">分類子の再トレーニングの全体的なワークフローの詳細については、「分類子を再トレーニングするプロセス フロー」 [を参照してください](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="67a95-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="67a95-122">分類子を再トレーニングするには、分類子が既に公開され、使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="67a95-123">コンテンツ エクスプローラーで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="67a95-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="67a95-124">コンプライアンス管理者またはセキュリティ管理者Microsoft 365アクセスしてコンプライアンス センターにサインインし、コンプライアンス センター **データ** Microsoft 365コンテンツ エクスプローラー  >  **を**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="67a95-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="67a95-125">[ラベル、 **情報の種類、または** カテゴリのフィルター] ボックスの一覧で、[トレーニング可能な **分類子] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="67a95-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67a95-126">トレーニング可能な分類子の見出しの下に集計アイテムが表示されるには、最大 8 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="67a95-127">保持ラベル ポリシーの自動適用で使用したトレーニング可能な分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="67a95-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="67a95-128">これは、フィードバックを提供するトレーニング可能な分類子です。</span><span class="sxs-lookup"><span data-stu-id="67a95-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="67a95-129">アイテムに [アイテム保持ラベル] 列にエントリ **がある** 場合は、アイテムが " として分類された" という意味です `match` 。</span><span class="sxs-lookup"><span data-stu-id="67a95-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="67a95-130">アイテムに [保持ラベル] 列にエントリが含されていない場合は、アイテムが [ 保持ラベル] 列に分類されたという意味です `close match` 。</span><span class="sxs-lookup"><span data-stu-id="67a95-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="67a95-131">アイテムに関するフィードバックを提供することで、分類子の精度を最も向上 `close match` できます。</span><span class="sxs-lookup"><span data-stu-id="67a95-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="67a95-132">アイテムを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="67a95-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="67a95-133">複数のアイテムに対するフィードバックを同時に提供するには、それらをすべて選択し、コマンド バーで [分類の **改善]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67a95-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="67a95-134">[フィードバック **の提供] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67a95-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="67a95-135">[詳細 **なフィードバック] ウィンドウで** 、アイテムが正の場合は、[一致] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67a95-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="67a95-136">アイテムが誤検知の場合、カテゴリに誤って含まれている場合は、[一致しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67a95-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="67a95-137">アイテムに適した別の分類子がある場合は、[他のトレーニング可能な分類子を提案する] リストから分類 **子を選択** できます。</span><span class="sxs-lookup"><span data-stu-id="67a95-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="67a95-138">これにより、他の分類子がアイテムを評価します。</span><span class="sxs-lookup"><span data-stu-id="67a95-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="67a95-139">[ **フィードバックの送信]** を選択して、評価の送信、分類、その他のトレーニング可能な分類子 `match` `not a match` の提案を行います。</span><span class="sxs-lookup"><span data-stu-id="67a95-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="67a95-140">分類子にフィードバックの 30 インスタンスを提供すると、自動的に再トレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="67a95-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="67a95-141">再トレーニングには 1 ~ 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="67a95-142">分類子は、1 日に 2 回のみ再トレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="67a95-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67a95-143">この情報はテナントの分類子に表示されます **。Microsoft には戻らない。**</span><span class="sxs-lookup"><span data-stu-id="67a95-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="67a95-144">トレーニング **可能な分類子を開きます**。</span><span class="sxs-lookup"><span data-stu-id="67a95-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="67a95-145">コミュニケーション コンプライアンス ポリシーで使用された分類子は、[再トレーニング] 見出し **の下に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="67a95-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![再トレーニング状態の分類子](../media/classifier-retraining.png)

11. <span data-ttu-id="67a95-147">再トレーニングが完了したら、分類子を選択して再トレーニングの概要を開きます。</span><span class="sxs-lookup"><span data-stu-id="67a95-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類子の再トレーニング結果の概要](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="67a95-149">推奨されるアクションと、再トレーニング済みおよび現在公開されているバージョンの分類子の予測比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="67a95-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="67a95-150">再トレーニングの結果に満足している場合は、[再発行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67a95-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="67a95-151">再トレーニングの結果に満足できない場合は、コミュニケーション コンプライアンス インターフェイスで分類子に追加のフィードバックを提供し、別の再トレーニング サイクルを開始するか、現在公開されているバージョンの分類子を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="67a95-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="67a95-152">推奨事項の再発行の詳細</span><span class="sxs-lookup"><span data-stu-id="67a95-152">Details on republishing recommendations</span></span>

<span data-ttu-id="67a95-153">再トレーニングされた分類子を再発行するか、さらに再トレーニングを提案する推奨事項を策定する方法に関する少しの情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="67a95-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="67a95-154">これには、トレーニング可能な分類子の動作を少し深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a95-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="67a95-155">再トレーニングの後、分類子のトレーニングに使用されたアイテムとフィードバックを含む両方のアイテムに対する分類子のパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="67a95-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="67a95-156">組み込みモデルの場合、分類子のトレーニングに使用されるアイテムは、Microsoft がモデルの構築に使用するアイテムです。</span><span class="sxs-lookup"><span data-stu-id="67a95-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="67a95-157">カスタム モデルの場合、元のトレーニングで使用されるアイテムは、テストとレビューのために追加したサイトの分類子です。</span><span class="sxs-lookup"><span data-stu-id="67a95-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="67a95-158">再トレーニング済み分類子と発行済み分類子の両方の項目セットのパフォーマンス番号を比較し、再発行の改善が行われたかどうかの推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="67a95-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="67a95-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a95-159">See also</span></span>

- [<span data-ttu-id="67a95-160">トレーニング可能な分類子の詳細</span><span class="sxs-lookup"><span data-stu-id="67a95-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="67a95-161">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="67a95-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)