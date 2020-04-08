---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
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
ms.openlocfilehash: 2094549e63be0a8e3c2bbc7997de13475c19bb0c
ms.sourcegitcommit: d1909d34ac0cddeb776ff5eb8414bfc9707d5ac1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "43163900"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="5f9fe-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="5f9fe-104">Microsoft Secure Score</span></span>

<span data-ttu-id="5f9fe-105">Microsoft セキュリティスコアは、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="5f9fe-106">セキュリティスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="5f9fe-107">Microsoft 365 セキュリティセンターの集中管理されたダッシュボードから、組織は、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="5f9fe-108">セキュリティで保護されたスコアは、組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="5f9fe-109">組織のセキュリティ体制の現状を報告します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-109">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="5f9fe-110">検出、可視性、ガイダンス、および制御を提供することによって、セキュリティに関する姿勢を向上させます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="5f9fe-111">ベンチマークと比較し、主要業績評価指標 (Kpi) を確立します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="5f9fe-112">組織は、測定基準と傾向の堅牢な視覚化、その他の Microsoft 製品との統合、類似の組織とのスコアの比較など、さまざまな方法でアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="5f9fe-113">このスコアは、サードパーティ製のソリューションが推奨アクションを解決した場合にも反映できます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="5f9fe-114">さらに、 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)を通じて、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="5f9fe-115">[セキュリティで保護されたスコアリソースの種類](https://go.microsoft.com/fwlink/?linkid=2092996)について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5f9fe-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="5f9fe-116">How it works</span></span>

<span data-ttu-id="5f9fe-117">推奨されるセキュリティ機能を構成するためのポイント、セキュリティ関連タスクの実行 (レポートの表示など)、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応を行います。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="5f9fe-118">一部の改善アクションでは、完全に完了した時点でポイントが提供されます。一部のデバイスまたはユーザーに対して完了した場合は、一部の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="5f9fe-119">セキュリティのベストプラクティスを理解し、スコアを向上させることができるように、ライセンスに関係なく、考えられるすべての機能強化を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="5f9fe-120">セキュリティの絶対的な姿勢は、セキュリティで保護されたスコアで表されます。これは、組織が所有しているライセンスの種類にかかわらず変わりません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="5f9fe-121">セキュリティは使いやすさとバランスをとる必要があることに注意してください。お客様の環境ですべての推奨事項が機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="5f9fe-122">スコアはリアルタイムで更新され、視覚エフェクトページと向上アクションページに示されている情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="5f9fe-123">セキュリティで保護されたスコアは、各アクションについて達成されたポイントに関するシステムデータを毎日同期することもあります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="5f9fe-124">改善アクションのスコア</span><span class="sxs-lookup"><span data-stu-id="5f9fe-124">How improvement actions are scored</span></span>

<span data-ttu-id="5f9fe-125">多くの場合、2進数でスコアが獲得されます。たとえば、新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善アクションを実装すると、ポイントの100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="5f9fe-126">その他の改善アクションについては、構成全体のパーセンテージとしてポイントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="5f9fe-127">たとえば、すべてのユーザーが多要素認証を使用していて、保護されているユーザーの合計数が100の場合、[改善] アクションで30ポイント獲得した場合、2ポイント前後の部分的なスコアが与えられます (5 つの保護/100 合計 \* 30 最大 pts = 2 pts パーシャルスコア)。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="5f9fe-128">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="5f9fe-128">Products included in Secure Score</span></span>

<span data-ttu-id="5f9fe-129">現時点では、Office 365 (SharePoint Online、Exchange Online、OneDrive for Business、Microsoft Information Protection など)、Azure AD、および Cloud App Security に関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-129">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="5f9fe-130">Azure ATP、Microsoft Defender ATP など、他のセキュリティ製品の推奨事項は近日中に公開されています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="5f9fe-131">推奨事項では、各製品に関連付けられているすべての攻撃対象が網羅されるわけではありませんが、適切な基準になっています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="5f9fe-132">また、改善アクションをサードパーティの対象としてマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="5f9fe-133">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5f9fe-133">Required permissions</span></span>

<span data-ttu-id="5f9fe-134">Microsoft セキュリティスコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory に次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="5f9fe-135">役割の読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="5f9fe-135">Read and write roles</span></span>

