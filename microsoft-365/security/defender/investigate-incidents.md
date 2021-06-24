---
title: インシデントを調査Microsoft 365 Defender
description: デバイス、ユーザー、メールボックスに関連するインシデントを調査します。
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105358"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="b5f26-104">インシデントを調査Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f26-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b5f26-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b5f26-105">**Applies to:**</span></span>

- <span data-ttu-id="b5f26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5f26-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b5f26-107">Microsoft 365 Defender、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="b5f26-108">インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を策定できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="b5f26-109">初期調査</span><span class="sxs-lookup"><span data-stu-id="b5f26-109">Initial investigation</span></span>

<span data-ttu-id="b5f26-110">詳細を確認する前に、インシデントのプロパティと概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b5f26-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="b5f26-111">まず、チェック マーク列からインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="b5f26-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="チェック マーク列からインシデントを選択する例":::

<span data-ttu-id="b5f26-114">その場合、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度、割り当て先、インシデントの[MITRE ATT&CK &trade; ](https://attack.mitre.org/)カテゴリなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="b5f26-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="インシデントの概要ウィンドウの例":::

<span data-ttu-id="b5f26-117">ここから、[インシデントページを開 **く] を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="b5f26-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="b5f26-118">これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、および証拠の概要情報とタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="b5f26-119">インシデント キューからインシデント名を選択して、インシデントのメイン ページを開く方法も指定できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="b5f26-120">概要</span><span class="sxs-lookup"><span data-stu-id="b5f26-120">Summary</span></span>

<span data-ttu-id="b5f26-121">[ **概要] ページ** では、インシデントに関する一番上の情報をスナップショットで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="セキュリティ センターのインシデントの概要ページMicrosoft 365例":::

<span data-ttu-id="b5f26-123">攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="b5f26-124">他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender CK フレームワークの[MITRE ATT &trade;&配置](https://attack.mitre.org/)されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="b5f26-125">範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="b5f26-126">この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="b5f26-127">アラートのタイムラインでは、アラートが発生した時系列の順序と、これらのアラートがこのインシデントにリンクされている理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="b5f26-128">最後に、 - 証拠セクションには、インシデントに含まれるさまざまなアーティファクトの数とその修復状態の概要が示されています。そのため、必要なアクションが必要な場合は直ちに特定できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="b5f26-129">この概要は、インシデントの最初のトリアージを支援するために、注意する必要があるインシデントの最高の特性に関する洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="b5f26-130">アラート</span><span class="sxs-lookup"><span data-stu-id="b5f26-130">Alerts</span></span>

<span data-ttu-id="b5f26-131">[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報のアラート キューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="b5f26-132">重大度。</span><span class="sxs-lookup"><span data-stu-id="b5f26-132">Severity.</span></span>
- <span data-ttu-id="b5f26-133">アラートに関与したエンティティ。</span><span class="sxs-lookup"><span data-stu-id="b5f26-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="b5f26-134">アラートのソース (Microsoft Defender for Identity、 Microsoft Defender for Endpoint、 Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="b5f26-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="b5f26-135">リンクされた理由。</span><span class="sxs-lookup"><span data-stu-id="b5f26-135">The reason they were linked together.</span></span>

<span data-ttu-id="b5f26-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="インシデントのアラート ページの例":::

<span data-ttu-id="b5f26-138">既定では、アラートは時系列的に順序付けされ、インシデントが時間の間にどのように再生されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="b5f26-139">インシデント内でアラートを選択すると、Microsoft 365 Defenderのコンテキストに固有のアラート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="b5f26-140">アラートのイベント、その他のトリガーされたアラートによって現在のアラートが発生したイベント、およびファイル、ユーザー、メールボックスなど、攻撃に関連する影響を受けるすべてのエンティティとアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="b5f26-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="インシデント内のアラートの詳細ページの例":::

<span data-ttu-id="b5f26-143">このインシデント アラート ページは、次のセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="b5f26-144">アラート ストーリー(発生した内容の概要を含む)</span><span class="sxs-lookup"><span data-stu-id="b5f26-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="b5f26-145">関連するイベントとアラート</span><span class="sxs-lookup"><span data-stu-id="b5f26-145">Related events and alerts</span></span>
- <span data-ttu-id="b5f26-146">概要の詳細</span><span class="sxs-lookup"><span data-stu-id="b5f26-146">Summary details</span></span>

<span data-ttu-id="b5f26-147">アラートの調査でアラート キューとアラート ページを使用する方法 [について説明します](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f26-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="b5f26-148">デバイス</span><span class="sxs-lookup"><span data-stu-id="b5f26-148">Devices</span></span>

<span data-ttu-id="b5f26-149">[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="b5f26-150">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="インシデントのデバイス ページの例":::

<span data-ttu-id="b5f26-152">デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="b5f26-153">デバイスの名前を選択すると、Microsoft Defender for Endpoints デバイス インベントリにデバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoints のデバイス ページの例":::

<span data-ttu-id="b5f26-155">デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="b5f26-156">たとえば、[タイムライン]タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="b5f26-157">デバイス ページでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="b5f26-158">セキュリティ センターでMicrosoft 365デバイス インベントリの **[エンドポイント] >を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5f26-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="b5f26-159">通知があるデバイスを選択し、ウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="b5f26-160">ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="b5f26-161">詳細については、「デバイスでスキャン[を実行Microsoft Defender ウイルス対策」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="b5f26-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="b5f26-162">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b5f26-162">Users</span></span>

<span data-ttu-id="b5f26-163">[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="b5f26-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

<span data-ttu-id="b5f26-166">ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="b5f26-167">ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="b5f26-168">ユーザーの調査で追加のユーザー情報を表示し、インシデントのユーザーを管理する方法 [について学習します](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f26-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="b5f26-169">メールボックス</span><span class="sxs-lookup"><span data-stu-id="b5f26-169">Mailboxes</span></span>

<span data-ttu-id="b5f26-170">[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="b5f26-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="インシデントのメールボックス ページの例":::

<span data-ttu-id="b5f26-173">メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="b5f26-174">メールボックス名を選択すると、Microsoft Defender for microsoft Defender の [エクスプローラー] ページに追加のメールボックスの詳細が表示Office 365。</span><span class="sxs-lookup"><span data-stu-id="b5f26-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="b5f26-175">調査</span><span class="sxs-lookup"><span data-stu-id="b5f26-175">Investigations</span></span>

<span data-ttu-id="b5f26-176">[ **調査] タブ** には、このインシデントのアラート [によって](m365d-autoir.md) トリガーされる自動調査の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="b5f26-177">調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="インシデントの [調査] ページの例":::

<span data-ttu-id="b5f26-179">調査を選択して詳細ページに移動し、調査と修復の状態に関する完全な情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-179">Select an investigation to navigate to its details page for full information on the investigation and remediation status.</span></span> <span data-ttu-id="b5f26-180">調査の一環として承認待ちアクションがある場合は、[保留中のアクションの履歴] **タブに表示** されます。インシデント修復の一環としてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-180">If there are any actions pending for approval as part of the investigation, they will appear in the **Pending actions history** tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="b5f26-181">[調査] グラフ タブ **には、次** の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-181">There is also an **Investigation graph** tab that shows:</span></span>

- <span data-ttu-id="b5f26-182">組織内の影響を受け取ったアセットへのアラートの接続。</span><span class="sxs-lookup"><span data-stu-id="b5f26-182">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="b5f26-183">どのエンティティが、どのアラートに関連付け、どのエンティティが攻撃のストーリーの一部であるのか。</span><span class="sxs-lookup"><span data-stu-id="b5f26-183">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="b5f26-184">インシデントのアラート。</span><span class="sxs-lookup"><span data-stu-id="b5f26-184">The alerts for the incident.</span></span>

<span data-ttu-id="b5f26-185">調査グラフを使用すると、攻撃の一部であるさまざまな不審なエンティティと、ユーザー、デバイス、メールボックスなどの関連する資産を接続することで、攻撃の全範囲をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-185">The investigation graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="b5f26-186">詳細については、「自動調査と応答[」](m365d-autoir.md)を参照Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="b5f26-186">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="b5f26-187">証拠と対応</span><span class="sxs-lookup"><span data-stu-id="b5f26-187">Evidence and Response</span></span>

<span data-ttu-id="b5f26-188">[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-188">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="b5f26-189">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-189">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="インシデントの証拠と応答ページの例":::

<span data-ttu-id="b5f26-191">Microsoft 365 Defenderアラート内のすべてのインシデントでサポートされているイベントと不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5f26-191">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="b5f26-192">これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-192">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="b5f26-193">分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-193">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="b5f26-194">これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="b5f26-194">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5f26-195">次の手順</span><span class="sxs-lookup"><span data-stu-id="b5f26-195">Next steps</span></span>

<span data-ttu-id="b5f26-196">必要に応じて、</span><span class="sxs-lookup"><span data-stu-id="b5f26-196">As needed:</span></span>

- [<span data-ttu-id="b5f26-197">インシデントのアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="b5f26-197">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="b5f26-198">インシデントのユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="b5f26-198">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="b5f26-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5f26-199">See also</span></span>

- [<span data-ttu-id="b5f26-200">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="b5f26-200">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b5f26-201">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="b5f26-201">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b5f26-202">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="b5f26-202">Manage incidents</span></span>](manage-incidents.md)

