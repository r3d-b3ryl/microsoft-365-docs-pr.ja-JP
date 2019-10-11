---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b337f020702b60ceeb02043e9b66d5614f58c228
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435561"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="b72b3-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="b72b3-104">Microsoft Secure Score</span></span>

<span data-ttu-id="b72b3-105">Microsoft セキュリティスコアは、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-105">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="b72b3-106">Microsoft 365 セキュリティセンターの集中管理されたダッシュボードから、組織は、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-106">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="b72b3-107">セキュリティで保護されたスコアは、組織が次のことを実現します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-107">Secure Score helps organizations do the following:</span></span>  

* <span data-ttu-id="b72b3-108">組織のセキュリティ体制の現状を報告します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-108">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="b72b3-109">検出、可視性、ガイダンス、および制御を提供することによって、セキュリティに関する姿勢を向上させます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-109">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="b72b3-110">ベンチマークと比較し、主要業績評価指標 (Kpi) を確立します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-110">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="b72b3-111">セキュリティで保護されたスコアは、測定基準と傾向、その他の Microsoft 製品との統合、類似の組織とのスコア比較などの堅牢な視覚化へのアクセスを組織に提供します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-111">Secure Score gives organizations access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="b72b3-112">このスコアは、サードパーティ製のソリューションが推奨アクションを解決した場合にも反映できます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-112">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="b72b3-113">さらに、 [Microsoft GRAPH API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)を通じて、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-113">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b72b3-114">しくみ</span><span class="sxs-lookup"><span data-stu-id="b72b3-114">How it works</span></span>

<span data-ttu-id="b72b3-115">推奨されるセキュリティ機能を構成するためのポイント、セキュリティ関連タスクの実行 (レポートの表示など)、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応を行います。</span><span class="sxs-lookup"><span data-stu-id="b72b3-115">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="b72b3-116">一部の改善アクションでは、完全に完了した時点でポイントが提供されます。一部のデバイスまたはユーザーに対して完了した場合は、一部の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-116">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="b72b3-117">セキュリティは常にユーザビリティにバランスをとる必要があり、お客様の環境ですべての推奨事項が機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-117">Security should always be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="b72b3-118">スコアはリアルタイムで更新され、視覚エフェクトページと向上アクションページに示されている情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-118">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="b72b3-119">セキュリティで保護されたスコアは、各アクションについて達成されたポイントに関するシステムデータを毎日同期することもあります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-119">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="b72b3-120">改善アクションのスコア</span><span class="sxs-lookup"><span data-stu-id="b72b3-120">How improvement actions are scored</span></span>

<span data-ttu-id="b72b3-121">多くの場合、2進数でスコアが獲得されます。たとえば、新しいポリシーを作成したり、特定の設定をオンにしたりするなど、改善アクションを実装すると、ポイントの 100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-121">Most are scored in a binary fashion — if you implement the improvement action, like creating a new policy or turning on a specific setting, you get 100% of the points .</span></span> <span data-ttu-id="b72b3-122">その他の改善アクションについては、構成全体のパーセンテージとしてポイントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-122">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="b72b3-123">たとえば、向上アクションによって、多要素認証を使用してすべて100のユーザーを保護することにより、すべてのユーザーを保護することによって30ポイント獲得した場合に、保護されたユーザーの合計数が5である場合は、約2ポイント (5 つの保護/100 合計 \* 30 最大 pts = 2 ポイント) 部分的なスコア)。</span><span class="sxs-lookup"><span data-stu-id="b72b3-123">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b72b3-124">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b72b3-124">Required permissions</span></span>

<span data-ttu-id="b72b3-125">Microsoft セキュリティスコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory に次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-125">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="b72b3-126">役割の読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="b72b3-126">Read and write roles</span></span>

<span data-ttu-id="b72b3-127">読み取りおよび書き込みアクセス権を使用すると、変更を加えて、セキュリティで保護されたスコアと直接対話できます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-127">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="b72b3-128">読み取り専用アクセスを他のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-128">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="b72b3-129">会社の管理者</span><span class="sxs-lookup"><span data-stu-id="b72b3-129">CompanyAdministrator</span></span>
* <span data-ttu-id="b72b3-130">SecurityAdministrator</span><span class="sxs-lookup"><span data-stu-id="b72b3-130">SecurityAdministrator</span></span>
* <span data-ttu-id="b72b3-131">ExchangeAdmin</span><span class="sxs-lookup"><span data-stu-id="b72b3-131">ExchangeAdmin</span></span>
* <span data-ttu-id="b72b3-132">SharePointAdmin</span><span class="sxs-lookup"><span data-stu-id="b72b3-132">SharePointAdmin</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="b72b3-133">読み取り専用ロール</span><span class="sxs-lookup"><span data-stu-id="b72b3-133">Read-only roles</span></span>

