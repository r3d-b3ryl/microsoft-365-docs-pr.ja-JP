---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
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
ms.openlocfilehash: aeae243b4e363f69729ccdbd2bc3fc465ec1449b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600174"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="4d514-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="4d514-104">Microsoft Secure Score</span></span>

<span data-ttu-id="4d514-105">Microsoft セキュリティスコアは、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="4d514-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="4d514-106">セキュリティスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-106">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="4d514-107">Microsoft 365 セキュリティセンターの集中管理されたダッシュボードから、組織は、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-107">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="4d514-108">セキュリティで保護されたスコアは、組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4d514-108">Secure Score helps organizations:</span></span>

* <span data-ttu-id="4d514-109">組織のセキュリティ体制の現状を報告します。</span><span class="sxs-lookup"><span data-stu-id="4d514-109">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="4d514-110">検出、可視性、ガイダンス、および制御を提供することによって、セキュリティに関する姿勢を向上させます。</span><span class="sxs-lookup"><span data-stu-id="4d514-110">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="4d514-111">ベンチマークと比較し、主要業績評価指標 (Kpi) を確立します。</span><span class="sxs-lookup"><span data-stu-id="4d514-111">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="4d514-112">組織は、測定基準と傾向の堅牢な視覚化、その他の Microsoft 製品との統合、類似の組織とのスコアの比較など、さまざまな方法でアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4d514-112">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="4d514-113">このスコアは、サードパーティ製のソリューションが推奨アクションを解決した場合にも反映できます。</span><span class="sxs-lookup"><span data-stu-id="4d514-113">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="4d514-114">さらに、 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)を通じて、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4d514-114">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="4d514-115">[セキュリティで保護されたスコアリソースの種類](https://go.microsoft.com/fwlink/?linkid=2092996)について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d514-115">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4d514-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="4d514-116">How it works</span></span>

<span data-ttu-id="4d514-117">推奨されるセキュリティ機能を構成するためのポイント、セキュリティ関連タスクの実行 (レポートの表示など)、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応を行います。</span><span class="sxs-lookup"><span data-stu-id="4d514-117">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="4d514-118">一部の改善アクションでは、完全に完了した時点でポイントが提供されます。一部のデバイスまたはユーザーに対して完了した場合は、一部の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d514-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span>

<span data-ttu-id="4d514-119">セキュリティのベストプラクティスを理解し、スコアを向上させることができるように、ライセンスに関係なく、考えられるすべての機能強化を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d514-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="4d514-120">セキュリティの絶対的な姿勢は、セキュリティで保護されたスコアで表されます。これは、組織が所有しているライセンスの種類にかかわらず変わりません。</span><span class="sxs-lookup"><span data-stu-id="4d514-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="4d514-121">セキュリティは使いやすさとバランスをとる必要があることに注意してください。お客様の環境ですべての推奨事項が機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="4d514-122">スコアはリアルタイムで更新され、視覚エフェクトページと向上アクションページに示されている情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="4d514-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="4d514-123">セキュリティで保護されたスコアは、各アクションについて達成されたポイントに関するシステムデータを毎日同期することもあります。</span><span class="sxs-lookup"><span data-stu-id="4d514-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="4d514-124">改善アクションのスコア</span><span class="sxs-lookup"><span data-stu-id="4d514-124">How improvement actions are scored</span></span>

<span data-ttu-id="4d514-125">多くの場合、2進数でスコアが獲得されます。たとえば、新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善アクションを実装すると、ポイントの100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="4d514-125">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="4d514-126">その他の改善アクションについては、構成全体のパーセンテージとしてポイントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="4d514-126">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="4d514-127">たとえば、すべてのユーザーが多要素認証を使用していて、保護されているユーザーの合計数が100の場合、[改善] アクションで30ポイント獲得した場合、2ポイント前後の部分的なスコアが与えられます (5 つの保護/100 合計 \* 30 最大 pts = 2 pts パーシャルスコア)。</span><span class="sxs-lookup"><span data-stu-id="4d514-127">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="4d514-128">セキュリティで保護されたスコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="4d514-128">Products included in Secure Score</span></span>

<span data-ttu-id="4d514-129">現時点では、Office 365 (SharePoint Online、Exchange Online、OneDrive for Business、Microsoft Information Protection など)、Azure AD、および Cloud App Security に関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d514-129">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, and Cloud App Security.</span></span> <span data-ttu-id="4d514-130">Azure ATP、Microsoft Defender ATP など、他のセキュリティ製品の推奨事項は近日中に公開されています。</span><span class="sxs-lookup"><span data-stu-id="4d514-130">Recommendations for other security products, like Azure ATP and Microsoft Defender ATP, are coming soon.</span></span> <span data-ttu-id="4d514-131">推奨事項では、各製品に関連付けられているすべての攻撃対象が網羅されるわけではありませんが、適切な基準になっています。</span><span class="sxs-lookup"><span data-stu-id="4d514-131">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="4d514-132">また、改善アクションをサードパーティの対象としてマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4d514-132">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="4d514-133">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4d514-133">Required permissions</span></span>

<span data-ttu-id="4d514-134">Microsoft セキュリティスコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory に次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-134">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="4d514-135">役割の読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="4d514-135">Read and write roles</span></span>

<span data-ttu-id="4d514-136">読み取りおよび書き込みアクセス権を使用すると、変更を加えて、セキュリティで保護されたスコアと直接対話できます。</span><span class="sxs-lookup"><span data-stu-id="4d514-136">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="4d514-137">読み取り専用アクセスを他のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4d514-137">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="4d514-138">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-138">Global administrator</span></span>
* <span data-ttu-id="4d514-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-139">Security administrator</span></span>
* <span data-ttu-id="4d514-140">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-140">Exchange administrator</span></span>
* <span data-ttu-id="4d514-141">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-141">SharePoint administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="4d514-142">読み取り専用ロール</span><span class="sxs-lookup"><span data-stu-id="4d514-142">Read-only roles</span></span>

<span data-ttu-id="4d514-143">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4d514-143">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="4d514-144">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-144">Helpdesk administrator</span></span>
* <span data-ttu-id="4d514-145">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-145">User administrator</span></span>
* <span data-ttu-id="4d514-146">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="4d514-146">Service administrator</span></span>
* <span data-ttu-id="4d514-147">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="4d514-147">Security reader</span></span>
* <span data-ttu-id="4d514-148">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="4d514-148">Security operator</span></span>
* <span data-ttu-id="4d514-149">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="4d514-149">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="4d514-150">Graph API</span><span class="sxs-lookup"><span data-stu-id="4d514-150">Graph API</span></span>

<span data-ttu-id="4d514-151">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-151">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="4d514-152">SecurityEvents (読み取り専用の役割の場合)</span><span class="sxs-lookup"><span data-stu-id="4d514-152">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="4d514-153">SecurityEvents. すべて (読み取りおよび書き込みの役割)</span><span class="sxs-lookup"><span data-stu-id="4d514-153">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="4d514-154">セキュリティに関する姿勢を把握する</span><span class="sxs-lookup"><span data-stu-id="4d514-154">Gain visibility into your security posture</span></span>

<span data-ttu-id="4d514-155">より迅速に必要な情報を提供するために、Microsoft の改善アクションがグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="4d514-155">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="4d514-156">Identity (azure AD アカウント & の役割、および Azure ATP が近日中の場合)</span><span class="sxs-lookup"><span data-stu-id="4d514-156">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="4d514-157">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="4d514-157">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="4d514-158">デバイス (Microsoft Defender ATP デバイス、近日公開予定)</span><span class="sxs-lookup"><span data-stu-id="4d514-158">Device (Microsoft Defender ATP devices, coming soon)</span></span>
* <span data-ttu-id="4d514-159">アプリ (Office 365 および Microsoft Cloud App Security を含む、電子メールおよびクラウドアプリ)</span><span class="sxs-lookup"><span data-stu-id="4d514-159">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="4d514-160">インフラストラクチャ (Azure リソース)</span><span class="sxs-lookup"><span data-stu-id="4d514-160">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="4d514-161">[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d514-161">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="4d514-162">また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-162">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="4d514-163">![セキュリティで保護](../media/secure-score/homepage-original.png)
されたスコアホーム*ページ図 1: Microsoft セキュリティスコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="4d514-163">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="4d514-164">スコアを向上させるためのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="4d514-164">Take action to improve your score</span></span>

<span data-ttu-id="4d514-165">[向上したアクション] タブには、発生する可能性のある攻撃対象範囲とその状態 (完了、未完了、サードパーティによる解決、無視) について説明するセキュリティ上の推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-165">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="4d514-166">すべての改善アクションを検索、フィルター、およびグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-166">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="4d514-167">付け</span><span class="sxs-lookup"><span data-stu-id="4d514-167">Ranking</span></span>

<span data-ttu-id="4d514-168">ランク付けは、残っている残りのポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4d514-168">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="4d514-169">最も順位の高い向上アクションには、低い問題点、ユーザーへの影響、および複雑さが残った大きなポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="4d514-169">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="4d514-170">Actions</span><span class="sxs-lookup"><span data-stu-id="4d514-170">Actions</span></span>

<span data-ttu-id="4d514-171">[採点なし] というラベルの付いたアクションは、Microsoft セキュリティスコアで追跡されません。</span><span class="sxs-lookup"><span data-stu-id="4d514-171">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="4d514-172">それでもアクションを実行することはできますが、スコアに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-172">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="4d514-173">将来的に Microsoft セキュリティスコアによってアクションが追跡され、既に完了している場合は、その変更がセキュリティスコアに自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-173">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="4d514-174">特定の改善アクションを選択すると、フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-174">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="4d514-175">この操作を完了するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4d514-175">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="4d514-176">[**ビューの設定**] を選択して構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="4d514-176">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="4d514-177">その後、スライドの上部に表示される、アクションに価値があるポイントを取得します。ポイントの更新には最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-177">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="4d514-178">向上アクションがサードパーティ製のアプリケーションまたはソフトウェアによって既に処理されているため、[**サードパーティによる解決**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d514-178">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="4d514-179">アクションが価値を持つ点が得られます。したがって、セキュリティの全体的な姿勢がより適切に反映されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-179">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="4d514-180">サードパーティがコントロールをカバーしなくなった場合は、[改善] アクションを未完了としてマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-180">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="4d514-181">Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合に、スコア要件が満たされているかどうかを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4d514-181">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="4d514-182">リスクを受け入れることを決定していて、改善アクションが実行されていないため、[**無視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d514-182">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="4d514-183">改善アクションを無視すると、達成できるセキュリティで保護されたスコアポイントの合計数が減少します。</span><span class="sxs-lookup"><span data-stu-id="4d514-183">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="4d514-184">このアクションは、履歴で表示するか、いつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-184">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="4d514-185">改善アクションでは、環境の一部を定期的に確認してポイントを取得および保持する必要があるので、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d514-185">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="4d514-186">たとえば、ネットワークからデータが抜き出しされないように、メールボックス転送ルールを週単位で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-186">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="4d514-187">変更を加える必要はありませんが、アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-187">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="4d514-188">ルールを定期的に確認すると、ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-188">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="4d514-189">含まれていない場合は、スコアが減少します。</span><span class="sxs-lookup"><span data-stu-id="4d514-189">If not, the score is reduced.</span></span>

![セキュリティで保護されたスコア向上アクションの例](../media/secure-score/secure-score1x450.png) ![セキュリティで保護されたスコアレビューの改善アクションの例](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="4d514-192">*図 2 & 3: 改善アクション flyouts*</span><span class="sxs-lookup"><span data-stu-id="4d514-192">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="4d514-193">時間の経過に伴う向上を監視する</span><span class="sxs-lookup"><span data-stu-id="4d514-193">Monitor improvements over time</span></span>

<span data-ttu-id="4d514-194">時間の経過と共に組織のスコアのグラフを表示するには、[**履歴**] タブを使用します。グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果の点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-194">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="4d514-195">日付範囲をカスタマイズして、カテゴリ別にフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-195">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="4d514-196">リスクの認識</span><span class="sxs-lookup"><span data-stu-id="4d514-196">Risk awareness</span></span>

<span data-ttu-id="4d514-197">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-197">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="4d514-198">そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="4d514-198">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="4d514-199">セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-199">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="4d514-200">今後の機能</span><span class="sxs-lookup"><span data-stu-id="4d514-200">What's coming?</span></span>

<span data-ttu-id="4d514-201">Microsoft のセキュリティスコアをより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="4d514-201">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="4d514-202">スコアと可能な最大スコアが変わります。</span><span class="sxs-lookup"><span data-stu-id="4d514-202">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="4d514-203">ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-203">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="4d514-204">Intune からの改善アクションの削除</span><span class="sxs-lookup"><span data-stu-id="4d514-204">Removing improvement actions from Intune</span></span>

<span data-ttu-id="4d514-205">Intune から提供された Microsoft のセキュリティで保護されたスコアの改善アクションを評価した後は、組織内のデバイスのセキュリティに関する有益な表現を提供していないと判断されました。</span><span class="sxs-lookup"><span data-stu-id="4d514-205">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="4d514-206">ポリシーを重視するのではなく、デバイスの構成状態を直接評価するセキュリティ制御に移行することに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="4d514-206">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="4d514-207">次の Intune 向上アクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-207">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="4d514-208">Microsoft Intune モバイルデバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="4d514-208">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="4d514-209">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-209">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="4d514-210">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-210">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="4d514-211">Android 用の Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-211">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="4d514-212">IOS 用 Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-212">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="4d514-213">Microsoft Intune コンプライアンスポリシーが割り当てられていないデバイスを、準拠していないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="4d514-213">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="4d514-214">IOS 用 Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-214">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="4d514-215">MacOS の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-215">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="4d514-216">Windows 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-216">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="4d514-217">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-217">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="4d514-218">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-218">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="4d514-219">MacOS 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-219">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="4d514-220">IOS 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-220">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="4d514-221">Windows 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-221">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="4d514-222">Microsoft Intune で拡張 jailbreak 検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="4d514-222">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="4d514-223">すべてのデバイスにパッチを適用して、ウイルス対策とファイアウォールを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="4d514-223">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="4d514-224">Microsoft Intune への Windows Defender ATP 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="4d514-224">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="4d514-225">Microsoft Intune Windows 情報保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4d514-225">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="4d514-226">すべてのデバイスに高度なセキュリティ構成を要求する</span><span class="sxs-lookup"><span data-stu-id="4d514-226">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="4d514-227">毎週ブロックされたデバイスのレポートを確認する</span><span class="sxs-lookup"><span data-stu-id="4d514-227">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="4d514-228">信頼性の高い測定要件を満たしていない改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="4d514-228">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="4d514-229">マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。</span><span class="sxs-lookup"><span data-stu-id="4d514-229">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="4d514-230">監査データの記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="4d514-230">Turn on audit data recording</span></span>
- <span data-ttu-id="4d514-231">危険かつ準拠していないシャドウ IT アプリケーションを検出する</span><span class="sxs-lookup"><span data-stu-id="4d514-231">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="4d514-232">環境に接続されたリスクの高い OAuth アプリケーションをブロック & アクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="4d514-232">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="4d514-233">SharePoint online ドキュメントライブラリのバージョン管理を設定する</span><span class="sxs-lookup"><span data-stu-id="4d514-233">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="4d514-234">MFA 向上アクションの更新</span><span class="sxs-lookup"><span data-stu-id="4d514-234">MFA improvement action updates</span></span>

<span data-ttu-id="4d514-235">ビジネスに適したポリシーを適用しているときに、最高レベルのセキュリティを確保するための企業の必要性を反映するために、Microsoft Secure Score は、多要素認証を中心とした3つの改善アクションを削除し、2つを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d514-235">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="4d514-236">削除される3つのを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4d514-236">The three that will be removed:</span></span>

- <span data-ttu-id="4d514-237">すべてのユーザーに多要素認証を登録する</span><span class="sxs-lookup"><span data-stu-id="4d514-237">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="4d514-238">すべてのユーザーに MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="4d514-238">Require MFA for all users</span></span>
- <span data-ttu-id="4d514-239">Azure AD の特権の役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="4d514-239">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="4d514-240">新しい向上アクションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="4d514-240">New improvement actions added:</span></span>

- <span data-ttu-id="4d514-241">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする</span><span class="sxs-lookup"><span data-stu-id="4d514-241">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="4d514-242">管理役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="4d514-242">Require MFA for administrative roles</span></span>

 <span data-ttu-id="4d514-243">これらの新しい改善アクションでは、ユーザーまたは管理者に対して複数要素認証 (MFA) をディレクトリに登録し、組織のニーズに合ったポリシーの適切なセットを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-243">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="4d514-244">主な目標は柔軟性にありますが、すべてのユーザーと管理者が複数の要因またはリスクベースの id 確認プロンプトで認証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4d514-244">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="4d514-245">これはセキュリティの既定値を設定することができます。これにより、Microsoft は、MFA のユーザーをチャレンジするタイミングを決定することができます。また、スコープ決定を適用する複数のポリシーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4d514-245">That can take the form of setting security defaults that let Microsoft decide when to challenge users for MFA, or having multiple policies that apply scoped decisions.</span></span>

### <a name="removing-not-scored-and-review-improvement-actions"></a><span data-ttu-id="4d514-246">[スコアを表示しない] および [レビュー] の強化アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="4d514-246">Removing “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="4d514-247">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="4d514-247">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="4d514-248">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="4d514-248">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="4d514-249">1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4d514-249">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="4d514-250">スコアの改善アクションは測定できません。また、改善アクションのレビューは、他の改善アクションと同じ基準ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-250">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="4d514-251">このような理由により、スコアリングされていない、またはレビューリズムを必要としないすべての改善アクションが一時的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-251">For these reasons, all improvement actions that were not scored or required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="4d514-252">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-252">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="4d514-253">ポイントシステムの簡略化</span><span class="sxs-lookup"><span data-stu-id="4d514-253">Simplification of the point system</span></span>

<span data-ttu-id="4d514-254">複数のエクスペリエンスにわたるポイントを標準化するために、各セキュリティで保護されたスコア向上のアクションポイント合計が10ポイント以下に更新されます。</span><span class="sxs-lookup"><span data-stu-id="4d514-254">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="4d514-255">現在、または将来的に追加する予定のセキュリティ制御の幅広い breather で、より一貫したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d514-255">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="4d514-256">これは非常に大きな変更になっていますが、総ポイント合計が表示されますが、セキュリティに関する姿勢に変化はありません。</span><span class="sxs-lookup"><span data-stu-id="4d514-256">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="4d514-257">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="4d514-257">Preview features</span></span>

<span data-ttu-id="4d514-258">[プレビューリリース](microsoft-secure-score-preview.md)には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d514-258">The following features will be included in the [preview release](microsoft-secure-score-preview.md):</span></span>

* <span data-ttu-id="4d514-259">CISO およびリードレベルのディスカッションのすべての新しい指標と傾向のビュー</span><span class="sxs-lookup"><span data-stu-id="4d514-259">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="4d514-260">スコアを追跡およびベンチマークするための新しい方法</span><span class="sxs-lookup"><span data-stu-id="4d514-260">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="4d514-261">スコア回帰の追跡と監視の向上</span><span class="sxs-lookup"><span data-stu-id="4d514-261">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="4d514-262">改善アクションのフィルター、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="4d514-262">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="4d514-263">スコアプロジェクションおよび計画されたアクションを使用して、将来の目標を管理する</span><span class="sxs-lookup"><span data-stu-id="4d514-263">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="4d514-264">その他多数。</span><span class="sxs-lookup"><span data-stu-id="4d514-264">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4d514-265">ご意見をお聞かせください</span><span class="sxs-lookup"><span data-stu-id="4d514-265">We want to hear from you</span></span>

<span data-ttu-id="4d514-266">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="4d514-266">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4d514-267">コミュニティを監視しており、ヘルプを提供しています。</span><span class="sxs-lookup"><span data-stu-id="4d514-267">We're monitoring the community and will provide help.</span></span>