---
title: 高度なハンティング スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威の保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、machinenetworkinfo、DeviceNetworkInfo、デバイス、コンピューター、mac、ip、アダプター、dns、dhcp、ゲートウェイ、トンネル
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1c8a3f3ab91add9e057c4661677997e658f42386
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063508"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="9bd85-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="9bd85-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9bd85-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9bd85-105">**Applies to:**</span></span>
- <span data-ttu-id="9bd85-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bd85-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9bd85-107">高度 `DeviceNetworkInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、コンピューターのネットワーク構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9bd85-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="9bd85-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bd85-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9bd85-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bd85-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9bd85-110">列名</span><span class="sxs-lookup"><span data-stu-id="9bd85-110">Column name</span></span> | <span data-ttu-id="9bd85-111">データ型</span><span class="sxs-lookup"><span data-stu-id="9bd85-111">Data type</span></span> | <span data-ttu-id="9bd85-112">説明</span><span class="sxs-lookup"><span data-stu-id="9bd85-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9bd85-113">日付型</span><span class="sxs-lookup"><span data-stu-id="9bd85-113">datetime</span></span> | <span data-ttu-id="9bd85-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="9bd85-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9bd85-115">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-115">string</span></span> | <span data-ttu-id="9bd85-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9bd85-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9bd85-117">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-117">string</span></span> | <span data-ttu-id="9bd85-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9bd85-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="9bd85-119">long</span><span class="sxs-lookup"><span data-stu-id="9bd85-119">long</span></span> | <span data-ttu-id="9bd85-120">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="9bd85-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9bd85-121">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd85-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="9bd85-122">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-122">string</span></span> | <span data-ttu-id="9bd85-123">ネットワーク アダプターの名前</span><span class="sxs-lookup"><span data-stu-id="9bd85-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="9bd85-124">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-124">string</span></span> | <span data-ttu-id="9bd85-125">ネットワーク アダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="9bd85-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="9bd85-126">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-126">string</span></span> | <span data-ttu-id="9bd85-127">ネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="9bd85-127">Network adapter type.</span></span> <span data-ttu-id="9bd85-128">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9bd85-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="9bd85-129">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-129">string</span></span> | <span data-ttu-id="9bd85-130">ネットワーク アダプターの運用状態。</span><span class="sxs-lookup"><span data-stu-id="9bd85-130">Operational status of the network adapter.</span></span> <span data-ttu-id="9bd85-131">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9bd85-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="9bd85-132">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-132">string</span></span> | <span data-ttu-id="9bd85-133">トンネリング プロトコル (インターフェイスが 6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) に使用されている場合</span><span class="sxs-lookup"><span data-stu-id="9bd85-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="9bd85-134">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-134">string</span></span> | <span data-ttu-id="9bd85-135">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="9bd85-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="9bd85-136">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="9bd85-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="9bd85-137">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-137">string</span></span> | <span data-ttu-id="9bd85-138">JSON 配列形式の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="9bd85-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="9bd85-139">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-139">string</span></span> | <span data-ttu-id="9bd85-140">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="9bd85-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="9bd85-141">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-141">string</span></span> | <span data-ttu-id="9bd85-142">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="9bd85-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="9bd85-143">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-143">string</span></span> | <span data-ttu-id="9bd85-144">JSON 配列形式の既定のゲートウェイ アドレス</span><span class="sxs-lookup"><span data-stu-id="9bd85-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="9bd85-145">string</span><span class="sxs-lookup"><span data-stu-id="9bd85-145">string</span></span> | <span data-ttu-id="9bd85-146">アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス空間 (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列</span><span class="sxs-lookup"><span data-stu-id="9bd85-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9bd85-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bd85-147">Related topics</span></span>
- [<span data-ttu-id="9bd85-148">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="9bd85-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9bd85-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="9bd85-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9bd85-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="9bd85-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9bd85-151">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="9bd85-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9bd85-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9bd85-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9bd85-153">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="9bd85-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)