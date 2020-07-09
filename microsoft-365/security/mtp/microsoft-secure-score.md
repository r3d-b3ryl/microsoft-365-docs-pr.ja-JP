---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
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
ms.openlocfilehash: 44c9992be3fe0e6919a498fea0ee1b480a30a2bb
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086681"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="7e09e-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="7e09e-104">Microsoft Secure Score</span></span>

<span data-ttu-id="7e09e-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="7e09e-106">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="7e09e-107">セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="7e09e-108">Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="7e09e-109">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="7e09e-110">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="7e09e-111">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="7e09e-112">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="7e09e-113">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="7e09e-114">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="7e09e-115">メカニズム</span><span class="sxs-lookup"><span data-stu-id="7e09e-115">How it works</span></span>

<span data-ttu-id="7e09e-116">推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対処、または別の軽減対策を行うためのポイントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-116">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="7e09e-117">改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-117">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="7e09e-118">改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-118">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="7e09e-119">ライセンスに関係なく、考えられるすべての改善策を紹介するため、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-119">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="7e09e-120">絶対的なセキュリティ体制がセキュア スコアによって示されます。これは、組織が所有する製品ライセンスに関係なく常に同じです。</span><span class="sxs-lookup"><span data-stu-id="7e09e-120">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="7e09e-121">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-121">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="7e09e-122">スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-122">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="7e09e-123">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-123">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="7e09e-124">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="7e09e-124">How improvement actions are scored</span></span>

<span data-ttu-id="7e09e-125">各改善アクションには、10ポイント以下の価値があります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-125">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="7e09e-126">多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善のための処置を実装すると、ポイントの 100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-126">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="7e09e-127">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-127">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="7e09e-128">たとえば、強化アクションによって、多要素認証を使用するすべてのユーザーを保護することにより、すべて100のユーザーを保護することによって10ポイント獲得した場合に、保護されているユーザーの合計数が50の場合は、5ポイント (50 保護/100 合計 \* 10 最大 pts = 5 ポイント部分スコア) になります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-128">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="7e09e-129">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="7e09e-129">Products included in Secure Score</span></span>

<span data-ttu-id="7e09e-130">現在、Microsoft 365 (Exchange Online を含む)、Azure AD、Microsoft Defender ATP、Azure ATP、および Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-130">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="7e09e-131">その他のセキュリティ製品の推奨事項は近日リリース予定です。</span><span class="sxs-lookup"><span data-stu-id="7e09e-131">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="7e09e-132">推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-132">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="7e09e-133">また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-133">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="7e09e-134">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="7e09e-134">Security defaults</span></span>

