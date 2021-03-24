---
title: Microsoft Defender ATP のインシデントを調査する
description: 関連付けられたアラートの表示、インシデントの管理、インシデントの調査に役立つアラート メタデータの表示
keywords: 調査、インシデント、アラート、メタデータ、リスク、検出ソース、影響を受けるデバイス、パターン、相関関係
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6f8986b3cb6b6fd846febefe8a64ab4099348f5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064316"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3cc51-104">Microsoft Defender for Endpoint のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="3cc51-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3cc51-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3cc51-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cc51-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3cc51-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3cc51-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cc51-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="3cc51-108">ネットワークに影響を与えるインシデントを調査し、その意味を理解し、証拠を照合して解決します。</span><span class="sxs-lookup"><span data-stu-id="3cc51-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="3cc51-109">インシデントを調査すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="3cc51-110">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="3cc51-110">Incident details</span></span>
- <span data-ttu-id="3cc51-111">インシデントのコメントとアクション</span><span class="sxs-lookup"><span data-stu-id="3cc51-111">Incident comments and actions</span></span>
- <span data-ttu-id="3cc51-112">タブ (アラート、デバイス、調査、証拠、グラフ)</span><span class="sxs-lookup"><span data-stu-id="3cc51-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="3cc51-113">インシデントの詳細を分析する</span><span class="sxs-lookup"><span data-stu-id="3cc51-113">Analyze incident details</span></span> 
<span data-ttu-id="3cc51-114">インシデントをクリックすると、[インシデント] ウィンドウ **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="3cc51-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="3cc51-115">[ **インシデントを開く] ページ** を選択して、インシデントの詳細と関連情報 (アラート、デバイス、調査、証拠、グラフ) を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cc51-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![インシデントの詳細の画像1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="3cc51-117">アラート</span><span class="sxs-lookup"><span data-stu-id="3cc51-117">Alerts</span></span>
<span data-ttu-id="3cc51-118">アラートを調査し、インシデントでどのようにリンクされたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="3cc51-119">アラートは、次の理由に基づいてインシデントにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="3cc51-120">自動調査 - 自動調査によって、元のアラートの調査中にリンクされたアラートがトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="3cc51-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="3cc51-121">ファイルの特性 - アラートに関連付けられているファイルの特性は類似しています</span><span class="sxs-lookup"><span data-stu-id="3cc51-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="3cc51-122">手動関連付け - ユーザーが手動でアラートをリンクした</span><span class="sxs-lookup"><span data-stu-id="3cc51-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="3cc51-123">近位時刻 - アラートは、特定の時間枠内に同じデバイスでトリガーされました</span><span class="sxs-lookup"><span data-stu-id="3cc51-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="3cc51-124">同じファイル - アラートに関連付けられているファイルは、まったく同じです</span><span class="sxs-lookup"><span data-stu-id="3cc51-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="3cc51-125">同じ URL - アラートをトリガーした URL は、まったく同じです。</span><span class="sxs-lookup"><span data-stu-id="3cc51-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![[アラート] タブのイメージで、インシデントの詳細ページに、そのインシデントでアラートがリンクされた理由を示します。](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="3cc51-127">アラートを管理し、他の情報と共にアラート メタデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="3cc51-128">詳細については、「アラートの調査 [」を参照してください](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc51-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="3cc51-129">デバイス</span><span class="sxs-lookup"><span data-stu-id="3cc51-129">Devices</span></span>
<span data-ttu-id="3cc51-130">また、特定のインシデントの一部または関連するデバイスを調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="3cc51-131">詳細については、「デバイスの調査 [」を参照してください](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc51-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![インシデントの詳細ページの [デバイス] タブのイメージ](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="3cc51-133">調査</span><span class="sxs-lookup"><span data-stu-id="3cc51-133">Investigations</span></span>
<span data-ttu-id="3cc51-134">[ **調査] を** 選択して、インシデント通知に応答してシステムによって起動された自動調査を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cc51-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![インシデントの詳細ページの [調査] タブのイメージ](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="3cc51-136">証拠を確認する</span><span class="sxs-lookup"><span data-stu-id="3cc51-136">Going through the evidence</span></span>
<span data-ttu-id="3cc51-137">Microsoft Defender for Endpoint は、インシデントがサポートしているすべてのイベントと、アラート内の不審なエンティティを自動的に調査し、自動応答と重要なファイル、プロセス、サービスなどの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cc51-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="3cc51-138">分析された各エンティティは、感染、修復、または疑わしいとマークされます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![インシデントの詳細ページの [証拠] タブの画像](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="3cc51-140">関連するサイバーセキュリティの脅威を視覚化する</span><span class="sxs-lookup"><span data-stu-id="3cc51-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="3cc51-141">Microsoft Defender for Endpoint は、脅威情報をインシデントに集約し、さまざまなデータ ポイントから入ってくるパターンと相関関係を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="3cc51-142">このような相関関係は、インシデント グラフを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="3cc51-143">インシデント グラフ</span><span class="sxs-lookup"><span data-stu-id="3cc51-143">Incident graph</span></span>
<span data-ttu-id="3cc51-144">Graph **は** 、サイバーセキュリティ攻撃のストーリーを示します。</span><span class="sxs-lookup"><span data-stu-id="3cc51-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="3cc51-145">たとえば、どのデバイスで侵害またはアクティビティが観察されたかを示すエントリ ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="3cc51-146">など</span><span class="sxs-lookup"><span data-stu-id="3cc51-146">etc.</span></span>

![インシデント グラフのイメージ](images/atp-incident-graph-tab.png)

<span data-ttu-id="3cc51-148">インシデント グラフの円をクリックすると、悪意のあるファイルの詳細、関連するファイルの検出、世界中に発生したインスタンスの数、組織で観察されている場合は、インスタンス数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3cc51-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![インシデントの詳細の画像](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="3cc51-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cc51-150">Related topics</span></span>
- [<span data-ttu-id="3cc51-151">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="3cc51-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="3cc51-152">Microsoft Defender for Endpoint のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="3cc51-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="3cc51-153">エンドポイント インシデントの Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="3cc51-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)
