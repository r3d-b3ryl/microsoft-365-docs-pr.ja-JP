---
title: Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する
description: Microsoft のセキュリティで保護されたスコアに影響を与えたアクティビティについての洞察を得ることができます。 傾向を検出し、目標を設定します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
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
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769246"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a><span data-ttu-id="ef213-105">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="ef213-105">Track your Microsoft Secure Score history and meet goals</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ef213-106">[Microsoft セキュリティスコア](microsoft-secure-score.md) は、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="ef213-106">[Microsoft Secure Score](microsoft-secure-score.md) is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="ef213-107">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef213-107">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a><span data-ttu-id="ef213-108">スコアに影響を与える状況を把握する</span><span class="sxs-lookup"><span data-stu-id="ef213-108">Gain insights into activity that has affected your score</span></span>

<span data-ttu-id="ef213-109">[ **履歴** ] タブで、組織のスコアのグラフを時間の経過と共に表示します。</span><span class="sxs-lookup"><span data-stu-id="ef213-109">View a graph of your organization's score over time in the **History** tab.</span></span>

<span data-ttu-id="ef213-110">グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果として得られる点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef213-110">Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="ef213-111">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="ef213-111">You can customize a date range and filter by category.</span></span>

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

<span data-ttu-id="ef213-113">アクティビティに関連付けられている改善アクションを選択すると、[完全な改善] アクションのポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef213-113">If you select the improvement action associated with an activity, the full improvement action flyout will appear.</span></span>

<span data-ttu-id="ef213-114">その特定の改善アクションの履歴をすべて表示するには、フライアウトの [履歴] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef213-114">To view all history for that specific improvement action, select the history link in the flyout.</span></span>

