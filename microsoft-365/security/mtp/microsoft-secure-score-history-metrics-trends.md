---
title: Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する
description: セキュリティで保護されたスコアに影響を与えたアクティビティに関する洞察を得ることができます。 傾向を検出し、目標を設定します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善のための処置
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
ms.openlocfilehash: b99f927711ed1015b38d8020e287d76155ce706f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45095082"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="406a6-105">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="406a6-105">Track your Microsoft Secure Score history and meet goals</span></span>

<span data-ttu-id="406a6-106">[Microsoft セキュリティスコア](microsoft-secure-score.md)は、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="406a6-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="406a6-107">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="406a6-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="406a6-108">スコアに影響を与える状況を把握する</span><span class="sxs-lookup"><span data-stu-id="406a6-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="406a6-109">[**履歴**] タブで、組織のスコアのグラフを時間の経過と共に表示します。</span><span class="sxs-lookup"><span data-stu-id="406a6-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="406a6-110">グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果として得られる点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="406a6-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="406a6-111">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="406a6-111">You can customize a date range and filter by category.</span></span>

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="406a6-113">アクティビティに関連付けられている改善アクションを選択すると、[完全な改善] アクションのポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="406a6-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="406a6-114">その特定の改善アクションの履歴をすべて表示するには、フライアウトの [履歴] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="406a6-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![向上アクションの履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="406a6-116">傾向を検出し、目標を設定する</span><span class="sxs-lookup"><span data-stu-id="406a6-116">Discover trends and set goals</span></span>

<span data-ttu-id="406a6-117">[**指標 & の傾向**] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="406a6-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="406a6-118">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="406a6-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="406a6-119">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="406a6-119">The visualizations include:</span></span>

* <span data-ttu-id="406a6-120">**セキュリティで保護されたスコアゾーン**: 組織の目標と、適切で良好な、悪いスコアの範囲の定義に基づいてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="406a6-120">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="406a6-121">**回帰傾向**: 構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="406a6-121">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="406a6-122">**比較傾向**-組織のセキュリティスコアと他のユーザーとの間の比較方法。</span><span class="sxs-lookup"><span data-stu-id="406a6-122">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="406a6-123">このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="406a6-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="406a6-124">**リスク許容度の傾向**— "リスクが許容される" としてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="406a6-124">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="406a6-125">**スコアの変更**: 獲得したポイント数、ポイント regressed、およびそれ以降のスコア変更 (指定された日付範囲)。</span><span class="sxs-lookup"><span data-stu-id="406a6-125">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="406a6-126">自分のスコアを組織と同じように比較する</span><span class="sxs-lookup"><span data-stu-id="406a6-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="406a6-127">自分に似た組織とスコアがどのように比較されるかを確認するには、2つの場所があります。</span><span class="sxs-lookup"><span data-stu-id="406a6-127">There are two place to see how your score compares to organizations that are similar to you.</span></span>

<span data-ttu-id="406a6-128">最初に [**概要**] タブが表示され、比較バーのグラフを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="406a6-128">The first place is in the **Overview** tab, where you will be able to see a comparison bar graph.</span></span> <span data-ttu-id="406a6-129">グラフをポイントすると、スコアとスコアの機会が表示されます。</span><span class="sxs-lookup"><span data-stu-id="406a6-129">Hover over the chart to view the score and score opportunity.</span></span>

![類似する組織のスコアの横棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

<span data-ttu-id="406a6-131">2番目の場所は [**指標 & 傾向**] タブで、組織のセキュリティスコアが他のユーザーとどのように比較されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="406a6-131">The second place is in the **Metrics & trends** tab, where you can view how your organization's Secure Score compares to others' over time.</span></span>

![類似の組織のスコアの折れ線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

<span data-ttu-id="406a6-133">両方のグラフで [比較の**管理**] を選択して、組織の情報を表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="406a6-133">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="406a6-134">また、業界、組織の規模、ライセンス、地域に基づいて、カスタム比較を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="406a6-134">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span> 

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="406a6-135">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="406a6-135">We want to hear from you</span></span>

<span data-ttu-id="406a6-136">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="406a6-136">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="406a6-137">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="406a6-137">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="406a6-138">関連リソース</span><span class="sxs-lookup"><span data-stu-id="406a6-138">Related resources</span></span>

- [<span data-ttu-id="406a6-139">Microsoft セキュリティスコアの概要</span><span class="sxs-lookup"><span data-stu-id="406a6-139">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="406a6-140">セキュリティ体制の可視性を獲得する</span><span class="sxs-lookup"><span data-stu-id="406a6-140">Gain visibility into your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="406a6-141">今後の予定</span><span class="sxs-lookup"><span data-stu-id="406a6-141">What's coming</span></span>](microsoft-secure-score-whats-coming.md)