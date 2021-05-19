---
title: Microsoft 365 Defender のインシデント
description: セキュリティ センター内のデバイス、ユーザー、メールボックス間で発生したインシデントMicrosoft 365調査します。
keywords: インシデント、アラート、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: cc2fcd7410c2f3122fb3ce49a40e93bfa0767331
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539025"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="896b5-104">Microsoft 365 Defender のインシデント</span><span class="sxs-lookup"><span data-stu-id="896b5-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="896b5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="896b5-105">**Applies to:**</span></span>
- <span data-ttu-id="896b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="896b5-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="896b5-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="896b5-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="896b5-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="896b5-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="896b5-109">Defender のインシデントMicrosoft 365、関連付けられたアラートと、攻撃のストーリーを構成する関連データのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="896b5-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="896b5-110">Microsoft 365やアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="896b5-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="896b5-111">個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="896b5-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="896b5-112">ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。</span><span class="sxs-lookup"><span data-stu-id="896b5-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="896b5-113">結果は、テナント内の複数のエンティティに対する複数の通知になります。</span><span class="sxs-lookup"><span data-stu-id="896b5-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="896b5-114">個々のアラートを組み合わせて攻撃に関する洞察を得る場合は、困難で時間がかかる場合があります。Microsoft 365 Defender は自動的にアラートと関連情報をインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="896b5-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Defender Microsoft 365エンティティからのイベントをインシデントに関連付ける方法":::

<span data-ttu-id="896b5-116">Defender でのインシデントのこの短い概要 (4 Microsoft 365) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="896b5-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="896b5-117">関連するアラートをインシデントにグループ化すると、攻撃の包括的なビューが得されます。</span><span class="sxs-lookup"><span data-stu-id="896b5-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="896b5-118">たとえば、次の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="896b5-118">For example, you can see:</span></span>