<span data-ttu-id="b72b3-134">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-134">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="b72b3-135">Helpadministration Admin</span><span class="sxs-lookup"><span data-stu-id="b72b3-135">HelpdeskAdmin</span></span>
* <span data-ttu-id="b72b3-136">UserAccountAdmin</span><span class="sxs-lookup"><span data-stu-id="b72b3-136">UserAccountAdmin</span></span>
* <span data-ttu-id="b72b3-137">サービスのアップポート管理者</span><span class="sxs-lookup"><span data-stu-id="b72b3-137">ServiceSupportAdmin</span></span>
* <span data-ttu-id="b72b3-138">SecurityReader</span><span class="sxs-lookup"><span data-stu-id="b72b3-138">SecurityReader</span></span>
* <span data-ttu-id="b72b3-139">SecurityOperator</span><span class="sxs-lookup"><span data-stu-id="b72b3-139">SecurityOperator</span></span>
* <span data-ttu-id="b72b3-140">GlobalReader</span><span class="sxs-lookup"><span data-stu-id="b72b3-140">GlobalReader</span></span>

### <a name="graph-api"></a><span data-ttu-id="b72b3-141">Graph API</span><span class="sxs-lookup"><span data-stu-id="b72b3-141">Graph API</span></span>

<span data-ttu-id="b72b3-142">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-142">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="b72b3-143">SecurityEvents (読み取り専用の役割の場合)</span><span class="sxs-lookup"><span data-stu-id="b72b3-143">SecurityEvents.Read.All (for read-only role)</span></span>
* <span data-ttu-id="b72b3-144">SecurityEvents. すべて (読み取りおよび書き込みの役割)</span><span class="sxs-lookup"><span data-stu-id="b72b3-144">SecurityEvents.ReadWrite.All (for read and write role)</span></span>

## <a name="rich-experiences--security-recommendations"></a><span data-ttu-id="b72b3-145">高度なエクスペリエンス & セキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="b72b3-145">Rich experiences & security recommendations</span></span>

<span data-ttu-id="b72b3-146">Microsoft のセキュリティで保護されたスコアには、Office 365、Azure AD、Intune、および Cloud App Security からの推奨事項があります。これには、Azure セキュリティセンターからの推奨事項と、近日中に Microsoft Defender セキュリティセンターが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-146">In Microsoft Secure Score, there are recommendations from Office 365, Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Microsoft Defender Security Center coming soon.</span></span>

