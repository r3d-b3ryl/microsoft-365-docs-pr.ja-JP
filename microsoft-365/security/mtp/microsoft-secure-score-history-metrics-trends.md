---
title: Microsoft セキュア スコアの履歴を追跡し、目標を達成する
description: Microsoft セキュア スコアに影響を与えたアクティビティに関する洞察を得る。 傾向を発見し、目標を設定します。
keywords: Microsoft セキュア スコア, セキュア スコア, Office 365 セキュア スコア, Microsoft セキュリティ スコア, Microsoft 365 セキュリティ センター, 改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738045"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="80a81-105">Microsoft セキュア スコアの履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="80a81-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="80a81-106">[Microsoft セキュア スコアは](microsoft-secure-score.md) 、組織のセキュリティ体制を測定する指標で、数値が大きいほど、より多くの改善アクションが実行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="80a81-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="80a81-107"> https://security.microsoft.com/securescore[これは、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。</span><span class="sxs-lookup"><span data-stu-id="80a81-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="80a81-108">スコアに影響を与えたアクティビティに関する洞察を得る</span><span class="sxs-lookup"><span data-stu-id="80a81-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="80a81-109">組織のスコアのグラフを [履歴] タブに **表示します。**</span><span class="sxs-lookup"><span data-stu-id="80a81-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="80a81-110">グラフの下には、選択した時間範囲で実行されたアクションとその属性 (結果のポイントやカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80a81-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="80a81-111">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="80a81-111">You can customize a date range and filter by category.</span></span>

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="80a81-113">アクティビティに関連付けられている改善アクションを選択すると、完全な改善アクションのフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80a81-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="80a81-114">特定の改善アクションのすべての履歴を表示するには、フライアウトで履歴リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="80a81-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![改善アクション履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="80a81-116">傾向を見付け、目標を設定する</span><span class="sxs-lookup"><span data-stu-id="80a81-116">Discover trends and set goals</span></span>

<span data-ttu-id="80a81-117">[指標 **と** &] タブには、傾向の可視性を向上し、目標を設定するグラフとグラフがあります。</span><span class="sxs-lookup"><span data-stu-id="80a81-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="80a81-118">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="80a81-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="80a81-119">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80a81-119">The visualizations include:</span></span>

* <span data-ttu-id="80a81-120">**セキュア スコア ゾーン** - 組織の目標と、良好、良好、および悪いスコア範囲の定義に基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="80a81-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="80a81-121">**回帰傾向** : 構成、ユーザー、またはデバイスの変更によって回帰したポイントのタイムラインです。</span><span class="sxs-lookup"><span data-stu-id="80a81-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="80a81-122">**比較傾向** - 組織のセキュア スコアと時間の流れとの比較。</span><span class="sxs-lookup"><span data-stu-id="80a81-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="80a81-123">このビューには、シート数が類似している組織のスコア平均を表す行と、設定できるカスタム比較ビューを含めできます。</span><span class="sxs-lookup"><span data-stu-id="80a81-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="80a81-124">**リスク受け入れ傾向** - 「リスク受け入れ」としてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="80a81-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="80a81-125">**スコアの** 変更 - 取得したポイント数、ポイントの回帰数、指定した日付範囲内のスコアの変更。</span><span class="sxs-lookup"><span data-stu-id="80a81-125">**Score changes** - The number of points achieved, points regressed, and changes to your score in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="80a81-126">スコアを自分のような組織と比較する</span><span class="sxs-lookup"><span data-stu-id="80a81-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="80a81-127">自分に似た組織とスコアがどのように比較されるのかは、2 つの場所で確認できます。</span><span class="sxs-lookup"><span data-stu-id="80a81-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="80a81-128">どちらのグラフでも、[比較の管理] **を** 選択して組織の情報を表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="80a81-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="80a81-129">また、業界、組織の規模、ライセンス、地域に基づいてカスタム比較を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="80a81-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="80a81-130">比較棒グラフ</span><span class="sxs-lookup"><span data-stu-id="80a81-130">Comparison bar chart</span></span>

<span data-ttu-id="80a81-131">比較棒グラフは [概要] **タブ** です。グラフにカーソルを合わせると、スコアとスコアの機会が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80a81-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="80a81-132">比較データは匿名化され、他のテナントが混在しているのが正確にわかりません。</span><span class="sxs-lookup"><span data-stu-id="80a81-132">The comparison data is anonymized so we don’t know exactly which others tenants are in the mix.</span></span>

![類似した組織のスコアの棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="80a81-134">**お客様のような組織**: 次の条件で条件を満たす他のテナントの平均スコア (比較対象のテナントが少なくとも 5 つ以上ある場合)。</span><span class="sxs-lookup"><span data-stu-id="80a81-134">**Organizations like yours**: an average score of other tenants (provided we have at least five or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="80a81-135">同じ業界</span><span class="sxs-lookup"><span data-stu-id="80a81-135">Same industry</span></span>
    2. <span data-ttu-id="80a81-136">同じ組織サイズ</span><span class="sxs-lookup"><span data-stu-id="80a81-136">Same organization size</span></span>
    3. <span data-ttu-id="80a81-137">すべての地域</span><span class="sxs-lookup"><span data-stu-id="80a81-137">All regions</span></span>
    4. <span data-ttu-id="80a81-138">使用されている Microsoft 製品が 80% 類似している</span><span class="sxs-lookup"><span data-stu-id="80a81-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="80a81-139">テナントから 20% の範囲内の機会 (現在のライセンスで達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="80a81-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="80a81-140">**カスタム比較**: 次の条件に基づいて[比較の管理] を選択して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80a81-140">**Custom Comparison**: needs to be set up by selecting **Manage Comparison** based on the following criteria:</span></span>
    1. <span data-ttu-id="80a81-141">選択された業界</span><span class="sxs-lookup"><span data-stu-id="80a81-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="80a81-142">選択した組織のサイズ</span><span class="sxs-lookup"><span data-stu-id="80a81-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="80a81-143">選択した地域</span><span class="sxs-lookup"><span data-stu-id="80a81-143">Selected region(s)</span></span>
    4. <span data-ttu-id="80a81-144">選択したライセンス</span><span class="sxs-lookup"><span data-stu-id="80a81-144">Selected license(s)</span></span>
    5. <span data-ttu-id="80a81-145">使用されている Microsoft 製品が 80% 類似している</span><span class="sxs-lookup"><span data-stu-id="80a81-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="80a81-146">テナントから 20% の範囲内の機会 (現在のライセンスで達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="80a81-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="80a81-147">カスタム選択を行ったが、結果が比較できる他の 5 つ未満のテナントを持つ場合は、「データが限られているので利用できません」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="80a81-147">If you've made a custom selection but the results have less than five other tenants that we can compare against, you'll see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="80a81-148">比較傾向</span><span class="sxs-lookup"><span data-stu-id="80a81-148">Comparison trend</span></span>

<span data-ttu-id="80a81-149">[指標 **と&]** タブで、組織のセキュア スコアと時間の流中の他のユーザーとの比較を確認します。</span><span class="sxs-lookup"><span data-stu-id="80a81-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![同じような組織の時間のスコアの線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="80a81-151">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="80a81-151">We want to hear from you</span></span>

<span data-ttu-id="80a81-152">問題がある場合は、セキュリティ/プライバシー/コンプライアンス コミュニティに投稿 [&知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) らせてください。</span><span class="sxs-lookup"><span data-stu-id="80a81-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="80a81-153">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="80a81-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="80a81-154">関連リソース</span><span class="sxs-lookup"><span data-stu-id="80a81-154">Related resources</span></span>

- [<span data-ttu-id="80a81-155">Microsoft セキュア スコアの概要</span><span class="sxs-lookup"><span data-stu-id="80a81-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="80a81-156">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="80a81-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="80a81-157">今後の予定</span><span class="sxs-lookup"><span data-stu-id="80a81-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="80a81-158">新機能</span><span class="sxs-lookup"><span data-stu-id="80a81-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
