---
title: Microsoft 365 Defender の高度な検索での AssignedIPAddresses() 関数
description: AssignedIPAddresses() 関数を使用して、デバイスに割り当てられた最新の IP アドレスを取得する方法について
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933020"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="5ba94-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="5ba94-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5ba94-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5ba94-105">**Applies to:**</span></span>
- <span data-ttu-id="5ba94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ba94-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5ba94-107">高度な `AssignedIPAddresses()` 検索クエリの [関数を使用](advanced-hunting-overview.md) して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="5ba94-108">timestamp 引数を指定すると、この関数は指定した時刻に最新の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="5ba94-109">この関数は、次の列を含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="5ba94-110">Column</span><span class="sxs-lookup"><span data-stu-id="5ba94-110">Column</span></span> | <span data-ttu-id="5ba94-111">データ型</span><span class="sxs-lookup"><span data-stu-id="5ba94-111">Data type</span></span> | <span data-ttu-id="5ba94-112">説明</span><span class="sxs-lookup"><span data-stu-id="5ba94-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="5ba94-113">日付型</span><span class="sxs-lookup"><span data-stu-id="5ba94-113">datetime</span></span> | <span data-ttu-id="5ba94-114">IP アドレスを使用してデバイスが確認された最新時刻</span><span class="sxs-lookup"><span data-stu-id="5ba94-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="5ba94-115">string</span><span class="sxs-lookup"><span data-stu-id="5ba94-115">string</span></span> | <span data-ttu-id="5ba94-116">デバイスで使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="5ba94-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="5ba94-117">string</span><span class="sxs-lookup"><span data-stu-id="5ba94-117">string</span></span> | <span data-ttu-id="5ba94-118">IP アドレスがパブリック アドレスかプライベート アドレスかを示します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="5ba94-119">int</span><span class="sxs-lookup"><span data-stu-id="5ba94-119">int</span></span> | <span data-ttu-id="5ba94-120">IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="5ba94-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="5ba94-121">使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="5ba94-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="5ba94-122">int</span><span class="sxs-lookup"><span data-stu-id="5ba94-122">int</span></span> | <span data-ttu-id="5ba94-123">割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="5ba94-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="5ba94-124">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびそれがインターネットに一般に接続されていることを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="5ba94-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="5ba94-125">構文</span><span class="sxs-lookup"><span data-stu-id="5ba94-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="5ba94-126">引数</span><span class="sxs-lookup"><span data-stu-id="5ba94-126">Arguments</span></span>

- <span data-ttu-id="5ba94-127">**x**— `DeviceId` または `DeviceName` デバイスを識別する値</span><span class="sxs-lookup"><span data-stu-id="5ba94-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="5ba94-128">**y**— 特定の時刻から割り当てられた最新の IP アドレスを取得するように関数に指示する `Timestamp` (datetime) 値。</span><span class="sxs-lookup"><span data-stu-id="5ba94-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="5ba94-129">指定しない場合、関数は最新の IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="5ba94-130">例</span><span class="sxs-lookup"><span data-stu-id="5ba94-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="5ba94-131">24 時間前にデバイスで使用された IP アドレスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="5ba94-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="5ba94-132">デバイスで使用される IP アドレスを取得し、デバイスと通信しているデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="5ba94-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="5ba94-133">このクエリは、この関数を使用して、特定の日付 ( ) 以前のデバイス ( ) の割り当てられた IP アドレス `AssignedIPAddresses()` `example-device-name` を取得します `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="5ba94-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="5ba94-134">その後、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。</span><span class="sxs-lookup"><span data-stu-id="5ba94-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="5ba94-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ba94-135">Related topics</span></span>
- [<span data-ttu-id="5ba94-136">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="5ba94-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ba94-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="5ba94-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ba94-138">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="5ba94-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
