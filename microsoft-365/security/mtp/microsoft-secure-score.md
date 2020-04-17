---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
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
ms.openlocfilehash: f70d2f601dfb697d8affa8bb47148f6e454c5d8e
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541097"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="3be75-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="3be75-104">Microsoft Secure Score</span></span>

<span data-ttu-id="3be75-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="3be75-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="3be75-106">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="3be75-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="3be75-107">Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="3be75-108">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="3be75-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="3be75-109">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="3be75-109">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="3be75-110">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="3be75-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="3be75-111">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="3be75-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="3be75-112">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="3be75-113">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="3be75-114">さらに、[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api) を介して、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="3be75-115">「[Secure Score リソースの種類](https://go.microsoft.com/fwlink/?linkid=2092996)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be75-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3be75-116">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="3be75-116">How it works</span></span>

<span data-ttu-id="3be75-117">推奨されるセキュリティ機能を構成したり、セキュリティ関連のタスク (レポートの表示など) を実行したり、サードパーティ製のアプリケーションやソフトウェアを使用して改善アクションに対応したりすると、ポイントが与えられます。</span><span class="sxs-lookup"><span data-stu-id="3be75-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="3be75-118">改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。</span><span class="sxs-lookup"><span data-stu-id="3be75-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="3be75-119">ライセンスに関係なく、考えられるすべての改善策を紹介するため、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="3be75-120">絶対的なセキュリティ体制がセキュア スコアによって示されます。これは、組織が所有する製品ライセンスに関係なく常に同じです。</span><span class="sxs-lookup"><span data-stu-id="3be75-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="3be75-121">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="3be75-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="3be75-122">スコアはリアルタイムで更新され、視覚エフェクト ページと改善アクション ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="3be75-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="3be75-123">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="3be75-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="3be75-124">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="3be75-124">How improvement actions are scored</span></span>

<span data-ttu-id="3be75-125">多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善アクションを実装すると、ポイントの 100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="3be75-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="3be75-126">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="3be75-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="3be75-127">たとえば、改善アクションで、すべてのユーザーを多要素認証で保護するなら 30 ポイントを取得すると示しているとします。合計 100 人のユーザーのうち 5 人しか保護されていない場合、部分的なスコアとして約 2 ポイントが与えられます (保護されているユーザー 5 ÷ 合計数 100 × 最大ポイント 30 = 2 ポイント)。</span><span class="sxs-lookup"><span data-stu-id="3be75-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="3be75-128">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="3be75-128">Products included in Secure Score</span></span>

<span data-ttu-id="3be75-129">現在、Office 365 (SharePoint Online、Exchange Online、OneDrive for Business、Microsoft Information Protection など)、Azure AD、Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-129">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="3be75-130">その他のセキュリティ製品 (Azure ATP、Microsoft Defender ATP など) に関する推奨事項は、近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="3be75-131">推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。</span><span class="sxs-lookup"><span data-stu-id="3be75-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="3be75-132">また、改善のための処置をサードパーティによるカバー対象としてマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="3be75-133">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="3be75-133">Required permissions</span></span>

<span data-ttu-id="3be75-134">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="3be75-135">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="3be75-135">Read and write roles</span></span>

<span data-ttu-id="3be75-136">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="3be75-137">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="3be75-138">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-138">Global administrator</span></span>
* <span data-ttu-id="3be75-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-139">Security administrator</span></span>
* <span data-ttu-id="3be75-140">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-140">Exchange administrator</span></span>
* <span data-ttu-id="3be75-141">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-141">SharePoint administrator</span></span>
* <span data-ttu-id="3be75-142">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-142">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="3be75-143">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="3be75-143">Read-only roles</span></span>

<span data-ttu-id="3be75-144">読み取り専用アクセス許可があっても、改善アクションのステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="3be75-144">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="3be75-145">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-145">Helpdesk administrator</span></span>
* <span data-ttu-id="3be75-146">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-146">User administrator</span></span>
* <span data-ttu-id="3be75-147">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="3be75-147">Service administrator</span></span>
* <span data-ttu-id="3be75-148">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="3be75-148">Security reader</span></span>
* <span data-ttu-id="3be75-149">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="3be75-149">Security operator</span></span>
* <span data-ttu-id="3be75-150">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="3be75-150">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="3be75-151">Graph API</span><span class="sxs-lookup"><span data-stu-id="3be75-151">Graph API</span></span>

<span data-ttu-id="3be75-152">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-152">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="3be75-153">SecurityEvents.Read.All (読み取り専用の役割)</span><span class="sxs-lookup"><span data-stu-id="3be75-153">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="3be75-154">SecurityEvents.ReadWrite.All (読み取りと書き込みの役割)</span><span class="sxs-lookup"><span data-stu-id="3be75-154">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="3be75-155">セキュリティ体制の可視性を獲得する</span><span class="sxs-lookup"><span data-stu-id="3be75-155">Gain visibility into your security posture</span></span>

<span data-ttu-id="3be75-156">必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="3be75-156">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="3be75-157">ID (Azure AD アカウントと役割)</span><span class="sxs-lookup"><span data-stu-id="3be75-157">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="3be75-158">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="3be75-158">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="3be75-159">デバイス (現在のところ、改善のための処置はありません)</span><span class="sxs-lookup"><span data-stu-id="3be75-159">Device (no improvement actions for now)</span></span>
* <span data-ttu-id="3be75-160">アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)</span><span class="sxs-lookup"><span data-stu-id="3be75-160">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="3be75-161">インフラストラクチャ (現在のところ、改善のための処置はありません)</span><span class="sxs-lookup"><span data-stu-id="3be75-161">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="3be75-162">[Microsoft セキュア スコアの概要] ページでは、これらのグループ間でポイントがどのように分割され、どのポイントが利用可能であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3be75-162">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="3be75-163">また、[概要] ページでは、合計スコアの全表示ビュー、ベンチマーク比較によるセキュア スコア履歴の傾向、スコアを上げるために優先して実装できる改善のための処置を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-163">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="3be75-164">![セキュア スコア ホームページ](../../media/secure-score/homepage-original.png)
*図 1: Microsoft セキュア スコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="3be75-164">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="3be75-165">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="3be75-165">Take action to improve your score</span></span>

