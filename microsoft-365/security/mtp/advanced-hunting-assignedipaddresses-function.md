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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f0b479051c46fe35ec9aea84b23ca0c4937fbfe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412324"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="57307-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="57307-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57307-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="57307-105">**Applies to:**</span></span>
- <span data-ttu-id="57307-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="57307-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="57307-107">`AssignedIPAddresses()`[高度な](advanced-hunting-overview.md)検索クエリの関数を使用して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="57307-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="57307-108">Timestamp 引数を指定すると、この関数は指定された時刻に最新の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="57307-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="57307-109">この関数は、次の列を持つテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="57307-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="57307-110">Column</span><span class="sxs-lookup"><span data-stu-id="57307-110">Column</span></span> | <span data-ttu-id="57307-111">データ型</span><span class="sxs-lookup"><span data-stu-id="57307-111">Data type</span></span> | <span data-ttu-id="57307-112">説明</span><span class="sxs-lookup"><span data-stu-id="57307-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="57307-113">日付型</span><span class="sxs-lookup"><span data-stu-id="57307-113">datetime</span></span> | <span data-ttu-id="57307-114">デバイスが IP アドレスを使用して観測された最新時刻</span><span class="sxs-lookup"><span data-stu-id="57307-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="57307-115">string</span><span class="sxs-lookup"><span data-stu-id="57307-115">string</span></span> | <span data-ttu-id="57307-116">デバイスによって使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="57307-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="57307-117">string</span><span class="sxs-lookup"><span data-stu-id="57307-117">string</span></span> | <span data-ttu-id="57307-118">IP アドレスがパブリックまたはプライベートアドレスであるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="57307-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="57307-119">int</span><span class="sxs-lookup"><span data-stu-id="57307-119">int</span></span> | <span data-ttu-id="57307-120">IP アドレスが割り当てられているデバイスによって使用されるネットワークアダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="57307-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="57307-121">可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57307-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="57307-122">int</span><span class="sxs-lookup"><span data-stu-id="57307-122">int</span></span> | <span data-ttu-id="57307-123">割り当てられた IP アドレスを持つアダプターがに接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="57307-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="57307-124">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57307-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="57307-125">構文</span><span class="sxs-lookup"><span data-stu-id="57307-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="57307-126">引数</span><span class="sxs-lookup"><span data-stu-id="57307-126">Arguments</span></span>

- <span data-ttu-id="57307-127">**x** `DeviceId` または `DeviceName` デバイスを識別する値</span><span class="sxs-lookup"><span data-stu-id="57307-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="57307-128">**y**- `Timestamp` (datetime) 値は、指定した時刻から最新の IP アドレスを取得するように関数に指示します。</span><span class="sxs-lookup"><span data-stu-id="57307-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="57307-129">指定しない場合、関数は最新の IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="57307-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="57307-130">例</span><span class="sxs-lookup"><span data-stu-id="57307-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="57307-131">デバイスによって使用される IP アドレスの一覧を取得する24時間前</span><span class="sxs-lookup"><span data-stu-id="57307-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="57307-132">デバイスによって使用される IP アドレスを取得し、それと通信するデバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="57307-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="57307-133">このクエリは、関数を使用して、 `AssignedIPAddresses()` デバイス () に割り当てられている IP アドレスを `example-device-name` 特定の日付 () に対して取得 `example-date` します。</span><span class="sxs-lookup"><span data-stu-id="57307-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="57307-134">その後、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。</span><span class="sxs-lookup"><span data-stu-id="57307-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="57307-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="57307-135">Related topics</span></span>
- [<span data-ttu-id="57307-136">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="57307-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="57307-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="57307-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="57307-138">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="57307-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
