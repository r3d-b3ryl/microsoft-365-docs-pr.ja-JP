---
title: Microsoft セキュリティスコアを使用してセキュリティの姿勢を評価する
description: Microsoft 365 セキュリティセンターで Microsoft セキュリティスコアを向上させるための処置を行う方法について説明します。
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
ms.openlocfilehash: 469056bbae4627e0b013bfc0f2e965586fd15175
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200064"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="860ea-104">Microsoft セキュリティスコアを使用してセキュリティの姿勢を評価する</span><span class="sxs-lookup"><span data-stu-id="860ea-104">Assess your security posture with Microsoft Secure Score</span></span>

<span data-ttu-id="860ea-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="860ea-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="860ea-106">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="860ea-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="860ea-107">必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="860ea-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="860ea-108">ID (Azure AD アカウントと役割)</span><span class="sxs-lookup"><span data-stu-id="860ea-108">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="860ea-109">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="860ea-109">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="860ea-110">デバイス (Microsoft Defender ATP、[構成スコア](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)と呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="860ea-110">Device (Microsoft Defender ATP, known as [Configuration score](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))</span></span>
* <span data-ttu-id="860ea-111">アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)</span><span class="sxs-lookup"><span data-stu-id="860ea-111">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="860ea-112">インフラストラクチャ (現在のところ、改善のための処置はありません)</span><span class="sxs-lookup"><span data-stu-id="860ea-112">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="860ea-113">Microsoft Secure Score の最近のリリースでは、Microsoft セキュリティスコアを Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がない、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="860ea-113">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="860ea-114">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="860ea-114">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="860ea-115">[Microsoft セキュア スコアの概要] ページでは、これらのグループ間でポイントがどのように分割され、どのポイントが利用可能であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="860ea-115">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="860ea-116">また、[概要] ページでは、合計スコアの全表示ビュー、ベンチマーク比較によるセキュア スコア履歴の傾向、スコアを上げるために優先して実装できる改善のための処置を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-116">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="860ea-118">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="860ea-118">Check your current score</span></span>

<span data-ttu-id="860ea-119">現在のスコアを確認するには、Microsoft の [セキュリティスコアの概要] ページに移動して、**セキュリティで保護さ**れたスコアを示すタイルを探します。</span><span class="sxs-lookup"><span data-stu-id="860ea-119">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="860ea-120">スコアは、パーセンテージとして表示され、総ポイント数のうちで得られたポイントの数を示します。</span><span class="sxs-lookup"><span data-stu-id="860ea-120">Your score will be shown as a percentage, along with the number of points you have achieved out of a total possible points.</span></span>

<span data-ttu-id="860ea-121">また、スコアの横にある [**追加**] ボタンを選択すると、スコアのさまざまなビューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="860ea-121">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="860ea-122">これらの異なるスコア表示は、スコアタイルおよび点の内訳グラフのグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-122">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="860ea-123">次のスコアは、全体的なスコアの表示に追加して、全体的なスコアをより正確に把握することができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-123">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="860ea-124">**予定スコア**: 計画されたアクションが完了したときに予想されるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="860ea-124">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="860ea-125">**現在のライセンススコア**: 現在の Microsoft ライセンスで達成できるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="860ea-125">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="860ea-126">**実現**可能なスコア: Microsoft のライセンスと現在のリスクの受け入れによって得られるスコアを表示します。</span><span class="sxs-lookup"><span data-stu-id="860ea-126">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="860ea-127">考えられるすべてのスコアビューを含めた場合は、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-127">This is what it will look like if you have included all possible score views:</span></span>

