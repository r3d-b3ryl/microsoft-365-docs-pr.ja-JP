---
title: Microsoft 365 Defender でのインシデントの分析
description: デバイス、ユーザー、メールボックスに関連するインシデントを分析します。
keywords: インシデント、インシデント、分析、応答、コンピューター、デバイス、ユーザー、ID、メール、メール、メールボックス、調査、グラフ、証拠
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
ms.openlocfilehash: 22d3bba03745cee330f89b67061e6c6b13e78aed
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939744"
---
# <a name="analyze-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f67ba-104">Microsoft 365 Defender でのインシデントの分析</span><span class="sxs-lookup"><span data-stu-id="f67ba-104">Analyze incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f67ba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f67ba-105">**Applies to:**</span></span>

- <span data-ttu-id="f67ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f67ba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f67ba-107">Microsoft 365 Defender は、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="f67ba-108">インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を策定できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-analysis"></a><span data-ttu-id="f67ba-109">初期分析</span><span class="sxs-lookup"><span data-stu-id="f67ba-109">Initial analysis</span></span>

<span data-ttu-id="f67ba-110">詳細を確認する前に、インシデントのプロパティと概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f67ba-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="f67ba-111">まず、チェック マーク列からインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="f67ba-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="チェック マーク列からインシデントを選択する例":::

<span data-ttu-id="f67ba-114">その場合、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度、割り当て先、インシデントの[MITRE ATT&CK &trade; ](https://attack.mitre.org/)カテゴリなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="f67ba-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="インシデントの概要ウィンドウの例":::

<span data-ttu-id="f67ba-117">ここから、[インシデントページを開 **く] を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="f67ba-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="f67ba-118">これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、および証拠の概要情報とタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="f67ba-119">インシデント キューからインシデント名を選択して、インシデントのメイン ページを開く方法も指定できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="f67ba-120">概要</span><span class="sxs-lookup"><span data-stu-id="f67ba-120">Summary</span></span>

<span data-ttu-id="f67ba-121">[ **概要] ページ** では、インシデントに関する一番上の情報をスナップショットで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

<span data-ttu-id="f67ba-123">攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="f67ba-124">他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender は[MITRE ATT &trade; ](https://attack.mitre.org/)と CK フレームワーク&揃っています。</span><span class="sxs-lookup"><span data-stu-id="f67ba-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="f67ba-125">範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="f67ba-126">この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="f67ba-127">アラートのタイムラインでは、アラートが発生した時系列の順序と、これらのアラートがこのインシデントにリンクされている理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="f67ba-128">最後に、 - 証拠セクションには、インシデントに含まれるさまざまなアーティファクトの数とその修復状態の概要が示されています。そのため、必要なアクションが必要な場合は直ちに特定できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="f67ba-129">この概要は、インシデントの最初のトリアージを支援するために、注意する必要があるインシデントの最高の特性に関する洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="f67ba-130">アラート</span><span class="sxs-lookup"><span data-stu-id="f67ba-130">Alerts</span></span>

<span data-ttu-id="f67ba-131">[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報のアラート キューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="f67ba-132">重大度。</span><span class="sxs-lookup"><span data-stu-id="f67ba-132">Severity.</span></span>
- <span data-ttu-id="f67ba-133">アラートに関与したエンティティ。</span><span class="sxs-lookup"><span data-stu-id="f67ba-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="f67ba-134">アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="f67ba-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="f67ba-135">リンクされた理由。</span><span class="sxs-lookup"><span data-stu-id="f67ba-135">The reason they were linked together.</span></span>

<span data-ttu-id="f67ba-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="インシデントのアラート ページの例":::

<span data-ttu-id="f67ba-138">既定では、アラートは時系列的に順序付けされ、インシデントが時間の間にどのように再生されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="f67ba-139">各アラートを選択すると、アラートのメイン ページに移動し、アラートの詳細な分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="f67ba-140">アラートの分析でアラート キューとアラート ページを使用する方法 [について説明します。](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f67ba-140">Learn how to use the alert queue and alert pages in [analyze alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="f67ba-141">デバイス</span><span class="sxs-lookup"><span data-stu-id="f67ba-141">Devices</span></span>

<span data-ttu-id="f67ba-142">[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="f67ba-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="インシデントのデバイス ページの例":::

<span data-ttu-id="f67ba-145">デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="f67ba-146">デバイスの名前を選択すると、Microsoft Defender for Endpoints デバイス インベントリにデバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoints のデバイス ページの例":::

<span data-ttu-id="f67ba-148">デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="f67ba-149">たとえば、[タイムライン]タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="f67ba-150">デバイス ページでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="f67ba-151">Microsoft 365 セキュリティ センターで、[エンドポイント] > **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f67ba-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="f67ba-152">通知があるデバイスを選択し、ウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="f67ba-153">ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="f67ba-154">詳細については、「デバイスで [Microsoft Defender ウイルス対策スキャンを実行する」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="f67ba-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="f67ba-155">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f67ba-155">Users</span></span>

<span data-ttu-id="f67ba-156">[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="f67ba-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

<span data-ttu-id="f67ba-159">ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="f67ba-160">ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="f67ba-161">メールボックス</span><span class="sxs-lookup"><span data-stu-id="f67ba-161">Mailboxes</span></span>

<span data-ttu-id="f67ba-162">[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="f67ba-163">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="インシデントのメールボックス ページの例":::

<span data-ttu-id="f67ba-165">メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="f67ba-166">メールボックス名を選択すると、Microsoft Defender for microsoft Defender for microsoft Defender 365 の [エクスプローラー] ページに追加Office表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="f67ba-167">調査</span><span class="sxs-lookup"><span data-stu-id="f67ba-167">Investigations</span></span>

<span data-ttu-id="f67ba-168">[ **調査] タブ** には、このインシデントのアラートによってトリガーされる自動調査の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="f67ba-169">調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="インシデントの [調査] ページの例":::

<span data-ttu-id="f67ba-171">調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="f67ba-172">調査の一環として承認待ちアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="f67ba-173">証拠と対応</span><span class="sxs-lookup"><span data-stu-id="f67ba-173">Evidence and Response</span></span>

<span data-ttu-id="f67ba-174">[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="f67ba-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="インシデントの証拠と応答ページの例":::

<span data-ttu-id="f67ba-177">Microsoft 365 Defender は、インシデントがサポートしているすべてのイベントと、アラート内の不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f67ba-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="f67ba-178">これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="f67ba-179">分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="f67ba-180">これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="f67ba-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f67ba-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="f67ba-181">Related topics</span></span>

- [<span data-ttu-id="f67ba-182">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="f67ba-182">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f67ba-183">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="f67ba-183">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f67ba-184">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="f67ba-184">Manage incidents</span></span>](manage-incidents.md)

