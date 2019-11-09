---
title: Microsoft セキュリティスコア (プレビュー)
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細の計算方法、およびセキュリティ管理者がどのようなものを使用できるかについて説明します。
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
ms.openlocfilehash: 55f962a82fcbacb5ca1c5e3026469880489fd5b7
ms.sourcegitcommit: 93cef4906c5495ae293450ceb52d6cc336f52b53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38076331"
---
# <a name="microsoft-secure-score-preview"></a><span data-ttu-id="b5171-104">Microsoft セキュリティスコア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b5171-104">Microsoft Secure Score (preview)</span></span>

>[!IMPORTANT]
><span data-ttu-id="b5171-105">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="b5171-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b5171-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b5171-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b5171-107">Microsoft セキュリティスコアは、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b5171-107">Microsoft Secure Score is a measurement of an organization’s security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="b5171-108">セキュリティスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-108">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="b5171-109">Microsoft 365 セキュリティセンターの集中管理されたダッシュボードから、組織は、Microsoft 365 の id、データ、アプリ、デバイス、およびインフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-109">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="b5171-110">セキュリティで保護されたスコアは、組織に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b5171-110">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="b5171-111">組織のセキュリティ体制の現状を報告します。</span><span class="sxs-lookup"><span data-stu-id="b5171-111">Report on the current state of the organization’s security posture.</span></span>
* <span data-ttu-id="b5171-112">検出、可視性、ガイダンス、および制御を提供することによって、セキュリティに関する姿勢を向上させます。</span><span class="sxs-lookup"><span data-stu-id="b5171-112">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="b5171-113">ベンチマークと比較し、主要業績評価指標 (Kpi) を確立します。</span><span class="sxs-lookup"><span data-stu-id="b5171-113">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="b5171-114">組織は、測定基準と傾向の堅牢な視覚化、その他の Microsoft 製品との統合、類似の組織とのスコアの比較など、さまざまな方法でアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5171-114">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="b5171-115">このスコアは、サードパーティ製のソリューションが推奨アクションを解決した場合にも反映できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-115">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="b5171-116">さらに、 [Microsoft GRAPH API](https://www.microsoft.com/security/partnerships/graph-security-api)を通じて、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b5171-116">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="b5171-117">[セキュリティで保護されたスコアリソースの種類](https://go.microsoft.com/fwlink/?linkid=2092996)について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5171-117">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b5171-118">しくみ</span><span class="sxs-lookup"><span data-stu-id="b5171-118">How it works</span></span>

<span data-ttu-id="b5171-119">推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対応のポイントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="b5171-119">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="b5171-120">一部の改善アクションでは、完全に完了した時点でポイントが提供されます。一部のデバイスまたはユーザーに対して完了した場合は、一部の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5171-120">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="b5171-121">改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-121">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="b5171-122">スコアはリアルタイムで更新され、視覚エフェクトページと向上アクションページに示されている情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="b5171-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="b5171-123">セキュリティで保護されたスコアは、各アクションについて達成されたポイントに関するシステムデータを毎日同期することもあります。</span><span class="sxs-lookup"><span data-stu-id="b5171-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="b5171-124">改善アクションのスコア</span><span class="sxs-lookup"><span data-stu-id="b5171-124">How improvement actions are scored</span></span>

<span data-ttu-id="b5171-125">各改善アクションには、10ポイント以下の価値があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-125">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="b5171-126">多くの場合、2進数でスコアが獲得されます。たとえば、新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善アクションを実装すると、ポイントの100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="b5171-126">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="b5171-127">その他の改善アクションについては、構成全体のパーセンテージとしてポイントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="b5171-127">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="b5171-128">たとえば、すべてのユーザーが多要素認証を使用していて、保護されているユーザーの合計数が100の場合、[改善] アクションで30ポイント獲得した場合、2ポイント前後の部分的なスコアが与えられます (5 つの保護/100 合計 \* 30 最大 pts = 2 pts パーシャルスコア)。</span><span class="sxs-lookup"><span data-stu-id="b5171-128">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="b5171-129">セキュリティで保護されたスコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="b5171-129">Products included in Secure Score</span></span>

<span data-ttu-id="b5171-130">現時点では、Office 365 (SharePoint Online、Exchange Online、OneDrive for Business、Microsoft Information Protection など)、Azure AD、Intune、Microsoft Defender ATP、および Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-130">Currently there are recommendations for Office 365 (including SharePoint Online, Exchange Online, OneDrive for Business, Microsoft Information Protection, and more), Azure AD, Intune, Microsoft Defender ATP, and Cloud App Security.</span></span> <span data-ttu-id="b5171-131">その他のセキュリティ製品の推奨事項は近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-131">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="b5171-132">推奨事項では、各製品に関連付けられているすべての攻撃対象が網羅されるわけではありませんが、適切な基準になっています。</span><span class="sxs-lookup"><span data-stu-id="b5171-132">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="b5171-133">また、改善アクションをサードパーティの対象としてマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b5171-133">You can also mark the improvement actions as covered by a third party.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b5171-134">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b5171-134">Required permissions</span></span>

<span data-ttu-id="b5171-135">Microsoft セキュリティスコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory に次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-135">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="b5171-136">役割の読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="b5171-136">Read and write roles</span></span>

<span data-ttu-id="b5171-137">読み取りおよび書き込みアクセス権を使用すると、変更を加えて、セキュリティで保護されたスコアと直接対話できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-137">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="b5171-138">読み取り専用アクセスを他のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="b5171-138">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="b5171-139">会社の管理者</span><span class="sxs-lookup"><span data-stu-id="b5171-139">CompanyAdministrator</span></span>
* <span data-ttu-id="b5171-140">SecurityAdministrator</span><span class="sxs-lookup"><span data-stu-id="b5171-140">SecurityAdministrator</span></span>
* <span data-ttu-id="b5171-141">ExchangeAdmin</span><span class="sxs-lookup"><span data-stu-id="b5171-141">ExchangeAdmin</span></span>
* <span data-ttu-id="b5171-142">SharePointAdmin</span><span class="sxs-lookup"><span data-stu-id="b5171-142">SharePointAdmin</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="b5171-143">読み取り専用ロール</span><span class="sxs-lookup"><span data-stu-id="b5171-143">Read-only roles</span></span>

<span data-ttu-id="b5171-144">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b5171-144">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="b5171-145">Helpadministration Admin</span><span class="sxs-lookup"><span data-stu-id="b5171-145">HelpdeskAdmin</span></span>
* <span data-ttu-id="b5171-146">UserAccountAdmin</span><span class="sxs-lookup"><span data-stu-id="b5171-146">UserAccountAdmin</span></span>
* <span data-ttu-id="b5171-147">サービスのアップポート管理者</span><span class="sxs-lookup"><span data-stu-id="b5171-147">ServiceSupportAdmin</span></span>
* <span data-ttu-id="b5171-148">SecurityReader</span><span class="sxs-lookup"><span data-stu-id="b5171-148">SecurityReader</span></span>
* <span data-ttu-id="b5171-149">SecurityOperator</span><span class="sxs-lookup"><span data-stu-id="b5171-149">SecurityOperator</span></span>
* <span data-ttu-id="b5171-150">GlobalReader</span><span class="sxs-lookup"><span data-stu-id="b5171-150">GlobalReader</span></span>

### <a name="graph-api"></a><span data-ttu-id="b5171-151">Graph API</span><span class="sxs-lookup"><span data-stu-id="b5171-151">Graph API</span></span>

<span data-ttu-id="b5171-152">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-152">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="b5171-153">SecurityEvents. All (読み取り専用の役割に対して)</span><span class="sxs-lookup"><span data-stu-id="b5171-153">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="b5171-154">SecurityEvents (読み取りおよび書き込みの役割に対して)</span><span class="sxs-lookup"><span data-stu-id="b5171-154">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="b5171-155">セキュリティに関する姿勢を把握する</span><span class="sxs-lookup"><span data-stu-id="b5171-155">Gain visibility into your security posture</span></span>

<span data-ttu-id="b5171-156">より迅速に必要な情報を提供するために、Microsoft の改善アクションがグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="b5171-156">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="b5171-157">Identity (azure AD アカウント & の役割、および Azure ATP が近日中の場合)</span><span class="sxs-lookup"><span data-stu-id="b5171-157">Identity (Azure AD accounts & roles, with Azure ATP coming soon)</span></span>
* <span data-ttu-id="b5171-158">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="b5171-158">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="b5171-159">デバイス (Microsoft Defender ATP デバイス)</span><span class="sxs-lookup"><span data-stu-id="b5171-159">Device (Microsoft Defender ATP devices)</span></span>
* <span data-ttu-id="b5171-160">アプリ (Office 365 および Microsoft Cloud App Security を含む、電子メールおよびクラウドアプリ)</span><span class="sxs-lookup"><span data-stu-id="b5171-160">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="b5171-161">インフラストラクチャ (Azure リソース)</span><span class="sxs-lookup"><span data-stu-id="b5171-161">Infrastructure (Azure resources)</span></span>

<span data-ttu-id="b5171-162">[Microsoft セキュリティスコアの概要] ページでは、これらのグループ間のポイントの分割方法と、使用可能なポイントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-162">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="b5171-163">また、概要ページでは、スコアの合計を表示し、セキュリティで保護されたスコアの傾向をベンチマーク比較によって把握し、スコアを向上させるために実行できる改善措置の優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-163">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

<span data-ttu-id="b5171-164">![セキュリティで保護](../media/secure-score/secure-score-homepage.png)
されたスコアホーム*ページ図 1: Microsoft セキュリティスコアの概要ページ*</span><span class="sxs-lookup"><span data-stu-id="b5171-164">![Secure Score homepage](../media/secure-score/secure-score-homepage.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="b5171-165">スコアを向上させるためのアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="b5171-165">Take action to improve your score</span></span>

<span data-ttu-id="b5171-166">[向上したアクション] タブには、発生する可能性のある攻撃対象範囲とその状態 (完了、計画済み、リスクがあり、サードパーティ、および宛先アドレス) について説明するセキュリティ上の推奨事項が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-166">The improvement actions tab lists the security recommendations that address possible attack surfaces, along with their status (completed, planned, risk accepted, third party, and to address).</span></span> <span data-ttu-id="b5171-167">すべての改善アクションを検索、フィルター、およびグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-167">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="b5171-168">付け</span><span class="sxs-lookup"><span data-stu-id="b5171-168">Ranking</span></span>

<span data-ttu-id="b5171-169">ランク付けは、残っている残りのポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="b5171-169">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="b5171-170">最も順位の高い向上アクションには、低い問題点、ユーザーへの影響、および複雑さが残った大きなポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="b5171-170">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="actions"></a><span data-ttu-id="b5171-171">Actions</span><span class="sxs-lookup"><span data-stu-id="b5171-171">Actions</span></span>

<span data-ttu-id="b5171-172">特定の改善アクションを選択すると、完全なページポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-172">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="b5171-173">![改善アクションのポップアップ](../media/secure-score/secure-score-improvement-action.png)
の例*図 2: 改善アクションのポップアップの例*</span><span class="sxs-lookup"><span data-stu-id="b5171-173">![Improvement action flyout example](../media/secure-score/secure-score-improvement-action.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="b5171-174">この操作を完了するには、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b5171-174">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="b5171-175">[**管理**] を選択して、構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="b5171-175">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="b5171-176">その後、そのアクションに価値があるポイントを取得して、フライアウトに表示されるようにします。通常、更新には約24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="b5171-176">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="b5171-177">[**共有**] を選択して、[改善] アクションへの直接リンクをコピーするか、電子メール、microsoft Teams、microsoft Planner、または ServiceNow などのリンクを共有するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5171-177">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="b5171-178">ServiceNow を選択すると、変更チケットを作成できるようになります。このチケットは、ServiceNow と Microsoft 365 セキュリティセンターのホームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-178">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="b5171-179">詳細については、「 [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5171-179">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

* <span data-ttu-id="b5171-180">[**状態とメモの編集**] を選択して、手動ステータスを編集するか、改善アクションに固有のメモを記録します。</span><span class="sxs-lookup"><span data-stu-id="b5171-180">Select **Edit status and notes** to edit any manual statuses or record notes specific to the improvement action.</span></span> <span data-ttu-id="b5171-181">[向上したアクション] タブの状態によって、フィルターまたはグループ化することができます。選択できる statues は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5171-181">You can filter or group by the statuses in the improvement actions tab. The statues you can select are the following</span></span>

    * <span data-ttu-id="b5171-182">[**宛先アドレス**] —改善アクションが必要であることを認識し、将来のある時点での対処を計画します。</span><span class="sxs-lookup"><span data-stu-id="b5171-182">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="b5171-183">この状態は、部分的に検出されたが完全に完了していない操作にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-183">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
    * <span data-ttu-id="b5171-184">**計画**済み: 改善アクションを完了するための具体的な計画があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-184">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
    * <span data-ttu-id="b5171-185">**承認**されたリスク: セキュリティは常にユーザビリティにバランスをとる必要がありますが、お客様の環境ですべての推奨事項が動作するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-185">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="b5171-186">その場合は、リスクを受け入れるか、またはリスクを軽減するかを選択して、改善アクションが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-186">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="b5171-187">ポイントはありませんが、改善アクションの一覧には表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b5171-187">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="b5171-188">このアクションは、履歴で表示するか、いつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-188">You can view this action in history or undo it at any time.</span></span>
    * <span data-ttu-id="b5171-189">**サードパーティによる解決**-向上アクションは、既にサードパーティ製のアプリケーションまたはソフトウェアによって処理されています。</span><span class="sxs-lookup"><span data-stu-id="b5171-189">**Resolve through third party** — The improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="b5171-190">この操作によって得られる価値を得ることができるようになります。そのため、スコアは全体的なセキュリティ姿勢をより適切に反映できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-190">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="b5171-191">サードパーティがコントロールをカバーしなくなった場合は、別の状態を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-191">If a third party no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="b5171-192">なお、Microsoft は、改善アクションがサードパーティによって解決済みとしてマークされている場合、実装の完全性を認識しません。</span><span class="sxs-lookup"><span data-stu-id="b5171-192">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as resolved through third party</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b5171-193">前提条件</span><span class="sxs-lookup"><span data-stu-id="b5171-193">Prerequisites</span></span>

<span data-ttu-id="b5171-194">[実装] セクションの前提条件には、取得する必要があるライセンス、または改善アクションを解決する前に完了する必要があるアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-194">Prerequisites in the Implementation section will list any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="b5171-195">改善アクションを完了し、それらのライセンスが必要なユーザーに適用されるように、ライセンスに十分な座席があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b5171-195">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="b5171-196">スコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="b5171-196">Track your score history and meet goals</span></span>

<span data-ttu-id="b5171-197">時間の経過と共に組織のスコアのグラフを表示するには、[**履歴**] タブを使用します。グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果の点やカテゴリなど) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-197">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="b5171-198">日付範囲をカスタマイズして、カテゴリ別にフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-198">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="b5171-199">[**指標 & の傾向**] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b5171-199">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="b5171-200">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5171-200">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="b5171-201">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5171-201">The visualizations include:</span></span>

* <span data-ttu-id="b5171-202">**セキュリティで保護されたスコアゾーン**: 組織の目標と、適切で良好な、悪いスコアの範囲の定義に基づいてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b5171-202">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="b5171-203">**回帰傾向**: 構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="b5171-203">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="b5171-204">**比較傾向**-組織のセキュリティスコアと他のユーザーとの間の比較方法。</span><span class="sxs-lookup"><span data-stu-id="b5171-204">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="b5171-205">このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b5171-205">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="b5171-206">**リスク許容度の傾向**— "リスクが許容される" としてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="b5171-206">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="b5171-207">**スコアの変更**: 獲得したポイント数、ポイント regressed、または新しいアクションが、指定された日付範囲内の後続のスコア変更と共に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b5171-207">**Score changes** — The number of points achieved, points regressed, or new actions added, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="b5171-208">リスクの認識</span><span class="sxs-lookup"><span data-stu-id="b5171-208">Risk awareness</span></span>

<span data-ttu-id="b5171-209">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-209">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="b5171-210">そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="b5171-210">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="b5171-211">セキュリティ侵害から完全に保護されていないオンラインサービスはないため、セキュリティ違反に対する保証として、どのような方法でも安全スコアを解釈しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-211">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="b5171-212">新機能</span><span class="sxs-lookup"><span data-stu-id="b5171-212">What’s new?</span></span> 

<span data-ttu-id="b5171-213">Microsoft のセキュリティスコアをより良いものにするために、セキュリティについてより良いものにして、使いやすくするために、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="b5171-213">To make Microsoft Secure Score a better representative of your security posture and improve usability, we have made some changes.</span></span> <span data-ttu-id="b5171-214">スコアと可能な最大スコアが変更されました。</span><span class="sxs-lookup"><span data-stu-id="b5171-214">Your score and the maximum possible score have changed.</span></span> <span data-ttu-id="b5171-215">ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-215">However, this does not imply a change in your security posture.</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="b5171-216">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="b5171-216">Updated interface and functionality</span></span>

* <span data-ttu-id="b5171-217">CISO およびリードレベルのディスカッションのすべての新しい指標と傾向のビュー</span><span class="sxs-lookup"><span data-stu-id="b5171-217">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="b5171-218">スコアを追跡およびベンチマークするための新しい方法</span><span class="sxs-lookup"><span data-stu-id="b5171-218">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="b5171-219">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="b5171-219">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="b5171-220">改善アクションのフィルター、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="b5171-220">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="b5171-221">スコアプロジェクションおよび計画されたアクションを使用して、将来の目標を管理する</span><span class="sxs-lookup"><span data-stu-id="b5171-221">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="b5171-222">その他多数。</span><span class="sxs-lookup"><span data-stu-id="b5171-222">And more!</span></span>

### <a name="removed-not-scored-and-review-improvement-actions"></a><span data-ttu-id="b5171-223">[スコアを表示しない] および [レビュー] の強化アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="b5171-223">Removed “not scored” and “review” improvement actions</span></span>

<span data-ttu-id="b5171-224">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="b5171-224">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="b5171-225">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="b5171-225">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="b5171-226">1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b5171-226">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="b5171-227">スコアの改善アクションは測定できません。また、改善アクションのレビューは、他の改善アクションと同じ基準ではありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-227">Not scored improvement actions are not measurable, and review improvement actions are not measured to the same standard as other improvement actions.</span></span>

<span data-ttu-id="b5171-228">このような理由により、スコアリングされていない、またはレビューのリズムを必要としたすべての改善アクションが一時的に削除されています。</span><span class="sxs-lookup"><span data-stu-id="b5171-228">For these reasons, all improvement actions that were not scored or required a review cadence have been temporarily removed.</span></span> <span data-ttu-id="b5171-229">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-229">No action is needed on your part.</span></span>

### <a name="simplification-of-the-point-system"></a><span data-ttu-id="b5171-230">ポイントシステムの簡略化</span><span class="sxs-lookup"><span data-stu-id="b5171-230">Simplification of the point system</span></span>

<span data-ttu-id="b5171-231">複数のエクスペリエンスにわたるポイントを標準化するために、各セキュリティで保護されたスコア向上のアクションポイント合計が10ポイント以下に更新されました。</span><span class="sxs-lookup"><span data-stu-id="b5171-231">To standardize points across multiple experiences, each Secure Score improvement action point total has been updated to be worth 10 points or less.</span></span> <span data-ttu-id="b5171-232">現在、または将来的に追加する予定のセキュリティ制御の幅広い breather で、より一貫したものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5171-232">It is necessary be more consistent across the wide breather of security controls that we have today and ones that we will be adding in the future.</span></span> <span data-ttu-id="b5171-233">これは非常に大きな変更になっていますが、総ポイント合計が表示されますが、セキュリティに関する姿勢に変化はありません。</span><span class="sxs-lookup"><span data-stu-id="b5171-233">While this is a significant change and you will see a drop in point totals, there will be no change to your security posture.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="b5171-234">ご意見をお聞かせください</span><span class="sxs-lookup"><span data-stu-id="b5171-234">We want to hear from you</span></span>

<span data-ttu-id="b5171-235">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="b5171-235">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="b5171-236">コミュニティを監視しており、ヘルプを提供しています。</span><span class="sxs-lookup"><span data-stu-id="b5171-236">We're monitoring the community and will provide help.</span></span>
