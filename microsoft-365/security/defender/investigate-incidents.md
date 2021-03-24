---
title: Microsoft 365 Defender のインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを分析します。
keywords: インシデント、コンピューター、デバイス、ユーザー、ID、メール、電子メール、メールボックス、調査、グラフ、証拠
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 10fa2765a4fe5bd256e0588af0db51f5a22339a2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062012"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="45e46-104">Microsoft 365 Defender のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="45e46-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45e46-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45e46-105">**Applies to:**</span></span>

- <span data-ttu-id="45e46-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45e46-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="45e46-107">Microsoft 365 Defender は、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠を集計し、攻撃の幅広い全体を総合的に調査します。</span><span class="sxs-lookup"><span data-stu-id="45e46-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="45e46-108">効果的な修復計画を考案できるようにするために、ネットワークに影響するアラートを調査し、その意味を理解し、インシデントに関連する証拠を照合します。</span><span class="sxs-lookup"><span data-stu-id="45e46-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="45e46-109">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="45e46-109">Investigate an incident</span></span>

1. <span data-ttu-id="45e46-110">インシデント キューからインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="45e46-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="45e46-111">サイド パネルが開き、ステータス、重大度、カテゴリ、影響を受け取ったエンティティなどの重要な情報のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![インシデント サイドパネルの画像](../../media/incident-side-panel.png)

2. <span data-ttu-id="45e46-113">[**インシデント ページを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45e46-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="45e46-114">インシデント ページが開き、インシデントの詳細、コメント、アクション、タブ (概要、アラート、デバイス、ユーザー、調査、証拠) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="45e46-115">インシデントに関連するアラート、デバイス、ユーザー、その他のエンティティを確認します。</span><span class="sxs-lookup"><span data-stu-id="45e46-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="45e46-116">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="45e46-116">Incident overview</span></span>

<span data-ttu-id="45e46-117">概要ページでは、インシデントに関する主な情報がスナップショットで表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![インシデントの概要ページの画像](../../media/incidents-overview.png)

<span data-ttu-id="45e46-119">攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="45e46-120">他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender は[MITRE ATT &trade; ](https://attack.mitre.org/)と CK フレームワーク&揃っています。</span><span class="sxs-lookup"><span data-stu-id="45e46-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="45e46-121">範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="45e46-122">この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="45e46-123">アラートのタイムラインでは、アラートの発生順に時系列でプレビューすることができ、これらのアラートがインシデントに関連付けられた理由も表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="45e46-124">最後に、証拠セクションでは、どれぐらいの数の成果物がインシデントに含まれるかや修復状況の概要が示されます。そのため、対応が必要かどうかをすぐに特定できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="45e46-125">この概要は、注意が必要なインシデントの特徴の洞察を提供することで、インシデントの初回トリアージに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="45e46-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="45e46-126">アラート</span><span class="sxs-lookup"><span data-stu-id="45e46-126">Alerts</span></span>

<span data-ttu-id="45e46-127">インシデントに関連するすべてのアラートと、重大度、アラートに関連したエンティティ、アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365)、および関連付けされた理由など、インシデントに関連するその他の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![インシデント アラート ページの画像](../../media/incident-alerts.png)

<span data-ttu-id="45e46-129">既定では、アラートは発生順に並べ替えられています。これにより、発生した攻撃を時系列で確認できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="45e46-130">各アラートをクリックすると、関連するアラート ページに移動し、そのアラートの詳細な調査を実行できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="45e46-131">アラート の調査でアラート ページと統合アラート キューを使用する方法 [について説明します。](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="45e46-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="45e46-132">デバイス</span><span class="sxs-lookup"><span data-stu-id="45e46-132">Devices</span></span>

<span data-ttu-id="45e46-133">[デバイス] タブには、インシデントに関連するアラートが表示されているすべてのデバイスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="45e46-134">攻撃が行われたコンピューターの名前をクリックすると、そのコンピューターのページが表示されます。調査を簡単にするために、トリガーされたアラートや関連イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![インシデントの [コンピューター] タブの画像](../../media/incident-machines.png)

<span data-ttu-id="45e46-136">[タイムライン] タブを選択すると、コンピューターのタイムラインをスクロールして、コンピューター上で監視されているすべてのイベントおよび動作、発生したアラートを日付順に表示できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="45e46-137">ユーザー</span><span class="sxs-lookup"><span data-stu-id="45e46-137">Users</span></span>

<span data-ttu-id="45e46-138">特定のインシデントに関連すると識別されたユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="45e46-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="45e46-139">ユーザー名をクリックすると、ユーザーの Cloud App Security ページに移動します。ここで詳細な調査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="45e46-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![インシデントの [ユーザー] タブの画像](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="45e46-141">メールボックス</span><span class="sxs-lookup"><span data-stu-id="45e46-141">Mailboxes</span></span>

<span data-ttu-id="45e46-142">インシデントに関連すると識別されたメールボックスを調査します。</span><span class="sxs-lookup"><span data-stu-id="45e46-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="45e46-143">さらに調査作業を行うには、メール関連のアラートを選択すると、Microsoft Defender for Office 365 が開き、修復アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="45e46-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![インシデントの [メールボックス] タブの画像](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="45e46-145">調査</span><span class="sxs-lookup"><span data-stu-id="45e46-145">Investigations</span></span>

<span data-ttu-id="45e46-146">[ **調査] を** 選択して、このインシデントのアラートによってトリガーされる自動調査を表示します。</span><span class="sxs-lookup"><span data-stu-id="45e46-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="45e46-147">調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。</span><span class="sxs-lookup"><span data-stu-id="45e46-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![インシデントの [調査] タブの画像](../../media/incident-investigations.png)

<span data-ttu-id="45e46-149">調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="45e46-150">調査の一環として承認待ちアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="45e46-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="45e46-151">証拠</span><span class="sxs-lookup"><span data-stu-id="45e46-151">Evidence</span></span>

<span data-ttu-id="45e46-152">Microsoft 365 Defender は、インシデントがサポートしているすべてのイベントと不審なエンティティを自動的にアラートで調査し、自動応答と重要なファイル、プロセス、サービス、電子メールなどの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45e46-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="45e46-153">これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="45e46-153">This helps quickly detect and block potential threats in the incident.</span></span>

![インシデントの [証拠] タブの画像](../../media/incident-evidence.png)

<span data-ttu-id="45e46-155">分析された各エンティティには、判定 (悪質、不審、クリーン)、および修復状況が示されます。</span><span class="sxs-lookup"><span data-stu-id="45e46-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="45e46-156">これにより、インシデント全体の修復状況、および修復の次の手順について理解するのをサポートします。</span><span class="sxs-lookup"><span data-stu-id="45e46-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="45e46-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="45e46-157">Related topics</span></span>

- [<span data-ttu-id="45e46-158">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="45e46-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="45e46-159">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="45e46-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="45e46-160">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="45e46-160">Manage incidents</span></span>](manage-incidents.md)