<span data-ttu-id="b72b3-147">より迅速に必要な情報を提供するために、Microsoft の推奨事項がグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-147">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="b72b3-148">Identity (Azure AD アカウントとロール)</span><span class="sxs-lookup"><span data-stu-id="b72b3-148">Identity (Azure AD accounts and roles)</span></span>
* <span data-ttu-id="b72b3-149">データ (Office 365 ドキュメント)</span><span class="sxs-lookup"><span data-stu-id="b72b3-149">Data  (Office 365 documents)</span></span>
* <span data-ttu-id="b72b3-150">デバイス (Microsoft Defender ATP デバイス)</span><span class="sxs-lookup"><span data-stu-id="b72b3-150">Device (Microsoft Defender ATP devices)</span></span>
* <span data-ttu-id="b72b3-151">アプリ (電子メールアプリとクラウドアプリ)</span><span class="sxs-lookup"><span data-stu-id="b72b3-151">App (email and cloud apps)</span></span>
* <span data-ttu-id="b72b3-152">インフラストラクチャ (Azure リソース)</span><span class="sxs-lookup"><span data-stu-id="b72b3-152">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="b72b3-153">[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-153">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="b72b3-154">また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-154">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span> <span data-ttu-id="b72b3-155">このデータを使用して、セキュリティに関する姿勢を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-155">You can use this data to act and make big differences in your security posture.</span></span>  

<span data-ttu-id="b72b3-156">![セキュリティで保護](../media/secure-score/homepage-original.png)
されたスコアホーム*ページ図 1: Microsoft セキュリティスコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="b72b3-156">![Secure Score homepage](../media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="b72b3-157">スコアを向上させるためのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="b72b3-157">Take action to improve your score</span></span>

<span data-ttu-id="b72b3-158">[向上したアクション] タブには、発生する可能性のある攻撃対象範囲とその状態 (完了、未完了、サードパーティによる解決、無視) について説明するセキュリティ上の推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-158">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="b72b3-159">すべての改善アクションを検索、フィルター、およびグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-159">You can search, filter, and group all the improvement actions.</span></span>

### <a name="ranking"></a><span data-ttu-id="b72b3-160">付け</span><span class="sxs-lookup"><span data-stu-id="b72b3-160">Ranking</span></span>

<span data-ttu-id="b72b3-161">ランク付けは、残っている残りのポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-161">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="b72b3-162">最も順位の高い向上アクションは、低い問題点、ユーザーへの影響、および複雑さが残った大きなポイントです。</span><span class="sxs-lookup"><span data-stu-id="b72b3-162">The highest ranked improvement actions have the large amount of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="b72b3-163">アクション</span><span class="sxs-lookup"><span data-stu-id="b72b3-163">Actions</span></span>

<span data-ttu-id="b72b3-164">[採点なし] というラベルの付いたアクションは、Microsoft セキュリティスコアで追跡されません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-164">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="b72b3-165">それでもアクションを実行することはできますが、スコアに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-165">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="b72b3-166">将来的に Microsoft セキュリティスコアによってアクションが追跡され、既に完了している場合は、その変更がセキュリティスコアに自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-166">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="b72b3-167">特定の改善アクションを選択すると、フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-167">When you select a specific improvement action, a fly out appears.</span></span> <span data-ttu-id="b72b3-168">この操作を完了するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-168">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="b72b3-169">[**ビューの設定**] を選択して構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="b72b3-169">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="b72b3-170">その後、スライドの上部に表示される、アクションに価値があるポイントを取得します。ポイントの更新には最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-170">You then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="b72b3-171">向上アクションがサードパーティ製のアプリケーションまたはソフトウェアによって既に処理されているため、[**サードパーティによる解決**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-171">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="b72b3-172">アクションが価値を持つ点が得られます。したがって、セキュリティの全体的な姿勢がより適切に反映されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-172">You gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="b72b3-173">サードパーティがコントロールをカバーしなくなった場合は、[改善] アクションを未完了としてマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-173">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="b72b3-174">Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合に、スコア要件が満たされているかどうかを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b72b3-174">Keep in mind, Microsoft has no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="b72b3-175">リスクを受け入れることを決定していて、改善アクションが実行されていないため、[**無視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-175">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="b72b3-176">改善アクションを無視すると、達成できるセキュリティで保護されたスコアポイントの合計数が減少します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-176">Once you ignore an improvement action, the total number of secure score points you can achieve is reduced.</span></span> <span data-ttu-id="b72b3-177">このアクションは、履歴で表示するか、いつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-177">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="b72b3-178">改善アクションでは、環境の一部を定期的に確認してポイントを取得および保持する必要があるので、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-178">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="b72b3-179">たとえば、ネットワークからデータが抜き出しされないように、メールボックス転送ルールを週単位で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-179">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="b72b3-180">変更を加える必要はありませんが、アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-180">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="b72b3-181">ルールを定期的に確認すると、ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-181">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="b72b3-182">含まれていない場合は、スコアが減少します。</span><span class="sxs-lookup"><span data-stu-id="b72b3-182">If not, the score is reduced.</span></span>

![セキュリティで保護されたスコア向上アクションの例](../media/secure-score/secure-score1x450.png) ![セキュリティで保護されたスコアレビューの改善アクションの例](../media/secure-score/secure-score2x450.png)

<span data-ttu-id="b72b3-185">*図 2 & 3: 改善アクション flyouts*</span><span class="sxs-lookup"><span data-stu-id="b72b3-185">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="b72b3-186">時間の経過に伴う向上を監視する</span><span class="sxs-lookup"><span data-stu-id="b72b3-186">Monitor improvements over time</span></span>

<span data-ttu-id="b72b3-187">時間の経過と共に組織のスコアのグラフを表示するには、[**履歴**] タブを使用します。グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果の点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-187">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="b72b3-188">日付範囲をカスタマイズして、カテゴリ別にフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-188">You can customize a date range and filter by category.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="b72b3-189">リスクの認識</span><span class="sxs-lookup"><span data-stu-id="b72b3-189">Risk awareness</span></span>

<span data-ttu-id="b72b3-190">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-190">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security-related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="b72b3-191">そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-191">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="b72b3-192">セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-192">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-coming"></a><span data-ttu-id="b72b3-193">今後の機能</span><span class="sxs-lookup"><span data-stu-id="b72b3-193">What's coming?</span></span>

<span data-ttu-id="b72b3-194">Microsoft のセキュリティスコアをより良い方法でセキュリティ上の姿勢にし、操作性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-194">In order to make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="b72b3-195">スコアと可能な最大スコアが変わります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-195">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="b72b3-196">ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-196">However, this does not imply a change in your security posture.</span></span>

### <a name="removing-not-scored-and-review-improvement-actions"></a><span data-ttu-id="b72b3-197">[スコアを表示しない] および [レビュー] の強化アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="b72b3-197">Removing “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="b72b3-198">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="b72b3-198">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="b72b3-199">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-199">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="b72b3-200">1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-200">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="b72b3-201">スコアの改善アクションは測定できません。また、改善アクションのレビューは、他の改善アクションと同じ基準ではありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-201">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="b72b3-202">このような理由により、スコアリングされていない、またはレビューリズムを必要としないすべての改善アクションが一時的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-202">For these reasons, all improvement actions that were not scored or required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="b72b3-203">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-203">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="b72b3-204">ポイントシステムの簡略化</span><span class="sxs-lookup"><span data-stu-id="b72b3-204">Simplification of the point system</span></span>

<span data-ttu-id="b72b3-205">複数のエクスペリエンスにわたるポイントを標準化するために、各セキュリティで保護されたスコア向上のアクションポイント合計が10ポイント以下に更新されます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-205">To standardize points across multiple experiences, each Secure Score improvement action point total will be updated to be worth 10 points or less.</span></span> <span data-ttu-id="b72b3-206">現在、または将来的に追加する予定のセキュリティ制御の幅広い breather で、より一貫したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b72b3-206">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="b72b3-207">これは非常に大きな変更になっていますが、総ポイント合計が表示されますが、セキュリティに関する姿勢に変化はありません。</span><span class="sxs-lookup"><span data-stu-id="b72b3-207">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>  

### <a name="preview-features"></a><span data-ttu-id="b72b3-208">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="b72b3-208">Preview features</span></span>

<span data-ttu-id="b72b3-209">プレビューリリースには、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b72b3-209">The following features will be included in the preview release:</span></span>

* <span data-ttu-id="b72b3-210">CISO およびリードレベルのディスカッションのすべての新しい指標と傾向のビュー</span><span class="sxs-lookup"><span data-stu-id="b72b3-210">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="b72b3-211">スコアを追跡およびベンチマークするための新しい方法</span><span class="sxs-lookup"><span data-stu-id="b72b3-211">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="b72b3-212">スコア回帰の追跡と監視の向上</span><span class="sxs-lookup"><span data-stu-id="b72b3-212">Better tracking and monitoring for score regressions</span></span>
* <span data-ttu-id="b72b3-213">改善アクションのフィルター、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="b72b3-213">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="b72b3-214">スコアプロジェクションおよび計画されたアクションを使用して、将来の目標を管理する</span><span class="sxs-lookup"><span data-stu-id="b72b3-214">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="b72b3-215">その他多数。</span><span class="sxs-lookup"><span data-stu-id="b72b3-215">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="b72b3-216">ご意見をお聞かせください</span><span class="sxs-lookup"><span data-stu-id="b72b3-216">We want to hear from you</span></span>

<span data-ttu-id="b72b3-217">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="b72b3-217">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="b72b3-218">コミュニティを監視しており、ヘルプを提供しています。</span><span class="sxs-lookup"><span data-stu-id="b72b3-218">We're monitoring the community and will provide help.</span></span>
