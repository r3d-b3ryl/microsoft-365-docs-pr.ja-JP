---
title: Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート
description: デバイスの正常性とコンプライアンス レポートを使用して、デバイスの正常性状態の検出、ウイルス対策の状態、OS プラットフォーム、および Windows 10 バージョンを追跡する
keywords: 正常性状態、ウイルス対策、OS プラットフォーム、Windows 10 バージョン、バージョン、正常性、コンプライアンス、状態
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860293"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="97ba1-104">Microsoft Defender for Endpoint のデバイスの正常性とコンプライアンス レポート</span><span class="sxs-lookup"><span data-stu-id="97ba1-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97ba1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="97ba1-105">**Applies to:**</span></span>
- [<span data-ttu-id="97ba1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="97ba1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="97ba1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97ba1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="97ba1-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="97ba1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="97ba1-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="97ba1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="97ba1-110">デバイスの状態レポートは、組織内のデバイスに関する高レベルの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="97ba1-111">このレポートには、センサーの正常性状態、ウイルス対策の状態、OS プラットフォーム、および Windows 10 バージョンを示す傾向情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="97ba1-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="97ba1-112">ダッシュボードは、デバイス レポートのイメージという 2 ![ つのセクションに構成されています。](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="97ba1-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="97ba1-113">Section</span><span class="sxs-lookup"><span data-stu-id="97ba1-113">Section</span></span> | <span data-ttu-id="97ba1-114">説明</span><span class="sxs-lookup"><span data-stu-id="97ba1-114">Description</span></span>
:---|:---
<span data-ttu-id="97ba1-115">1</span><span class="sxs-lookup"><span data-stu-id="97ba1-115">1</span></span> | <span data-ttu-id="97ba1-116">デバイスの傾向</span><span class="sxs-lookup"><span data-stu-id="97ba1-116">Device trends</span></span>
<span data-ttu-id="97ba1-117">2</span><span class="sxs-lookup"><span data-stu-id="97ba1-117">2</span></span> | <span data-ttu-id="97ba1-118">デバイスの概要 (現在の日)</span><span class="sxs-lookup"><span data-stu-id="97ba1-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="97ba1-119">デバイスの傾向</span><span class="sxs-lookup"><span data-stu-id="97ba1-119">Device trends</span></span> 
<span data-ttu-id="97ba1-120">既定では、デバイスの傾向には、最新の 1 日で終わる 30 日間の期間のデバイス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="97ba1-121">組織で発生している傾向についてより良い視点を得るために、表示される期間を調整してレポート期間を微調整できます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="97ba1-122">期間を調整するには、ドロップダウン オプションから時間範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="97ba1-123">30 日間</span><span class="sxs-lookup"><span data-stu-id="97ba1-123">30 days</span></span>
- <span data-ttu-id="97ba1-124">3 か月</span><span class="sxs-lookup"><span data-stu-id="97ba1-124">3 months</span></span>
- <span data-ttu-id="97ba1-125">6 か月</span><span class="sxs-lookup"><span data-stu-id="97ba1-125">6 months</span></span>
- <span data-ttu-id="97ba1-126">Custom</span><span class="sxs-lookup"><span data-stu-id="97ba1-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="97ba1-127">これらのフィルターは、[デバイスの傾向] セクションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="97ba1-128">[デバイスの概要] セクションには影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="97ba1-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="97ba1-129">デバイスの概要</span><span class="sxs-lookup"><span data-stu-id="97ba1-129">Device summary</span></span> 
<span data-ttu-id="97ba1-130">デバイスの傾向はデバイス情報の傾向を示しますが、デバイスの概要には、現在の日を対象にしたデバイス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="97ba1-131">[概要] セクションに反映されるデータの範囲は、現在の日付の 180 日前です。</span><span class="sxs-lookup"><span data-stu-id="97ba1-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="97ba1-132">たとえば、今日の日付が 2019 年 3 月 27 日の場合、概要セクションのデータには、2018 年 9 月 28 日から 2019 年 3 月 27 日の数値が反映されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="97ba1-133">[傾向] セクションに適用されるフィルターは、[概要] セクションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="97ba1-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="97ba1-134">[デバイスの傾向] セクションでは、対応するフィルターが適用されたデバイス リストにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="97ba1-135">たとえば、センサーの正常性状態カードの [非アクティブ] バーをクリックすると、センサーの状態が非アクティブなデバイスのみを表示する結果が表示されるデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="97ba1-136">デバイス属性</span><span class="sxs-lookup"><span data-stu-id="97ba1-136">Device attributes</span></span>
<span data-ttu-id="97ba1-137">レポートは、次のデバイス属性を表示するカードで構成されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="97ba1-138">**正常性状態**: デバイス上のセンサー状態に関する情報を表示し、アクティブなデバイス、通信障害、非アクティブ、またはセンサー データが見られないデバイスの集計ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="97ba1-139">**アクティブな Windows 10 デバイスのウイルス対策の状態**: デバイスの数と Microsoft Defender ウイルス対策の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="97ba1-140">**OS プラットフォーム**: 組織内に存在する OS プラットフォームの配布を示します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="97ba1-141">**Windows 10 バージョン**: 組織内の Windows 10 デバイスとそのバージョンの配布を示します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="97ba1-142">データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="97ba1-142">Filter data</span></span>
 
<span data-ttu-id="97ba1-143">指定されたフィルターを使用して、特定の属性を持つデバイスを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="97ba1-144">デバイス属性から適用する複数のフィルターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="97ba1-145">これらのフィルターは、 **レポート内のすべての** カードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="97ba1-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="97ba1-146">たとえば、アクティブ センサーの正常性状態を持つ Windows 10 デバイスに関するデータを表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="97ba1-147">[ **フィルター] >センサーの正常性状態>アクティブです**。</span><span class="sxs-lookup"><span data-stu-id="97ba1-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="97ba1-148">次に **、[Windows 10 > OS プラットフォーム] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="97ba1-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="97ba1-149">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97ba1-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="97ba1-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="97ba1-150">Related topic</span></span>
- [<span data-ttu-id="97ba1-151">脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="97ba1-151">Threat protection report</span></span>](threat-protection-reports.md)
