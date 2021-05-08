---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
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
ms.openlocfilehash: 4a2c220cab15751671b9b38c3bb2fda3db12c9e1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245379"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="35184-104">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="35184-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="35184-105">Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="35184-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="35184-106">これは、セキュリティ センター https://security.microsoft.com/securescore のMicrosoft 365[にあります](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="35184-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="35184-107">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="35184-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="35184-108">組織は、Microsoft 365 セキュリティ センターの一元的なダッシュボードから、ユーザー ID、アプリ、デバイスのセキュリティを監視Microsoft 365作業できます。</span><span class="sxs-lookup"><span data-stu-id="35184-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="35184-109">セキュア スコアは、次のような方法で組織の役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="35184-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="35184-110">組織のセキュリティ体制の現在の状態について報告します。</span><span class="sxs-lookup"><span data-stu-id="35184-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="35184-111">検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。</span><span class="sxs-lookup"><span data-stu-id="35184-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="35184-112">ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。</span><span class="sxs-lookup"><span data-stu-id="35184-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="35184-113">指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。</span><span class="sxs-lookup"><span data-stu-id="35184-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="35184-114">スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。</span><span class="sxs-lookup"><span data-stu-id="35184-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Secure Score のホームページ](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a><span data-ttu-id="35184-116">しくみ</span><span class="sxs-lookup"><span data-stu-id="35184-116">How it works</span></span>

<span data-ttu-id="35184-117">次のアクションのポイントが与えられる。</span><span class="sxs-lookup"><span data-stu-id="35184-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="35184-118">推奨されるセキュリティ機能の構成</span><span class="sxs-lookup"><span data-stu-id="35184-118">Configuring recommended security features</span></span>
- <span data-ttu-id="35184-119">セキュリティ関連のタスクを実行する</span><span class="sxs-lookup"><span data-stu-id="35184-119">Doing security-related tasks</span></span>
- <span data-ttu-id="35184-120">サード パーティ製のアプリケーションまたはソフトウェア、または代替の軽減策を使用して改善アクションに対処する</span><span class="sxs-lookup"><span data-stu-id="35184-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="35184-121">一部の改善アクションは、完全に完了した場合にのみポイントを与える。</span><span class="sxs-lookup"><span data-stu-id="35184-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="35184-122">一部のデバイスまたはユーザーに対して完了した場合、部分的にポイントを与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="35184-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="35184-123">改善アクションの 1 つを実行できない場合、または実行しない場合は、リスクまたは残存リスクを受け入れるか選択できます。</span><span class="sxs-lookup"><span data-stu-id="35184-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="35184-124">サポートされている Microsoft 製品のライセンスがある場合は、それらの製品に関する推奨事項が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35184-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="35184-125">ライセンス のエディション、サブスクリプション、またはプランに関係なく、製品に対して可能な改善点の完全なセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35184-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="35184-126">これにより、セキュリティのベスト プラクティスを理解し、スコアを向上できます。</span><span class="sxs-lookup"><span data-stu-id="35184-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="35184-127">Secure Score で表される絶対的なセキュリティ体制は、組織が特定の製品に対して所有しているライセンスに関係なく同じままです。</span><span class="sxs-lookup"><span data-stu-id="35184-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="35184-128">セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="35184-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="35184-129">スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。</span><span class="sxs-lookup"><span data-stu-id="35184-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="35184-130">またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。</span><span class="sxs-lookup"><span data-stu-id="35184-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="35184-131">重要なシナリオ</span><span class="sxs-lookup"><span data-stu-id="35184-131">Key scenarios</span></span>

- [<span data-ttu-id="35184-132">現在のスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="35184-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="35184-133">スコアを自分のような組織と比較する</span><span class="sxs-lookup"><span data-stu-id="35184-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="35184-134">改善アクションを表示し、アクション プランを決定する</span><span class="sxs-lookup"><span data-stu-id="35184-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="35184-135">調査または実装するための作業フローの開始</span><span class="sxs-lookup"><span data-stu-id="35184-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="35184-136">改善のための処置のスコア</span><span class="sxs-lookup"><span data-stu-id="35184-136">How improvement actions are scored</span></span>

<span data-ttu-id="35184-137">各改善アクションの価値は 10 ポイント以下で、ほとんどがバイナリ形式でスコア付けされます。</span><span class="sxs-lookup"><span data-stu-id="35184-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="35184-138">新しいポリシーの作成や特定の設定の有効など、改善アクションを実装する場合は、ポイントの 100% を取得します。</span><span class="sxs-lookup"><span data-stu-id="35184-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="35184-139">その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。</span><span class="sxs-lookup"><span data-stu-id="35184-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="35184-140">たとえば、改善アクションでは、多要素認証を使用してすべてのユーザーを保護することで、10 ポイントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="35184-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="35184-141">保護されているユーザーは 100 人中 50 人しかいないので、部分的なスコアは 5 ポイント (50 protected / 100 total \* 10 max pts = 5 pts) になります。</span><span class="sxs-lookup"><span data-stu-id="35184-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="35184-142">セキュア スコアに含まれる製品</span><span class="sxs-lookup"><span data-stu-id="35184-142">Products included in Secure Score</span></span>

<span data-ttu-id="35184-143">現在、次の製品に関する推奨事項があります。</span><span class="sxs-lookup"><span data-stu-id="35184-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="35184-144">Microsoft 365 (Exchange Online を含む)</span><span class="sxs-lookup"><span data-stu-id="35184-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="35184-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="35184-145">Azure Active Directory</span></span>
- <span data-ttu-id="35184-146">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35184-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="35184-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="35184-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="35184-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="35184-148">Cloud App Security</span></span>
- <span data-ttu-id="35184-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35184-149">Microsoft Teams</span></span>

<span data-ttu-id="35184-150">その他のセキュリティ製品の推奨事項は近日リリース予定です。</span><span class="sxs-lookup"><span data-stu-id="35184-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="35184-151">推奨事項は、各製品に関連付けられているすべての攻撃表面をカバーするのではなく、優れたベースラインです。</span><span class="sxs-lookup"><span data-stu-id="35184-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="35184-152">また、改善アクションをサード パーティまたは代替の軽減策の対象としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="35184-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="35184-153">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="35184-153">Security defaults</span></span>

<span data-ttu-id="35184-154">Microsoft Secure Score では[、Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)でセキュリティの既定値をサポートするように改善アクションが更新され、一般的な攻撃に対して事前に構成されたセキュリティ設定を使用して組織を保護しやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="35184-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="35184-155">セキュリティの既定値を有効にした場合、次の改善アクションの完全なポイントが与されます。</span><span class="sxs-lookup"><span data-stu-id="35184-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="35184-156">すべてのユーザーがセキュリティで保護されたアクセスのための多要素認証を完了できる (9 ポイント)</span><span class="sxs-lookup"><span data-stu-id="35184-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="35184-157">管理役割に MFA を要求する (10 ポイント)</span><span class="sxs-lookup"><span data-stu-id="35184-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="35184-158">従来の認証をブロックするポリシーを有効にする (7 ポイント)</span><span class="sxs-lookup"><span data-stu-id="35184-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="35184-159">セキュリティの既定値には、"サインイン リスク ポリシー" や "ユーザー リスク ポリシー" の改善アクションと同様のセキュリティを提供するセキュリティ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35184-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="35184-160">これらのポリシーをセキュリティの既定値の上に設定する代わりに、状態を "別の軽減策によって解決済み" に更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35184-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="35184-161">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="35184-161">Required permissions</span></span>

<span data-ttu-id="35184-162">Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="35184-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="35184-163">読み取りと書き込みの役割</span><span class="sxs-lookup"><span data-stu-id="35184-163">Read and write roles</span></span>

<span data-ttu-id="35184-164">読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="35184-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="35184-165">他のユーザーに読み取り専用アクセス権を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="35184-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="35184-166">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="35184-166">Global administrator</span></span>
* <span data-ttu-id="35184-167">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="35184-167">Security administrator</span></span>
* <span data-ttu-id="35184-168">Exchange 管理者</span><span class="sxs-lookup"><span data-stu-id="35184-168">Exchange administrator</span></span>
* <span data-ttu-id="35184-169">SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="35184-169">SharePoint administrator</span></span>
* <span data-ttu-id="35184-170">アカウント管理者</span><span class="sxs-lookup"><span data-stu-id="35184-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="35184-171">読み取り専用の役割</span><span class="sxs-lookup"><span data-stu-id="35184-171">Read-only roles</span></span>

<span data-ttu-id="35184-172">読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア ゾーンを編集したり、カスタム比較を編集したりできない。</span><span class="sxs-lookup"><span data-stu-id="35184-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="35184-173">ヘルプデスク管理者</span><span class="sxs-lookup"><span data-stu-id="35184-173">Helpdesk administrator</span></span>
* <span data-ttu-id="35184-174">ユーザー管理者</span><span class="sxs-lookup"><span data-stu-id="35184-174">User administrator</span></span>
* <span data-ttu-id="35184-175">サービス管理者</span><span class="sxs-lookup"><span data-stu-id="35184-175">Service administrator</span></span>
* <span data-ttu-id="35184-176">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="35184-176">Security reader</span></span>
* <span data-ttu-id="35184-177">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="35184-177">Security operator</span></span>
* <span data-ttu-id="35184-178">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="35184-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="35184-179">リスク認識</span><span class="sxs-lookup"><span data-stu-id="35184-179">Risk awareness</span></span>

<span data-ttu-id="35184-180">Microsoft Secure Score は、システム構成、ユーザーの動作、その他のセキュリティ関連の測定値に基づくセキュリティ体制の数値要約です。</span><span class="sxs-lookup"><span data-stu-id="35184-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="35184-181">システムやデータが侵害される可能性を絶対に測定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35184-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="35184-182">むしろ、侵害されるリスクを相殺するのに役立つ Microsoft 環境でセキュリティ制御を採用した範囲を表します。</span><span class="sxs-lookup"><span data-stu-id="35184-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="35184-183">セキュリティ侵害から保護されたオンライン サービスはありません。セキュリティ違反に対する保証として安全なスコアを解釈する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="35184-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="35184-184">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="35184-184">We want to hear from you</span></span>

<span data-ttu-id="35184-185">問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="35184-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="35184-186">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="35184-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="35184-187">関連リソース</span><span class="sxs-lookup"><span data-stu-id="35184-187">Related resources</span></span>

- [<span data-ttu-id="35184-188">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="35184-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="35184-189">Microsoft Secure Score の履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="35184-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="35184-190">今後の予定</span><span class="sxs-lookup"><span data-stu-id="35184-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="35184-191">新機能</span><span class="sxs-lookup"><span data-stu-id="35184-191">What's new</span></span>](microsoft-secure-score-whats-new.md)