<span data-ttu-id="5f9fe-136">読み取りおよび書き込みアクセス権を使用すると、変更を加えて、セキュリティで保護されたスコアと直接対話できます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="5f9fe-137">読み取り専用アクセスを他のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="5f9fe-138">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-138">Global administrator</span></span>
* <span data-ttu-id="5f9fe-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-139">Security administrator</span></span>
* <span data-ttu-id="5f9fe-140">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-140">Exchange administrator</span></span>
* <span data-ttu-id="5f9fe-141">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-141">SharePoint administrator</span></span>
* <span data-ttu-id="5f9fe-142">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-142">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="5f9fe-143">読み取り専用ロール</span><span class="sxs-lookup"><span data-stu-id="5f9fe-143">Read-only roles</span></span>

<span data-ttu-id="5f9fe-144">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-144">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="5f9fe-145">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-145">Helpdesk administrator</span></span>
* <span data-ttu-id="5f9fe-146">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-146">User administrator</span></span>
* <span data-ttu-id="5f9fe-147">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-147">Service administrator</span></span>
* <span data-ttu-id="5f9fe-148">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-148">Security reader</span></span>
* <span data-ttu-id="5f9fe-149">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="5f9fe-149">Security operator</span></span>
* <span data-ttu-id="5f9fe-150">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="5f9fe-150">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="5f9fe-151">Graph API</span><span class="sxs-lookup"><span data-stu-id="5f9fe-151">Graph API</span></span>

<span data-ttu-id="5f9fe-152">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-152">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="5f9fe-153">SecurityEvents.Read.All (読み取り専用の役割の場合)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-153">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="5f9fe-154">SecurityEvents.ReadWrite.All (読み取りおよび書き込みの役割)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-154">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="5f9fe-155">セキュリティに関する姿勢を把握する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-155">Gain visibility into your security posture</span></span>

