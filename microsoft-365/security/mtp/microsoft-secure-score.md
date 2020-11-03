---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
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
ms.openlocfilehash: a41e05f54a8ba94752c6df91628a2200367ac0f3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843842"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="33a59-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="33a59-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="33a59-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="33a59-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="33a59-106">この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33a59-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="33a59-107">セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="33a59-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="33a59-108">Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。</span><span class="sxs-lookup"><span data-stu-id="33a59-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="33a59-109">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="33a59-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="33a59-110">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="33a59-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="33a59-111">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="33a59-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="33a59-112">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="33a59-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="33a59-113">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="33a59-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="33a59-114">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="33a59-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="33a59-116">メカニズム</span><span class="sxs-lookup"><span data-stu-id="33a59-116">How it works</span></span>

<span data-ttu-id="33a59-117">ここでは、次のアクションのポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="33a59-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="33a59-118">推奨されるセキュリティ機能を構成する</span><span class="sxs-lookup"><span data-stu-id="33a59-118">Configuring recommended security features</span></span>
- <span data-ttu-id="33a59-119">セキュリティ関連タスクの実行</span><span class="sxs-lookup"><span data-stu-id="33a59-119">Performing security-related tasks</span></span>
- <span data-ttu-id="33a59-120">サードパーティ製のアプリケーションまたはソフトウェア、または別の対策を使用した改善アクションへの対応</span><span class="sxs-lookup"><span data-stu-id="33a59-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="33a59-121">一部の改善アクションでは、完全に完了した時点のみが指定できます。</span><span class="sxs-lookup"><span data-stu-id="33a59-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="33a59-122">一部のデバイスまたはユーザーについては、一部のポイントを部分的に指定します。</span><span class="sxs-lookup"><span data-stu-id="33a59-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="33a59-123">改善アクションの1つを実行できない、または実行する必要がない場合は、リスクまたは残存リスクを受け入れるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="33a59-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="33a59-124">サポートされているいずれかの Microsoft 製品のライセンスを所有している場合は、これらの製品に関する推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33a59-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="33a59-125">ライセンスエディション、サブスクリプション、またはプランに関係なく、製品に対して提供される機能強化の完全なセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="33a59-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="33a59-126">これにより、セキュリティ上のベストプラクティスを理解し、スコアを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="33a59-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="33a59-127">セキュリティで保護されたスコアで表される絶対的なセキュリティに関する姿勢は、組織が特定の製品についてどのライセンスを所有しているかにかかわらず変わりません。</span><span class="sxs-lookup"><span data-stu-id="33a59-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="33a59-128">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="33a59-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="33a59-129">スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="33a59-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="33a59-130">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="33a59-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="33a59-131">重要なシナリオ</span><span class="sxs-lookup"><span data-stu-id="33a59-131">Key scenarios</span></span>

