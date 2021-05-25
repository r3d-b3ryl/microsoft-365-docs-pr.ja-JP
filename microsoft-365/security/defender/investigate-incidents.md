---
title: Defender でインシデントをMicrosoft 365する
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 865aa9dc34a91be251d6f7772da5cc686f9641a4
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651317"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="2bcde-104">Defender でインシデントをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="2bcde-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2bcde-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2bcde-105">**Applies to:**</span></span>

- <span data-ttu-id="2bcde-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bcde-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2bcde-107">Microsoft 365Defender は、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠をインシデントに集約し、攻撃の幅広い全体を総合的に調査します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="2bcde-108">インシデント内では、ネットワークに影響を与えるアラートを分析し、その意味を理解し、証拠を照合して、効果的な修復計画を策定できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="2bcde-109">初期調査</span><span class="sxs-lookup"><span data-stu-id="2bcde-109">Initial investigation</span></span>

<span data-ttu-id="2bcde-110">詳細を確認する前に、インシデントのプロパティと概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bcde-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="2bcde-111">まず、チェック マーク列からインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="2bcde-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="チェック マーク列からインシデントを選択する例":::

<span data-ttu-id="2bcde-114">その場合、概要ウィンドウが開き、インシデントに関する重要な情報 (重大度、割り当て先、インシデントの[MITRE ATT&CK &trade; ](https://attack.mitre.org/)カテゴリなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="2bcde-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="インシデントの概要ウィンドウの例":::

<span data-ttu-id="2bcde-117">ここから、[インシデントページを開 **く] を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="2bcde-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="2bcde-118">これにより、インシデントのメイン ページが開き、アラート、デバイス、ユーザー、調査、および証拠の概要情報とタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="2bcde-119">インシデント キューからインシデント名を選択して、インシデントのメイン ページを開く方法も指定できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="2bcde-120">概要</span><span class="sxs-lookup"><span data-stu-id="2bcde-120">Summary</span></span>

<span data-ttu-id="2bcde-121">[ **概要] ページ** では、インシデントに関する一番上の情報をスナップショットで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="セキュリティ センターのインシデントの概要ページMicrosoft 365例":::

<span data-ttu-id="2bcde-123">攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="2bcde-124">他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender は CK フレームワークの[MITRE ATT &trade;&揃](https://attack.mitre.org/)っています。</span><span class="sxs-lookup"><span data-stu-id="2bcde-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="2bcde-125">範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="2bcde-126">この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="2bcde-127">アラートのタイムラインでは、アラートが発生した時系列の順序と、これらのアラートがこのインシデントにリンクされている理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="2bcde-128">最後に、 - 証拠セクションには、インシデントに含まれるさまざまなアーティファクトの数とその修復状態の概要が示されています。そのため、必要なアクションが必要な場合は直ちに特定できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="2bcde-129">この概要は、インシデントの最初のトリアージを支援するために、注意する必要があるインシデントの最高の特性に関する洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="2bcde-130">アラート</span><span class="sxs-lookup"><span data-stu-id="2bcde-130">Alerts</span></span>

<span data-ttu-id="2bcde-131">[アラート **] タブ** で、インシデントに関連するアラートや、次のようなアラートに関するその他の情報のアラート キューを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="2bcde-132">重大度。</span><span class="sxs-lookup"><span data-stu-id="2bcde-132">Severity.</span></span>
- <span data-ttu-id="2bcde-133">アラートに関与したエンティティ。</span><span class="sxs-lookup"><span data-stu-id="2bcde-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="2bcde-134">アラートのソース (Microsoft Defender for Identity、 Microsoft Defender for Endpoint、 Microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="2bcde-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="2bcde-135">リンクされた理由。</span><span class="sxs-lookup"><span data-stu-id="2bcde-135">The reason they were linked together.</span></span>

<span data-ttu-id="2bcde-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="インシデントのアラート ページの例":::

<span data-ttu-id="2bcde-138">既定では、アラートは時系列的に順序付けされ、インシデントが時間の間にどのように再生されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="2bcde-139">インシデント内でアラートを選択すると、Microsoft 365のコンテキストに固有のアラート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="2bcde-140">アラートのイベント、その他のトリガーされたアラートによって現在のアラートが発生したイベント、およびファイル、ユーザー、メールボックスなど、攻撃に関連する影響を受けるすべてのエンティティとアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="2bcde-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="インシデント内のアラートの詳細ページの例":::

<span data-ttu-id="2bcde-143">このインシデント アラート ページは、次のセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="2bcde-144">アラート ストーリー(発生した内容の概要を含む)</span><span class="sxs-lookup"><span data-stu-id="2bcde-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="2bcde-145">関連するイベントとアラート</span><span class="sxs-lookup"><span data-stu-id="2bcde-145">Related events and alerts</span></span>
- <span data-ttu-id="2bcde-146">概要の詳細</span><span class="sxs-lookup"><span data-stu-id="2bcde-146">Summary details</span></span>

<span data-ttu-id="2bcde-147">アラートの調査でアラート キューとアラート ページを使用する方法 [について説明します](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="2bcde-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="2bcde-148">デバイス</span><span class="sxs-lookup"><span data-stu-id="2bcde-148">Devices</span></span>

<span data-ttu-id="2bcde-149">[ **デバイス]** タブには、インシデントに関連付けたすべてのデバイスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="2bcde-150">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="インシデントのデバイス ページの例":::

<span data-ttu-id="2bcde-152">デバイスのチェック マークを選択すると、デバイス、ディレクトリ データ、アクティブなアラート、ログオンしているユーザーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="2bcde-153">デバイスの名前を選択すると、Microsoft Defender for Endpoints デバイス インベントリにデバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Microsoft Defender for Endpoints のデバイス ページの例":::

<span data-ttu-id="2bcde-155">デバイス ページから、すべての通知、タイムライン、セキュリティに関する推奨事項など、デバイスに関する追加情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="2bcde-156">たとえば、[タイムライン]タブから、コンピューターのタイムラインをスクロールして、発生したアラートと一緒に、コンピューター上で観察されたイベントと動作を時系列順に表示できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="2bcde-157">デバイス ページでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="2bcde-158">セキュリティ センターでMicrosoft 365デバイス インベントリの **[エンドポイント] >を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2bcde-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="2bcde-159">通知があるデバイスを選択し、ウイルス対策スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="2bcde-160">ウイルス対策スキャンなどのアクションは追跡され、[デバイス インベントリ] ページ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="2bcde-161">詳細については、「デバイスでスキャン[を実行Microsoft Defender ウイルス対策」を参照してください](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="2bcde-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="2bcde-162">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2bcde-162">Users</span></span>

<span data-ttu-id="2bcde-163">[ **ユーザー]** タブには、インシデントの一部または関連付けとして識別されたすべてのユーザーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="2bcde-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="インシデントの [ユーザー] ページの例":::

<span data-ttu-id="2bcde-166">ユーザーのチェック マークを選択すると、ユーザー アカウントの脅威、露出、連絡先情報の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="2bcde-167">ユーザー名を選択すると、追加のユーザー アカウントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="2bcde-168">ユーザーの調査で追加のユーザー情報を表示し、インシデントのユーザーを管理する方法 [について学習します](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="2bcde-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="2bcde-169">メールボックス</span><span class="sxs-lookup"><span data-stu-id="2bcde-169">Mailboxes</span></span>

<span data-ttu-id="2bcde-170">[ **メールボックス] タブ** には、インシデントの一部または関連付けとして識別されたすべてのメールボックスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="2bcde-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="インシデントのメールボックス ページの例":::

<span data-ttu-id="2bcde-173">メールボックスのチェック マークを選択すると、アクティブなアラートの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="2bcde-174">メールボックス名を選択すると、Microsoft Defender for microsoft Defender の [エクスプローラー] ページに追加のメールボックスの詳細が表示Office 365。</span><span class="sxs-lookup"><span data-stu-id="2bcde-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="2bcde-175">調査</span><span class="sxs-lookup"><span data-stu-id="2bcde-175">Investigations</span></span>

<span data-ttu-id="2bcde-176">[ **調査] タブ** には、このインシデントのアラート [によって](m365d-autoir.md) トリガーされる自動調査の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="2bcde-177">調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="インシデントの [調査] ページの例":::

<span data-ttu-id="2bcde-179">調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-179">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="2bcde-180">調査の一環として承認待ちアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-180">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="2bcde-181">詳細については、「Defender の自動調査と対応」[をMicrosoft 365してください](m365d-autoir.md)。</span><span class="sxs-lookup"><span data-stu-id="2bcde-181">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="2bcde-182">証拠と対応</span><span class="sxs-lookup"><span data-stu-id="2bcde-182">Evidence and Response</span></span>

<span data-ttu-id="2bcde-183">[ **証拠と応答] タブ** には、インシデント内のアラートでサポートされているイベントと疑わしいエンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-183">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="2bcde-184">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-184">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="インシデントの証拠と応答ページの例":::

<span data-ttu-id="2bcde-186">Microsoft 365Defender は、アラート内のすべてのインシデントでサポートされているイベントと不審なエンティティを自動的に調査し、重要な電子メール、ファイル、プロセス、サービス、IP アドレスなどの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-186">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="2bcde-187">これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-187">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="2bcde-188">分析された各エンティティには、評決 (悪意のある、疑わしい、クリーン) と修復状態がマークされます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-188">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="2bcde-189">これにより、インシデント全体の修復状態と、次に実行できる手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-189">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="2bcde-190">Graph (プレビューで)</span><span class="sxs-lookup"><span data-stu-id="2bcde-190">Graph (in preview)</span></span>

<span data-ttu-id="2bcde-191">新しい **[Graph]** タブ (プレビュー) を使用すると、次の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-191">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="2bcde-192">組織内の影響を受け取ったアセットへのアラートの接続。</span><span class="sxs-lookup"><span data-stu-id="2bcde-192">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="2bcde-193">どのエンティティが、どのアラートに関連付け、どのエンティティが攻撃のストーリーの一部であるのか。</span><span class="sxs-lookup"><span data-stu-id="2bcde-193">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="2bcde-194">インシデントのアラート。</span><span class="sxs-lookup"><span data-stu-id="2bcde-194">The alerts for the incident.</span></span>

<span data-ttu-id="2bcde-195">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bcde-195">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="インシデントのGraphページの例":::

<span data-ttu-id="2bcde-197">インシデント グラフを使用すると、攻撃の一部であるさまざまな不審なエンティティを、ユーザー、デバイス、メールボックスなどの関連資産と接続することで、攻撃の範囲全体をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-197">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="2bcde-198">これで、攻撃がネットワークを通じて時間の間にどのように広がったか、どこから始まったのか、攻撃がどこまで行ったのか理解できます。</span><span class="sxs-lookup"><span data-stu-id="2bcde-198">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2bcde-199">次の手順</span><span class="sxs-lookup"><span data-stu-id="2bcde-199">Next steps</span></span>

<span data-ttu-id="2bcde-200">必要に応じて、</span><span class="sxs-lookup"><span data-stu-id="2bcde-200">As needed:</span></span>

- [<span data-ttu-id="2bcde-201">インシデントのアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="2bcde-201">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="2bcde-202">インシデントのユーザーを調査する</span><span class="sxs-lookup"><span data-stu-id="2bcde-202">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="2bcde-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bcde-203">See also</span></span>

- [<span data-ttu-id="2bcde-204">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="2bcde-204">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2bcde-205">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="2bcde-205">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="2bcde-206">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="2bcde-206">Manage incidents</span></span>](manage-incidents.md)