<span data-ttu-id="3be75-166">[改善のための処置] タブには、攻撃を受ける可能性がある対象のセキュリティ推奨事項とその状態 (完了済み、未完了、サード パーティを通じて解決済み、無視) が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-166">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="3be75-167">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-167">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="3be75-168">ランク付け</span><span class="sxs-lookup"><span data-stu-id="3be75-168">Ranking</span></span>

<span data-ttu-id="3be75-169">ランク付けは、残りのポイント数、実装の難しさ、ユーザーへの影響、複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="3be75-169">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="3be75-170">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3be75-170">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="3be75-171">アクション</span><span class="sxs-lookup"><span data-stu-id="3be75-171">Actions</span></span>

<span data-ttu-id="3be75-172">Microsoft セキュア スコアでは、[スコアなし] と表示されたアクションは追跡しません。</span><span class="sxs-lookup"><span data-stu-id="3be75-172">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="3be75-173">アクションを実行することはできますが、完了してもスコアには影響しません。</span><span class="sxs-lookup"><span data-stu-id="3be75-173">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="3be75-174">将来、Microsoft セキュア スコアによってアクションが追跡されるようになったときに既にそれを完了していた場合、その変更は自動的にセキュア スコアに反映されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-174">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="3be75-175">特定の改善アクションを選択すると、ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-175">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="3be75-176">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-176">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="3be75-177">**[ビューの設定]** を選択して構成画面に移動し、変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="3be75-177">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="3be75-178">アクションに応じたポイントが獲得され、ポップアップの上部に表示されます。ポイントの更新には最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-178">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="3be75-179">改善アクションがサードパーティ製のアプリケーションやソフトウェアによって既に処理されている場合は、**[サードパーティを通じて解決する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be75-179">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="3be75-180">アクションに応じたポイントが獲得されるので、セキュア スコアはセキュリティ体制全体をより正確に反映します。</span><span class="sxs-lookup"><span data-stu-id="3be75-180">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="3be75-181">サードパーティがコントロールをカバーしなくなった場合は、改善アクションを未完了としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-181">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="3be75-182">Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合、スコアの要件を満たしているかどうかを確認できません。</span><span class="sxs-lookup"><span data-stu-id="3be75-182">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="3be75-183">リスクを許容し、改善アクションを実行しないことに決めた場合は、**[無視]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be75-183">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="3be75-184">改善アクションを無視すると、達成できるセキュア スコアのポイント合計が減ります。</span><span class="sxs-lookup"><span data-stu-id="3be75-184">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="3be75-185">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="3be75-185">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="3be75-186">改善アクションを選択すると、ポイントを取得して保持するために環境の一部を定期的に確認する必要がある場合は、**[レビュー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3be75-186">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="3be75-187">たとえば、メールボックス転送ルールでは、データがネットワークから流出していないことを毎週確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-187">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="3be75-188">何も変更する必要はありませんが、アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-188">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="3be75-189">定期的にルールを確認すると、ポイントが与えられます。</span><span class="sxs-lookup"><span data-stu-id="3be75-189">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="3be75-190">そうしない場合、スコアは減点されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-190">If not, the score is reduced.</span></span>

![セキュア スコア改善アクションの例](../../media/secure-score/secure-score1x450.png) ![セキュア スコア改善アクションのレビューの例](../../media/secure-score/secure-score2x450.png)

<span data-ttu-id="3be75-193">*図 2 & 3: 改善アクションのポップアップ*</span><span class="sxs-lookup"><span data-stu-id="3be75-193">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="3be75-194">時間の経過に伴う改善のモニタリング</span><span class="sxs-lookup"><span data-stu-id="3be75-194">Monitor improvements over time</span></span>

<span data-ttu-id="3be75-195">**[履歴]** タブで、組織のスコアのグラフを時系列で表示することができます。グラフの下には、選択した期間内に実行されたすべてのアクションと、結果として得られるポイントやカテゴリなどの属性が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3be75-195">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="3be75-196">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="3be75-196">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="3be75-197">リスク認識</span><span class="sxs-lookup"><span data-stu-id="3be75-197">Risk awareness</span></span>

<span data-ttu-id="3be75-198">Microsoft セキュア スコアは、システム構成、ユーザーの行動、その他セキュリティ関連の測定に基づいて、セキュリティ体制の概要を数値的に表したものです。システムまたはデータが侵害される可能性を絶対的に測定するものではありません。</span><span class="sxs-lookup"><span data-stu-id="3be75-198">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="3be75-199">むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3be75-199">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="3be75-200">オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="3be75-200">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="3be75-201">新機能</span><span class="sxs-lookup"><span data-stu-id="3be75-201">What's new?</span></span>

<span data-ttu-id="3be75-202">Microsoft セキュア スコアがお客様のセキュリティ体制をよりよく反映するように、いくつかの変更を加えました。</span><span class="sxs-lookup"><span data-stu-id="3be75-202">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span>

<span data-ttu-id="3be75-203">今後の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be75-203">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="march-2020"></a><span data-ttu-id="3be75-204">2020 年 3 月</span><span class="sxs-lookup"><span data-stu-id="3be75-204">March 2020</span></span>

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="3be75-205">Azure AD の改善のための処置に関するセキュリティの既定群をサポートする</span><span class="sxs-lookup"><span data-stu-id="3be75-205">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="3be75-206">Microsoft セキュア スコアは、[Azure AD のセキュリティの既定群](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善のための処置を更新します。これにより、構成済みのセキュリティ設定を使用して、一般的な攻撃から組織を保護することが簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3be75-206">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="3be75-207">これは、次の改善のための処置に影響します。</span><span class="sxs-lookup"><span data-stu-id="3be75-207">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="3be75-208">安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする</span><span class="sxs-lookup"><span data-stu-id="3be75-208">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="3be75-209">管理者の役割に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-209">Require MFA for administrative roles</span></span>
- <span data-ttu-id="3be75-210">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="3be75-210">Enable policy to block legacy authentication</span></span>

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="3be75-211">改善のための処置のうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しました。</span><span class="sxs-lookup"><span data-stu-id="3be75-211">Removed improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="3be75-212">Microsoft セキュリティ スコアが有意義であり、すべての改善のための処置が測定可能かつ信頼性の高いものになるよう、次の改善のための処置については削除します。</span><span class="sxs-lookup"><span data-stu-id="3be75-212">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="3be75-213">OneDrive for Business でユーザー ドキュメントを保存する</span><span class="sxs-lookup"><span data-stu-id="3be75-213">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="3be75-214">Office 365 ATP の安全な添付ファイルに関するポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="3be75-214">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="3be75-215">Office 365 の安全なリンクをセットアップして URL を確認する</span><span class="sxs-lookup"><span data-stu-id="3be75-215">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="3be75-216">メールボックスの委任を許可しない</span><span class="sxs-lookup"><span data-stu-id="3be75-216">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="3be75-217">サイトとドキュメントの匿名ゲストの共有リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="3be75-217">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="3be75-218">Cloud App Security コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="3be75-218">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="3be75-219">外部共有リンクの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="3be75-219">Configure expiration time for external sharing links</span></span>
- <span data-ttu-id="3be75-220">監査データの記録をオンにする</span><span class="sxs-lookup"><span data-stu-id="3be75-220">Turn on audit data recording</span></span>
- <span data-ttu-id="3be75-221">危険な非準拠のシャドウ IT アプリケーションを検出する</span><span class="sxs-lookup"><span data-stu-id="3be75-221">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="3be75-222">アクセス許可を確認し、環境に接続されたリスクの高い OAuth アプリの接続をブロックする</span><span class="sxs-lookup"><span data-stu-id="3be75-222">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="3be75-223">SharePoint Online ドキュメント ライブラリでバージョン管理を設定する</span><span class="sxs-lookup"><span data-stu-id="3be75-223">Set up versioning on SharePoint online document libraries</span></span>
- <span data-ttu-id="3be75-224">過去30日間に使用されていないアカウントの削除/ブロック</span><span class="sxs-lookup"><span data-stu-id="3be75-224">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="3be75-225">グローバル管理者を5名未満で指定する</span><span class="sxs-lookup"><span data-stu-id="3be75-225">Designate fewer than 5 global admins</span></span>

#### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="3be75-226">[スコア未計算] の改善のための処置を削除済み</span><span class="sxs-lookup"><span data-stu-id="3be75-226">Removed "not scored" improvement actions</span></span>

<span data-ttu-id="3be75-227">セキュア スコアの原則の 1 つは、スコアが標準化され、関連付けが容易でなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="3be75-227">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="3be75-228">測定できない、または実用的ではない改善のための処置は、混乱を引き起こしてきました。</span><span class="sxs-lookup"><span data-stu-id="3be75-228">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="3be75-229">Microsoft セキュア スコアは、すべての推奨事項が明確にスコア化できる場合にのみ意味を成します。</span><span class="sxs-lookup"><span data-stu-id="3be75-229">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="3be75-230">スコアの付かない改善のための処置は、測ることもできません。</span><span class="sxs-lookup"><span data-stu-id="3be75-230">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="3be75-231">このような理由から、スコアの付かない改善のための処置はすべて削除されました。</span><span class="sxs-lookup"><span data-stu-id="3be75-231">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="3be75-232">お客様は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3be75-232">No action is needed on your part.</span></span>

#### <a name="removed-device-improvement-actions"></a><span data-ttu-id="3be75-233">デバイス向け改善のための処置の削除</span><span class="sxs-lookup"><span data-stu-id="3be75-233">Removed device improvement actions</span></span>

<span data-ttu-id="3be75-234">Microsoft セキュア スコア デバイス カテゴリの改善のための処置を査定した結果、このアクションは現在、デバイスの構成状態ではなくポリシーの状態を評価していると判断されました。</span><span class="sxs-lookup"><span data-stu-id="3be75-234">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="3be75-235">構成はセキュリティ体制に直結しているため、既存のデバイス向けのアクションは組織の体制を十分に反映していないと判断されました。</span><span class="sxs-lookup"><span data-stu-id="3be75-235">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="3be75-236">診断データを直接使用して、デバイスのセキュリティ体制をより十分に反映する一連の推奨事項を提供するため、デバイス カテゴリの現在のアクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3be75-236">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="3be75-237">次の改善のための処置が削除されました。</span><span class="sxs-lookup"><span data-stu-id="3be75-237">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="3be75-238">Microsoft Intune Mobile Device Management を有効にする</span><span class="sxs-lookup"><span data-stu-id="3be75-238">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="3be75-239">Microsoft Intune の Android 用コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-239">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="3be75-240">Microsoft Intune の Android for Work 用コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-240">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="3be75-241">Microsoft Intune の Android 用アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-241">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="3be75-242">Microsoft Intune の iOS 用アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-242">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="3be75-243">Microsoft Intune コンプライアンス ポリシーが割り当てられていないデバイスを未準拠としてマークする</span><span class="sxs-lookup"><span data-stu-id="3be75-243">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="3be75-244">Microsoft Intune の iOS 用コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-244">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="3be75-245">Microsoft Intune の macOS 用コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-245">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="3be75-246">Microsoft Intune の Windows 用コンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-246">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="3be75-247">Microsoft Intune の Android 用構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-247">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="3be75-248">Microsoft Intune の Android for Work 用構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-248">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="3be75-249">Microsoft Intune の macOS 用構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-249">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="3be75-250">Microsoft Intune の iOS 用構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-250">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="3be75-251">Microsoft Intune の Windows 用構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-251">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="3be75-252">Microsoft Intune で脱獄の高度な検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="3be75-252">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="3be75-253">すべてのデバイスに修正プログラムを適用し、ウイルス対策およびファイアウォールを有効にするよう要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-253">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="3be75-254">Microsoft Intune への Windows Defender ATP の統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="3be75-254">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="3be75-255">Microsoft Intune の Windows 用情報保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3be75-255">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="3be75-256">すべてのデバイスに高度なセキュリティ構成を要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-256">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="3be75-257">ブロックされたデバイスのレポートを毎週確認する</span><span class="sxs-lookup"><span data-stu-id="3be75-257">Review blocked devices report weekly</span></span>

#### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="3be75-258">MFA 改善アクションの更新</span><span class="sxs-lookup"><span data-stu-id="3be75-258">MFA improvement action updates</span></span>

<span data-ttu-id="3be75-259">企業には、自社の業務に適したポリシーを適用するとともに最高度のセキュリティを確保する必要性があります。そのニーズを反映して、Microsoft セキュア スコアでは多要素認証を中心とした 3 つの改善のための処置を削除し、2 つを追加しました。</span><span class="sxs-lookup"><span data-stu-id="3be75-259">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="3be75-260">削除された改善のための処置は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3be75-260">Removed improvement actions:</span></span>

- <span data-ttu-id="3be75-261">すべてのユーザーを多要素認証に登録する</span><span class="sxs-lookup"><span data-stu-id="3be75-261">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="3be75-262">すべてのユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-262">Require MFA for all users</span></span>
- <span data-ttu-id="3be75-263">Azure AD 特権ロールに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-263">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="3be75-264">追加された改善のための処置は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3be75-264">Added improvement actions:</span></span>

- <span data-ttu-id="3be75-265">安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする</span><span class="sxs-lookup"><span data-stu-id="3be75-265">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="3be75-266">管理者の役割に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3be75-266">Require MFA for administrative roles</span></span>

 <span data-ttu-id="3be75-267">この新しい改善のための処置では、ディレクトリ全体で多要素認証 (MFA) をユーザーまたは管理者に登録し、組織のニーズに合ったポリシーの適切な設定を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be75-267">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="3be75-268">主な目標は、柔軟性を持ち、すべてのユーザーと管理者が複数の要因またはリスク ベースの ID 検証プロンプトで認証できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="3be75-268">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="3be75-269">これは、スコープ設定された決定を適用する複数のポリシーを持つか、またはセキュリティの既定値 (3 月 16 日公開) を設定して、Microsoft がユーザーに MFA を要求するタイミングを決定するという形で行えます。</span><span class="sxs-lookup"><span data-stu-id="3be75-269">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

#### <a name="removed-review-improvement-actions"></a><span data-ttu-id="3be75-270">"レビュー" 改善のための処置の削除</span><span class="sxs-lookup"><span data-stu-id="3be75-270">Removed "review" improvement actions</span></span>

<span data-ttu-id="3be75-271">セキュア スコアの原則の 1 つは、スコアが標準化され、関連付けが容易でなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="3be75-271">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="3be75-272">測定できない、または実用的ではない改善のための処置は、混乱を引き起こしてきました。</span><span class="sxs-lookup"><span data-stu-id="3be75-272">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="3be75-273">1 つの Microsoft セキュア スコアが意味を成すのは、すべての推奨事項が明確にスコア化できる場合のみです。</span><span class="sxs-lookup"><span data-stu-id="3be75-273">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="3be75-274">レビュー改善のための処置は、他の改善のための処置と同じ基準で計測することができません。</span><span class="sxs-lookup"><span data-stu-id="3be75-274">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="3be75-275">このような理由から、レビュー ケーデンスを必要としたすべての改善のための処置は一時的に削除されています。</span><span class="sxs-lookup"><span data-stu-id="3be75-275">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="3be75-276">お客様は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3be75-276">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="3be75-277">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="3be75-277">Preview features</span></span>

<span data-ttu-id="3be75-278">以下の機能が[プレビュー リリース](microsoft-secure-score-preview.md)に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="3be75-278">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="3be75-279">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="3be75-279">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="3be75-280">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="3be75-280">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="3be75-281">スコア回帰の追跡と監視の向上</span><span class="sxs-lookup"><span data-stu-id="3be75-281">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="3be75-282">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="3be75-282">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="3be75-283">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="3be75-283">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="3be75-284">ポイント システムの単純化</span><span class="sxs-lookup"><span data-stu-id="3be75-284">Simplification of the points system</span></span>
* <span data-ttu-id="3be75-285">その他多数。</span><span class="sxs-lookup"><span data-stu-id="3be75-285">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="3be75-286">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="3be75-286">We want to hear from you</span></span>

<span data-ttu-id="3be75-287">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="3be75-287">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="3be75-288">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="3be75-288">We're monitoring the community and will provide help.</span></span>
