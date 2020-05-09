---
title: Microsoft セキュリティスコアの新規作成
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細の計算方法、およびセキュリティ管理者がどのようなものを使用できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善のための処置
ms.prod: w10
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
ms.openlocfilehash: 965b4cf872129dc7bc9b439c1c15025acceb44c6
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173553"
---
# <a name="microsoft-secure-score-new"></a><span data-ttu-id="420b6-104">Microsoft セキュリティスコア (新)</span><span class="sxs-lookup"><span data-stu-id="420b6-104">Microsoft Secure Score (new)</span></span>

>[!IMPORTANT]
><span data-ttu-id="420b6-105">Microsoft のセキュリティで保護されたスコアの新しいイテレーションは、前のイテレーションを今後数か月の間に新しいデザイン要素および新機能に置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="420b6-105">This new iteration of Microsoft Secure Score is replacing the previous iteration with new design elements and features over the next few months</span></span>
>
><span data-ttu-id="420b6-106">**指標 & [傾向**] タブが表示されない場合は、以前のイテレーションになっています。</span><span class="sxs-lookup"><span data-stu-id="420b6-106">If you DO NOT see a **Metrics & trends** tab next to History, you are in the previous iteration.</span></span> [<span data-ttu-id="420b6-107">Microsoft Secure Score (以前のイテレーション) に移動します。</span><span class="sxs-lookup"><span data-stu-id="420b6-107">Go to Microsoft Secure Score (previous iteration)</span></span>](microsoft-secure-score.md)

<span data-ttu-id="420b6-108">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="420b6-108">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="420b6-109">この点https://security.microsoft.com/securescoreについては、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="420b6-109">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="420b6-110">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-110">Following the Security Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="420b6-111">Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-111">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="420b6-112">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="420b6-112">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="420b6-113">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="420b6-113">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="420b6-114">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="420b6-114">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="420b6-115">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="420b6-115">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="420b6-116">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-116">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="420b6-117">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-117">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

