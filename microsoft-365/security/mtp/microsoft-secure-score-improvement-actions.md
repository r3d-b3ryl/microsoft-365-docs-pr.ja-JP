---
title: Microsoft セキュア スコアを使用してセキュリティの状態を評価する
description: Microsoft 365 セキュリティ センターで Microsoft セキュア スコアを向上させるアクションを実行する方法について説明します。
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
ms.openlocfilehash: 8ebfe5746a69cc0161c38f0467954fabb3839240
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683345"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="d212f-104">Microsoft セキュア スコアを使用してセキュリティの状況を評価する</span><span class="sxs-lookup"><span data-stu-id="d212f-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d212f-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d212f-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="d212f-106"> https://security.microsoft.com/securescore[これは、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。</span><span class="sxs-lookup"><span data-stu-id="d212f-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="d212f-107">必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="d212f-107">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="d212f-108">ID (Azure Active Directory アカウント&ロール)</span><span class="sxs-lookup"><span data-stu-id="d212f-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="d212f-109">デバイス (デバイスの Microsoft セキュア スコアと呼ばれる [、エンドポイント用 Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)Defender)</span><span class="sxs-lookup"><span data-stu-id="d212f-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="d212f-110">アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)</span><span class="sxs-lookup"><span data-stu-id="d212f-110">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="d212f-111">Microsoft セキュア スコアの最近のリリースでは、スコアモデルが改善され、Microsoft セキュア スコアと Id セキュア スコアおよび Graph API との互換性が一時的に改善されました。</span><span class="sxs-lookup"><span data-stu-id="d212f-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="d212f-112">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="d212f-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="d212f-113">Microsoft セキュア スコアの概要ページで、これらのグループ間でのポイントの分割方法と使用可能なポイントを確認します。</span><span class="sxs-lookup"><span data-stu-id="d212f-113">In the Microsoft Secure Score overview page, see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="d212f-114">また、合計スコアの全体表示、ベンチマーク比較によるセキュア スコアの履歴傾向、スコアを向上させるために実行できる優先順位付けされた改善アクションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![セキュア スコア ホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a><span data-ttu-id="d212f-116">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="d212f-116">Check your current score</span></span>

<span data-ttu-id="d212f-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span><span class="sxs-lookup"><span data-stu-id="d212f-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="d212f-118">スコアは、合計で得たポイント数と共にパーセンテージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-118">Your score will be shown as a percentage, along with the number of points you've achieved out of a total possible points.</span></span>

<span data-ttu-id="d212f-119">さらに、スコアの横にある [ **含** める] ボタンを選択した場合は、スコアの異なるビューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="d212f-120">これらのさまざまなスコア ビューは、スコア タイルとポイントブレークダウン グラフのグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="d212f-121">全体的なスコアのビューに追加できるスコアを次に示します。スコア全体の全体像を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="d212f-122">**計画されたスコア**: 計画されたアクションが完了すると、投影されたスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="d212f-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="d212f-123">**現在のライセンス スコア**: 現在の Microsoft ライセンスで実現できるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="d212f-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="d212f-124">**達成可能なスコア**: Microsoft ライセンスと現在のリスク受け入れで達成できるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="d212f-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="d212f-125">考えられるすべてのスコア ビューを含めた場合、このビューは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-125">This view is what it will look like if you've included all possible score views:</span></span>

