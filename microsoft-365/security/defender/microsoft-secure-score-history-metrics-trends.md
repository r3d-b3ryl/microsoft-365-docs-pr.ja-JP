---
title: Microsoft Secure Score の履歴を追跡し、目標を達成する
description: Microsoft Secure Score に影響を与えたアクティビティに関する分析情報を取得します。 傾向を発見し、目標を設定します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.technology: m365d
ms.openlocfilehash: 70b20755de836d3fce2469da00bd41520e70ca57
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064635"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="1f836-105">Microsoft Secure Score の履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="1f836-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1f836-106">[Microsoft Secure Score](microsoft-secure-score.md) は、組織のセキュリティ体制の測定で、より多くの改善アクションが実行されたことを示す数値が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1f836-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="1f836-107">これは https://security.microsoft.com/securescore [、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。</span><span class="sxs-lookup"><span data-stu-id="1f836-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="1f836-108">スコアに影響を与えたアクティビティに関する分析情報を取得する</span><span class="sxs-lookup"><span data-stu-id="1f836-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="1f836-109">[履歴] タブで、時間の過ぎた組織のスコアのグラフ **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="1f836-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="1f836-110">グラフの下には、選択した時間範囲で行ったすべてのアクションとその属性 (結果のポイントやカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f836-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="1f836-111">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1f836-111">You can customize a date range and filter by category.</span></span>

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="1f836-113">アクティビティに関連付けられた改善アクションを選択すると、完全な改善アクションのフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f836-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="1f836-114">特定の改善アクションのすべての履歴を表示するには、フライアウトで履歴リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="1f836-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![改善アクションの履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="1f836-116">傾向を発見し、目標を設定する</span><span class="sxs-lookup"><span data-stu-id="1f836-116">Discover trends and set goals</span></span>

<span data-ttu-id="1f836-117">[指標 **の傾向&]** タブには、傾向の可視性を高め、目標を設定するグラフとグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="1f836-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="1f836-118">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1f836-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="1f836-119">視覚化には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f836-119">The visualizations include:</span></span>

* <span data-ttu-id="1f836-120">**Secure Score Zone** - 組織の目標と、良好、大丈夫、および悪いスコア範囲の定義に基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="1f836-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="1f836-121">**回帰傾向** - 構成、ユーザー、またはデバイスの変更のために回帰したポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="1f836-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="1f836-122">**比較傾向** - 組織の Secure Score が他のユーザーの時間と比較する方法。</span><span class="sxs-lookup"><span data-stu-id="1f836-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="1f836-123">このビューには、同じようなシート数を持つ組織のスコア平均を表す線と、設定できるカスタム比較ビューを含めできます。</span><span class="sxs-lookup"><span data-stu-id="1f836-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="1f836-124">**リスク受け入れ** 傾向 - "リスクが受け入れられる" とマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="1f836-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="1f836-125">**スコアの** 変更 - 達成されたポイント数、ポイントが後退し、指定した日付範囲のスコアに対する変更。</span><span class="sxs-lookup"><span data-stu-id="1f836-125">**Score changes** - The number of points achieved, points regressed, and changes to your score in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="1f836-126">スコアを自分のような組織と比較する</span><span class="sxs-lookup"><span data-stu-id="1f836-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="1f836-127">スコアが類似している組織とどのように比較されるのかについては、2 つの場所で確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f836-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="1f836-128">どちらのグラフでも、[比較の管理] **を選択して** 、組織の情報を表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="1f836-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="1f836-129">また、業界、組織の規模、ライセンス、地域に基づいてカスタム比較を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f836-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="1f836-130">比較棒グラフ</span><span class="sxs-lookup"><span data-stu-id="1f836-130">Comparison bar chart</span></span>

<span data-ttu-id="1f836-131">比較棒グラフは [概要] **タブ** です。グラフにカーソルを合わせると、スコアとスコアの機会が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f836-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="1f836-132">比較データは匿名化され、他のテナントが混在しているかどうかは正確にはわかりません。</span><span class="sxs-lookup"><span data-stu-id="1f836-132">The comparison data is anonymized so we don’t know exactly which others tenants are in the mix.</span></span>

![類似する組織のスコアの棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="1f836-134">**お客様のような組織**: 他のテナントの平均スコア (比較するテナントが少なくとも 5 つ以上ある場合) は、次の条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="1f836-134">**Organizations like yours**: an average score of other tenants (provided we have at least five or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="1f836-135">同じ業界</span><span class="sxs-lookup"><span data-stu-id="1f836-135">Same industry</span></span>
    2. <span data-ttu-id="1f836-136">同じ組織のサイズ</span><span class="sxs-lookup"><span data-stu-id="1f836-136">Same organization size</span></span>
    3. <span data-ttu-id="1f836-137">すべての地域</span><span class="sxs-lookup"><span data-stu-id="1f836-137">All regions</span></span>
    4. <span data-ttu-id="1f836-138">使用される Microsoft 製品は 80% 類似しています</span><span class="sxs-lookup"><span data-stu-id="1f836-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="1f836-139">テナントから 20% の範囲内の営業案件 (現在のライセンスで達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="1f836-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="1f836-140">**カスタム比較**: 次の条件に基づいて [比較の管理] を **選択** して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f836-140">**Custom Comparison**: needs to be set up by selecting **Manage Comparison** based on the following criteria:</span></span>
    1. <span data-ttu-id="1f836-141">選択された業界</span><span class="sxs-lookup"><span data-stu-id="1f836-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="1f836-142">選択した組織のサイズ</span><span class="sxs-lookup"><span data-stu-id="1f836-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="1f836-143">選択した地域</span><span class="sxs-lookup"><span data-stu-id="1f836-143">Selected region(s)</span></span>
    4. <span data-ttu-id="1f836-144">選択したライセンス</span><span class="sxs-lookup"><span data-stu-id="1f836-144">Selected license(s)</span></span>
    5. <span data-ttu-id="1f836-145">使用される Microsoft 製品は 80% 類似しています</span><span class="sxs-lookup"><span data-stu-id="1f836-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="1f836-146">テナントから 20% の範囲内の営業案件 (現在のライセンスで達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="1f836-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="1f836-147">カスタム選択を行ったが、比較できる他のテナントが 5 つ未満の場合は、「データが限られているので利用できません」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f836-147">If you've made a custom selection but the results have less than five other tenants that we can compare against, you'll see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="1f836-148">比較傾向</span><span class="sxs-lookup"><span data-stu-id="1f836-148">Comparison trend</span></span>

<span data-ttu-id="1f836-149">[指標 **と傾向&]** タブで、組織の Secure Score が他のユーザーの時間と比較する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f836-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![同様の組織の時間のスコアの線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="1f836-151">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="1f836-151">We want to hear from you</span></span>

<span data-ttu-id="1f836-152">問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="1f836-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="1f836-153">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="1f836-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="1f836-154">関連リソース</span><span class="sxs-lookup"><span data-stu-id="1f836-154">Related resources</span></span>

- [<span data-ttu-id="1f836-155">Microsoft Secure Score の概要</span><span class="sxs-lookup"><span data-stu-id="1f836-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="1f836-156">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="1f836-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="1f836-157">今後の予定</span><span class="sxs-lookup"><span data-stu-id="1f836-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="1f836-158">新機能</span><span class="sxs-lookup"><span data-stu-id="1f836-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