![予定スコア、現在のライセンススコア、実現可能スコアを含む、セキュリティで保護されたスコア](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="860ea-129">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="860ea-129">Take action to improve your score</span></span>

<span data-ttu-id="860ea-130">[**向上**したアクション] タブには、発生する可能性のある攻撃対象の範囲とその状態 (サードパーティによって解決され、代替の軽減によって解決されたもの) とその状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-130">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="860ea-131">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-131">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="860ea-132">ランク付け</span><span class="sxs-lookup"><span data-stu-id="860ea-132">Ranking</span></span>

<span data-ttu-id="860ea-133">ランク付けは、残りのポイント数、実装の難しさ、ユーザーへの影響、複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="860ea-133">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="860ea-134">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-134">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="860ea-135">向上アクションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="860ea-135">View improvement action details</span></span>

<span data-ttu-id="860ea-136">特定の改善アクションを選択すると、完全なページポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-136">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="860ea-137">![改善アクションのポップアップの例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *図 2: 改善アクションのポップアップの例*</span><span class="sxs-lookup"><span data-stu-id="860ea-137">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="860ea-138">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="860ea-138">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="860ea-139">[**管理**] を選択して、構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="860ea-139">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="860ea-140">その後、そのアクションに価値があるポイントを取得して、フライアウトに表示されるようにします。通常、更新には約24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="860ea-140">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="860ea-141">[**共有**] を選択して、[改善] アクションへの直接リンクをコピーするか、電子メール、microsoft Teams、microsoft Planner、または ServiceNow などのリンクを共有するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="860ea-141">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="860ea-142">ServiceNow を選択すると、変更チケットを作成できるようになります。このチケットは、ServiceNow と Microsoft 365 セキュリティセンターのホームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-142">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="860ea-143">詳細については、「 [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="860ea-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="860ea-144">改善アクションの状態を選択する</span><span class="sxs-lookup"><span data-stu-id="860ea-144">Choose an improvement action status</span></span>

<span data-ttu-id="860ea-145">[改善] アクションに固有の状態を選択し、メモを記録します。</span><span class="sxs-lookup"><span data-stu-id="860ea-145">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="860ea-146">選択できる statues は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="860ea-146">The statues you can select are the following:</span></span>

* <span data-ttu-id="860ea-147">[**宛先アドレス**] —改善アクションが必要であることを認識し、将来のある時点での対処を計画します。</span><span class="sxs-lookup"><span data-stu-id="860ea-147">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="860ea-148">この状態は、部分的に検出されたが完全に完了していない操作にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-148">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="860ea-149">**計画**済み: 改善アクションを完了するための具体的な計画があります。</span><span class="sxs-lookup"><span data-stu-id="860ea-149">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="860ea-150">**承認**されたリスク: セキュリティは常にユーザビリティにバランスをとる必要がありますが、お客様の環境ですべての推奨事項が動作するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="860ea-150">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="860ea-151">その場合は、リスクを受け入れるか、またはリスクを軽減するかを選択して、改善アクションが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-151">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="860ea-152">ポイントはありませんが、改善アクションの一覧には表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="860ea-152">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="860ea-153">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="860ea-153">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="860ea-154">**サード**パーティによって解決され、**代替の軽減**によって解決されました。向上アクションは、サードパーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既にアドレス指定されています。</span><span class="sxs-lookup"><span data-stu-id="860ea-154">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="860ea-155">この操作によって得られる価値を得ることができるようになります。そのため、スコアは全体的なセキュリティ姿勢をより適切に反映できます。</span><span class="sxs-lookup"><span data-stu-id="860ea-155">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="860ea-156">サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="860ea-156">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="860ea-157">改善アクションがこれらの状態のどちらかとしてマークされている場合、Microsoft は、実装の完全性を確認することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="860ea-157">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="860ea-158">脅威 & 脆弱性管理の改善アクション</span><span class="sxs-lookup"><span data-stu-id="860ea-158">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="860ea-159">"Device" カテゴリの向上アクションについては、[状態] を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="860ea-159">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="860ea-160">代わりに、 [Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)で、関連付けられている[脅威 & 脆弱性管理 (tvm) セキュリティに関する推奨事項](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)に従ってアクションを実行することになります。</span><span class="sxs-lookup"><span data-stu-id="860ea-160">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="860ea-161">選択する例外と、作成する根拠は、そのポータルに固有のものであり、Microsoft Secure Score ポータルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="860ea-161">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="860ea-162">完了した改善アクション</span><span class="sxs-lookup"><span data-stu-id="860ea-162">Completed improvement actions</span></span>

<span data-ttu-id="860ea-163">改善アクションのすべての可能なポイントが達成されたら、改善アクションの状態は "完了" になります。</span><span class="sxs-lookup"><span data-stu-id="860ea-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="860ea-164">完了した改善アクションは Microsoft データによって確認され、状態を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="860ea-164">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="860ea-165">情報を評価し、ユーザーへの影響を確認する</span><span class="sxs-lookup"><span data-stu-id="860ea-165">Assess information and review user impact</span></span>

<span data-ttu-id="860ea-166">[**概要**] セクションには、カテゴリ、保護できる攻撃、および製品がわかります。</span><span class="sxs-lookup"><span data-stu-id="860ea-166">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="860ea-167">**ユーザーへの影響**は、改善アクションが実行された場合にユーザーが**受ける**影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="860ea-167">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="860ea-168">向上アクションを実装する</span><span class="sxs-lookup"><span data-stu-id="860ea-168">Implement the improvement action</span></span>

<span data-ttu-id="860ea-169">[**実装**] セクションには、すべての前提条件、[改善] アクションを完了するための次のステップ、向上アクションの現在の実装状況、および詳細なリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="860ea-169">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="860ea-170">前提条件は、取得する必要があるライセンス、または改善アクションが解決される前に完了する必要があるアクションです。</span><span class="sxs-lookup"><span data-stu-id="860ea-170">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="860ea-171">改善アクションを完了し、それらのライセンスが必要なユーザーに適用されるように、ライセンスに十分な座席があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="860ea-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="860ea-172">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="860ea-172">We want to hear from you</span></span>

<span data-ttu-id="860ea-173">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="860ea-173">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="860ea-174">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="860ea-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="860ea-175">関連リソース</span><span class="sxs-lookup"><span data-stu-id="860ea-175">Related resources</span></span>

- [<span data-ttu-id="860ea-176">Microsoft セキュリティスコアの概要</span><span class="sxs-lookup"><span data-stu-id="860ea-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="860ea-177">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="860ea-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="860ea-178">今後の予定</span><span class="sxs-lookup"><span data-stu-id="860ea-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="860ea-179">新機能</span><span class="sxs-lookup"><span data-stu-id="860ea-179">What's new</span></span>](microsoft-secure-score-whats-new.md)