- <span data-ttu-id="896b5-119">攻撃が開始された場所。</span><span class="sxs-lookup"><span data-stu-id="896b5-119">Where the attack started.</span></span>
- <span data-ttu-id="896b5-120">どのような戦術が使用されたのか。</span><span class="sxs-lookup"><span data-stu-id="896b5-120">What tactics were used.</span></span>
- <span data-ttu-id="896b5-121">攻撃がテナントにどれくらいまで入ったか。</span><span class="sxs-lookup"><span data-stu-id="896b5-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="896b5-122">攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。</span><span class="sxs-lookup"><span data-stu-id="896b5-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="896b5-123">攻撃に関連付けられているすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="896b5-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="896b5-124">有効[にした場合](m365d-enable.md)、Microsoft 365 Defender は自動化[と](m365d-autoir.md)人工知能を通じてアラートを自動的に調査および解決できます。</span><span class="sxs-lookup"><span data-stu-id="896b5-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="896b5-125">また、追加の修復手順を実行して攻撃を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="896b5-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="896b5-126">セキュリティ センターでのインシデントMicrosoft 365アラート</span><span class="sxs-lookup"><span data-stu-id="896b5-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="896b5-127">インシデント &**アラート>** インシデントを管理するには、Microsoft 365 セキュリティ センター (security.microsoft.com) を [security.microsoft.com。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="896b5-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="896b5-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="896b5-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="セキュリティ センターの [インシデントMicrosoft 365ページ":::

<span data-ttu-id="896b5-130">インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="896b5-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="セキュリティ センターのインシデントの概要ページMicrosoft 365例":::

<span data-ttu-id="896b5-132">インシデントの追加タブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="896b5-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="896b5-133">アラート</span><span class="sxs-lookup"><span data-stu-id="896b5-133">Alerts</span></span> 

  <span data-ttu-id="896b5-134">インシデントとその情報に関連するすべてのアラート。</span><span class="sxs-lookup"><span data-stu-id="896b5-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="896b5-135">デバイス</span><span class="sxs-lookup"><span data-stu-id="896b5-135">Devices</span></span>

  <span data-ttu-id="896b5-136">インシデントの一部または関連付けとして識別されたすべてのデバイス。</span><span class="sxs-lookup"><span data-stu-id="896b5-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="896b5-137">ユーザー</span><span class="sxs-lookup"><span data-stu-id="896b5-137">Users</span></span>

  <span data-ttu-id="896b5-138">インシデントの一部または関連付けとして識別されたすべてのユーザー。</span><span class="sxs-lookup"><span data-stu-id="896b5-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="896b5-139">メールボックス</span><span class="sxs-lookup"><span data-stu-id="896b5-139">Mailboxes</span></span>

  <span data-ttu-id="896b5-140">インシデントの一部または関連付けとして識別されたすべてのメールボックス。</span><span class="sxs-lookup"><span data-stu-id="896b5-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="896b5-141">調査</span><span class="sxs-lookup"><span data-stu-id="896b5-141">Investigations</span></span>

  <span data-ttu-id="896b5-142">インシデント内 [のアラートによって](m365d-autoir.md) トリガーされる、すべての自動調査。</span><span class="sxs-lookup"><span data-stu-id="896b5-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="896b5-143">証拠と対応</span><span class="sxs-lookup"><span data-stu-id="896b5-143">Evidence and Response</span></span>

  <span data-ttu-id="896b5-144">インシデント内のアラートでサポートされているイベントと疑わしいエンティティすべて。</span><span class="sxs-lookup"><span data-stu-id="896b5-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="896b5-145">Graph (プレビューで)</span><span class="sxs-lookup"><span data-stu-id="896b5-145">Graph (in preview)</span></span>

  <span data-ttu-id="896b5-146">組織内の影響を受け取った資産へのアラートの接続を示す図。</span><span class="sxs-lookup"><span data-stu-id="896b5-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="896b5-147">インシデントとそのデータと、セキュリティ センター内のインシデントのタブとのMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="896b5-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータとセキュリティ センター内のインシデントのタブMicrosoft 365関係":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="896b5-149">Defender のインシデント対応ワークフロー Microsoft 365例</span><span class="sxs-lookup"><span data-stu-id="896b5-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="896b5-150">次に、セキュリティ センターでインシデントに対応Microsoft 365ワークフロー Microsoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="896b5-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="インシデント対応ワークフローの例Microsoft 365":::

<span data-ttu-id="896b5-152">継続的に、インシデント キューの分析と解決に最も優先度の高いインシデントを特定し、対応の準備を整えます。</span><span class="sxs-lookup"><span data-stu-id="896b5-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="896b5-153">これは、次の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="896b5-153">This is a combination of:</span></span>

- <span data-ttu-id="896b5-154">[インシデント キューの](incident-queue.md) フィルター処理と並べ替えを通じて、優先度の高いインシデントを特定するトリアージ。</span><span class="sxs-lookup"><span data-stu-id="896b5-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="896b5-155">[タイトルを](manage-incidents.md) 変更し、アナリストに割り当て、タグとコメントを追加してインシデントを管理します。</span><span class="sxs-lookup"><span data-stu-id="896b5-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="896b5-156">インシデントごとに、攻撃とアラート [の調査と分析を開始します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="896b5-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="896b5-157">a.</span><span class="sxs-lookup"><span data-stu-id="896b5-157">a.</span></span> <span data-ttu-id="896b5-158">インシデントの概要を表示して、インシデントの範囲と重大度、および影響を受けるエンティティ ([概要] タブ) **を理解** します。</span><span class="sxs-lookup"><span data-stu-id="896b5-158">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="896b5-159">b.</span><span class="sxs-lookup"><span data-stu-id="896b5-159">b.</span></span> <span data-ttu-id="896b5-160">アラートの分析を開始して、発生元、スコープ、重大度 ([アラート] タブ) **を理解** します。</span><span class="sxs-lookup"><span data-stu-id="896b5-160">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="896b5-161">c.</span><span class="sxs-lookup"><span data-stu-id="896b5-161">c.</span></span> <span data-ttu-id="896b5-162">必要に応じて、影響を受け取ったデバイス、ユーザー、およびメールボックス([デバイス]、[ユーザー]、および [メールボックス] タブ) に関する **情報を収集** します。</span><span class="sxs-lookup"><span data-stu-id="896b5-162">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="896b5-163">d.</span><span class="sxs-lookup"><span data-stu-id="896b5-163">d.</span></span> <span data-ttu-id="896b5-164">Defender が一部Microsoft 365自動的に解決した方法 [([](m365d-autoir.md)調査] タブ)**を参照** してください。</span><span class="sxs-lookup"><span data-stu-id="896b5-164">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="896b5-165">e.</span><span class="sxs-lookup"><span data-stu-id="896b5-165">e.</span></span> <span data-ttu-id="896b5-166">必要に応じて、インシデントのデータ セットの情報を使用して詳細を確認します ([証拠と応答] **タブ** )。</span><span class="sxs-lookup"><span data-stu-id="896b5-166">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="896b5-167">分析の後または分析中に、攻撃による追加の影響を軽減し、セキュリティ上の脅威を根絶するために、格納を実行します。</span><span class="sxs-lookup"><span data-stu-id="896b5-167">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="896b5-168">可能な限り、テナント リソースをインシデントの前の状態に復元して攻撃から回復します。</span><span class="sxs-lookup"><span data-stu-id="896b5-168">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="896b5-169">[インシデント](manage-incidents.md#resolve-an-incident) を解決し、インシデント後の学習に時間を取って、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="896b5-169">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="896b5-170">攻撃の種類とその影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="896b5-170">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="896b5-171">[Threat Analytics](threat-analytics.md)とセキュリティ コミュニティの攻撃を調査して、セキュリティ攻撃の傾向を調査します。</span><span class="sxs-lookup"><span data-stu-id="896b5-171">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="896b5-172">インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフロー、プロセス、ポリシー、プレイブックを更新します。</span><span class="sxs-lookup"><span data-stu-id="896b5-172">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="896b5-173">セキュリティ構成の変更が必要かどうかを判断し、実装します。</span><span class="sxs-lookup"><span data-stu-id="896b5-173">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="896b5-174">セキュリティ分析を初めて使用する場合は、[](incidents-overview.md)最初のインシデントへの対応の概要を参照し、詳細については、「インシデントの例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="896b5-174">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="896b5-175">Defender のセキュリティ操作Microsoft 365例</span><span class="sxs-lookup"><span data-stu-id="896b5-175">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="896b5-176">Defender のセキュリティ操作の例をMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="896b5-176">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Defender のセキュリティ操作のMicrosoft 365例":::

<span data-ttu-id="896b5-178">毎日のタスクには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="896b5-178">Daily tasks can include:</span></span>

- <span data-ttu-id="896b5-179">[インシデントの](manage-incidents.md) 管理</span><span class="sxs-lookup"><span data-stu-id="896b5-179">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="896b5-180">アクション センター [での自動調査と応答 (AIR)](m365d-action-center.md) アクションの確認</span><span class="sxs-lookup"><span data-stu-id="896b5-180">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="896b5-181">最新の脅威分析 [の確認](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="896b5-181">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="896b5-182">[インシデントへの](investigate-incidents.md) 対応</span><span class="sxs-lookup"><span data-stu-id="896b5-182">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="896b5-183">毎月のタスクには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="896b5-183">Monthly tasks can include:</span></span>

- <span data-ttu-id="896b5-184">AIR 設定 [の確認](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="896b5-184">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="896b5-185">セキュリティで保護[されたスコアと](microsoft-secure-score-improvement-actions.md)[脅威の&の管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="896b5-185">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="896b5-186">IT セキュリティ管理チェーンへのレポート</span><span class="sxs-lookup"><span data-stu-id="896b5-186">Reporting to your IT security management chain</span></span>

<span data-ttu-id="896b5-187">四半期ごとに、最高情報セキュリティ責任者 (CISO) へのセキュリティ結果の報告とブリーフィングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="896b5-187">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="896b5-188">年次タスクには、スタッフ、システム、およびプロセスをテストする重大なインシデントや違反の演習を実行できます。</span><span class="sxs-lookup"><span data-stu-id="896b5-188">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="896b5-189">毎日、月次、四半期、年次のタスクを使用して、プロセス、ポリシー、およびセキュリティ構成を更新または調整できます。</span><span class="sxs-lookup"><span data-stu-id="896b5-189">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="896b5-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="896b5-190">Next steps</span></span>

<span data-ttu-id="896b5-191">**セキュリティ分析とインシデント** 対応に関する情報が必要な場合は、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="896b5-191">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="896b5-192">Microsoft 365[](first-incident-overview.md)セキュリティ センターの分析、修復、インシデント後の一般的なプロセスのガイド付きツアーについては、「最初のインシデントに対応する」のチュートリアルを参照してください。攻撃の例を示します。</span><span class="sxs-lookup"><span data-stu-id="896b5-192">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 security center with an example of an attack.</span></span>

<span data-ttu-id="896b5-193">**セキュリティ分析とインシデント** 対応に関する経験がある場合:</span><span class="sxs-lookup"><span data-stu-id="896b5-193">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="896b5-194">セキュリティ センターの [インシデント]ページからインシデント キュー Microsoft 365開始します。</span><span class="sxs-lookup"><span data-stu-id="896b5-194">Get started with the incident queue from the **Incidents** page of the Microsoft 365 security center.</span></span> <span data-ttu-id="896b5-195">ここから、以下の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="896b5-195">From here, you can:</span></span>

  - <span data-ttu-id="896b5-196">重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。</span><span class="sxs-lookup"><span data-stu-id="896b5-196">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="896b5-197">[インシデント管理ワークフローに](manage-incidents.md)基づいて、名前の変更、割り当て、分類、タグとコメントの追加を含むインシデントを管理します。</span><span class="sxs-lookup"><span data-stu-id="896b5-197">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="896b5-198">インシデント [の調査](investigate-incidents.md) を実行します。</span><span class="sxs-lookup"><span data-stu-id="896b5-198">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="896b5-199">フィッシング攻撃 [、パスワード スプレー攻撃](https://docs.microsoft.com/security/compass/incident-response-playbooks) 、アプリ同意許可攻撃の詳細なガイダンスについては、次のインシデント対応プレイブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="896b5-199">See these [incident response playbooks](https://docs.microsoft.com/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