<span data-ttu-id="420b6-118">さらに、[Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api) を介して、推奨事項やスコアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="420b6-118">Additionally, you can access your recommendations and score through the [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api).</span></span> <span data-ttu-id="420b6-119">「[Secure Score リソースの種類](https://go.microsoft.com/fwlink/?linkid=2092996)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="420b6-119">Learn about the [Secure Score resource type](https://go.microsoft.com/fwlink/?linkid=2092996).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="420b6-120">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="420b6-120">How it works</span></span>

<span data-ttu-id="420b6-121">推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対処、または別の軽減対策を行うためのポイントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="420b6-121">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="420b6-122">改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。</span><span class="sxs-lookup"><span data-stu-id="420b6-122">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="420b6-123">改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-123">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="420b6-124">ライセンスに関係なく、考えられるすべての改善策を紹介するため、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-124">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="420b6-125">絶対的なセキュリティ体制がセキュア スコアによって示されます。これは、組織が所有する製品ライセンスに関係なく常に同じです。</span><span class="sxs-lookup"><span data-stu-id="420b6-125">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="420b6-126">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="420b6-126">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="420b6-127">スコアはリアルタイムで更新され、視覚エフェクト ページと改善アクション ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="420b6-127">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="420b6-128">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="420b6-128">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="420b6-129">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="420b6-129">How improvement actions are scored</span></span>

<span data-ttu-id="420b6-130">各改善アクションには、10ポイント以下の価値があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-130">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="420b6-131">多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善アクションを実装すると、ポイントの 100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="420b6-131">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="420b6-132">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="420b6-132">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="420b6-133">たとえば、改善アクションで、すべてのユーザーを多要素認証で保護するなら 30 ポイントを取得すると示しているとします。合計 100 人のユーザーのうち 5 人しか保護されていない場合、部分的なスコアとして約 2 ポイントが与えられます (保護されているユーザー 5 ÷ 合計数 100 × 最大ポイント 30 = 2 ポイント)。</span><span class="sxs-lookup"><span data-stu-id="420b6-133">For example, if the improvement action states you get 30 points by protecting all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="420b6-134">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="420b6-134">Products included in Secure Score</span></span>

<span data-ttu-id="420b6-135">現時点では、Microsoft 365 (Exchange Online を含む)、Azure AD、Microsoft Defender ATP、Azure ATP、および Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-135">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="420b6-136">その他のセキュリティ製品の推奨事項は近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-136">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="420b6-137">推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。</span><span class="sxs-lookup"><span data-stu-id="420b6-137">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="420b6-138">また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="420b6-138">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="420b6-139">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="420b6-139">Required permissions</span></span>

<span data-ttu-id="420b6-140">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-140">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="420b6-141">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="420b6-141">Read and write roles</span></span>

<span data-ttu-id="420b6-142">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="420b6-142">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="420b6-143">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="420b6-143">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="420b6-144">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-144">Global administrator</span></span>
* <span data-ttu-id="420b6-145">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-145">Security administrator</span></span>
* <span data-ttu-id="420b6-146">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-146">Exchange administrator</span></span>
* <span data-ttu-id="420b6-147">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-147">SharePoint administrator</span></span>
* <span data-ttu-id="420b6-148">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-148">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="420b6-149">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="420b6-149">Read-only roles</span></span>

<span data-ttu-id="420b6-150">読み取り専用アクセス許可があっても、改善アクションのステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="420b6-150">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="420b6-151">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-151">Helpdesk administrator</span></span>
* <span data-ttu-id="420b6-152">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-152">User administrator</span></span>
* <span data-ttu-id="420b6-153">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="420b6-153">Service administrator</span></span>
* <span data-ttu-id="420b6-154">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="420b6-154">Security reader</span></span>
* <span data-ttu-id="420b6-155">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="420b6-155">Security operator</span></span>
* <span data-ttu-id="420b6-156">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="420b6-156">Global reader</span></span>

### <a name="graph-api"></a><span data-ttu-id="420b6-157">Graph API</span><span class="sxs-lookup"><span data-stu-id="420b6-157">Graph API</span></span>

<span data-ttu-id="420b6-158">Graph API にアクセスするには、役割に加えて、次のいずれかのスコープを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-158">To access the Graph API, you need to have one of the following scopes in addition to a role:</span></span>

* <span data-ttu-id="420b6-159">SecurityEvents. All (読み取り専用の役割に対して)</span><span class="sxs-lookup"><span data-stu-id="420b6-159">SecurityEvents.Read.All (for read-only roles)</span></span>
* <span data-ttu-id="420b6-160">SecurityEvents (読み取りおよび書き込みの役割に対して)</span><span class="sxs-lookup"><span data-stu-id="420b6-160">SecurityEvents.ReadWrite.All (for read and write roles)</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="420b6-161">セキュリティ体制の可視性を獲得する</span><span class="sxs-lookup"><span data-stu-id="420b6-161">Gain visibility into your security posture</span></span>

<span data-ttu-id="420b6-162">必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="420b6-162">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="420b6-163">ID (Azure AD アカウントと役割)</span><span class="sxs-lookup"><span data-stu-id="420b6-163">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="420b6-164">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="420b6-164">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="420b6-165">デバイス (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="420b6-165">Device (Microsoft Defender ATP)</span></span>
* <span data-ttu-id="420b6-166">アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)</span><span class="sxs-lookup"><span data-stu-id="420b6-166">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="420b6-167">インフラストラクチャ (現在のところ、改善のための処置はありません)</span><span class="sxs-lookup"><span data-stu-id="420b6-167">Infrastructure (no improvement actions for now)</span></span>

<span data-ttu-id="420b6-168">[Microsoft セキュア スコアの概要] ページでは、これらのグループ間でポイントがどのように分割され、どのポイントが利用可能であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-168">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="420b6-169">また、[概要] ページでは、合計スコアの全表示ビュー、ベンチマーク比較によるセキュア スコア履歴の傾向、スコアを上げるために優先して実装できる改善のための処置を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-169">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)


## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="420b6-171">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="420b6-171">Take action to improve your score</span></span>

<span data-ttu-id="420b6-172">[**向上**したアクション] タブには、発生する可能性のある攻撃対象の範囲とその状態 (サードパーティによって解決され、代替の軽減によって解決されたもの) とその状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-172">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="420b6-173">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-173">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="420b6-174">ランク付け</span><span class="sxs-lookup"><span data-stu-id="420b6-174">Ranking</span></span>

