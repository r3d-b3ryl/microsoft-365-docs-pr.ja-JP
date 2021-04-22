---
title: Microsoft 365 Defender の高度な狩猟での AssignedIPAddresses() 関数
description: AssignedIPAddresses() 関数を使用してデバイスに割り当てられた最新の IP アドレスを取得する方法について学習する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ebd301d6c79bf5286d9293e04e4073b99d1e35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934911"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="f1459-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="f1459-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f1459-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f1459-105">**Applies to:**</span></span>
- <span data-ttu-id="f1459-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1459-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f1459-107">高度な `AssignedIPAddresses()` 検索クエリの [関数を](advanced-hunting-overview.md) 使用して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="f1459-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="f1459-108">タイムスタンプ引数を指定すると、指定した時刻に最新の IP アドレスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f1459-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="f1459-109">この関数は、次の列を持つテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="f1459-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="f1459-110">Column</span><span class="sxs-lookup"><span data-stu-id="f1459-110">Column</span></span> | <span data-ttu-id="f1459-111">データ型</span><span class="sxs-lookup"><span data-stu-id="f1459-111">Data type</span></span> | <span data-ttu-id="f1459-112">説明</span><span class="sxs-lookup"><span data-stu-id="f1459-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="f1459-113">日付型</span><span class="sxs-lookup"><span data-stu-id="f1459-113">datetime</span></span> | <span data-ttu-id="f1459-114">IP アドレスを使用してデバイスが観察された最新の時刻</span><span class="sxs-lookup"><span data-stu-id="f1459-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="f1459-115">string</span><span class="sxs-lookup"><span data-stu-id="f1459-115">string</span></span> | <span data-ttu-id="f1459-116">デバイスで使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f1459-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="f1459-117">string</span><span class="sxs-lookup"><span data-stu-id="f1459-117">string</span></span> | <span data-ttu-id="f1459-118">IP アドレスがパブリック アドレスかプライベート アドレスかを示します。</span><span class="sxs-lookup"><span data-stu-id="f1459-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="f1459-119">int</span><span class="sxs-lookup"><span data-stu-id="f1459-119">int</span></span> | <span data-ttu-id="f1459-120">IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="f1459-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="f1459-121">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="f1459-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="f1459-122">int</span><span class="sxs-lookup"><span data-stu-id="f1459-122">int</span></span> | <span data-ttu-id="f1459-123">割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="f1459-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="f1459-124">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="f1459-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="f1459-125">構文</span><span class="sxs-lookup"><span data-stu-id="f1459-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="f1459-126">引数</span><span class="sxs-lookup"><span data-stu-id="f1459-126">Arguments</span></span>

- <span data-ttu-id="f1459-127">**x**— `DeviceId` または `DeviceName` デバイスを識別する値</span><span class="sxs-lookup"><span data-stu-id="f1459-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="f1459-128">**y**— 特定の時刻から最新の割り当てられた IP アドレスを取得するように関数に指示する `Timestamp` (datetime) 値。</span><span class="sxs-lookup"><span data-stu-id="f1459-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="f1459-129">指定しない場合、関数は最新の IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="f1459-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="f1459-130">例</span><span class="sxs-lookup"><span data-stu-id="f1459-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="f1459-131">24 時間前にデバイスで使用される IP アドレスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="f1459-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="f1459-132">デバイスで使用される IP アドレスを取得し、デバイスと通信するデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="f1459-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="f1459-133">このクエリでは、この関数を使用して、デバイス ( ) の割り当てられた IP アドレスを、特定の日付 ( ) のオンまたは前 `AssignedIPAddresses()` `example-device-name` に取得します `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="f1459-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="f1459-134">次に、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。</span><span class="sxs-lookup"><span data-stu-id="f1459-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="f1459-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1459-135">Related topics</span></span>
- [<span data-ttu-id="f1459-136">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="f1459-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f1459-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f1459-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f1459-138">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f1459-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)