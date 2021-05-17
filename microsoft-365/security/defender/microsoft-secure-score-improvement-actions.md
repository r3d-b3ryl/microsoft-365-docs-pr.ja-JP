---
title: Microsoft Secure Score を通じてセキュリティの態勢を評価する
description: セキュリティ センターで Microsoft Secure Score を改善するためのアクションを実行するMicrosoft 365説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246399"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="e5361-104">Microsoft Secure Score を使用してセキュリティの態勢を評価する</span><span class="sxs-lookup"><span data-stu-id="e5361-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e5361-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5361-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="e5361-106">これは、セキュリティ センター https://security.microsoft.com/securescore のMicrosoft 365[にあります](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e5361-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="e5361-107">必要な情報を迅速に見つけるために、Microsoft の改善アクションはグループに整理されています。</span><span class="sxs-lookup"><span data-stu-id="e5361-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="e5361-108">ID (Azure Active Directoryアカウント&ロール)</span><span class="sxs-lookup"><span data-stu-id="e5361-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="e5361-109">デバイス (Microsoft Defender for Endpoint, 既知 [の Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="e5361-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="e5361-110">アプリ (電子メールアプリとクラウド アプリ (Office 365 Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="e5361-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="e5361-111">Microsoft Secure Score の最近のリリースでは、スコア付けモデルが改善され、Microsoft Secure Score が一時的に Identity Secure Score および Graph API と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="e5361-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="e5361-112">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="e5361-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="e5361-113">Microsoft Secure Score の概要ページで、これらのグループ間でのポイントの分割方法と使用可能なポイントを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5361-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="e5361-114">また、合計スコアの全体表示、ベンチマーク比較によるセキュリティで保護されたスコアの履歴傾向、スコアを向上させるために実行できる優先順位付けされた改善アクションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Secure Score のホームページ](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="e5361-116">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="e5361-116">Check your current score</span></span>

<span data-ttu-id="e5361-117">現在のスコアを確認するには、[Microsoft Secure Score の概要] ページに移動し、[セキュリティで保護されたスコア] というタイル **を探します**。</span><span class="sxs-lookup"><span data-stu-id="e5361-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="e5361-118">スコアはパーセンテージで表示され、合計可能なポイント数から達成したポイント数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="e5361-119">さらに、スコアの横にある **[含** める] ボタンを選択した場合は、スコアの異なるビューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="e5361-120">これらの異なるスコア ビューは、スコア タイルとポイント内訳グラフのグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="e5361-121">全体的なスコアのビューに追加できるスコアを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e5361-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="e5361-122">**計画スコア**: 計画されたアクションが完了すると、投影スコアを表示する</span><span class="sxs-lookup"><span data-stu-id="e5361-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="e5361-123">**現在のライセンス スコア**: 現在の Microsoft ライセンスで達成できるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="e5361-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="e5361-124">**達成可能なスコア**: Microsoft ライセンスと現在のリスク受け入れで達成できるスコアを表示する</span><span class="sxs-lookup"><span data-stu-id="e5361-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="e5361-125">このビューは、すべての可能なスコア ビューを含めた場合の外観です。</span><span class="sxs-lookup"><span data-stu-id="e5361-125">This view is what it will look like if you've included all possible score views:</span></span>