- [<span data-ttu-id="33a59-132">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="33a59-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="33a59-133">自分のスコアを組織と同じように比較する</span><span class="sxs-lookup"><span data-stu-id="33a59-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="33a59-134">改善アクションを表示し、アクションプランを決定する</span><span class="sxs-lookup"><span data-stu-id="33a59-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="33a59-135">調査または実装のための作業フローの開始</span><span class="sxs-lookup"><span data-stu-id="33a59-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="33a59-136">Microsoft 365 セキュリティセンターと ServiceNow 統合</span><span class="sxs-lookup"><span data-stu-id="33a59-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="33a59-137">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="33a59-137">How improvement actions are scored</span></span>

<span data-ttu-id="33a59-138">各改善アクションは、10ポイント以下の価値があり、ほとんどはバイナリ形式でスコアされます。</span><span class="sxs-lookup"><span data-stu-id="33a59-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="33a59-139">[改善] アクションを実装して、新しいポリシーを作成したり、特定の設定を有効にしたりすると、ポイントの100% が得られます。</span><span class="sxs-lookup"><span data-stu-id="33a59-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="33a59-140">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="33a59-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="33a59-141">たとえば、改善アクションによって、多要素認証を使用するすべてのユーザーを保護することで、10ポイントが得られることが示されます。</span><span class="sxs-lookup"><span data-stu-id="33a59-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="33a59-142">保護されているユーザー100の総数は50のみで、5ポイント (50 保護/100 合計 \* 10、最大ポイント5ポイント) の部分的なスコアを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a59-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="33a59-143">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="33a59-143">Products included in Secure Score</span></span>

<span data-ttu-id="33a59-144">現時点では、Microsoft 365 (Exchange Online)、Azure Active Directory、Microsoft Defender for Endpoint、microsoft Defender for Identity、および Cloud App Security に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="33a59-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="33a59-145">その他のセキュリティ製品の推奨事項は近日リリース予定です。</span><span class="sxs-lookup"><span data-stu-id="33a59-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="33a59-146">推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅しているわけではありませんが、適切な基準になっています。</span><span class="sxs-lookup"><span data-stu-id="33a59-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="33a59-147">また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="33a59-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="33a59-148">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="33a59-148">Security defaults</span></span>

<span data-ttu-id="33a59-149">Microsoft のセキュリティで保護されたスコア [では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります</span><span class="sxs-lookup"><span data-stu-id="33a59-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="33a59-150">[セキュリティの既定] をオンにすると、次の強化された操作について完全なポイントが与えられます。</span><span class="sxs-lookup"><span data-stu-id="33a59-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="33a59-151">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする (9 ポイント)</span><span class="sxs-lookup"><span data-stu-id="33a59-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="33a59-152">管理役割に MFA を必要とする (10 ポイント)</span><span class="sxs-lookup"><span data-stu-id="33a59-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="33a59-153">従来の認証をブロックするポリシーを有効にする (7 ポイント)</span><span class="sxs-lookup"><span data-stu-id="33a59-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="33a59-154">セキュリティの既定値には、「サインインリスクポリシー」と「ユーザーリスクポリシー」の強化アクションに似たセキュリティを提供するセキュリティ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="33a59-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="33a59-155">これらのポリシーをセキュリティの既定の設定の上で設定する代わりに、それぞれの状態を "代替対策によって解決されました" に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33a59-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="33a59-156">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="33a59-156">Required permissions</span></span>

<span data-ttu-id="33a59-157">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a59-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="33a59-158">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="33a59-158">Read and write roles</span></span>

<span data-ttu-id="33a59-159">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="33a59-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="33a59-160">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="33a59-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="33a59-161">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-161">Global administrator</span></span>
* <span data-ttu-id="33a59-162">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-162">Security administrator</span></span>
* <span data-ttu-id="33a59-163">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-163">Exchange administrator</span></span>
* <span data-ttu-id="33a59-164">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-164">SharePoint administrator</span></span>
* <span data-ttu-id="33a59-165">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="33a59-166">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="33a59-166">Read-only roles</span></span>

<span data-ttu-id="33a59-167">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="33a59-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="33a59-168">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-168">Helpdesk administrator</span></span>
* <span data-ttu-id="33a59-169">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-169">User administrator</span></span>
* <span data-ttu-id="33a59-170">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="33a59-170">Service administrator</span></span>
* <span data-ttu-id="33a59-171">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="33a59-171">Security reader</span></span>
* <span data-ttu-id="33a59-172">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="33a59-172">Security operator</span></span>
* <span data-ttu-id="33a59-173">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="33a59-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="33a59-174">リスク認識</span><span class="sxs-lookup"><span data-stu-id="33a59-174">Risk awareness</span></span>

<span data-ttu-id="33a59-175">Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティについての数値の概要です。</span><span class="sxs-lookup"><span data-stu-id="33a59-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="33a59-176">これは、システムやデータが侵害される可能性の絶対的な測定値ではありません。</span><span class="sxs-lookup"><span data-stu-id="33a59-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="33a59-177">そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="33a59-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="33a59-178">セキュリティ侵害の対象となるオンラインサービスは一切なく、セキュリティ違反に対する保証としては、どのような方法でも安全なスコアを保証しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a59-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="33a59-179">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="33a59-179">We want to hear from you</span></span>

<span data-ttu-id="33a59-180">問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="33a59-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="33a59-181">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="33a59-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="33a59-182">関連リソース</span><span class="sxs-lookup"><span data-stu-id="33a59-182">Related resources</span></span>

- [<span data-ttu-id="33a59-183">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="33a59-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="33a59-184">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="33a59-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="33a59-185">今後の予定</span><span class="sxs-lookup"><span data-stu-id="33a59-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="33a59-186">新機能</span><span class="sxs-lookup"><span data-stu-id="33a59-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