<span data-ttu-id="7e09e-135">Microsoft のセキュリティで保護されたスコア[では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります</span><span class="sxs-lookup"><span data-stu-id="7e09e-135">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="7e09e-136">[セキュリティの既定] をオンにすると、次の強化されたアクションについて完全なポイントが付与されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-136">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="7e09e-137">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする (9 ポイント)</span><span class="sxs-lookup"><span data-stu-id="7e09e-137">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="7e09e-138">管理役割に MFA を必要とする (10 ポイント)</span><span class="sxs-lookup"><span data-stu-id="7e09e-138">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="7e09e-139">従来の認証をブロックするポリシーを有効にする (7 ポイント)</span><span class="sxs-lookup"><span data-stu-id="7e09e-139">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="7e09e-140">セキュリティの既定値には、「サインインリスクポリシー」と「ユーザーリスクポリシー」の強化アクションに似たセキュリティを提供するセキュリティ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-140">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="7e09e-141">これらのポリシーをセキュリティの既定の設定の上で設定する代わりに、それぞれの状態を "代替対策によって解決されました" に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e09e-141">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="7e09e-142">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7e09e-142">Required permissions</span></span>

<span data-ttu-id="7e09e-143">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-143">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="7e09e-144">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="7e09e-144">Read and write roles</span></span>

<span data-ttu-id="7e09e-145">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-145">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="7e09e-146">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-146">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="7e09e-147">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-147">Global administrator</span></span>
* <span data-ttu-id="7e09e-148">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-148">Security administrator</span></span>
* <span data-ttu-id="7e09e-149">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-149">Exchange administrator</span></span>
* <span data-ttu-id="7e09e-150">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-150">SharePoint administrator</span></span>
* <span data-ttu-id="7e09e-151">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-151">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="7e09e-152">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="7e09e-152">Read-only roles</span></span>

<span data-ttu-id="7e09e-153">読み取り専用アクセス許可があっても、改善のための処置のステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-153">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="7e09e-154">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-154">Helpdesk administrator</span></span>
* <span data-ttu-id="7e09e-155">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-155">User administrator</span></span>
* <span data-ttu-id="7e09e-156">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="7e09e-156">Service administrator</span></span>
* <span data-ttu-id="7e09e-157">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="7e09e-157">Security reader</span></span>
* <span data-ttu-id="7e09e-158">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="7e09e-158">Security operator</span></span>
* <span data-ttu-id="7e09e-159">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="7e09e-159">Global reader</span></span>

## <a name="gain-visibility-into-your-security-posture"></a><span data-ttu-id="7e09e-160">セキュリティ体制の可視性を獲得する</span><span class="sxs-lookup"><span data-stu-id="7e09e-160">Gain visibility into your security posture</span></span>

<span data-ttu-id="7e09e-161">必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-161">To help you the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="7e09e-162">ID (Azure AD アカウントと役割)</span><span class="sxs-lookup"><span data-stu-id="7e09e-162">Identity (Azure AD accounts & roles)</span></span>
* <span data-ttu-id="7e09e-163">データ (Microsoft Information Protection)</span><span class="sxs-lookup"><span data-stu-id="7e09e-163">Data  (Microsoft Information Protection)</span></span>
* <span data-ttu-id="7e09e-164">デバイス (Microsoft Defender ATP、[構成スコア](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score)と呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="7e09e-164">Device (Microsoft Defender ATP, known as [Configuration score](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))</span></span>
* <span data-ttu-id="7e09e-165">アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)</span><span class="sxs-lookup"><span data-stu-id="7e09e-165">App (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>
* <span data-ttu-id="7e09e-166">インフラストラクチャ (現在のところ、改善のための処置はありません)</span><span class="sxs-lookup"><span data-stu-id="7e09e-166">Infrastructure (no improvement actions for now)</span></span>

>[!NOTE]
><span data-ttu-id="7e09e-167">Microsoft Secure Score の最近のリリースでは、Microsoft セキュリティスコアを Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がない、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="7e09e-167">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="7e09e-168">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="7e09e-168">View details</span></span>](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

<span data-ttu-id="7e09e-169">[Microsoft セキュア スコアの概要] ページでは、これらのグループ間でポイントがどのように分割され、どのポイントが利用可能であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-169">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="7e09e-170">また、[概要] ページでは、合計スコアの全表示ビュー、ベンチマーク比較によるセキュア スコア履歴の傾向、スコアを上げるために優先して実装できる改善のための処置を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-170">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="7e09e-172">スコアを上げるための対策</span><span class="sxs-lookup"><span data-stu-id="7e09e-172">Take action to improve your score</span></span>

<span data-ttu-id="7e09e-173">[**向上**したアクション] タブには、発生する可能性のある攻撃対象の範囲とその状態 (サードパーティによって解決され、代替の軽減によって解決されたもの) とその状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-173">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces, along with their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="7e09e-174">すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-174">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="7e09e-175">ランク付け</span><span class="sxs-lookup"><span data-stu-id="7e09e-175">Ranking</span></span>

<span data-ttu-id="7e09e-176">ランク付けは、残りのポイント数、実装の難しさ、ユーザーへの影響、複雑さに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-176">Ranking is based on the number of remaining points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="7e09e-177">最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-177">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="7e09e-178">向上アクションの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="7e09e-178">View improvement action details</span></span>

<span data-ttu-id="7e09e-179">特定の改善アクションを選択すると、完全なページポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-179">When you select a specific improvement action, a full page flyout appears.</span></span>  

<span data-ttu-id="7e09e-180">![改善アクションのポップアップの例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *図 2: 改善アクションのポップアップの例*</span><span class="sxs-lookup"><span data-stu-id="7e09e-180">![Improvement action flyout example](../../media/secure-score/secure-score-improvement-action-details.png)
*Figure 2: Improvement action flyout example*</span></span>

<span data-ttu-id="7e09e-181">この操作を完了するには、いくつかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-181">To complete the action, you have a few options:</span></span>

* <span data-ttu-id="7e09e-182">[**管理**] を選択して、構成画面に移動し、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="7e09e-182">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="7e09e-183">その後、そのアクションに価値があるポイントを取得して、フライアウトに表示されるようにします。通常、更新には約24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-183">You will then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

* <span data-ttu-id="7e09e-184">[**共有**] を選択して、[改善] アクションへの直接リンクをコピーするか、電子メール、microsoft Teams、microsoft Planner、または ServiceNow などのリンクを共有するプラットフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-184">Select **Share** to copy the direct link to the improvement action, or choose the platform to share the link such as email, Microsoft Teams, Microsoft Planner, or ServiceNow.</span></span> <span data-ttu-id="7e09e-185">ServiceNow を選択すると、変更チケットを作成できるようになります。このチケットは、ServiceNow と Microsoft 365 セキュリティセンターのホームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-185">Selecting ServiceNow will let you create a change ticket which will be visible in ServiceNow and the Microsoft 365 security center home.</span></span> <span data-ttu-id="7e09e-186">詳細については、「 [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-186">To learn more, see [Microsoft 365 Security Center and ServiceNow integration](tickets-security-center.md).</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="7e09e-187">改善アクションの状態を選択する</span><span class="sxs-lookup"><span data-stu-id="7e09e-187">Choose an improvement action status</span></span>

<span data-ttu-id="7e09e-188">[改善] アクションに固有の状態を選択し、メモを記録します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-188">Choose any statuses and record notes specific to the improvement action.</span></span> <span data-ttu-id="7e09e-189">選択できる statues は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7e09e-189">The statues you can select are the following:</span></span>

* <span data-ttu-id="7e09e-190">[**宛先アドレス**] —改善アクションが必要であることを認識し、将来のある時点での対処を計画します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-190">**To address** — You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="7e09e-191">この状態は、部分的に検出されたが完全に完了していない操作にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-191">This state also applies to actions which are detected as partially, but not fully completed.</span></span>
* <span data-ttu-id="7e09e-192">**計画**済み: 改善アクションを完了するための具体的な計画があります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-192">**Planned** — There are concrete plans in place to complete the improvement action.</span></span>
* <span data-ttu-id="7e09e-193">**承認**されたリスク: セキュリティは常にユーザビリティにバランスをとる必要がありますが、お客様の環境ですべての推奨事項が動作するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-193">**Risk accepted** — Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="7e09e-194">その場合は、リスクを受け入れるか、またはリスクを軽減するかを選択して、改善アクションが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-194">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="7e09e-195">ポイントはありませんが、改善アクションの一覧には表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-195">You will not be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="7e09e-196">このアクションは履歴で表示したり、いつでも元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-196">You can view this action in history or undo it at any time.</span></span>
* <span data-ttu-id="7e09e-197">**サード**パーティによって解決され、**代替の軽減**によって解決されました。向上アクションは、サードパーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既にアドレス指定されています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-197">**Resolved through third party** and **Resolved through alternate mitigation** — The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="7e09e-198">この操作によって得られる価値を得ることができるようになります。そのため、スコアは全体的なセキュリティ姿勢をより適切に反映できます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-198">You will gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="7e09e-199">サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-199">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="7e09e-200">改善アクションがこれらの状態のどちらかとしてマークされている場合、Microsoft は、実装の完全性を確認することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-200">Please keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="7e09e-201">脅威 & 脆弱性管理の改善アクション</span><span class="sxs-lookup"><span data-stu-id="7e09e-201">Threat & Vulnerability Management improvement actions</span></span>

<span data-ttu-id="7e09e-202">"Device" カテゴリの向上アクションについては、[状態] を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-202">For improvement actions in the "Device" category, you will not be able to choose statuses.</span></span> <span data-ttu-id="7e09e-203">代わりに、 [Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)で、関連付けられている[脅威 & 脆弱性管理 (tvm) セキュリティに関する推奨事項](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)に従ってアクションを実行することになります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-203">Instead, you will be directed to the associated [Threat & Vulnerability Management (TVM) security recommendation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="7e09e-204">選択する例外と、作成する根拠は、そのポータルに固有のものであり、Microsoft Secure Score ポータルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-204">The exception you choose and justification you write will specific to that portal, and will not be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="7e09e-205">完了した改善アクション</span><span class="sxs-lookup"><span data-stu-id="7e09e-205">Completed improvement actions</span></span>

<span data-ttu-id="7e09e-206">改善アクションのすべての可能なポイントが達成されたら、改善アクションの状態は "完了" になります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-206">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="7e09e-207">完了した改善アクションは Microsoft データによって確認され、状態を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-207">Completed improvement actions are confirmed though Microsoft data, and you will not be able to change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="7e09e-208">情報を評価し、ユーザーへの影響を確認する</span><span class="sxs-lookup"><span data-stu-id="7e09e-208">Assess information and review user impact</span></span>

<span data-ttu-id="7e09e-209">[**概要**] セクションには、カテゴリ、保護できる攻撃、および製品がわかります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-209">The **At a glance** section will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="7e09e-210">**ユーザーへの影響**は、改善アクションが実行された場合にユーザーが**受ける**影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e09e-210">The **User impact** shows what the users will experience if the improvement action is enacted, and **Users affected** shows who will experience it.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="7e09e-211">向上アクションを実装する</span><span class="sxs-lookup"><span data-stu-id="7e09e-211">Implement the improvement action</span></span>

<span data-ttu-id="7e09e-212">[**実装**] セクションには、すべての前提条件、[改善] アクションを完了するための次のステップ、向上アクションの現在の実装状況、および詳細なリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-212">The **Implementation** section shows any prerequisites, step by step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="7e09e-213">前提条件は、取得する必要があるライセンス、または改善アクションが解決される前に完了する必要があるアクションです。</span><span class="sxs-lookup"><span data-stu-id="7e09e-213">Prerequisites will be any licenses that need to be obtained or actions that need to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="7e09e-214">改善アクションを完了し、それらのライセンスが必要なユーザーに適用されるように、ライセンスに十分な座席があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-214">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="track-your-score-history-and-meet-goals"></a><span data-ttu-id="7e09e-215">スコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="7e09e-215">Track your score history and meet goals</span></span>

<span data-ttu-id="7e09e-216">**[履歴]** タブで、組織のスコアのグラフを時系列で表示することができます。グラフの下には、選択した期間内に実行されたすべてのアクションと、結果として得られるポイントやカテゴリなどの属性が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-216">You can view a graph of your organization's score over time in the **History** tab. Below the graph is a list of all the actions taken in the selected time range and their attributes, such as resulting points and category.</span></span> <span data-ttu-id="7e09e-217">日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-217">You can customize a date range and filter by category.</span></span>

<span data-ttu-id="7e09e-218">[**指標 & の傾向**] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-218">In the **Metrics & trends** tab, there are several graphs and charts to give you more visibility into trends and set goals.</span></span> <span data-ttu-id="7e09e-219">視覚エフェクトのページ全体の日付範囲を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-219">You can set the date range for the whole page of visualizations.</span></span> <span data-ttu-id="7e09e-220">視覚エフェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7e09e-220">The visualizations include:</span></span>

* <span data-ttu-id="7e09e-221">**セキュリティで保護されたスコアゾーン**: 組織の目標と、適切で良好な、悪いスコアの範囲の定義に基づいてカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7e09e-221">**Your Secure Score zone** — Customized based on your organization's goals and definitions of good, okay, and bad score ranges.</span></span>
* <span data-ttu-id="7e09e-222">**回帰傾向**: 構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="7e09e-222">**Regression trend** — A timeline of points that have regressed due to configuration, user, or device changes.</span></span>  
* <span data-ttu-id="7e09e-223">**比較傾向**-組織のセキュリティスコアと他のユーザーとの間の比較方法。</span><span class="sxs-lookup"><span data-stu-id="7e09e-223">**Comparison trend** — How your organization's Secure Score compares to others' over time.</span></span> <span data-ttu-id="7e09e-224">このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-224">This view can include lines representing the score average of organizations with similar seat count and a custom comparison view that you can set.</span></span>
* <span data-ttu-id="7e09e-225">**リスク許容度の傾向**— "リスクが許容される" としてマークされた改善アクションのタイムライン。</span><span class="sxs-lookup"><span data-stu-id="7e09e-225">**Risk acceptance trend** — Timeline of improvement actions marked as "risk accepted."</span></span>
* <span data-ttu-id="7e09e-226">**スコアの変更**: 獲得したポイント数、ポイント regressed、およびそれ以降のスコア変更 (指定された日付範囲)。</span><span class="sxs-lookup"><span data-stu-id="7e09e-226">**Score changes** — The number of points achieved, points regressed, along with the subsequent score change, in the specified date range.</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="7e09e-227">リスク認識</span><span class="sxs-lookup"><span data-stu-id="7e09e-227">Risk awareness</span></span>

<span data-ttu-id="7e09e-228">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-228">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="7e09e-229">むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-229">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="7e09e-230">オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="7e09e-230">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="7e09e-231">新機能</span><span class="sxs-lookup"><span data-stu-id="7e09e-231">What's new?</span></span> 

<span data-ttu-id="7e09e-232">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="7e09e-232">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="7e09e-233">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-233">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="7e09e-234">Id のセキュリティで保護されたスコアとグラフ API の非互換性</span><span class="sxs-lookup"><span data-stu-id="7e09e-234">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="7e09e-235">Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="7e09e-235">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="7e09e-236">これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-236">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="7e09e-237">しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7e09e-237">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="7e09e-238">時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-238">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="7e09e-239">その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。</span><span class="sxs-lookup"><span data-stu-id="7e09e-239">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="7e09e-240">ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="7e09e-240">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

### <a name="updated-improvement-actions"></a><span data-ttu-id="7e09e-241">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="7e09e-241">Updated improvement actions</span></span>

- <span data-ttu-id="7e09e-242">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="7e09e-242">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="7e09e-243">Azure Advanced Threat Protection の向上アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="7e09e-243">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="7e09e-244">Microsoft Defender ATP の[脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="7e09e-244">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="7e09e-245">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7e09e-245">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="7e09e-246">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="7e09e-246">Updated interface and functionality</span></span>

* <span data-ttu-id="7e09e-247">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="7e09e-247">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="7e09e-248">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="7e09e-248">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="7e09e-249">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="7e09e-249">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="7e09e-250">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="7e09e-250">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="7e09e-251">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="7e09e-251">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="7e09e-252">その他多数。</span><span class="sxs-lookup"><span data-stu-id="7e09e-252">And more!</span></span>

### <a name="june-2020"></a><span data-ttu-id="7e09e-253">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="7e09e-253">June 2020</span></span>

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7e09e-254">Microsoft Defender Advanced Threat Protection の改善アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="7e09e-254">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7e09e-255">Attack Surface Reduction ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="7e09e-255">Turn on Attack Surface Reduction rules</span></span>

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7e09e-256">Microsoft Defender Advanced Threat Protection の改善アクションが追加されました</span><span class="sxs-lookup"><span data-stu-id="7e09e-256">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7e09e-257">Adobe Reader が子プロセスを作成するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-257">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="7e09e-258">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="7e09e-258">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="7e09e-259">すべての Office アプリケーションで子プロセスを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="7e09e-259">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="7e09e-260">Office アプリケーションで実行可能なコンテンツを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="7e09e-260">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="7e09e-261">JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-261">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="7e09e-262">難読化する可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-262">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="7e09e-263">電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-263">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="7e09e-264">Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="7e09e-264">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="7e09e-265">USB から実行される信頼できないおよび署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-265">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="7e09e-266">WMI イベントサブスクリプション経由の永続化をブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-266">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="7e09e-267">Office アプリケーションが他のプロセスにコードを挿入するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-267">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="7e09e-268">実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="7e09e-268">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="7e09e-269">PSExec および WMI コマンドからのプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-269">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="7e09e-270">Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="7e09e-270">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="7e09e-271">Office マクロからの Win32 API 呼び出しをブロックする</span><span class="sxs-lookup"><span data-stu-id="7e09e-271">Block Win32 API calls from Office macros</span></span>


## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="7e09e-272">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-272">We want to hear from you</span></span>

<span data-ttu-id="7e09e-273">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="7e09e-273">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="7e09e-274">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="7e09e-274">We're monitoring the community and will provide help.</span></span>