![計画されたスコア、現在のライセンス スコア、達成可能なスコアを含むセキュリティ スコア](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="d212f-127">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="d212f-127">Take action to improve your score</span></span>

<span data-ttu-id="d212f-128">[ **改善アクション]** タブには、攻撃の可能性に対処するセキュリティの推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="d212f-129">また、その状態 (対処、計画済み、リスク受け入れ、サード パーティ経由での解決、代替軽減策による解決、完了) も含まれます。</span><span class="sxs-lookup"><span data-stu-id="d212f-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="d212f-130">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d212f-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="d212f-131">ランク付け</span><span class="sxs-lookup"><span data-stu-id="d212f-131">Ranking</span></span>

<span data-ttu-id="d212f-132">ランク付けは、達成するポイント数、実装の難易度、ユーザーへの影響、複雑さに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="d212f-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="d212f-133">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d212f-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="d212f-134">改善アクションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="d212f-134">View improvement action details</span></span>

<span data-ttu-id="d212f-135">特定の改善アクションを選択すると、ページ全体のフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="d212f-136">![改善アクションのフライアウトの例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *図 2: 改善アクションのフライアウトの例*</span><span class="sxs-lookup"><span data-stu-id="d212f-136">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="d212f-137">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d212f-137">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="d212f-138">[ **管理] を** 選択して構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d212f-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="d212f-139">その後、アクションが価値のあるポイントを取得し、フライアウトに表示されます。ポイントの更新には、通常約 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d212f-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="d212f-140">[ **共有]** を選択して、改善アクションへの直接リンクをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d212f-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="d212f-141">また、電子メール、Microsoft Teams、Microsoft Planner、ServiceNow などのリンクを共有するプラットフォームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-141">You can also choose the platform to share the link, such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="d212f-142">ServiceNow を選択すると、ServiceNow と Microsoft 365 セキュリティ センター ホームに表示される変更チケットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-142">Selecting ServiceNow will let you create a change ticket that will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="d212f-143">詳細については [、Microsoft 365 セキュリティ センターと ServiceNow の統合を参照してください](tickets-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d212f-143">To learn more, see [Microsoft 365 security center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="d212f-144">改善アクションの状態を選択する</span><span class="sxs-lookup"><span data-stu-id="d212f-144">Choose an improvement action status</span></span>

<span data-ttu-id="d212f-145">状態を選択し、改善アクションに固有のメモを記録します。</span><span class="sxs-lookup"><span data-stu-id="d212f-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="d212f-146">**対処するには** 、 - 改善アクションが必要なと認識し、将来ある時点で対処する予定です。</span><span class="sxs-lookup"><span data-stu-id="d212f-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="d212f-147">この状態は、部分的に検出されたが、完全には完了していないアクションにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="d212f-148">**計画済** み - 改善アクションを完了する具体的な計画が実施されています。</span><span class="sxs-lookup"><span data-stu-id="d212f-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="d212f-149">**受け入れられる** リスク - セキュリティは常に使いやすさとバランスを取る必要があります。すべての推奨事項が環境で機能するとは限しません。</span><span class="sxs-lookup"><span data-stu-id="d212f-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="d212f-150">その場合は、リスクまたは残りのリスクを受け入れ、改善アクションを実行しない選択をすることができます。</span><span class="sxs-lookup"><span data-stu-id="d212f-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="d212f-151">ポイントは与えらえませんが、改善アクションの一覧にアクションが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d212f-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="d212f-152">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="d212f-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="d212f-153">**サード パーティを通** じて解決され、別の軽減策によって **解決されました。** 改善アクションは、サードパーティのアプリケーションまたはソフトウェア、または内部ツールによって既に対処されています。</span><span class="sxs-lookup"><span data-stu-id="d212f-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="d212f-154">アクションの価値のあるポイントが得られるので、スコアは全体的なセキュリティの体勢をより良く反映します。</span><span class="sxs-lookup"><span data-stu-id="d212f-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="d212f-155">サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d212f-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="d212f-156">改善アクションがこれらの状態のいずれかとしてマークされている場合、Microsoft は実装の完全性を確認できません。</span><span class="sxs-lookup"><span data-stu-id="d212f-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="d212f-157">脅威&脆弱性管理の改善アクション</span><span class="sxs-lookup"><span data-stu-id="d212f-157">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="d212f-158">[デバイス] カテゴリの改善のためのアクションでは、状態を選択できません。</span><span class="sxs-lookup"><span data-stu-id="d212f-158">For improvement actions in the "Device" category, you won't be able to choose statuses.</span></span> <span data-ttu-id="d212f-159">代わりに[、Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)セキュリティ センターの関連する脅威&脆弱性管理[(TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)のセキュリティに関する推奨事項に指示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-159">Instead, you'll be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="d212f-160">選択した例外と記述する正当な理由は、そのポータルに固有です。</span><span class="sxs-lookup"><span data-stu-id="d212f-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="d212f-161">Microsoft セキュア スコア ポータルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d212f-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="d212f-162">完了した改善アクション</span><span class="sxs-lookup"><span data-stu-id="d212f-162">Completed improvement actions</span></span>

<span data-ttu-id="d212f-163">改善アクションの可能性があるすべてのポイントが達成された後、改善アクションは"完了" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="d212f-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="d212f-164">完了した改善アクションは Microsoft データによって確認され、ステータスを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d212f-164">Completed improvement actions are confirmed though Microsoft data, and you won't be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="d212f-165">情報を評価し、ユーザーへの影響を確認する</span><span class="sxs-lookup"><span data-stu-id="d212f-165">Assess information and review user impact</span></span>

<span data-ttu-id="d212f-166">「一目 **で」という** セクションには、カテゴリ、保護できる攻撃、製品が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="d212f-167">ユーザー **への影響は**、改善アクションが実施された場合にユーザーが経験する操作を示し、影響を受けるユーザーには、その操作を行うユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-167">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="d212f-168">改善アクションを実装する</span><span class="sxs-lookup"><span data-stu-id="d212f-168">Implement the improvement action</span></span>

<span data-ttu-id="d212f-169">[ **実装** ] セクションには、すべての前提条件、改善アクションを完了するためのステップ バイ ステップの次の手順、改善アクションの現在の実装状態、および詳細なリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="d212f-170">前提条件には、取得する必要があるライセンス、または改善アクションに対処する前に完了する必要があるアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d212f-170">Prerequisites include any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="d212f-171">改善アクションを完了するのに十分なシートがライセンスに含まれています。また、それらのライセンスが必要なユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d212f-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="d212f-172">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="d212f-172">We want to hear from you</span></span>

<span data-ttu-id="d212f-173">問題がある場合は、セキュリティ/プライバシー/コンプライアンス コミュニティに投稿して [&知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) らせてください。</span><span class="sxs-lookup"><span data-stu-id="d212f-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="d212f-174">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="d212f-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="d212f-175">関連リソース</span><span class="sxs-lookup"><span data-stu-id="d212f-175">Related resources</span></span>

- [<span data-ttu-id="d212f-176">Microsoft セキュア スコアの概要</span><span class="sxs-lookup"><span data-stu-id="d212f-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="d212f-177">Microsoft セキュア スコアの履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="d212f-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="d212f-178">今後の予定</span><span class="sxs-lookup"><span data-stu-id="d212f-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="d212f-179">新機能</span><span class="sxs-lookup"><span data-stu-id="d212f-179">What's new</span></span>](microsoft-secure-score-whats-new.md)
