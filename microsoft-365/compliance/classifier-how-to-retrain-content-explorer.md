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
ms.openlocfilehash: 786ebb682e9cdd96c0c6503294bd4f316f777f68
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752625"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="71716-103">コンテンツ エクスプローラーで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="71716-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="71716-104">Microsoft 365 トレーニング可能な分類子は、さまざまな種類のコンテンツを見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。</span><span class="sxs-lookup"><span data-stu-id="71716-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="71716-105">トレーニングを受けたら、それを使用して、Office の感度ラベル、通信コンプライアンス ポリシー、および保持ラベル ポリシーの適用項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="71716-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="71716-106">この記事では、追加のフィードバックを提供することで、カスタムのトレーニング可能な分類子といくつかの事前トレーニング済みの分類子のパフォーマンスを向上させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71716-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="71716-107">さまざまな種類の分類子の詳細については、「トレーニング可能な分類子について [」を参照してください](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="71716-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="71716-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="71716-108">Permissions</span></span>

<span data-ttu-id="71716-109">Microsoft 365 コンプライアンス センターの分類子にアクセスするには、</span><span class="sxs-lookup"><span data-stu-id="71716-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="71716-110">分類子をトレーニングするには、コンプライアンス管理者の役割またはコンプライアンス データ管理者が必要です。</span><span class="sxs-lookup"><span data-stu-id="71716-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="71716-111">次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="71716-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="71716-112">保持ラベル ポリシー のシナリオ: レコード管理とアイテム保持管理の役割</span><span class="sxs-lookup"><span data-stu-id="71716-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="71716-113">ワークフロー全体</span><span class="sxs-lookup"><span data-stu-id="71716-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71716-114">保持ラベル ポリシーを Exchange アイテムに自動適用するために、コンテンツ エクスプローラーでフィードバックを提供し、条件として分類子を使用します。</span><span class="sxs-lookup"><span data-stu-id="71716-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="71716-115">**アイテム保持ラベルを Exchange アイテムに自動適用し、条件として分類子を使用するアイテム保持ポリシーを持たなかった場合は、ここで停止します。**</span><span class="sxs-lookup"><span data-stu-id="71716-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="71716-116">分類子を使用する場合は、分類子が作成する分類の精度を高くする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71716-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="71716-117">これを行うには、一致として識別されたアイテムまたは一致していないアイテムに対して行われた分類の品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="71716-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="71716-118">分類子に対して 30 の評価を行った後、そのフィードバックを受け取り、自動的に再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="71716-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="71716-119">分類子の再トレーニングのワークフロー全体の詳細については、「分類子の再トレーニングのプロセス フロー」を [参照してください](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="71716-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="71716-120">再トレーニングを行う前に、分類子が既に公開され、使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71716-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="71716-121">コンテンツ エクスプローラーで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="71716-121">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="71716-122">コンプライアンス管理者またはセキュリティ管理者の役割にアクセスして Microsoft 365 コンプライアンス センターにサインインし **、Microsoft 365** コンプライアンス センターのデータ分類コンテンツ エクスプローラー  >  **を**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="71716-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="71716-123">[ラベル、 **情報の種類、またはカテゴリのフィルター** ] の一覧で、[トレーニング可能な分類 **子] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="71716-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71716-124">集計アイテムがトレーニング可能な分類子の見出しの下に表示されるには、最大 8 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71716-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="71716-125">保持ラベル ポリシーの自動適用で使用したトレーニング可能な分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="71716-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="71716-126">これは、フィードバックを提供するトレーニング可能な分類子です。</span><span class="sxs-lookup"><span data-stu-id="71716-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="71716-127">アイテムの [保持ラベル]列にエントリがある場合は、アイテムがアイテムとして分類されたという意味です `match` 。</span><span class="sxs-lookup"><span data-stu-id="71716-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="71716-128">アイテムが保持ラベル列にエントリを持たなかった場合は、アイテムがアイテムとして分類されたという意味です `close match` 。</span><span class="sxs-lookup"><span data-stu-id="71716-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="71716-129">分類子の精度を最も高くするには、アイテムに関するフィードバックを提供 `close match` します。</span><span class="sxs-lookup"><span data-stu-id="71716-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="71716-130">アイテムを選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="71716-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="71716-131">すべての項目を選択し、コマンド バーの [分類の向上]を選択すると、複数の項目に対するフィードバックを同時に提供できます。</span><span class="sxs-lookup"><span data-stu-id="71716-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="71716-132">[フィードバック **の提供] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="71716-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="71716-133">[詳細 **なフィードバック] ウィンドウで** 、アイテムが正の場合は、[一致] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="71716-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="71716-134">アイテムが誤検知の場合、カテゴリに誤って含まれている場合は、[一致しない] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="71716-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="71716-135">アイテムに適した別の分類子がある場合は、[他のトレーニング可能な分類子を提案する] リストから **選択できます。**</span><span class="sxs-lookup"><span data-stu-id="71716-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="71716-136">これにより、他の分類子がアイテムを評価します。</span><span class="sxs-lookup"><span data-stu-id="71716-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="71716-137">[ **フィードバックの送信]** を選択して、評価を送信し、他のトレーニング可能な分類子 `match` `not a match` を提案します。</span><span class="sxs-lookup"><span data-stu-id="71716-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="71716-138">分類子にフィードバックのインスタンスを 30 回提供すると、自動的に再トレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="71716-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="71716-139">再トレーニングには 1 ~ 4 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71716-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="71716-140">分類子は、1 日に 2 回のみ再トレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="71716-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71716-141">この情報は、テナント内の分類子に移動します **が、Microsoft に戻るのではありません**。</span><span class="sxs-lookup"><span data-stu-id="71716-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="71716-142">トレーニング **可能な分類子を開きます**。</span><span class="sxs-lookup"><span data-stu-id="71716-142">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="71716-143">コミュニケーション コンプライアンス ポリシーで使用された分類子は、[再トレーニング] 見出 **しの下に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="71716-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![再トレーニング状態の分類子](../media/classifier-retraining.png)

11. <span data-ttu-id="71716-145">再トレーニングが完了したら、分類子を選択して再トレーニングの概要を開きます。</span><span class="sxs-lookup"><span data-stu-id="71716-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類子再トレーニング結果の概要](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="71716-147">推奨されるアクションと、再トレーニング済みバージョンと現在公開されているバージョンの分類子の予測比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="71716-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="71716-148">再トレーニングの結果に問題がなければ、[再発行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="71716-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="71716-149">再トレーニングの結果に満足できない場合は、コミュニケーション コンプライアンス インターフェイスで分類子に追加のフィードバックを提供し、別の再トレーニング サイクルを開始するか、現在公開されているバージョンの分類子が引き続き使用される場合は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="71716-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="71716-150">推奨事項の再発行に関する詳細</span><span class="sxs-lookup"><span data-stu-id="71716-150">Details on republishing recommendations</span></span>

<span data-ttu-id="71716-151">ここでは、再トレーニングされた分類子を再発行するか、さらに再トレーニングを提案する推奨事項を策定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71716-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="71716-152">これには、トレーニング可能な分類子の動作を少し深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71716-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="71716-153">再トレーニングの後、フィードバックを含むアイテムと、分類子のトレーニングに最初に使用されたアイテムの両方に対する分類子のパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="71716-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="71716-154">組み込みモデルの場合、分類子のトレーニングに使用されるアイテムは、Microsoft がモデルを構築するために使用するアイテムです。</span><span class="sxs-lookup"><span data-stu-id="71716-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="71716-155">カスタム モデルの場合、分類子は、テストとレビューのために追加したサイトの元のトレーニングで使用されるアイテムです。</span><span class="sxs-lookup"><span data-stu-id="71716-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="71716-156">再発行の改善点が得たかどうかに関する推奨事項を示す、再トレーニング済み分類子と発行済み分類子の両方のアイテムセットのパフォーマンス値を比較します。</span><span class="sxs-lookup"><span data-stu-id="71716-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="71716-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="71716-157">See also</span></span>

- [<span data-ttu-id="71716-158">トレーニング可能な分類子について</span><span class="sxs-lookup"><span data-stu-id="71716-158">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="71716-159">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="71716-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
