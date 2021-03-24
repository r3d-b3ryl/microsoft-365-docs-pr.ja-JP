---
title: エンドポイント用 Microsoft Defender の高度な検索での AssignedIPAddresses() 関数
description: AssignedIPAddresses() 関数を使用してデバイスに割り当てられた最新の IP アドレスを取得する方法について学習する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、Microsoft Defender ATP、エンドポイント用 Microsoft Defender、Windows Defender、Windows Defender ATP、Windows Defender Advanced Threat Protection、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064396"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="419ea-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="419ea-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="419ea-105">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="419ea-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="419ea-106">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="419ea-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="419ea-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="419ea-107">**Applies to:**</span></span>
- [<span data-ttu-id="419ea-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="419ea-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="419ea-109">高度な `AssignedIPAddresses()` 検索クエリの関数を使用して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="419ea-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="419ea-110">タイムスタンプ引数を指定すると、指定した時刻に最新の IP アドレスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="419ea-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="419ea-111">この関数は、次の列を持つテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="419ea-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="419ea-112">Column</span><span class="sxs-lookup"><span data-stu-id="419ea-112">Column</span></span> | <span data-ttu-id="419ea-113">データ型</span><span class="sxs-lookup"><span data-stu-id="419ea-113">Data type</span></span> | <span data-ttu-id="419ea-114">説明</span><span class="sxs-lookup"><span data-stu-id="419ea-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="419ea-115">日付型</span><span class="sxs-lookup"><span data-stu-id="419ea-115">datetime</span></span> | <span data-ttu-id="419ea-116">IP アドレスを使用してデバイスが観察された最新の時刻</span><span class="sxs-lookup"><span data-stu-id="419ea-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="419ea-117">string</span><span class="sxs-lookup"><span data-stu-id="419ea-117">string</span></span> | <span data-ttu-id="419ea-118">デバイスで使用される IP アドレス</span><span class="sxs-lookup"><span data-stu-id="419ea-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="419ea-119">string</span><span class="sxs-lookup"><span data-stu-id="419ea-119">string</span></span> | <span data-ttu-id="419ea-120">IP アドレスがパブリック アドレスかプライベート アドレスかを示します。</span><span class="sxs-lookup"><span data-stu-id="419ea-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="419ea-121">int</span><span class="sxs-lookup"><span data-stu-id="419ea-121">int</span></span> | <span data-ttu-id="419ea-122">IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="419ea-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="419ea-123">使用できる値については、この列挙 [を参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="419ea-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="419ea-124">int</span><span class="sxs-lookup"><span data-stu-id="419ea-124">int</span></span> | <span data-ttu-id="419ea-125">割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="419ea-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="419ea-126">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="419ea-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="419ea-127">構文</span><span class="sxs-lookup"><span data-stu-id="419ea-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="419ea-128">引数</span><span class="sxs-lookup"><span data-stu-id="419ea-128">Arguments</span></span>

- <span data-ttu-id="419ea-129">**x**— `DeviceId` または `DeviceName` デバイスを識別する値</span><span class="sxs-lookup"><span data-stu-id="419ea-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="419ea-130">**y**— 特定の時刻から最新の割り当てられた IP アドレスを取得するように関数に指示する `Timestamp` (datetime) 値。</span><span class="sxs-lookup"><span data-stu-id="419ea-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="419ea-131">指定しない場合、関数は最新の IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="419ea-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="419ea-132">例</span><span class="sxs-lookup"><span data-stu-id="419ea-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="419ea-133">24 時間前にデバイスで使用される IP アドレスの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="419ea-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="419ea-134">デバイスで使用される IP アドレスを取得し、デバイスと通信するデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="419ea-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="419ea-135">このクエリでは、この関数を使用して、デバイス ( ) の割り当てられた IP アドレスを、特定の日付 ( ) のオンまたは前 `AssignedIPAddresses()` `example-device-name` に取得します `example-date` 。</span><span class="sxs-lookup"><span data-stu-id="419ea-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="419ea-136">次に、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。</span><span class="sxs-lookup"><span data-stu-id="419ea-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="419ea-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="419ea-137">Related topics</span></span>

- [<span data-ttu-id="419ea-138">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="419ea-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="419ea-139">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="419ea-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="419ea-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="419ea-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
