---
title: コミュニケーションコンプライアンスで分類子を再トレーニングする方法 (プレビュー)
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
description: コミュニケーションコンプライアンスの trainable 分類子にフィードバックを提供する方法について説明します。
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132355"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="a0e56-103">コミュニケーションコンプライアンスで分類子を再トレーニングする方法 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a0e56-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="a0e56-104">Microsoft 365 trainable クラシファイアは、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。このツールを使用して、さまざまな種類のコンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="a0e56-105">トレーニングを受けた後、それを使用して、Office の秘密度ラベル、通信コンプライアンスポリシー、および保持ラベルポリシーのアプリケーションの項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="a0e56-106">この記事では、カスタムの trainable 分類子のパフォーマンスを向上させる方法、およびその他のフィードバックを提供することによって事前に学習した分類子について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="a0e56-107">分類子のさまざまな種類の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-learn-about.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0e56-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="a0e56-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a0e56-108">Permissions</span></span>

<span data-ttu-id="a0e56-109">Microsoft 365 コンプライアンスセンターで分類子にアクセスするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a0e56-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="a0e56-110">分類子を教育するには、コンプライアンス管理者ロールまたはコンプライアンスデータ管理者が必要です。</span><span class="sxs-lookup"><span data-stu-id="a0e56-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="a0e56-111">次のシナリオでは、分類子を使用するために、以下のアクセス許可を持つアカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a0e56-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="a0e56-112">コミュニケーションコンプライアンスポリシーのシナリオ: Insider リスク管理管理者、監督レビュー管理者</span><span class="sxs-lookup"><span data-stu-id="a0e56-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="a0e56-113">全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="a0e56-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0e56-114">分類子を条件として使用するコンプライアンスソリューションにフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="a0e56-115">**分類子を条件として使用する通信コンプライアンスポリシーがない場合は、ここで停止してください。**</span><span class="sxs-lookup"><span data-stu-id="a0e56-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="a0e56-116">分類子を使用する際には、作成する分類の精度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="a0e56-117">これを行うには、一致していると判断されたアイテムに対して行われた分類の品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="a0e56-118">分類子に対して30の評価を行うと、そのフィードバックが取得され、自動的に retrains ます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="a0e56-119">分類子の再トレーニングの全体的なワークフローの詳細については、「分類の再 [トレーニングのプロセスフロー](classifier-learn-about.md#retraining-classifiers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0e56-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="a0e56-120">分類子は、retrained する前に、既に公開され、使用中である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0e56-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="a0e56-121">コミュニケーションコンプライアンスポリシー (プレビュー) で分類子を再トレーニングする方法</span><span class="sxs-lookup"><span data-stu-id="a0e56-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="a0e56-122">分類子を条件として使用する通信コンプライアンスポリシーを開き、[ **保留中** ] リストから特定されたアイテムの1つを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="a0e56-123">省略記号を選択して、 **分類を改善**します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="a0e56-124">[ **詳細なフィードバック** ] ウィンドウで、アイテムが真陽性の場合は、[ **一致**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="a0e56-125">アイテムが誤検知の場合は、そのアイテムが誤ってカテゴリに含まれている場合は、[ **一致しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="a0e56-126">アイテムにより適した別の分類子がある場合は、[ **その他の trainable 分類子の候補** リスト] から選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="a0e56-127">これにより、他の分類子がアイテムを評価するようになります。</span><span class="sxs-lookup"><span data-stu-id="a0e56-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="a0e56-128">複数のアイテムを選択して、コマンドバーに [ **詳細なフィードバックを提供** する] を選択することにより、複数のアイテムに対してフィードバックを同時に提供することができます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="a0e56-129">[ **フィードバックの送信** ] を選択して、の評価を送信し、 `match` 分類された `not a match` 他の trainable 分類子を提案します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="a0e56-130">フィードバックの30個のインスタンスを分類子に提供した場合、その結果は自動的に再トレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="a0e56-131">再トレーニングには1-4 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a0e56-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="a0e56-132">分類子は、1日に2回だけ retrained することができます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0e56-133">この情報は、テナント内の分類子に送られるので、 **Microsoft には戻りません**。</span><span class="sxs-lookup"><span data-stu-id="a0e56-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="a0e56-134">**Microsoft 365 コンプライアンスセンター**で [**データ分類**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="a0e56-135">**Trainable 分類子 (プレビュー)** を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="a0e56-136">コミュニケーションコンプライアンスポリシーで使用されていた分類子が、[ **トレーニング** ] の見出しの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![再トレーニングの状態の分類子](../media/classifier-retraining.png)

9. <span data-ttu-id="a0e56-138">再トレーニングが完了したら、分類子を選択して、[再トレーニングの概要] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![分類子の再トレーニング結果の概要](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="a0e56-140">推奨されるアクションと、分類子の retrained および現在公開されているバージョンの予測比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="a0e56-141">再トレーニングの結果に問題がなければ、[ **再公開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="a0e56-142">再トレーニングの結果に満足できない場合は、コミュニケーションコンプライアンスインターフェイスの分類子に対して追加のフィードバックを提供し、別の再トレーニングサイクルを開始するか、または何も実行しないで、現在公開されている分類子の現在のバージョンを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0e56-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="a0e56-143">おすすめ候補の再発行の詳細</span><span class="sxs-lookup"><span data-stu-id="a0e56-143">Details on republishing recommendations</span></span>

<span data-ttu-id="a0e56-144">Retrained 分類子を再発行したり、さらに再トレーニングを提案したりする際の推奨事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="a0e56-145">これには、trainable 分類子のしくみについて、さらに深く理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0e56-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="a0e56-146">再トレーニングの後は、フィードバック付きのアイテムと、分類子の学習に使用されたアイテムの両方で、分類子のパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="a0e56-147">組み込みモデルでは、分類子のトレーニングに使用されるアイテムは、モデルを構築するために Microsoft によって使用されるアイテムです。</span><span class="sxs-lookup"><span data-stu-id="a0e56-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="a0e56-148">カスタムモデルの場合、分類子の元のトレーニングで使用されたアイテムは、テストおよびレビュー用に追加したサイトのものです。</span><span class="sxs-lookup"><span data-stu-id="a0e56-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="a0e56-149">Retrained と発行された分類子の両方のアイテムセットのパフォーマンス番号を比較して、再発行が改善されたかどうかに関する推奨事項を提示します。</span><span class="sxs-lookup"><span data-stu-id="a0e56-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a0e56-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0e56-150">See also</span></span>

- [<span data-ttu-id="a0e56-151">Trainable 分類子 (プレビュー) について</span><span class="sxs-lookup"><span data-stu-id="a0e56-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="a0e56-152">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="a0e56-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
