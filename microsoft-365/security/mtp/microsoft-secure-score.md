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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094800"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="e7f22-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="e7f22-104">Microsoft Secure Score</span></span>

<span data-ttu-id="e7f22-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="e7f22-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="e7f22-106">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f22-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="e7f22-107">セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="e7f22-108">Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="e7f22-109">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="e7f22-110">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="e7f22-111">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="e7f22-112">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="e7f22-113">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="e7f22-114">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="e7f22-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="e7f22-116">How it works</span></span>

<span data-ttu-id="e7f22-117">推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対処、または別の軽減対策を行うためのポイントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="e7f22-117">You are given points for configuring recommended security features, performing security-related tasks, or addressing the improvement action with a third-party application or software, or an alternate mitigation.</span></span> <span data-ttu-id="e7f22-118">改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-118">Some improvement actions only give points when fully completed, and some give partial points if they are completed for some devices or users.</span></span> <span data-ttu-id="e7f22-119">改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-119">If you cannot or do not want to enact one of the improvement actions, you can choose to accept the risk or the remaining risk.</span></span>

<span data-ttu-id="e7f22-120">ライセンスに関係なく、考えられるすべての改善策を紹介するため、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-120">We show you the full set of possible improvements, regardless of license, so you can understand security best practices and improve your score.</span></span> <span data-ttu-id="e7f22-121">絶対的なセキュリティ体制がセキュア スコアによって示されます。これは、組織が所有する製品ライセンスに関係なく常に同じです。</span><span class="sxs-lookup"><span data-stu-id="e7f22-121">Your absolute security posture is represented by Secure Score, which stays the same no matter what product licenses your organization owns.</span></span> <span data-ttu-id="e7f22-122">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="e7f22-122">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="e7f22-123">スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-123">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="e7f22-124">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-124">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="e7f22-125">重要なシナリオ</span><span class="sxs-lookup"><span data-stu-id="e7f22-125">Key scenarios</span></span>

- [<span data-ttu-id="e7f22-126">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="e7f22-126">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="e7f22-127">自分のスコアを組織と同じように比較する</span><span class="sxs-lookup"><span data-stu-id="e7f22-127">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="e7f22-128">改善アクションを表示し、アクションプランを決定する</span><span class="sxs-lookup"><span data-stu-id="e7f22-128">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="e7f22-129">調査または実装のための作業フローの開始</span><span class="sxs-lookup"><span data-stu-id="e7f22-129">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="e7f22-130">Microsoft 365 セキュリティセンターと ServiceNow 統合</span><span class="sxs-lookup"><span data-stu-id="e7f22-130">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="e7f22-131">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="e7f22-131">How improvement actions are scored</span></span>

<span data-ttu-id="e7f22-132">各改善アクションには、10ポイント以下の価値があります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-132">Each improvement action is worth 10 points or less.</span></span> <span data-ttu-id="e7f22-133">多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善のための処置を実装すると、ポイントの 100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-133">Most are scored in a binary fashion — if you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="e7f22-134">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-134">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="e7f22-135">たとえば、強化アクションによって、多要素認証を使用するすべてのユーザーを保護することにより、すべて100のユーザーを保護することによって10ポイント獲得した場合に、保護されているユーザーの合計数が50の場合は、5ポイント (50 保護/100 合計 \* 10 最大 pts = 5 ポイント部分スコア) になります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-135">For example, if the improvement action states you get 10 points by protecting all your users with multi-factor authentication and you only have 50 of 100 total users protected, you would be given a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts partial score).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="e7f22-136">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="e7f22-136">Products included in Secure Score</span></span>

<span data-ttu-id="e7f22-137">現在、Microsoft 365 (Exchange Online を含む)、Azure AD、Microsoft Defender ATP、Azure ATP、および Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-137">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP, and Cloud App Security.</span></span> <span data-ttu-id="e7f22-138">その他のセキュリティ製品の推奨事項は近日リリース予定です。</span><span class="sxs-lookup"><span data-stu-id="e7f22-138">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="e7f22-139">推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-139">The recommendations will not cover all the attack surfaces associated with each product, but they are a good baseline.</span></span> <span data-ttu-id="e7f22-140">また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-140">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="e7f22-141">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="e7f22-141">Security defaults</span></span>

