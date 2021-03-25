---
title: 高度なハンティング スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、devicenetworkinfo、デバイス、mac、IP、アダプター、dns、dhcp、ゲートウェイ、トンネル、DeviceNetworkInfo
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
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067052"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="edf02-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="edf02-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="edf02-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="edf02-105">**Applies to:**</span></span>
- [<span data-ttu-id="edf02-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="edf02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="edf02-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="edf02-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="edf02-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="edf02-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="edf02-109">高度 `DeviceNetworkInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、デバイスのネットワーク構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="edf02-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="edf02-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="edf02-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="edf02-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="edf02-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="edf02-112">列名</span><span class="sxs-lookup"><span data-stu-id="edf02-112">Column name</span></span> | <span data-ttu-id="edf02-113">データ型</span><span class="sxs-lookup"><span data-stu-id="edf02-113">Data type</span></span> | <span data-ttu-id="edf02-114">説明</span><span class="sxs-lookup"><span data-stu-id="edf02-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="edf02-115">日付型</span><span class="sxs-lookup"><span data-stu-id="edf02-115">datetime</span></span> | <span data-ttu-id="edf02-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="edf02-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="edf02-117">string</span><span class="sxs-lookup"><span data-stu-id="edf02-117">string</span></span> | <span data-ttu-id="edf02-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="edf02-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="edf02-119">string</span><span class="sxs-lookup"><span data-stu-id="edf02-119">string</span></span> | <span data-ttu-id="edf02-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="edf02-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="edf02-121">long</span><span class="sxs-lookup"><span data-stu-id="edf02-121">long</span></span> | <span data-ttu-id="edf02-122">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="edf02-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="edf02-123">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="edf02-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="edf02-124">string</span><span class="sxs-lookup"><span data-stu-id="edf02-124">string</span></span> | <span data-ttu-id="edf02-125">ネットワーク アダプターの名前</span><span class="sxs-lookup"><span data-stu-id="edf02-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="edf02-126">string</span><span class="sxs-lookup"><span data-stu-id="edf02-126">string</span></span> | <span data-ttu-id="edf02-127">ネットワーク アダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="edf02-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="edf02-128">string</span><span class="sxs-lookup"><span data-stu-id="edf02-128">string</span></span> | <span data-ttu-id="edf02-129">ネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="edf02-129">Network adapter type.</span></span> <span data-ttu-id="edf02-130">使用できる値については、この列挙 [を参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="edf02-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="edf02-131">string</span><span class="sxs-lookup"><span data-stu-id="edf02-131">string</span></span> | <span data-ttu-id="edf02-132">ネットワーク アダプターの運用状態。</span><span class="sxs-lookup"><span data-stu-id="edf02-132">Operational status of the network adapter.</span></span> <span data-ttu-id="edf02-133">使用できる値については、この列挙 [を参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="edf02-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="edf02-134">string</span><span class="sxs-lookup"><span data-stu-id="edf02-134">string</span></span> | <span data-ttu-id="edf02-135">トンネリング プロトコル (インターフェイスが 6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) に使用されている場合</span><span class="sxs-lookup"><span data-stu-id="edf02-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="edf02-136">string</span><span class="sxs-lookup"><span data-stu-id="edf02-136">string</span></span> | <span data-ttu-id="edf02-137">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="edf02-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="edf02-138">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="edf02-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="edf02-139">string</span><span class="sxs-lookup"><span data-stu-id="edf02-139">string</span></span> | <span data-ttu-id="edf02-140">JSON 配列形式の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="edf02-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="edf02-141">string</span><span class="sxs-lookup"><span data-stu-id="edf02-141">string</span></span> | <span data-ttu-id="edf02-142">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="edf02-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="edf02-143">string</span><span class="sxs-lookup"><span data-stu-id="edf02-143">string</span></span> | <span data-ttu-id="edf02-144">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="edf02-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="edf02-145">string</span><span class="sxs-lookup"><span data-stu-id="edf02-145">string</span></span> | <span data-ttu-id="edf02-146">JSON 配列形式の既定のゲートウェイ アドレス</span><span class="sxs-lookup"><span data-stu-id="edf02-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="edf02-147">string</span><span class="sxs-lookup"><span data-stu-id="edf02-147">string</span></span> | <span data-ttu-id="edf02-148">アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス空間 (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列</span><span class="sxs-lookup"><span data-stu-id="edf02-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="edf02-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="edf02-149">Related topics</span></span>
- [<span data-ttu-id="edf02-150">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="edf02-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="edf02-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="edf02-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="edf02-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="edf02-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
