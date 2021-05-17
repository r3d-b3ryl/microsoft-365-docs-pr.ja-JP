---
title: Microsoft Defender for Endpoint の脅威保護レポート
description: 脅威保護レポートを使用してアラートの検出、カテゴリ、重大度を追跡する
keywords: アラート検出, ソース, カテゴリ別アラート, アラート重大度, アラート分類, 決定
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688983"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4d1bd-104">Microsoft Defender for Endpoint の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="4d1bd-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4d1bd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4d1bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d1bd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d1bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d1bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d1bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4d1bd-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4d1bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4d1bd-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="4d1bd-110">脅威保護レポートは、組織で生成されたアラートに関する高レベルの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="4d1bd-111">このレポートには、検出元、カテゴリ、重大度、状態、分類、および時間の間のアラートの決定を示す傾向情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="4d1bd-112">ダッシュボードは、次の 2 つのセクションに構成されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-112">The dashboard is structured into two sections:</span></span>

![脅威保護レポートの画像](images/threat-protection-reports.png)

<span data-ttu-id="4d1bd-114">Section</span><span class="sxs-lookup"><span data-stu-id="4d1bd-114">Section</span></span> | <span data-ttu-id="4d1bd-115">説明</span><span class="sxs-lookup"><span data-stu-id="4d1bd-115">Description</span></span> 
:---|:---
<span data-ttu-id="4d1bd-116">1</span><span class="sxs-lookup"><span data-stu-id="4d1bd-116">1</span></span> | <span data-ttu-id="4d1bd-117">アラートの傾向</span><span class="sxs-lookup"><span data-stu-id="4d1bd-117">Alerts trends</span></span>
<span data-ttu-id="4d1bd-118">2</span><span class="sxs-lookup"><span data-stu-id="4d1bd-118">2</span></span> | <span data-ttu-id="4d1bd-119">アラートの概要</span><span class="sxs-lookup"><span data-stu-id="4d1bd-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="4d1bd-120">アラートの傾向</span><span class="sxs-lookup"><span data-stu-id="4d1bd-120">Alert trends</span></span>
<span data-ttu-id="4d1bd-121">既定では、アラートの傾向には、最新の 1 日で終了する 30 日間の期間のアラート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="4d1bd-122">組織で発生している傾向についてより良い視点を得るために、表示される期間を調整してレポート期間を微調整できます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="4d1bd-123">期間を調整するには、ドロップダウン オプションから時間範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="4d1bd-124">30 日間</span><span class="sxs-lookup"><span data-stu-id="4d1bd-124">30 days</span></span>
- <span data-ttu-id="4d1bd-125">3 か月</span><span class="sxs-lookup"><span data-stu-id="4d1bd-125">3 months</span></span>
- <span data-ttu-id="4d1bd-126">6 か月</span><span class="sxs-lookup"><span data-stu-id="4d1bd-126">6 months</span></span>
- <span data-ttu-id="4d1bd-127">Custom</span><span class="sxs-lookup"><span data-stu-id="4d1bd-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="4d1bd-128">これらのフィルターは、[アラートの傾向] セクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="4d1bd-129">アラートの概要セクションには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="4d1bd-130">アラートの概要</span><span class="sxs-lookup"><span data-stu-id="4d1bd-130">Alert summary</span></span>
<span data-ttu-id="4d1bd-131">アラートの傾向に傾向アラート情報が表示される一方で、アラートの概要には、現在の日を対象にしたアラート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="4d1bd-132">アラートの概要を使用すると、対応するフィルターが適用された特定のアラート キューにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="4d1bd-133">たとえば、[検出ソース] カードの [EDR] バーをクリックすると、通知キューに通知キューが表示され、検出から生成されたEDR表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="4d1bd-134">[概要] セクションに反映されるデータの範囲は、現在の日付の 180 日前です。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="4d1bd-135">たとえば、今日の日付が 2019 年 11 月 5 日の場合、概要セクションのデータには、2019 年 5 月 5 日から 2019 年 11 月 5 日の数値が反映されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="4d1bd-136">[傾向] セクションに適用されるフィルターは、[概要] セクションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="4d1bd-137">アラート属性</span><span class="sxs-lookup"><span data-stu-id="4d1bd-137">Alert attributes</span></span>
<span data-ttu-id="4d1bd-138">レポートは、次のアラート属性を表示するカードで構成されています。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="4d1bd-139">**検出ソース**: Microsoft Defender for Endpoint がアラートをトリガーするために使用するデータを提供するセンサーと検出テクノロジに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="4d1bd-140">**脅威のカテゴリ**: アラートをトリガーした脅威または攻撃アクティビティの種類を示し、セキュリティ操作の可能なフォーカス領域を示します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="4d1bd-141">**重大度**: アラートの重大度レベルを示し、組織に対する脅威の潜在的な影響の集合的な潜在的な影響と、脅威に対処するために必要な対応のレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="4d1bd-142">**Status**: アラートの解決状態を示し、手動のアラート応答の効率と自動修復 (有効な場合) を示します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="4d1bd-143">**分類&決定**: 解決時にアラートを分類した方法、実際の脅威 (真のアラート) として分類したかどうか、または誤った検出 (誤ったアラート) として分類した方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="4d1bd-144">これらのカードには、解決されたアラートの決定も表示され、検出された実際の脅威の種類や、誤って検出された正当なアクティビティなどの追加の分析情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="4d1bd-145">データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="4d1bd-145">Filter data</span></span>

<span data-ttu-id="4d1bd-146">指定されたフィルターを使用して、特定の属性を持つアラートを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="4d1bd-147">これらのフィルターは、 **レポート内のすべての** カードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="4d1bd-148">たとえば、重大度の高いアラートに関するデータのみを表示するには、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="4d1bd-149">[フィルター **と重大度>] で、[** 高] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="4d1bd-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="4d1bd-150">[重大度] の下の他のすべての **オプションが選択** 解除されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="4d1bd-151">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d1bd-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="4d1bd-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4d1bd-152">Related topic</span></span>
- [<span data-ttu-id="4d1bd-153">デバイスの正常性とコンプライアンス レポート</span><span class="sxs-lookup"><span data-stu-id="4d1bd-153">Device health and compliance report</span></span>](machine-reports.md)