<span data-ttu-id="e7f22-142">Microsoft のセキュリティで保護されたスコア[では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります</span><span class="sxs-lookup"><span data-stu-id="e7f22-142">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="e7f22-143">[セキュリティの既定] をオンにすると、次の強化されたアクションについて完全なポイントが付与されます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-143">If you turn on security defaults, you will be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="e7f22-144">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする (9 ポイント)</span><span class="sxs-lookup"><span data-stu-id="e7f22-144">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="e7f22-145">管理役割に MFA を必要とする (10 ポイント)</span><span class="sxs-lookup"><span data-stu-id="e7f22-145">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="e7f22-146">従来の認証をブロックするポリシーを有効にする (7 ポイント)</span><span class="sxs-lookup"><span data-stu-id="e7f22-146">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7f22-147">セキュリティの既定値には、「サインインリスクポリシー」と「ユーザーリスクポリシー」の強化アクションに似たセキュリティを提供するセキュリティ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-147">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="e7f22-148">これらのポリシーをセキュリティの既定の設定の上で設定する代わりに、それぞれの状態を "代替対策によって解決されました" に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7f22-148">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="e7f22-149">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e7f22-149">Required permissions</span></span>

<span data-ttu-id="e7f22-150">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-150">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="e7f22-151">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="e7f22-151">Read and write roles</span></span>

<span data-ttu-id="e7f22-152">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-152">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="e7f22-153">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-153">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="e7f22-154">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-154">Global administrator</span></span>
* <span data-ttu-id="e7f22-155">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-155">Security administrator</span></span>
* <span data-ttu-id="e7f22-156">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-156">Exchange administrator</span></span>
* <span data-ttu-id="e7f22-157">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-157">SharePoint administrator</span></span>
* <span data-ttu-id="e7f22-158">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-158">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="e7f22-159">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="e7f22-159">Read-only roles</span></span>

<span data-ttu-id="e7f22-160">読み取り専用アクセス許可があっても、改善のための処置のステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e7f22-160">With read-only access, you are not able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="e7f22-161">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-161">Helpdesk administrator</span></span>
* <span data-ttu-id="e7f22-162">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-162">User administrator</span></span>
* <span data-ttu-id="e7f22-163">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="e7f22-163">Service administrator</span></span>
* <span data-ttu-id="e7f22-164">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="e7f22-164">Security reader</span></span>
* <span data-ttu-id="e7f22-165">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="e7f22-165">Security operator</span></span>
* <span data-ttu-id="e7f22-166">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="e7f22-166">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="e7f22-167">リスク認識</span><span class="sxs-lookup"><span data-stu-id="e7f22-167">Risk awareness</span></span>

<span data-ttu-id="e7f22-168">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="e7f22-168">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="e7f22-169">むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-169">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="e7f22-170">オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="e7f22-170">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="whats-new"></a><span data-ttu-id="e7f22-171">新機能</span><span class="sxs-lookup"><span data-stu-id="e7f22-171">What's new?</span></span> 

<span data-ttu-id="e7f22-172">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="e7f22-172">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="e7f22-173">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f22-173">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="e7f22-174">Id のセキュリティで保護されたスコアとグラフ API の非互換性</span><span class="sxs-lookup"><span data-stu-id="e7f22-174">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="e7f22-175">Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="e7f22-175">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="e7f22-176">これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-176">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="e7f22-177">しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e7f22-177">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="e7f22-178">時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-178">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="e7f22-179">その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。</span><span class="sxs-lookup"><span data-stu-id="e7f22-179">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="e7f22-180">ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="e7f22-180">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

### <a name="updated-improvement-actions"></a><span data-ttu-id="e7f22-181">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="e7f22-181">Updated improvement actions</span></span>

- <span data-ttu-id="e7f22-182">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="e7f22-182">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="e7f22-183">Azure Advanced Threat Protection の向上アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="e7f22-183">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="e7f22-184">Microsoft Defender ATP の[脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="e7f22-184">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="e7f22-185">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e7f22-185">All released security recommendations supplied by TVM are now available</span></span>

### <a name="updated-interface-and-functionality"></a><span data-ttu-id="e7f22-186">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="e7f22-186">Updated interface and functionality</span></span>

* <span data-ttu-id="e7f22-187">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="e7f22-187">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="e7f22-188">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="e7f22-188">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="e7f22-189">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="e7f22-189">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="e7f22-190">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="e7f22-190">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="e7f22-191">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="e7f22-191">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="e7f22-192">その他多数。</span><span class="sxs-lookup"><span data-stu-id="e7f22-192">And more!</span></span>

### <a name="june-2020"></a><span data-ttu-id="e7f22-193">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="e7f22-193">June 2020</span></span>

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e7f22-194">Microsoft Defender Advanced Threat Protection の改善アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="e7f22-194">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="e7f22-195">Attack Surface Reduction ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="e7f22-195">Turn on Attack Surface Reduction rules</span></span>

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e7f22-196">Microsoft Defender Advanced Threat Protection の改善アクションが追加されました</span><span class="sxs-lookup"><span data-stu-id="e7f22-196">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="e7f22-197">Adobe Reader が子プロセスを作成するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-197">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="e7f22-198">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="e7f22-198">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="e7f22-199">すべての Office アプリケーションで子プロセスを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="e7f22-199">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="e7f22-200">Office アプリケーションで実行可能なコンテンツを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="e7f22-200">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="e7f22-201">JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-201">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="e7f22-202">難読化する可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-202">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="e7f22-203">電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-203">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="e7f22-204">Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="e7f22-204">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="e7f22-205">USB から実行される信頼できないおよび署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-205">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="e7f22-206">WMI イベントサブスクリプション経由の永続化をブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-206">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="e7f22-207">Office アプリケーションが他のプロセスにコードを挿入するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-207">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="e7f22-208">実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="e7f22-208">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="e7f22-209">PSExec および WMI コマンドからのプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-209">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="e7f22-210">Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="e7f22-210">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="e7f22-211">Office マクロからの Win32 API 呼び出しをブロックする</span><span class="sxs-lookup"><span data-stu-id="e7f22-211">Block Win32 API calls from Office macros</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e7f22-212">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="e7f22-212">We want to hear from you</span></span>

<span data-ttu-id="e7f22-213">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="e7f22-213">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e7f22-214">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="e7f22-214">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e7f22-215">関連リソース</span><span class="sxs-lookup"><span data-stu-id="e7f22-215">Related resources</span></span>

- [<span data-ttu-id="e7f22-216">セキュリティ体制の可視性を獲得する</span><span class="sxs-lookup"><span data-stu-id="e7f22-216">Gain visibility into your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e7f22-217">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="e7f22-217">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e7f22-218">今後の予定</span><span class="sxs-lookup"><span data-stu-id="e7f22-218">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
