---
title: 通信コンプライアンスで分類子を再トレーニングする方法
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
description: コミュニケーション コンプライアンスでトレーニング可能な分類子にフィードバックを提供する方法について学習します。
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918148"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="2a4ea-103">通信コンプライアンスで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="2a4ea-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="2a4ea-104">Microsoft 365 トレーニング可能な分類子は、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="2a4ea-105">トレーニングが完了したら、このラベルを使用して、Office、通信コンプライアンス ポリシー、および保持ラベル ポリシーを適用するためのアイテムを識別できます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="2a4ea-106">この記事では、追加のフィードバックを提供することで、カスタムトレーニング可能な分類子といくつかの事前トレーニング済みの分類子のパフォーマンスを向上させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="2a4ea-107">分類子の種類の詳細については、「トレーニング可能な分類子について」 [を参照してください](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="2a4ea-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2a4ea-108">Permissions</span></span>

<span data-ttu-id="2a4ea-109">Microsoft 365 コンプライアンス センターの分類子にアクセスするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="2a4ea-110">分類子をトレーニングするには、コンプライアンス管理者の役割またはコンプライアンス データ管理者が必要です</span><span class="sxs-lookup"><span data-stu-id="2a4ea-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="2a4ea-111">次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="2a4ea-112">コミュニケーション コンプライアンス ポリシーのシナリオ: Insider Risk Management Admin、Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="2a4ea-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="2a4ea-113">全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="2a4ea-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a4ea-114">分類子を条件として使用しているコンプライアンス ソリューションでフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="2a4ea-115">**分類子を条件として使用する通信コンプライアンス ポリシーを使用しない場合は、ここで停止します。**</span><span class="sxs-lookup"><span data-stu-id="2a4ea-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="2a4ea-116">分類子を使用する場合は、分類の精度を上げてほしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="2a4ea-117">これを行うには、一致または一致ではないと識別されたアイテムに対して行われた分類の品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="2a4ea-118">分類子に対して 30 の評価を行った後、そのフィードバックを受け取り、自動的に再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="2a4ea-119">分類子の再トレーニングの全体的なワークフローの詳細については、「分類子を再トレーニングするプロセス フロー」 [を参照してください](classifier-learn-about.md#retraining-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="2a4ea-120">分類子を再トレーニングするには、分類子が既に公開され、使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="2a4ea-121">通信コンプライアンス ポリシーで分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="2a4ea-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="2a4ea-122">分類子を条件として使用する通信コンプライアンス ポリシーを開き、[保留中] リストから識別されたアイテム **のいずれかを選択** します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="2a4ea-123">省略記号と分類の改善 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="2a4ea-124">[詳細 **なフィードバック] ウィンドウで** 、アイテムが正の場合は、[一致] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="2a4ea-125">アイテムが誤検知の場合、カテゴリに誤って含まれている場合は、[一致しない **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="2a4ea-126">アイテムに適した別の分類子がある場合は、[他のトレーニング可能な分類子を提案する] リストから分類 **子を選択** できます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="2a4ea-127">これにより、他の分類子がアイテムを評価します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="2a4ea-128">複数のアイテムに対するフィードバックを同時に提供するには、それらをすべて選択し、[コマンド バーで詳細なフィードバックを提供する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="2a4ea-129">[ **フィードバックの送信]** を選択して、評価の送信、分類、その他のトレーニング可能な分類子 `match` `not a match` の提案を行います。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="2a4ea-130">分類子にフィードバックの 30 インスタンスを提供すると、自動的に再トレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="2a4ea-131">再トレーニングには 1 ~ 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="2a4ea-132">分類子は、1 日に 2 回のみ再トレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a4ea-133">この情報はテナントの分類子に表示されます **。Microsoft には戻らない。**</span><span class="sxs-lookup"><span data-stu-id="2a4ea-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="2a4ea-134">Microsoft 365 コンプライアンス **センターで** **[データ分類] ページを開きます**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="2a4ea-135">トレーニング **可能な分類子を開きます**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="2a4ea-136">コミュニケーション コンプライアンス ポリシーで使用された分類子は、[再トレーニング] 見出し **の下に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![再トレーニング状態の分類子](../media/classifier-retraining.png)

9. <span data-ttu-id="2a4ea-138">再トレーニングが完了したら、分類子を選択して再トレーニングの概要を開きます。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類子の再トレーニング結果の概要](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="2a4ea-140">推奨されるアクションと、再トレーニング済みおよび現在公開されているバージョンの分類子の予測比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="2a4ea-141">再トレーニングの結果に満足している場合は、[再発行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="2a4ea-142">再トレーニングの結果に満足できない場合は、コミュニケーション コンプライアンス インターフェイスで分類子に追加のフィードバックを提供し、別の再トレーニング サイクルを開始するか、現在公開されているバージョンの分類子を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="2a4ea-143">推奨事項の再発行の詳細</span><span class="sxs-lookup"><span data-stu-id="2a4ea-143">Details on republishing recommendations</span></span>

<span data-ttu-id="2a4ea-144">再トレーニングされた分類子を再発行するか、さらに再トレーニングを提案する推奨事項を策定する方法に関する少しの情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="2a4ea-145">これには、トレーニング可能な分類子の動作を少し深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="2a4ea-146">再トレーニングの後、分類子のトレーニングに使用されたアイテムとフィードバックを含む両方のアイテムに対する分類子のパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="2a4ea-147">組み込みモデルの場合、分類子のトレーニングに使用されるアイテムは、Microsoft がモデルの構築に使用するアイテムです。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="2a4ea-148">カスタム モデルの場合、元のトレーニングで使用されるアイテムは、テストとレビューのために追加したサイトの分類子です。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="2a4ea-149">再トレーニング済み分類子と発行済み分類子の両方の項目セットのパフォーマンス番号を比較し、再発行の改善が行われたかどうかの推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="2a4ea-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="2a4ea-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4ea-150">See also</span></span>

- [<span data-ttu-id="2a4ea-151">トレーニング可能な分類子の詳細</span><span class="sxs-lookup"><span data-stu-id="2a4ea-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="2a4ea-152">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="2a4ea-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)