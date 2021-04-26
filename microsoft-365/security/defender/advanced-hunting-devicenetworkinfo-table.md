---
title: 高度なハンティング スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度なハンティング、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machinenetworkinfo、DeviceNetworkInfo、デバイス、コンピューター、mac、ip、アダプター、dns、dhcp、ゲートウェイ、トンネル
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
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023191"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="d7495-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="d7495-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7495-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d7495-105">**Applies to:**</span></span>
- <span data-ttu-id="d7495-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7495-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d7495-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7495-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="d7495-108">高度 `DeviceNetworkInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、コンピューターのネットワーク構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d7495-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="d7495-109">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7495-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="d7495-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7495-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d7495-111">列名</span><span class="sxs-lookup"><span data-stu-id="d7495-111">Column name</span></span> | <span data-ttu-id="d7495-112">データ型</span><span class="sxs-lookup"><span data-stu-id="d7495-112">Data type</span></span> | <span data-ttu-id="d7495-113">説明</span><span class="sxs-lookup"><span data-stu-id="d7495-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d7495-114">日付型</span><span class="sxs-lookup"><span data-stu-id="d7495-114">datetime</span></span> | <span data-ttu-id="d7495-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="d7495-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d7495-116">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-116">string</span></span> | <span data-ttu-id="d7495-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="d7495-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d7495-118">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-118">string</span></span> | <span data-ttu-id="d7495-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d7495-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="d7495-120">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-120">string</span></span> | <span data-ttu-id="d7495-121">ネットワーク アダプターの名前</span><span class="sxs-lookup"><span data-stu-id="d7495-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="d7495-122">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-122">string</span></span> | <span data-ttu-id="d7495-123">ネットワーク アダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="d7495-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="d7495-124">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-124">string</span></span> | <span data-ttu-id="d7495-125">ネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="d7495-125">Network adapter type.</span></span> <span data-ttu-id="d7495-126">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="d7495-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="d7495-127">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-127">string</span></span> | <span data-ttu-id="d7495-128">ネットワーク アダプターの運用状態。</span><span class="sxs-lookup"><span data-stu-id="d7495-128">Operational status of the network adapter.</span></span> <span data-ttu-id="d7495-129">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="d7495-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="d7495-130">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-130">string</span></span> | <span data-ttu-id="d7495-131">トンネリング プロトコル (インターフェイスが 6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) に使用されている場合</span><span class="sxs-lookup"><span data-stu-id="d7495-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="d7495-132">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-132">string</span></span> | <span data-ttu-id="d7495-133">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="d7495-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="d7495-134">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="d7495-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="d7495-135">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-135">string</span></span> | <span data-ttu-id="d7495-136">JSON 配列形式の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="d7495-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="d7495-137">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-137">string</span></span> | <span data-ttu-id="d7495-138">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="d7495-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="d7495-139">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-139">string</span></span> | <span data-ttu-id="d7495-140">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="d7495-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="d7495-141">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-141">string</span></span> | <span data-ttu-id="d7495-142">JSON 配列形式の既定のゲートウェイ アドレス</span><span class="sxs-lookup"><span data-stu-id="d7495-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="d7495-143">文字列</span><span class="sxs-lookup"><span data-stu-id="d7495-143">string</span></span> | <span data-ttu-id="d7495-144">アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス空間 (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列</span><span class="sxs-lookup"><span data-stu-id="d7495-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="d7495-145">long</span><span class="sxs-lookup"><span data-stu-id="d7495-145">long</span></span> | <span data-ttu-id="d7495-146">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="d7495-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d7495-147">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7495-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d7495-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7495-148">Related topics</span></span>
- [<span data-ttu-id="d7495-149">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="d7495-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d7495-150">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d7495-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d7495-151">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="d7495-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d7495-152">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="d7495-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d7495-153">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d7495-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d7495-154">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="d7495-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)