---
title: Microsoft 365 Defender でのインシデントの優先順位付け
description: Microsoft 365 Defender のインシデント キューからインシデントをフィルター処理する方法について説明します。
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、メール、インシデント
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
ms.openlocfilehash: cd571414512ce876e730199b21bf755e4c4b733f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876201"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="fe781-104">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="fe781-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="fe781-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fe781-105">**Applies to:**</span></span>
- <span data-ttu-id="fe781-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe781-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fe781-107">Microsoft 365 Defender は、相関分析を適用し、関連するアラートと、さまざまな製品からの自動調査をインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="fe781-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="fe781-108">Microsoft 365 Defender は、製品スイート全体で Microsoft 365 Defender が持っているエンドツーエンドの可視性を考えると、悪意のあるアクティビティとしてのみ識別できるアクティビティに対する一意のアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="fe781-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="fe781-109">このビューは、セキュリティ アナリストに広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe781-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="fe781-110">インシデント **キューには、** デバイス、ユーザー、メールボックス間で作成されたインシデントのコレクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe781-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="fe781-111">これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="fe781-112">インシデント キューにアクセスするには、Microsoft 365 セキュリティ センター (& >) のクイック 起動時にインシデント に関する通知を[security.microsoft.com。](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="fe781-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="インシデント キューの例":::

<span data-ttu-id="fe781-114">既定では、Microsoft 365 セキュリティ センターのインシデント キューには、過去 6 か月間に発生したインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe781-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="fe781-115">最新のインシデントはリストの一番上にあるので、最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="fe781-116">インシデント キューには、インシデントの異なる特性や影響を受けたエンティティを表示できるカスタマイズ可能な列 ([列の選択] を選択) があります。</span><span class="sxs-lookup"><span data-stu-id="fe781-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="fe781-117">これにより、分析のためのインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe781-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="fe781-118">一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fe781-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="fe781-119">これにより、インシデントの範囲をすばやく理解できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="fe781-120">たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*</span><span class="sxs-lookup"><span data-stu-id="fe781-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="fe781-121">自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="fe781-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="fe781-122">インシデント キューでは、複数のフィルター オプションも公開されます。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。</span><span class="sxs-lookup"><span data-stu-id="fe781-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="fe781-123">インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="fe781-124">利用可能なフィルター</span><span class="sxs-lookup"><span data-stu-id="fe781-124">Available filters</span></span>

<span data-ttu-id="fe781-125">既定のインシデント キューから [フィルター] を **選択して** [フィルター] ウィンドウを表示し、そこからフィルター処理されたインシデントのセットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="fe781-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe781-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="インシデント キューのフィルター ウィンドウの例":::

<span data-ttu-id="fe781-128">次の表に、使用可能なフィルター名を示します。</span><span class="sxs-lookup"><span data-stu-id="fe781-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="fe781-129">フィルター名</span><span class="sxs-lookup"><span data-stu-id="fe781-129">Filter name</span></span> | <span data-ttu-id="fe781-130">説明</span><span class="sxs-lookup"><span data-stu-id="fe781-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="fe781-131">割り当て先</span><span class="sxs-lookup"><span data-stu-id="fe781-131">Assigned to</span></span> | <span data-ttu-id="fe781-132">自分に割り当てられているアラート、または自動化によって処理されたアラートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="fe781-133">Categories</span><span class="sxs-lookup"><span data-stu-id="fe781-133">Categories</span></span> | <span data-ttu-id="fe781-134">カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="fe781-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="fe781-135">分類</span><span class="sxs-lookup"><span data-stu-id="fe781-135">Classification</span></span> | <span data-ttu-id="fe781-136">関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fe781-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="fe781-137">値には、true アラート、false アラート、または設定されていないが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe781-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="fe781-138">データの機密性</span><span class="sxs-lookup"><span data-stu-id="fe781-138">Data sensitivity</span></span> | <span data-ttu-id="fe781-139">一部の攻撃では、機密データや貴重なデータを排除することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="fe781-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="fe781-140">機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fe781-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="fe781-141">Microsoft Information Protection が有効になっている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe781-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="fe781-142">デバイス グループ</span><span class="sxs-lookup"><span data-stu-id="fe781-142">Device group</span></span> | <span data-ttu-id="fe781-143">定義済みのデバイス グループでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fe781-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="fe781-144">調査の状態</span><span class="sxs-lookup"><span data-stu-id="fe781-144">Investigation state</span></span> | <span data-ttu-id="fe781-145">自動調査の状態によってインシデントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="fe781-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="fe781-146">複数のカテゴリ</span><span class="sxs-lookup"><span data-stu-id="fe781-146">Multiple categories</span></span> | <span data-ttu-id="fe781-147">複数のカテゴリにマップされたインシデントのみを表示し、より多くの損害を引き起こす可能性がある場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="fe781-148">複数のサービス ソース</span><span class="sxs-lookup"><span data-stu-id="fe781-148">Multiple service sources</span></span>  | <span data-ttu-id="fe781-149">フィルターを適用して、さまざまなソースからの通知を含むインシデントのみを表示します (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="fe781-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="fe781-150">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="fe781-150">OS platform</span></span> | <span data-ttu-id="fe781-151">オペレーティング システムによってインシデント キュー ビューを制限します。</span><span class="sxs-lookup"><span data-stu-id="fe781-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="fe781-152">サービス ソース</span><span class="sxs-lookup"><span data-stu-id="fe781-152">Service sources</span></span> | <span data-ttu-id="fe781-153">特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fe781-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="fe781-154">重要度</span><span class="sxs-lookup"><span data-stu-id="fe781-154">Severity</span></span> | <span data-ttu-id="fe781-155">インシデントの重大度は、資産に与える影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe781-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="fe781-156">重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="fe781-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="fe781-157">状態</span><span class="sxs-lookup"><span data-stu-id="fe781-157">Status</span></span> | <span data-ttu-id="fe781-158">状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe781-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="fe781-159">インシデント対応ワークフロー</span><span class="sxs-lookup"><span data-stu-id="fe781-159">Incident response workflow</span></span>

<span data-ttu-id="fe781-160">インシデントに対応する一般的なワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe781-160">Here's the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="fe781-161">調査と解決に最も優先度の高いインシデントを特定し、トリアージします。</span><span class="sxs-lookup"><span data-stu-id="fe781-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="fe781-162">優先度の高いインシデントごとに、調査を開始 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="fe781-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="fe781-163">a.</span><span class="sxs-lookup"><span data-stu-id="fe781-163">a.</span></span> <span data-ttu-id="fe781-164">インシデントの概要を表示して、インシデントの範囲と重大度、および影響を受けるエンティティ ([概要] タブ) **を理解** します。</span><span class="sxs-lookup"><span data-stu-id="fe781-164">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="fe781-165">b.</span><span class="sxs-lookup"><span data-stu-id="fe781-165">b.</span></span> <span data-ttu-id="fe781-166">アラートを見て、発生元、スコープ、重大度 ([アラート] タブ) を **理解** します。</span><span class="sxs-lookup"><span data-stu-id="fe781-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="fe781-167">c.</span><span class="sxs-lookup"><span data-stu-id="fe781-167">c.</span></span> <span data-ttu-id="fe781-168">必要に応じて、影響を受け取ったデバイス、ユーザー、およびメールボックス([デバイス]、[ユーザー]、および [メールボックス] タブ) に関する **情報を収集** します。</span><span class="sxs-lookup"><span data-stu-id="fe781-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="fe781-169">d. </span><span class="sxs-lookup"><span data-stu-id="fe781-169">d.</span></span> <span data-ttu-id="fe781-170">Microsoft 365 Defender が一部のアラートを自動的に解決した方法 ([調査] タブ) **を参照** してください。</span><span class="sxs-lookup"><span data-stu-id="fe781-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="fe781-171">e. </span><span class="sxs-lookup"><span data-stu-id="fe781-171">e.</span></span> <span data-ttu-id="fe781-172">必要に応じて、インシデントのデータ セットの情報を使用して詳細を確認します ([証拠と応答] **タブ** )。</span><span class="sxs-lookup"><span data-stu-id="fe781-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

   <span data-ttu-id="fe781-173">調査を行う場合は、次の事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe781-173">As you investigate, you should be concerned with:</span></span>

   - <span data-ttu-id="fe781-174">格納: テナントへの追加の影響を軽減します。</span><span class="sxs-lookup"><span data-stu-id="fe781-174">Containment: Reducing any additional impact on your tenant.</span></span>
   - <span data-ttu-id="fe781-175">根絶: セキュリティの脅威を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe781-175">Eradication: Removing the security threat.</span></span>
   - <span data-ttu-id="fe781-176">回復: 攻撃前の状態にテナント リソースを復元します。</span><span class="sxs-lookup"><span data-stu-id="fe781-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

3. <span data-ttu-id="fe781-177">インシデントを解決した後、時間を取って次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe781-177">After you resolve the incident, take the time to:</span></span>

   - <span data-ttu-id="fe781-178">攻撃の種類とその影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="fe781-178">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="fe781-179">セキュリティコミュニティの攻撃を調査して、セキュリティ攻撃の傾向を調査します。</span><span class="sxs-lookup"><span data-stu-id="fe781-179">Research the attack in the security community for a security attack trend.</span></span>
   - <span data-ttu-id="fe781-180">インシデントの解決に使用したワークフローを思い出し、必要に応じて標準のワークフローとプレイブックを更新します。</span><span class="sxs-lookup"><span data-stu-id="fe781-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>
   - <span data-ttu-id="fe781-181">セキュリティ態勢の変更が必要かどうかを判断し、それらを実装するための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe781-181">Determine whether changes in your security posture are needed and take the steps to implement them.</span></span>

<span data-ttu-id="fe781-182">基本的なプロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe781-182">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="インシデントを調査する基本的なプロセス":::

## <a name="next-step"></a><span data-ttu-id="fe781-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="fe781-184">Next step</span></span>

<span data-ttu-id="fe781-185">優先度が最も高いインシデントを決定した後、それを選択して調査を開始 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="fe781-185">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe781-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe781-186">See also</span></span>
- [<span data-ttu-id="fe781-187">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="fe781-187">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fe781-188">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="fe781-188">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="fe781-189">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="fe781-189">Manage incidents</span></span>](manage-incidents.md)
