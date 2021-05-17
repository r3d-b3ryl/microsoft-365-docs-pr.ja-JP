---
title: Microsoft Defender for Endpoint のセンサーの正常性状態を確認する
description: デバイスのセンサーの正常性を確認して、構成が誤り、非アクティブ、またはセンサー データを報告していないデバイスを特定します。
keywords: センサー、センサーの正常性、構成ミス、非アクティブ、センサー データなし、センサー データ、通信障害、通信障害
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904166"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="bcfa7-104">Microsoft Defender for Endpoint のセンサーの正常性状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bcfa7-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bcfa7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bcfa7-105">**Applies to:**</span></span>
- [<span data-ttu-id="bcfa7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bcfa7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bcfa7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcfa7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bcfa7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bcfa7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bcfa7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="bcfa7-110">[ **センサーの問題があるデバイス] タイル** は、[セキュリティ操作] ダッシュボードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="bcfa7-111">このタイルは、センサー データを提供し、Defender for Endpoint サービスと通信する個々のデバイスの機能に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="bcfa7-112">注意が必要なデバイスの数を報告し、問題のあるデバイスを特定し、既知の問題を修正するためのアクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="bcfa7-113">タイルには、サービスに適切に報告されていないデバイスの数に関する情報を提供する 2 つの状態インジケーターがあります。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="bcfa7-114">**正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性があります。また、修正が必要な構成エラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="bcfa7-115">**非** アクティブ - 過去 1 か月で 7 日間以上 Defender for Endpoint サービスへの報告を停止したデバイス。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="bcfa7-116">グループをクリックすると、[デバイス] リストが表示 **され、選択** に従ってフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![センサーの問題があるデバイスタイルのスクリーンショット](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="bcfa7-118">[ **デバイス] リスト** で、正常性状態リストを次の状態でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="bcfa7-119">**Active** - Defender for Endpoint サービスに対してアクティブにレポートしているデバイス。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="bcfa7-120">**正しく構成されていない** - これらのデバイスは、センサー データを部分的に Defender for Endpoint サービスに報告している可能性がありますが、修正する必要がある構成エラーがあります。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="bcfa7-121">構成が正しく設定されていないデバイスには、次の問題の 1 つまたは組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="bcfa7-122">**センサー データなし** - デバイスがセンサー データの送信を停止しました。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="bcfa7-123">制限付きアラートは、デバイスからトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="bcfa7-124">**通信障害** - デバイスと通信する機能が損なわれる。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="bcfa7-125">ディープ分析用のファイルの送信、ファイルのブロック、ネットワークからのデバイスの分離、デバイスとの通信が必要なその他のアクションが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="bcfa7-126">**非** アクティブ - Defender for Endpoint サービスへのレポートを停止したデバイス。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="bcfa7-127">エクスポート機能を使用して、リスト全体を CSV 形式で **ダウンロード** できます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="bcfa7-128">フィルターの詳細については、「デバイスリストの [表示と整理」を参照してください](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="bcfa7-129">リストを CSV 形式でエクスポートして、フィルター処理されていないデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="bcfa7-130">CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![[デバイス] リスト ページのスクリーンショット](images/atp-devices-list-page.png)

<span data-ttu-id="bcfa7-132">構成が正しく設定されていないデバイスまたは非アクティブなデバイスをクリックすると、デバイスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bcfa7-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="bcfa7-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bcfa7-133">Related topic</span></span>
- [<span data-ttu-id="bcfa7-134">Defender for Endpoint で不健康なセンサーを修正する</span><span class="sxs-lookup"><span data-stu-id="bcfa7-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
