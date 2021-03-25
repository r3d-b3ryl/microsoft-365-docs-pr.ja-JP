---
title: Microsoft Defender Security Center Security operations dashboard
description: ダッシュボードを使用して、危険にさらされているデバイスを特定し、サービスの状態を追跡し、デバイスとアラートに関する統計情報と情報を確認します。
keywords: ダッシュボード、アラート、新規、進行中、解決済み、リスク、リスクのあるデバイス、感染、レポート、統計、グラフ、グラフ、正常性、アクティブなマルウェア検出、脅威カテゴリ、カテゴリ、パスワード盗用、ランサムウェア、悪用、脅威、重要度の低い、アクティブ なマルウェア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064915"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="48024-104">Microsoft Defender Security Center Security operations dashboard</span><span class="sxs-lookup"><span data-stu-id="48024-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="48024-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="48024-105">**Applies to:**</span></span>
- [<span data-ttu-id="48024-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="48024-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="48024-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="48024-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48024-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="48024-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="48024-109">セキュリティ **操作ダッシュボードでは** 、エンドポイントの検出および応答機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="48024-110">検出がどこで見られたかの概要と、応答アクションが必要な場所を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="48024-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="48024-111">ダッシュボードには、次のスナップショットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="48024-112">アクティブなアラート</span><span class="sxs-lookup"><span data-stu-id="48024-112">Active alerts</span></span>
- <span data-ttu-id="48024-113">危険にさらされているデバイス</span><span class="sxs-lookup"><span data-stu-id="48024-113">Devices at risk</span></span>
- <span data-ttu-id="48024-114">センサーの正常性</span><span class="sxs-lookup"><span data-stu-id="48024-114">Sensor health</span></span>
- <span data-ttu-id="48024-115">サービス正常性</span><span class="sxs-lookup"><span data-stu-id="48024-115">Service health</span></span>
- <span data-ttu-id="48024-116">毎日のデバイスレポート</span><span class="sxs-lookup"><span data-stu-id="48024-116">Daily devices reporting</span></span>
- <span data-ttu-id="48024-117">アクティブな自動調査</span><span class="sxs-lookup"><span data-stu-id="48024-117">Active automated investigations</span></span>
- <span data-ttu-id="48024-118">自動調査の統計</span><span class="sxs-lookup"><span data-stu-id="48024-118">Automated investigations statistics</span></span>
- <span data-ttu-id="48024-119">リスクにさらされているユーザー</span><span class="sxs-lookup"><span data-stu-id="48024-119">Users at risk</span></span>
- <span data-ttu-id="48024-120">疑わしいアクティビティ</span><span class="sxs-lookup"><span data-stu-id="48024-120">Suspicious activities</span></span>


![セキュリティ操作ダッシュボードのイメージ](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="48024-122">アラートとデバイスを調査して調査し、ネットワーク内で疑わしいアクティビティが発生したかどうかを迅速に判断し、それが表示されたコンテキストを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48024-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="48024-123">セキュリティ操作 **ダッシュボードには、** デバイス上の重要なイベントや動作を識別するための集約イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="48024-124">詳細なイベントと低レベルインジケーターをドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="48024-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="48024-125">また、クリック可能なタイルを使用して、組織の全体的な正常性状態に視覚的な手がかりを与えます。</span><span class="sxs-lookup"><span data-stu-id="48024-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="48024-126">各タイルは、対応する概要の詳細なビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="48024-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="48024-127">アクティブなアラート</span><span class="sxs-lookup"><span data-stu-id="48024-127">Active alerts</span></span>
<span data-ttu-id="48024-128">ネットワーク内の過去 30 日間のアクティブなアラートの全体数をタイルから表示できます。</span><span class="sxs-lookup"><span data-stu-id="48024-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="48024-129">アラートは、[新規] と **[進行中] に\*\*\*\*グループ化されます**。</span><span class="sxs-lookup"><span data-stu-id="48024-129">Alerts are grouped into **New** and **In progress**.</span></span>

![各スライスまたは重大度をクリックして、過去 30 日間のアラートの一覧を表示する](images/active-alerts-tile.png)

<span data-ttu-id="48024-131">各グループは、対応するアラートの重大度レベルにさらにサブ分類されます。</span><span class="sxs-lookup"><span data-stu-id="48024-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="48024-132">各アラート リング内のアラートの数をクリックすると、そのカテゴリのキュー (**新規** または進行中) の並べ替えビュー **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="48024-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="48024-133">詳細については、「アラートの概要 [」を参照してください](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="48024-134">各行には、アラートの重大度カテゴリと、アラートの簡単な説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48024-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="48024-135">アラートをクリックすると、その詳細なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="48024-136">詳細については[、「Microsoft Defender for Endpoint アラートとアラートの概要を調査する」](investigate-alerts.md)[を参照してください](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="48024-137">危険にさらされているデバイス</span><span class="sxs-lookup"><span data-stu-id="48024-137">Devices at risk</span></span>
<span data-ttu-id="48024-138">このタイルには、アクティブなアラートの数が最も多いデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="48024-139">各デバイスのアラートの総数は、デバイス名の横の円に表示され、さらにタイルの端にある重大度レベル別に分類されます (各重大度バーにカーソルを合わせると、ラベルが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="48024-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![[危険なデバイス] タイルには、アラートの数が最も多いデバイスの一覧と、アラートの重大度の内訳が表示されます。](images/devices-at-risk-tile.png)

<span data-ttu-id="48024-141">デバイスの名前をクリックすると、そのデバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="48024-142">詳細については、「Microsoft Defender for Endpoint Devices リストのデバイスを [調査する」を参照してください](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="48024-143">タイルの上部にある **[デバイス一** 覧] をクリックして、[デバイス]リストに直接移動し、アクティブなアラートの数で並べ替えすることもできます。</span><span class="sxs-lookup"><span data-stu-id="48024-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="48024-144">詳細については、「Microsoft Defender for Endpoint Devices リストのデバイスを [調査する」を参照してください](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="48024-145">センサーの問題があるデバイス</span><span class="sxs-lookup"><span data-stu-id="48024-145">Devices with sensor issues</span></span>
<span data-ttu-id="48024-146">[ **センサーの問題があるデバイス]** タイルは、Microsoft Defender for Endpoint サービスにセンサー データを提供する個々のデバイスの機能に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="48024-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="48024-147">注意が必要なデバイスの数を報告し、問題のあるデバイスを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48024-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![センサーの問題のタイルを持つデバイス](images/atp-tile-sensor-health.png)

<span data-ttu-id="48024-149">サービスに適切に報告されていないデバイスの数に関する情報を提供する 2 つの状態インジケーターがあります。</span><span class="sxs-lookup"><span data-stu-id="48024-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="48024-150">**正しく構成** されていない – これらのデバイスは、部分的にセンサー データを Microsoft Defender for Endpoint サービスに報告している可能性があります。また、修正が必要な構成エラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48024-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="48024-151">**非** アクティブ - 過去 1 か月で 7 日間以上 Microsoft Defender for Endpoint サービスへの報告を停止したデバイス。</span><span class="sxs-lookup"><span data-stu-id="48024-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="48024-152">グループをクリックすると、選択に応じてフィルター処理されたデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="48024-153">詳細については、「センサーの状態を [確認する」および「デバイスの](check-sensor-status.md) 調査 [」を参照してください](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="48024-154">サービス正常性</span><span class="sxs-lookup"><span data-stu-id="48024-154">Service health</span></span>
<span data-ttu-id="48024-155">[ **サービス正常性]** タイルは、サービスがアクティブか、または問題が発生した場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="48024-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![[サービスの正常性] タイルには、サービスの全体的なインジケーターが表示されます。](images/status-tile.png)

<span data-ttu-id="48024-157">サービス正常性の詳細については [、「Check the Microsoft Defender for Endpoint service health」を参照してください](service-status.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="48024-158">毎日のデバイスレポート</span><span class="sxs-lookup"><span data-stu-id="48024-158">Daily devices reporting</span></span>
<span data-ttu-id="48024-159">[ **日次デバイスのレポート** ] タイルには、過去 30 日間の毎日のデバイスレポートの数を表す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="48024-160">グラフ上の個々のバーにカーソルを合わせると、1 日にレポートするデバイスの正確な数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![毎日のデバイスレポート タイルのイメージ](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="48024-162">アクティブな自動調査</span><span class="sxs-lookup"><span data-stu-id="48024-162">Active automated investigations</span></span>
<span data-ttu-id="48024-163">[アクティブな自動調査] タイルから、ネットワーク内の過去 30 日間の自動調査の全体数 **を表示** できます。</span><span class="sxs-lookup"><span data-stu-id="48024-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="48024-164">調査は、保留中のアクション **、** デバイスの待機、および実行中 **に** グループ **化されます**。</span><span class="sxs-lookup"><span data-stu-id="48024-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![アクティブな自動調査のインマゲ](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="48024-166">自動調査の統計</span><span class="sxs-lookup"><span data-stu-id="48024-166">Automated investigations statistics</span></span>
<span data-ttu-id="48024-167">このタイルには、過去 7 日間の自動調査に関連する統計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="48024-168">完了した調査の数、正常に修復された調査の数、調査の開始に要する平均保留中の時間、アラートの修復にかかる平均時間、調査したアラートの数、および一般的な手動調査から保存された自動化の時間数を示します。</span><span class="sxs-lookup"><span data-stu-id="48024-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![自動調査統計のイメージ](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="48024-170">[自動調査]、[修復された調査]、および [調査されたアラート] をクリックして、[調査] ページに移動し、適切なカテゴリでフィルター処理できます。  </span><span class="sxs-lookup"><span data-stu-id="48024-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="48024-171">これにより、状況に合った調査の詳細な内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="48024-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="48024-172">リスクにさらされているユーザー</span><span class="sxs-lookup"><span data-stu-id="48024-172">Users at risk</span></span>
<span data-ttu-id="48024-173">タイルには、最もアクティブなアラートを含むユーザー アカウントの一覧と、高、中、低のアラートに表示されるアラートの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![[危険度のあるユーザー アカウント] タイルには、アラートの数が最も多いユーザー アカウントの一覧と、アラートの重大度の内訳が表示されます。](images/atp-users-at-risk.png)

<span data-ttu-id="48024-175">ユーザー アカウントをクリックすると、ユーザー アカウントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48024-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="48024-176">詳細については、「ユーザー アカウント [の調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="48024-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="48024-177">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="48024-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48024-178">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="48024-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="48024-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="48024-179">Related topics</span></span>
- [<span data-ttu-id="48024-180">Microsoft Defender for Endpoint ポータルについて</span><span class="sxs-lookup"><span data-stu-id="48024-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="48024-181">ポータルの概要</span><span class="sxs-lookup"><span data-stu-id="48024-181">Portal overview</span></span>](portal-overview.md)
- <span data-ttu-id="48024-182">[[脅威の管理] &のダッシュボードを表示する](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="48024-182">[View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md)</span></span>
- [<span data-ttu-id="48024-183">脅威分析ダッシュボードを表示し、推奨される軽減アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="48024-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