<span data-ttu-id="5f9fe-156">より迅速に必要な情報を提供するために、Microsoft の改善アクションがグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-156">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="5f9fe-157">Identity (Azure AD アカウント & の役割)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-157">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="5f9fe-158">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-158">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="5f9fe-159">デバイス (現時点では改善アクションはありません)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-159">Device (no improvement actions for now)</span></span>
* <span data-ttu-id="5f9fe-160">アプリ (Office 365 および Microsoft Cloud App Security を含む、電子メールおよびクラウドアプリ)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-160">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="5f9fe-161">インフラストラクチャ (現時点では改善アクションはありません)</span><span class="sxs-lookup"><span data-stu-id="5f9fe-161">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="5f9fe-162">[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-162">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="5f9fe-163">また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-163">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="5f9fe-164">![セキュリティで保護](../../media/secure-score/homepage-original.png)
されたスコアホーム*ページ図 1: Microsoft セキュリティスコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="5f9fe-164">![Secure Score homepage](../../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="5f9fe-165">スコアを向上させるためのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-165">Take action to improve your score</span></span>

<span data-ttu-id="5f9fe-166">[向上したアクション] タブには、発生する可能性のある攻撃対象範囲とその状態 (完了、未完了、サードパーティによる解決、無視) について説明するセキュリティ上の推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-166">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="5f9fe-167">すべての改善アクションを検索、フィルター、およびグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-167">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="5f9fe-168">ランク付け</span><span class="sxs-lookup"><span data-stu-id="5f9fe-168">Ranking</span></span>

<span data-ttu-id="5f9fe-169">ランク付けは、残っている残りのポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-169">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="5f9fe-170">最も順位の高い向上アクションには、低い問題点、ユーザーへの影響、および複雑さが残った大きなポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-170">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="5f9fe-171">操作</span><span class="sxs-lookup"><span data-stu-id="5f9fe-171">Actions</span></span>

<span data-ttu-id="5f9fe-172">[採点なし] というラベルの付いたアクションは、Microsoft セキュリティスコアで追跡されません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-172">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="5f9fe-173">それでもアクションを実行することはできますが、スコアに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-173">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="5f9fe-174">将来的に Microsoft セキュリティスコアによってアクションが追跡され、既に完了している場合は、その変更がセキュリティスコアに自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-174">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="5f9fe-175">特定の改善アクションを選択すると、フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-175">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="5f9fe-176">この操作を完了するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-176">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="5f9fe-177">[**ビューの設定**] を選択して構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-177">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="5f9fe-178">その後、スライドの上部に表示される、アクションに価値があるポイントを取得します。ポイントの更新には最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-178">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="5f9fe-179">向上アクションがサードパーティ製のアプリケーションまたはソフトウェアによって既に処理されているため、[**サードパーティによる解決**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-179">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="5f9fe-180">アクションが価値を持つ点が得られます。したがって、セキュリティの全体的な姿勢がより適切に反映されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-180">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="5f9fe-181">サードパーティがコントロールをカバーしなくなった場合は、[改善] アクションを未完了としてマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-181">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="5f9fe-182">Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合に、スコア要件が満たされているかどうかを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-182">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="5f9fe-183">リスクを受け入れることを決定していて、改善アクションが実行されていないため、[**無視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-183">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="5f9fe-184">改善アクションを無視すると、達成できるセキュリティで保護されたスコアポイントの合計数が減少します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-184">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="5f9fe-185">このアクションは、履歴で表示するか、いつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-185">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="5f9fe-186">改善アクションでは、環境の一部を定期的に確認してポイントを取得および保持する必要があるので、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-186">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="5f9fe-187">たとえば、ネットワークからデータが抜き出しされないように、メールボックス転送ルールを週単位で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-187">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="5f9fe-188">変更を加える必要はありませんが、アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-188">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="5f9fe-189">ルールを定期的に確認すると、ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-189">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="5f9fe-190">含まれていない場合は、スコアが減少します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-190">If not, the score is reduced.</span></span>

![セキュリティで保護されたスコア向上アクションの例](../../media/secure-score/secure-score1x450.png) ![セキュリティで保護されたスコアレビューの改善アクションの例](../../media/secure-score/secure-score2x450.png)

<span data-ttu-id="5f9fe-193">*図 2 & 3: 改善アクション flyouts*</span><span class="sxs-lookup"><span data-stu-id="5f9fe-193">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="5f9fe-194">時間の経過に伴う向上を監視する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-194">Monitor improvements over time</span></span>

<span data-ttu-id="5f9fe-195">時間の経過と共に組織のスコアのグラフを表示するには、[**履歴**] タブを使用します。グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果の点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-195">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="5f9fe-196">日付範囲をカスタマイズして、カテゴリ別にフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-196">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="5f9fe-197">リスクの認識</span><span class="sxs-lookup"><span data-stu-id="5f9fe-197">Risk awareness</span></span>

<span data-ttu-id="5f9fe-198">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-198">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="5f9fe-199">そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-199">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="5f9fe-200">セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-200">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="5f9fe-201">新機能</span><span class="sxs-lookup"><span data-stu-id="5f9fe-201">What's new?</span></span>

<span data-ttu-id="5f9fe-202">Microsoft のセキュリティに関する評価をより良いものにするために、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-202">To make Microsoft Secure Score a better representative of your security posture we have made some changes.</span></span>

<span data-ttu-id="5f9fe-203">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-203">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

### <a name="march-2020"></a><span data-ttu-id="5f9fe-204">2020 年 3 月</span><span class="sxs-lookup"><span data-stu-id="5f9fe-204">March 2020</span></span>

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="5f9fe-205">Azure AD の改善アクションに関するセキュリティの既定群をサポートする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-205">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="5f9fe-206">Microsoft セキュア スコアは、[Azure AD のセキュリティの既定群](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションを更新します。これにより、構成済みのセキュリティ設定を使用して、一般的な攻撃から組織を保護することが簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-206">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="5f9fe-207">これは、次の改善アクションに影響します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-207">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="5f9fe-208">安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-208">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="5f9fe-209">管理者の役割に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-209">Require MFA for administrative roles</span></span>
- <span data-ttu-id="5f9fe-210">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-210">Enable policy to block legacy authentication</span></span>

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="5f9fe-211">信頼性の高い測定要件を満たしていない改善アクションを削除したか、セキュリティに関する有益な表現を提供していません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-211">Removed improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="5f9fe-212">Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-212">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="5f9fe-213">OneDrive for Business でユーザー ドキュメントを保存する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-213">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="5f9fe-214">Office 365 ATP の安全な添付ファイルに関するポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-214">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="5f9fe-215">Office 365 の安全なリンクをセットアップして URL を確認する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-215">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="5f9fe-216">メールボックスの委任を許可しない</span><span class="sxs-lookup"><span data-stu-id="5f9fe-216">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="5f9fe-217">サイトとドキュメントの匿名ゲストの共有リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-217">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="5f9fe-218">Cloud App Security コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-218">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="5f9fe-219">外部共有リンクの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-219">Configure expiration time for external sharing links</span></span>
- <span data-ttu-id="5f9fe-220">監査データの記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-220">Turn on audit data recording</span></span>
- <span data-ttu-id="5f9fe-221">危険かつ準拠していないシャドウ IT アプリケーションを検出する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-221">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="5f9fe-222">環境に接続されたリスクの高い OAuth アプリケーションをブロック & アクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-222">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="5f9fe-223">SharePoint online ドキュメントライブラリのバージョン管理を設定する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-223">Set up versioning on SharePoint online document libraries</span></span>

#### <a name="removed-not-scored-improvement-actions"></a><span data-ttu-id="5f9fe-224">[スコア未計算] の改善のための処置を削除済み</span><span class="sxs-lookup"><span data-stu-id="5f9fe-224">Removed "not scored" improvement actions</span></span>

<span data-ttu-id="5f9fe-225">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-225">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="5f9fe-226">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-226">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="5f9fe-227">Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-227">Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="5f9fe-228">スコアの向上アクションは測定できません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-228">Not scored improvement actions are not measurable.</span></span>  

<span data-ttu-id="5f9fe-229">このような理由により、スコアされなかったすべての改善アクションが削除されました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-229">For these reasons, all improvement actions that were not scored have been removed.</span></span> <span data-ttu-id="5f9fe-230">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-230">No action is needed on your part.</span></span>

#### <a name="removed-device-improvement-actions"></a><span data-ttu-id="5f9fe-231">デバイス向上アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="5f9fe-231">Removed device improvement actions</span></span>

<span data-ttu-id="5f9fe-232">「Microsoft Secure Score devices」カテゴリの改善アクションを評価した後、これらのアクションは、デバイスの構成状態ではなく、現在ポリシーの状態を評価していると判断されました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-232">After an evaluation of the Microsoft Secure Score device category of improvement actions, it was determined that those actions currently assess the policy state and not the configuration state of devices.</span></span> <span data-ttu-id="5f9fe-233">構成はセキュリティの姿勢に直接関連しているため、既存のデバイスアクションが組織の姿勢を完全には表示していないと判断されました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-233">Since configuration is directly tied to security posture, the existing device actions were determined to not fully represent organizational posture.</span></span>  <span data-ttu-id="5f9fe-234">診断データを直接使用してデバイスのセキュリティに関する姿勢をより完全に表現する一連の推奨事項を提供しているため、現在のアクションをデバイスカテゴリで削除します。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-234">We will be removing the current actions in the device category as we work to provide a set of recommendations which directly use diagnostic data to more fully represent device security posture.</span></span>

<span data-ttu-id="5f9fe-235">次の改善アクションが削除されました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-235">The following improvement actions have been removed:</span></span>

- <span data-ttu-id="5f9fe-236">Microsoft Intune モバイルデバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-236">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="5f9fe-237">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-237">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="5f9fe-238">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-238">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="5f9fe-239">Android 用の Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-239">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="5f9fe-240">IOS 用 Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-240">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="5f9fe-241">Microsoft Intune コンプライアンスポリシーが割り当てられていないデバイスを、準拠していないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-241">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="5f9fe-242">IOS 用 Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-242">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="5f9fe-243">MacOS の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-243">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="5f9fe-244">Windows 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-244">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="5f9fe-245">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-245">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="5f9fe-246">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-246">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="5f9fe-247">MacOS 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-247">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="5f9fe-248">IOS 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-248">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="5f9fe-249">Windows 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-249">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="5f9fe-250">Microsoft Intune で拡張 jailbreak 検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-250">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="5f9fe-251">すべてのデバイスにパッチを適用して、ウイルス対策とファイアウォールを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="5f9fe-251">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="5f9fe-252">Microsoft Intune への Windows Defender ATP 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-252">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="5f9fe-253">Microsoft Intune Windows 情報保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-253">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="5f9fe-254">すべてのデバイスに高度なセキュリティ構成を要求する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-254">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="5f9fe-255">毎週ブロックされたデバイスのレポートを確認する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-255">Review blocked devices report weekly</span></span>

#### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="5f9fe-256">MFA 向上アクションの更新</span><span class="sxs-lookup"><span data-stu-id="5f9fe-256">MFA improvement action updates</span></span>

<span data-ttu-id="5f9fe-257">ビジネスに適したポリシーを適用しているときに、最高レベルのセキュリティを確保するための企業の必要性を反映するために、Microsoft セキュリティスコアでは多要素認証を中心とした3つの改善アクションが削除され、2つ追加されました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-257">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score has removed three improvement actions centered around multi-factor authentication, and added two.</span></span>

<span data-ttu-id="5f9fe-258">改善アクションを削除しました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-258">Removed improvement actions:</span></span>

- <span data-ttu-id="5f9fe-259">すべてのユーザーに多要素認証を登録する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-259">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="5f9fe-260">すべてのユーザーに MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-260">Require MFA for all users</span></span>
- <span data-ttu-id="5f9fe-261">Azure AD の特権の役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-261">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="5f9fe-262">改善アクションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-262">Added improvement actions:</span></span>

- <span data-ttu-id="5f9fe-263">安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする</span><span class="sxs-lookup"><span data-stu-id="5f9fe-263">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="5f9fe-264">管理者の役割に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-264">Require MFA for administrative roles</span></span>

 <span data-ttu-id="5f9fe-265">これらの新しい改善アクションでは、ユーザーまたは管理者による複数要素認証 (MFA) をディレクトリに登録し、組織のニーズに合ったポリシーの適切なセットを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-265">These new improvement actions require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="5f9fe-266">主な目標は柔軟性にありますが、すべてのユーザーと管理者が複数の要因またはリスクベースの id 確認プロンプトで認証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-266">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="5f9fe-267">これには、スコープ決定を適用する複数のポリシーを作成するか、または Microsoft が MFA のユーザーをチャレンジするタイミングを決定するセキュリティの既定値 (3 月16日) を設定するという形をとることができます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-267">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

#### <a name="removed-review-improvement-actions"></a><span data-ttu-id="5f9fe-268">"レビュー" の改善アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="5f9fe-268">Removed "review" improvement actions</span></span>

<span data-ttu-id="5f9fe-269">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-269">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="5f9fe-270">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-270">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="5f9fe-271">1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-271">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="5f9fe-272">改善アクションのレビューは、他の改善アクションと同じ基準として測定されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-272">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="5f9fe-273">これらの理由により、レビューリズムを必要とするすべての改善アクションが一時的に削除されています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-273">For these reasons, all improvement actions that required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="5f9fe-274">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-274">No action is needed on your part.</span></span>

### <a name="preview-features"></a><span data-ttu-id="5f9fe-275">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="5f9fe-275">Preview features</span></span>

<span data-ttu-id="5f9fe-276">[プレビューリリース](microsoft-secure-score-preview.md)には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-276">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="5f9fe-277">CISO およびリードレベルのディスカッションのすべての新しい指標と傾向のビュー</span><span class="sxs-lookup"><span data-stu-id="5f9fe-277">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="5f9fe-278">スコアを追跡およびベンチマークするための新しい方法</span><span class="sxs-lookup"><span data-stu-id="5f9fe-278">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="5f9fe-279">スコア回帰の追跡と監視の向上</span><span class="sxs-lookup"><span data-stu-id="5f9fe-279">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="5f9fe-280">改善アクションのフィルター、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="5f9fe-280">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="5f9fe-281">スコアプロジェクションおよび計画されたアクションを使用して、将来の目標を管理する</span><span class="sxs-lookup"><span data-stu-id="5f9fe-281">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="5f9fe-282">ポイントシステムの単純化</span><span class="sxs-lookup"><span data-stu-id="5f9fe-282">Simplification of the points system</span></span>
* <span data-ttu-id="5f9fe-283">その他多数。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-283">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5f9fe-284">ご意見をお聞かせください</span><span class="sxs-lookup"><span data-stu-id="5f9fe-284">We want to hear from you</span></span>

<span data-ttu-id="5f9fe-285">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-285">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5f9fe-286">コミュニティを監視しており、ヘルプを提供しています。</span><span class="sxs-lookup"><span data-stu-id="5f9fe-286">We're monitoring the community and will provide help.</span></span>
