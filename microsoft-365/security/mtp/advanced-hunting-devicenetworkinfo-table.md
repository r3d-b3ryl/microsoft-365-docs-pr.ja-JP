---
title: 高度な検索スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machinenetworkinfo、DeviceNetworkInfo、device、machine、mac、ip、adapter、dns、dhcp、gateway、tunnel
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
ms.openlocfilehash: 0fd6000f4d3a4b9fafb0eede74cbbe4e6c3d494e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899245"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="595fb-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="595fb-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="595fb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="595fb-105">**Applies to:**</span></span>
- <span data-ttu-id="595fb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="595fb-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="595fb-107">`DeviceNetworkInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、ネットワークアダプター、IP アドレスと MAC アドレス、および接続されたネットワークまたはドメインなど、マシンのネットワーク構成に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="595fb-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="595fb-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="595fb-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="595fb-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="595fb-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="595fb-110">列名</span><span class="sxs-lookup"><span data-stu-id="595fb-110">Column name</span></span> | <span data-ttu-id="595fb-111">データ型</span><span class="sxs-lookup"><span data-stu-id="595fb-111">Data type</span></span> | <span data-ttu-id="595fb-112">説明</span><span class="sxs-lookup"><span data-stu-id="595fb-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="595fb-113">日付型</span><span class="sxs-lookup"><span data-stu-id="595fb-113">datetime</span></span> | <span data-ttu-id="595fb-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="595fb-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="595fb-115">string</span><span class="sxs-lookup"><span data-stu-id="595fb-115">string</span></span> | <span data-ttu-id="595fb-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="595fb-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="595fb-117">string</span><span class="sxs-lookup"><span data-stu-id="595fb-117">string</span></span> | <span data-ttu-id="595fb-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="595fb-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="595fb-119">long</span><span class="sxs-lookup"><span data-stu-id="595fb-119">long</span></span> | <span data-ttu-id="595fb-120">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="595fb-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="595fb-121">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="595fb-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="595fb-122">string</span><span class="sxs-lookup"><span data-stu-id="595fb-122">string</span></span> | <span data-ttu-id="595fb-123">ネットワークアダプターの名前</span><span class="sxs-lookup"><span data-stu-id="595fb-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="595fb-124">string</span><span class="sxs-lookup"><span data-stu-id="595fb-124">string</span></span> | <span data-ttu-id="595fb-125">ネットワークアダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="595fb-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="595fb-126">string</span><span class="sxs-lookup"><span data-stu-id="595fb-126">string</span></span> | <span data-ttu-id="595fb-127">ネットワークアダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="595fb-127">Network adapter type.</span></span> <span data-ttu-id="595fb-128">可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="595fb-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="595fb-129">string</span><span class="sxs-lookup"><span data-stu-id="595fb-129">string</span></span> | <span data-ttu-id="595fb-130">ネットワークアダプターの動作状態。</span><span class="sxs-lookup"><span data-stu-id="595fb-130">Operational status of the network adapter.</span></span> <span data-ttu-id="595fb-131">可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="595fb-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="595fb-132">string</span><span class="sxs-lookup"><span data-stu-id="595fb-132">string</span></span> | <span data-ttu-id="595fb-133">トンネリングプロトコル (6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) にインターフェイスが使用されている場合</span><span class="sxs-lookup"><span data-stu-id="595fb-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="595fb-134">string</span><span class="sxs-lookup"><span data-stu-id="595fb-134">string</span></span> | <span data-ttu-id="595fb-135">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="595fb-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="595fb-136">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベートまたはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="595fb-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="595fb-137">string</span><span class="sxs-lookup"><span data-stu-id="595fb-137">string</span></span> | <span data-ttu-id="595fb-138">JSON 配列形式の DNS サーバーアドレス</span><span class="sxs-lookup"><span data-stu-id="595fb-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="595fb-139">string</span><span class="sxs-lookup"><span data-stu-id="595fb-139">string</span></span> | <span data-ttu-id="595fb-140">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="595fb-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="595fb-141">string</span><span class="sxs-lookup"><span data-stu-id="595fb-141">string</span></span> | <span data-ttu-id="595fb-142">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="595fb-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="595fb-143">string</span><span class="sxs-lookup"><span data-stu-id="595fb-143">string</span></span> | <span data-ttu-id="595fb-144">JSON 配列形式の既定のゲートウェイアドレス</span><span class="sxs-lookup"><span data-stu-id="595fb-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="595fb-145">string</span><span class="sxs-lookup"><span data-stu-id="595fb-145">string</span></span> | <span data-ttu-id="595fb-146">アダプターに割り当てられたすべての IP アドレスと、それぞれのサブネットプレフィックスと IP アドレス空間 (パブリック、プライベート、リンクローカルなど) を含む JSON 配列。</span><span class="sxs-lookup"><span data-stu-id="595fb-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="595fb-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="595fb-147">Related topics</span></span>
- [<span data-ttu-id="595fb-148">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="595fb-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="595fb-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="595fb-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="595fb-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="595fb-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="595fb-151">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="595fb-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="595fb-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="595fb-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="595fb-153">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="595fb-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