![計画スコア、現在のライセンス スコア、達成可能なスコアを含む安全なスコア](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="e5361-127">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="e5361-127">Take action to improve your score</span></span>

<span data-ttu-id="e5361-128">[ **改善アクション] タブ** には、攻撃の可能性がある表面に対処するセキュリティ推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="e5361-129">また、その状態 (対処、計画、リスクの受け入れ、第三者による解決、代替緩和による解決、完了) も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5361-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="e5361-130">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5361-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="e5361-131">ランク付け</span><span class="sxs-lookup"><span data-stu-id="e5361-131">Ranking</span></span>

<span data-ttu-id="e5361-132">ランキングは、達成するために残されたポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="e5361-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="e5361-133">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e5361-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="e5361-134">改善アクションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e5361-134">View improvement action details</span></span>

<span data-ttu-id="e5361-135">特定の改善アクションを選択すると、ページ全体の飛び出しが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![改善アクションの飛び出しの例](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="e5361-137">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="e5361-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="e5361-138">[ **管理] を** 選択して構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="e5361-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="e5361-139">その後、アクションが価値のあるポイントを取得し、フライアウトに表示されます。ポイントの更新には通常約 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="e5361-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="e5361-140">[ **共有] を** 選択して、改善アクションへの直接リンクをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e5361-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="e5361-141">また、リンクを共有するプラットフォーム (メール、Microsoft Planner など) をMicrosoft Teams選択できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="e5361-142">メモ **を追加** して、進行状況やコメントする他の項目を追跡します。</span><span class="sxs-lookup"><span data-stu-id="e5361-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="e5361-143">改善アクションに独自の **タグ** を追加する場合は、それらのタグでフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="e5361-144">改善アクションの状態を選択する</span><span class="sxs-lookup"><span data-stu-id="e5361-144">Choose an improvement action status</span></span>

<span data-ttu-id="e5361-145">ステータスを選択し、改善アクションに固有のメモを記録します。</span><span class="sxs-lookup"><span data-stu-id="e5361-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="e5361-146">**対処するには** - 改善アクションが必要と認識し、将来ある時点で対処する予定です。</span><span class="sxs-lookup"><span data-stu-id="e5361-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="e5361-147">この状態は、部分的に検出されたが完全には完了していないアクションにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="e5361-148">**計画済** み - 改善アクションを完了する具体的な計画が実施されています。</span><span class="sxs-lookup"><span data-stu-id="e5361-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="e5361-149">**リスクの受け** 入れ - セキュリティは常に使いやすさとバランスを取り、すべての推奨事項が環境で機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5361-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="e5361-150">その場合は、リスクまたは残りのリスクを受け入れ、改善アクションを実行しない選択できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="e5361-151">ポイントは指定されませんが、改善アクションの一覧にアクションが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e5361-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="e5361-152">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="e5361-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="e5361-153">**サード パーティによって解決され** 、代替の軽減策によって **解決されました。** 改善アクションは、サード パーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既に対処されています。</span><span class="sxs-lookup"><span data-stu-id="e5361-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="e5361-154">アクションが価値のあるポイントを得られるので、スコアは全体的なセキュリティの姿勢をよりよく反映します。</span><span class="sxs-lookup"><span data-stu-id="e5361-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="e5361-155">サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e5361-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="e5361-156">改善アクションがこれらの状態のいずれかとしてマークされている場合、Microsoft は実装の完全性を確認できません。</span><span class="sxs-lookup"><span data-stu-id="e5361-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="e5361-157">脅威& 脆弱性の管理改善アクション</span><span class="sxs-lookup"><span data-stu-id="e5361-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="e5361-158">[デバイス] カテゴリの改善アクションでは、状態を選択できません。</span><span class="sxs-lookup"><span data-stu-id="e5361-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="e5361-159">代わりに、アクションを実行する脅威と脆弱性の管理[関連付けられている](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)セキュリティ[Microsoft Defender セキュリティ センター指示されます](/windows/security/threat-protection/microsoft-defender-atp/use)。</span><span class="sxs-lookup"><span data-stu-id="e5361-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="e5361-160">選択した例外と、作成する正当化は、そのポータルに固有です。</span><span class="sxs-lookup"><span data-stu-id="e5361-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="e5361-161">Microsoft Secure Score ポータルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="e5361-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="e5361-162">改善アクションの完了</span><span class="sxs-lookup"><span data-stu-id="e5361-162">Completed improvement actions</span></span>

<span data-ttu-id="e5361-163">改善アクションの可能性があるすべてのポイントが達成された後、改善アクションの状態は "完了" になります。</span><span class="sxs-lookup"><span data-stu-id="e5361-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="e5361-164">Microsoft データを使用して、完了した改善アクションが確認され、状態を変更できない。</span><span class="sxs-lookup"><span data-stu-id="e5361-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="e5361-165">情報を評価し、ユーザーへの影響を確認する</span><span class="sxs-lookup"><span data-stu-id="e5361-165">Assess information and review user impact</span></span>

<span data-ttu-id="e5361-166">「一目で **見る」** というセクションには、カテゴリ、保護できる攻撃、製品が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="e5361-167">**ユーザーの影響** は、改善アクションが実行された場合にユーザーが発生する操作であり、影響を受けるユーザーは影響を受けるユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e5361-167">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="e5361-168">改善アクションの実装</span><span class="sxs-lookup"><span data-stu-id="e5361-168">Implement the improvement action</span></span>

<span data-ttu-id="e5361-169">[ **実装]** セクションには、前提条件、改善アクションを完了するためのステップ バイ ステップの次の手順、改善アクションの現在の実装状態、および詳細なリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="e5361-170">前提条件には、必要なライセンス、または改善アクションに対処する前に完了するアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5361-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="e5361-171">ライセンスに十分なシートが含まれていますので、改善アクションを完了し、それらのライセンスが必要なユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5361-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e5361-172">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="e5361-172">We want to hear from you</span></span>

<span data-ttu-id="e5361-173">問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="e5361-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e5361-174">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="e5361-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e5361-175">関連リソース</span><span class="sxs-lookup"><span data-stu-id="e5361-175">Related resources</span></span>

- [<span data-ttu-id="e5361-176">Microsoft Secure Score の概要</span><span class="sxs-lookup"><span data-stu-id="e5361-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="e5361-177">Microsoft Secure Score の履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="e5361-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e5361-178">今後の予定</span><span class="sxs-lookup"><span data-stu-id="e5361-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="e5361-179">新機能</span><span class="sxs-lookup"><span data-stu-id="e5361-179">What's new</span></span>](microsoft-secure-score-whats-new.md)