![向上アクションの履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a><span data-ttu-id="ef213-116">傾向を検出し、目標を設定する</span><span class="sxs-lookup"><span data-stu-id="ef213-116">Discover trends and set goals</span></span>

<span data-ttu-id="ef213-117">[ **指標 & の傾向** ] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ef213-117">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="ef213-118">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ef213-118">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="ef213-119">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ef213-119">The visualizations include:</span></span>

* <span data-ttu-id="ef213-120">**セキュリティで保護されたスコアゾーン** -組織の目標と、適切、適正、および悪いスコアの範囲の定義に基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="ef213-120">**Your Secure Score zone** - Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="ef213-121">**回帰傾向** -構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="ef213-121">**Regression trend** - A timeline of points that have regressed because of configuration, user, or device changes.</span></span>  
* <span data-ttu-id="ef213-122">**比較傾向** -組織のセキュリティスコアと他のユーザーとの間の比較方法。</span><span class="sxs-lookup"><span data-stu-id="ef213-122">**Comparison trend** - How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="ef213-123">このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ef213-123">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="ef213-124">**リスク許容傾向** -向上したリスクとしてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="ef213-124">**Risk acceptance trend** - Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="ef213-125">**スコアの変更** 。指定された日付範囲で、獲得したポイント数と、それ以降のスコア変更と regressed をポイントします。</span><span class="sxs-lookup"><span data-stu-id="ef213-125">**Score changes** - The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

### <a name="compare-your-score-to-organizations-like-yours"></a><span data-ttu-id="ef213-126">自分のスコアを組織と同じように比較する</span><span class="sxs-lookup"><span data-stu-id="ef213-126">Compare your score to organizations like yours</span></span>

<span data-ttu-id="ef213-127">自分に似た組織とスコアがどのように比較されるかを確認するには、2つの場所があります。</span><span class="sxs-lookup"><span data-stu-id="ef213-127">There are two places to see how your score compares to organizations that are similar to you.</span></span> <span data-ttu-id="ef213-128">両方のグラフで [比較の **管理** ] を選択して、組織の情報を表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="ef213-128">In both charts, you can select **Manage comparisons** to view and edit your organization's information.</span></span> <span data-ttu-id="ef213-129">また、業界、組織の規模、ライセンス、地域に基づいて、カスタム比較を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef213-129">You can also create a custom comparison based on industry, organization size, licenses, and regions.</span></span>

#### <a name="comparison-bar-chart"></a><span data-ttu-id="ef213-130">比較横棒グラフ</span><span class="sxs-lookup"><span data-stu-id="ef213-130">Comparison bar chart</span></span>

<span data-ttu-id="ef213-131">比較横棒グラフは [ **概要** ] タブです。グラフをポイントすると、スコアとスコアの機会が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef213-131">The comparison bar chart is the **Overview** tab. Hover over the chart to view the score and score opportunity.</span></span> <span data-ttu-id="ef213-132">比較データは匿名化で、他のテナントが混在していることを正確に知ることはできません。</span><span class="sxs-lookup"><span data-stu-id="ef213-132">The comparison data is anonymized so we don’t know exactly which others tenant are in the mix.</span></span>

![類似する組織のスコアの横棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

- <span data-ttu-id="ef213-134">**自分の組織のよう** になります。次の条件に該当する、他のテナントの平均スコアが提供されます (比較するテナントが少なくとも5つ以上ある場合)。</span><span class="sxs-lookup"><span data-stu-id="ef213-134">**Organizations like yours** : we give you an average score of other tenants (provided we have at least 5 or more tenants to compare) that qualify with the following criteria:</span></span>
    1. <span data-ttu-id="ef213-135">同じ業種</span><span class="sxs-lookup"><span data-stu-id="ef213-135">Same industry</span></span>
    2. <span data-ttu-id="ef213-136">同じ組織サイズ</span><span class="sxs-lookup"><span data-stu-id="ef213-136">Same organization size</span></span>
    3. <span data-ttu-id="ef213-137">すべての地域</span><span class="sxs-lookup"><span data-stu-id="ef213-137">All regions</span></span>
    4. <span data-ttu-id="ef213-138">使用されている Microsoft 製品は80% に似ています。</span><span class="sxs-lookup"><span data-stu-id="ef213-138">Microsoft products used are 80% similar</span></span>
    5. <span data-ttu-id="ef213-139">テナントから20% の範囲内の営業案件 (現在のライセンスによって達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="ef213-139">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

- <span data-ttu-id="ef213-140">**カスタム比較** : 次の条件に基づいて、[ **Manage Comparison** (複数のテナントが見つかった場合のみ)] を選択して最初にセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef213-140">**Custom Comparison** : needs to be setup up first by selecting **Manage Comparison** (only if we find 5 or more tenants) based on the following criteria:</span></span>
    1. <span data-ttu-id="ef213-141">選択された業界 (s)</span><span class="sxs-lookup"><span data-stu-id="ef213-141">Selected industry(s)</span></span>
    2. <span data-ttu-id="ef213-142">選択されている組織のサイズ</span><span class="sxs-lookup"><span data-stu-id="ef213-142">Selected organization size(s)</span></span>
    3. <span data-ttu-id="ef213-143">選択した地域 (s)</span><span class="sxs-lookup"><span data-stu-id="ef213-143">Selected region(s)</span></span>
    4. <span data-ttu-id="ef213-144">選択されたライセンス</span><span class="sxs-lookup"><span data-stu-id="ef213-144">Selected license(s)</span></span>
    5. <span data-ttu-id="ef213-145">使用されている Microsoft 製品は80% に似ています。</span><span class="sxs-lookup"><span data-stu-id="ef213-145">Microsoft products used are 80% similar</span></span>
    6. <span data-ttu-id="ef213-146">テナントから20% の範囲内の営業案件 (現在のライセンスによって達成できる最大スコア)</span><span class="sxs-lookup"><span data-stu-id="ef213-146">Opportunity (max score that can be achieved by current license) within a 20% range from your tenant</span></span>

<span data-ttu-id="ef213-147">比較に使用できる他のテナントが5個未満になるように、選択範囲の選択をカスタマイズするためのオプションを選択していない場合は、「データが制限されているため、利用できません」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef213-147">If you have not made a selection for custom selection of the selection result in getting less than 5 other tenants that we can compare against, you will see “Not available due to limited data”.</span></span>

#### <a name="comparison-trend"></a><span data-ttu-id="ef213-148">比較傾向</span><span class="sxs-lookup"><span data-stu-id="ef213-148">Comparison trend</span></span>

<span data-ttu-id="ef213-149">[ **指標 & の傾向** ] タブで、組織のセキュリティスコアが他のユーザーとどのように比較されるかを表示します。</span><span class="sxs-lookup"><span data-stu-id="ef213-149">In the **Metrics & trends** tab, view how your organization's Secure Score compares to others' over time.</span></span>

![類似の組織のスコアの折れ線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="ef213-151">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="ef213-151">We want to hear from you</span></span>

<span data-ttu-id="ef213-152">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="ef213-152">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="ef213-153">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="ef213-153">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="ef213-154">関連リソース</span><span class="sxs-lookup"><span data-stu-id="ef213-154">Related resources</span></span>

- [<span data-ttu-id="ef213-155">Microsoft セキュリティスコアの概要</span><span class="sxs-lookup"><span data-stu-id="ef213-155">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="ef213-156">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="ef213-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="ef213-157">今後の予定</span><span class="sxs-lookup"><span data-stu-id="ef213-157">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="ef213-158">新機能</span><span class="sxs-lookup"><span data-stu-id="ef213-158">What's new</span></span>](microsoft-secure-score-whats-new.md)
