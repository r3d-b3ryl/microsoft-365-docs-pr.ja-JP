---
title: Microsoft Threat Protection のインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを分析します。
keywords: インシデント、コンピューター、デバイス、ユーザー、ID、メール、電子メール、メールボックス、調査、グラフ、証拠
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 869c97e32639f4553e49b99069c4bfd180e09f46
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808652"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="c87fc-104">Microsoft Threat Protection のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="c87fc-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="c87fc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c87fc-105">**Applies to:**</span></span>
- <span data-ttu-id="c87fc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c87fc-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="c87fc-107">Microsoft Threat Protection は、すべてのデバイス、ユーザー、およびメールボックスを対象に、関連するすべてのアラート、資産、調査、エビデンスを集計して、あらゆる攻撃を総合的に把握できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c87fc-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span> 

<span data-ttu-id="c87fc-108">効果的な修復計画を考案できるようにするために、ネットワークに影響するアラートを調査し、その意味を理解し、インシデントに関連する証拠を照合します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span> 

## <a name="investigate-an-incident"></a><span data-ttu-id="c87fc-109">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="c87fc-109">Investigate an incident</span></span>

1. <span data-ttu-id="c87fc-110">インシデント キューからインシデントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="c87fc-111">これにより、サイドパネルが開き、状態、重要度、カテゴリ、影響を受けるエンティティなどの重要な情報のプレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![インシデント サイドパネルの画像](../images/incident-side-panel.png)

2. <span data-ttu-id="c87fc-113">[**インシデント ページを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="c87fc-114">これにより、インシデント ページが開き、インシデントの詳細、コメントとアクション、タブ (概要、アラート、デバイス、ユーザー、調査、証拠) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="c87fc-115">インシデントに関連するアラート、デバイス、ユーザー、その他のエンティティを確認します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="c87fc-116">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="c87fc-116">Incident overview</span></span> 
<span data-ttu-id="c87fc-117">概要ページでは、インシデントに関する主な情報がスナップショットで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>


![インシデントの概要ページの画像](../images/incidents-overview.png)


<span data-ttu-id="c87fc-119">攻撃のカテゴリでは、キルチェーンに対する攻撃の状況を視覚的に、そして数値で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="c87fc-120">他の Microsoft セキュリティ製品と同様に、Microsoft Threat Protection は、[MITRE ATT&CK&trade;](https://attack.mitre.org/) フレームワークに準拠します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span> 

<span data-ttu-id="c87fc-121">範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="c87fc-122">この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="c87fc-123">アラートのタイムラインでは、アラートの発生順に時系列でプレビューすることができ、これらのアラートがインシデントに関連付けられた理由も表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="c87fc-124">最後に、証拠セクションでは、どれぐらいの数の成果物がインシデントに含まれるかや修復状況の概要が示されます。そのため、対応が必要かどうかをすぐに特定できます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span> 

<span data-ttu-id="c87fc-125">この概要は、注意が必要なインシデントの特徴の洞察を提供することで、インシデントの初回トリアージに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span> 


## <a name="alerts"></a><span data-ttu-id="c87fc-126">アラート</span><span class="sxs-lookup"><span data-stu-id="c87fc-126">Alerts</span></span> 
<span data-ttu-id="c87fc-127">インシデントに関連するすべてのアラートを表示することができます。重要度、アラートに関係したエンティティ、アラートのソース (Azure ATP、Microsoft Defender ATP、Office 365 ATP)、およびそれらのアラートが相互にリンクされた理由などの情報も確認できます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span> 

![インシデント アラート ページの画像](../images/incident-alerts.png)

<span data-ttu-id="c87fc-129">既定では、アラートは発生順に並べ替えられています。これにより、発生した攻撃を時系列で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="c87fc-130">各アラートをクリックすると、関連するアラート ページが表示され、そのアラートについて詳細な調査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span> 

## <a name="devices"></a><span data-ttu-id="c87fc-131">デバイス</span><span class="sxs-lookup"><span data-stu-id="c87fc-131">Devices</span></span> 
<span data-ttu-id="c87fc-132">[デバイス] タブには、インシデントに関連するアラートが表示されているすべてのデバイスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span> 

<span data-ttu-id="c87fc-133">攻撃が行われたコンピューターの名前をクリックすると、そのコンピューターのページが表示されます。調査を簡単にするために、トリガーされたアラートや関連イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span> 

![インシデントの [コンピューター] タブの画像](../images/incident-machines.png)

<span data-ttu-id="c87fc-135">[タイムライン] タブを選択すると、コンピューターのタイムラインをスクロールして、コンピューター上で監視されているすべてのイベントおよび動作、発生したアラートを日付順に表示できます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span> 


## <a name="users"></a><span data-ttu-id="c87fc-136">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c87fc-136">Users</span></span> 
<span data-ttu-id="c87fc-137">特定のインシデントに関連すると識別されたユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-137">See users that have been identified to be part of, or related to a given incident.</span></span> 

<span data-ttu-id="c87fc-138">ユーザー名をクリックすると、ユーザーの Cloud App Security ページに移動します。ここで詳細な調査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>


![インシデントの [ユーザー] タブの画像](../images/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="c87fc-140">メールボックス</span><span class="sxs-lookup"><span data-stu-id="c87fc-140">Mailboxes</span></span>
<span data-ttu-id="c87fc-141">インシデントに関連すると識別されたメールボックスを調査します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="c87fc-142">メール関連アラートを選択し Office 365 Advanced Threat Protection を開くと、修復アクションを実行でき、さらに調査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>


![インシデントの [メールボックス] タブの画像](../images/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="c87fc-144">調査</span><span class="sxs-lookup"><span data-stu-id="c87fc-144">Investigations</span></span>
<span data-ttu-id="c87fc-145">このインシデントのアラートによって実行されたすべての自動調査を表示するには、[**調査**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-145">Select **Investigations** to see all the automated investigation striggered by alerts in this incident.</span></span> <span data-ttu-id="c87fc-146">調査は、Microsoft Defender ATP および Office 365 Advanced Threat Protection での自動調査の実行をどのように構成したかによって、修復アクションを実行するか、またはアナリストからのアクションの承認を待ちます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![インシデントの [調査] タブの画像](../images/incident-investigations.png)


<span data-ttu-id="c87fc-148">調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="c87fc-149">調査の一部として承認待ちのアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを行います。</span><span class="sxs-lookup"><span data-stu-id="c87fc-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>


## <a name="evidence"></a><span data-ttu-id="c87fc-150">証拠</span><span class="sxs-lookup"><span data-stu-id="c87fc-150">Evidence</span></span>
<span data-ttu-id="c87fc-151">Microsoft Threat Protection は、アラート内のすべてのインシデントのサポートされているイベントおよび不審なエンティティを自動的に調査し、自動応答や重要なファイル、プロセス、サービス、メールなどに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c87fc-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="c87fc-152">これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-152">This helps quickly detect and block potential threats in the incident.</span></span> 

![インシデントの [証拠] タブの画像](../images/incident-evidence.png)

<span data-ttu-id="c87fc-154">分析された各エンティティには、判定 (悪質、不審、クリーン)、および修復状況が示されます。</span><span class="sxs-lookup"><span data-stu-id="c87fc-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="c87fc-155">これにより、インシデント全体の修復状況、および修復の次の手順について理解するのをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c87fc-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c87fc-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="c87fc-156">Related topics</span></span>
- [<span data-ttu-id="c87fc-157">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="c87fc-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c87fc-158">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="c87fc-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="c87fc-159">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="c87fc-159">Manage incidents</span></span>](manage-incidents.md)