<span data-ttu-id="420b6-175">ランク付けは、残りのポイント数、実装の難しさ、ユーザーへの影響、複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="420b6-175">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="420b6-176">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-176">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="420b6-177">向上アクションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="420b6-177">View improvement action details</span></span>

<span data-ttu-id="420b6-178">特定の改善アクションを選択すると、完全なページポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-178">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="420b6-179">![改善アクションのポップアップ](../../media/secure-score/secure-score-improvement-action-details.png)
の例*図 2: 改善アクションのポップアップの例*</span><span class="sxs-lookup"><span data-stu-id="420b6-179">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="420b6-180">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-180">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="420b6-181">[**管理**] を選択して、構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="420b6-181">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="420b6-182">その後、そのアクションに価値があるポイントを取得して、フライアウトに表示されるようにします。通常、更新には約24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="420b6-182">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="420b6-183">[**共有**] を選択して、[改善] アクションへの直接リンクをコピーするか、電子メール、microsoft Teams、microsoft Planner、または ServiceNow などのリンクを共有するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="420b6-183">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="420b6-184">ServiceNow を選択すると、変更チケットを作成できるようになります。このチケットは、ServiceNow と Microsoft 365 セキュリティセンターのホームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-184">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="420b6-185">詳細については、「 [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="420b6-185">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="420b6-186">改善アクションの状態を選択する</span><span class="sxs-lookup"><span data-stu-id="420b6-186">Choose an improvement action status</span></span>

<span data-ttu-id="420b6-187">[改善] アクションに固有の状態を選択し、メモを記録します。</span><span class="sxs-lookup"><span data-stu-id="420b6-187">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="420b6-188">選択できる statues は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="420b6-188">The statues you can select are the following:</span></span>

* <span data-ttu-id="420b6-189">[**宛先アドレス**] —改善アクションが必要であることを認識し、将来のある時点での対処を計画します。</span><span class="sxs-lookup"><span data-stu-id="420b6-189">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="420b6-190">この状態は、部分的に検出されたが完全に完了していない操作にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-190">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="420b6-191">**計画**済み: 改善アクションを完了するための具体的な計画があります。</span><span class="sxs-lookup"><span data-stu-id="420b6-191">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="420b6-192">**承認**されたリスク: セキュリティは常にユーザビリティにバランスをとる必要がありますが、お客様の環境ですべての推奨事項が動作するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="420b6-192">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="420b6-193">その場合は、リスクを受け入れるか、またはリスクを軽減するかを選択して、改善アクションが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-193">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="420b6-194">ポイントはありませんが、改善アクションの一覧には表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="420b6-194">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="420b6-195">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="420b6-195">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="420b6-196">**サード**パーティによって解決され、**代替の軽減**によって解決されました。向上アクションは、サードパーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既にアドレス指定されています。</span><span class="sxs-lookup"><span data-stu-id="420b6-196">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="420b6-197">この操作によって得られる価値を得ることができるようになります。そのため、スコアは全体的なセキュリティ姿勢をより適切に反映できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-197">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="420b6-198">サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-198">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="420b6-199">改善アクションがこれらの状態のどちらかとしてマークされている場合、Microsoft は、実装の完全性を確認することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="420b6-199">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="420b6-200">脅威 & 脆弱性管理の改善アクション</span><span class="sxs-lookup"><span data-stu-id="420b6-200">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="420b6-201">"Device" カテゴリの向上アクションについては、[状態] を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="420b6-201">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="420b6-202">代わりに、 [Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)で、関連付けられている[脅威 & 脆弱性管理 (tvm) セキュリティに関する推奨事項](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)に従ってアクションを実行することになります。</span><span class="sxs-lookup"><span data-stu-id="420b6-202">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="420b6-203">選択する例外と、作成する根拠は、そのポータルに固有のものであり、Microsoft Secure Score ポータルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="420b6-203">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="420b6-204">完了した改善アクション</span><span class="sxs-lookup"><span data-stu-id="420b6-204">Completed improvement actions</span></span>

<span data-ttu-id="420b6-205">改善アクションのすべての可能なポイントが達成されたら、改善アクションの状態は "完了" になります。</span><span class="sxs-lookup"><span data-stu-id="420b6-205">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="420b6-206">完了した改善アクションは Microsoft データによって確認され、状態を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="420b6-206">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="420b6-207">情報を評価し、ユーザーへの影響を確認する</span><span class="sxs-lookup"><span data-stu-id="420b6-207">Assess information and review user impact</span></span>

<span data-ttu-id="420b6-208">[**概要**] セクションには、カテゴリ、保護できる攻撃、および製品がわかります。</span><span class="sxs-lookup"><span data-stu-id="420b6-208">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="420b6-209">**ユーザーへの影響**は、改善アクションが実行された場合にユーザーが**受ける**影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="420b6-209">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="420b6-210">向上アクションを実装する</span><span class="sxs-lookup"><span data-stu-id="420b6-210">Implement the improvement action</span></span>

<span data-ttu-id="420b6-211">[**実装**] セクションには、すべての前提条件、[改善] アクションを完了するための次のステップ、向上アクションの現在の実装状況、および詳細なリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-211">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="420b6-212">前提条件は、取得する必要があるライセンス、または改善アクションが解決される前に完了する必要があるアクションです。</span><span class="sxs-lookup"><span data-stu-id="420b6-212">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="420b6-213">改善アクションを完了し、それらのライセンスが必要なユーザーに適用されるように、ライセンスに十分な座席があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="420b6-213">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="420b6-214">スコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="420b6-214">Track your score history and meet goals</span></span>

<span data-ttu-id="420b6-215">**[履歴]** タブで、組織のスコアのグラフを時系列で表示することができます。グラフの下には、選択した期間内に実行されたすべてのアクションと、結果として得られるポイントやカテゴリなどの属性が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="420b6-215">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="420b6-216">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-216">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="420b6-217">[**指標 & の傾向**] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="420b6-217">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="420b6-218">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="420b6-218">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="420b6-219">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="420b6-219">The visualizations include:</span></span>

* <span data-ttu-id="420b6-220">**セキュリティで保護されたスコアゾーン**: 組織の目標と、適切で良好な、悪いスコアの範囲の定義に基づいてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="420b6-220">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="420b6-221">**回帰傾向**: 構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="420b6-221">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="420b6-222">**比較傾向**-組織のセキュリティスコアと他のユーザーとの間の比較方法。</span><span class="sxs-lookup"><span data-stu-id="420b6-222">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="420b6-223">このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="420b6-223">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="420b6-224">**リスク許容度の傾向**— "リスクが許容される" としてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="420b6-224">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="420b6-225">**スコアの変更**: 獲得したポイント数、ポイント regressed、およびそれ以降のスコア変更 (指定された日付範囲)。</span><span class="sxs-lookup"><span data-stu-id="420b6-225">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="420b6-226">リスク認識</span><span class="sxs-lookup"><span data-stu-id="420b6-226">Risk awareness</span></span>

<span data-ttu-id="420b6-227">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="420b6-227">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="420b6-228">むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="420b6-228">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="420b6-229">オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="420b6-229">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="420b6-230">新機能</span><span class="sxs-lookup"><span data-stu-id="420b6-230">What's new?</span></span> 

<span data-ttu-id="420b6-231">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="420b6-231">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="420b6-232">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="420b6-232">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

- <span data-ttu-id="420b6-233">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="420b6-233">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="420b6-234">Azure Advanced Threat Protection の向上アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="420b6-234">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="420b6-235">Microsoft Defender ATP の[脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="420b6-235">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="420b6-236">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="420b6-236">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="420b6-237">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="420b6-237">Updated interface and functionality</span></span>

* <span data-ttu-id="420b6-238">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="420b6-238">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="420b6-239">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="420b6-239">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="420b6-240">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="420b6-240">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="420b6-241">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="420b6-241">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="420b6-242">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="420b6-242">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="420b6-243">その他多数。</span><span class="sxs-lookup"><span data-stu-id="420b6-243">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="420b6-244">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="420b6-244">We want to hear from you</span></span>

<span data-ttu-id="420b6-245">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="420b6-245">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="420b6-246">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="420b6-246">We're monitoring the community and will provide help.</span></span>
