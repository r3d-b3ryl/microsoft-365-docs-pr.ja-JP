---
title: AssignedIPAddresses () 関数の詳細については、「Microsoft の脅威保護」をお探しください。
description: AssignedIPAddresses () 関数を使用して、デバイスに割り当てられている最新の IP アドレスを取得する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、FileProfile、file profile、function、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794233"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="3e159-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="3e159-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="3e159-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3e159-105">**Applies to:**</span></span>
- <span data-ttu-id="3e159-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e159-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="3e159-107">関数を使用して、 `AssignedIPAddresses()` デバイスに割り当てられている最新の ip アドレスや、指定した時点からの最新の ip アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="3e159-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="3e159-108">この関数は、次の列を持つテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="3e159-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="3e159-109">列</span><span class="sxs-lookup"><span data-stu-id="3e159-109">Column</span></span> | <span data-ttu-id="3e159-110">データ型</span><span class="sxs-lookup"><span data-stu-id="3e159-110">Data type</span></span> | <span data-ttu-id="3e159-111">説明</span><span class="sxs-lookup"><span data-stu-id="3e159-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="3e159-112">Timestamp</span><span class="sxs-lookup"><span data-stu-id="3e159-112">Timestamp</span></span> | <span data-ttu-id="3e159-113">日付型</span><span class="sxs-lookup"><span data-stu-id="3e159-113">datetime</span></span> | <span data-ttu-id="3e159-114">デバイスが IP アドレスを使用して観測された最新時刻</span><span class="sxs-lookup"><span data-stu-id="3e159-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="3e159-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="3e159-115">IPAddress</span></span> | <span data-ttu-id="3e159-116">string</span><span class="sxs-lookup"><span data-stu-id="3e159-116">string</span></span> | <span data-ttu-id="3e159-117">デバイスによって使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3e159-117">IP address used by the device</span></span> |
| <span data-ttu-id="3e159-118">IPType</span><span class="sxs-lookup"><span data-stu-id="3e159-118">IPType</span></span> | <span data-ttu-id="3e159-119">string</span><span class="sxs-lookup"><span data-stu-id="3e159-119">string</span></span> | <span data-ttu-id="3e159-120">IP アドレスがパブリックまたはプライベートアドレスであるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="3e159-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="3e159-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="3e159-121">NetworkAdapterType</span></span> | <span data-ttu-id="3e159-122">int</span><span class="sxs-lookup"><span data-stu-id="3e159-122">int</span></span> | <span data-ttu-id="3e159-123">IP アドレスが割り当てられているデバイスによって使用されるネットワークアダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="3e159-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="3e159-124">可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e159-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="3e159-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="3e159-125">ConnectedNetworks</span></span> | <span data-ttu-id="3e159-126">int</span><span class="sxs-lookup"><span data-stu-id="3e159-126">int</span></span> | <span data-ttu-id="3e159-127">割り当てられた IP アドレスを持つアダプターがに接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="3e159-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="3e159-128">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベートまたはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e159-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="3e159-129">構文</span><span class="sxs-lookup"><span data-stu-id="3e159-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="3e159-130">引数</span><span class="sxs-lookup"><span data-stu-id="3e159-130">Arguments</span></span>

- <span data-ttu-id="3e159-131">**x** `DeviceId` または `DeviceName` デバイスを識別する値</span><span class="sxs-lookup"><span data-stu-id="3e159-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="3e159-132">**y** - `Timestamp` (datetime) 値は、最新の IP アドレスを取得する特定の時点を示します。</span><span class="sxs-lookup"><span data-stu-id="3e159-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="3e159-133">指定しない場合、関数は最新の IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="3e159-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="3e159-134">例</span><span class="sxs-lookup"><span data-stu-id="3e159-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="3e159-135">24時間前にデバイスによって使用された IP アドレスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="3e159-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="3e159-136">デバイスによって使用される IP アドレスを取得し、それと通信するデバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="3e159-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="3e159-137">このクエリは、関数を使用して、 `AssignedIPAddresses()` デバイス () に割り当てられている IP アドレスを `example-device-name` 特定の日付 () に対して取得 `example-date` します。</span><span class="sxs-lookup"><span data-stu-id="3e159-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="3e159-138">その後、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。</span><span class="sxs-lookup"><span data-stu-id="3e159-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="3e159-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3e159-139">Related topics</span></span>
- [<span data-ttu-id="3e159-140">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3e159-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3e159-141">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3e159-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3e159-142">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3e159-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)