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
ms.openlocfilehash: 6d860e20bdd116d579b3cb178e3352825c60fe44
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500899"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="4cf74-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="4cf74-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4cf74-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4cf74-105">**Applies to:**</span></span>
- <span data-ttu-id="4cf74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cf74-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4cf74-107">高度 `DeviceNetworkInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、コンピューターのネットワーク構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4cf74-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="4cf74-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cf74-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4cf74-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cf74-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4cf74-110">列名</span><span class="sxs-lookup"><span data-stu-id="4cf74-110">Column name</span></span> | <span data-ttu-id="4cf74-111">データ型</span><span class="sxs-lookup"><span data-stu-id="4cf74-111">Data type</span></span> | <span data-ttu-id="4cf74-112">説明</span><span class="sxs-lookup"><span data-stu-id="4cf74-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4cf74-113">日付型</span><span class="sxs-lookup"><span data-stu-id="4cf74-113">datetime</span></span> | <span data-ttu-id="4cf74-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="4cf74-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4cf74-115">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-115">string</span></span> | <span data-ttu-id="4cf74-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="4cf74-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4cf74-117">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-117">string</span></span> | <span data-ttu-id="4cf74-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4cf74-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="4cf74-119">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-119">string</span></span> | <span data-ttu-id="4cf74-120">ネットワーク アダプターの名前</span><span class="sxs-lookup"><span data-stu-id="4cf74-120">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="4cf74-121">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-121">string</span></span> | <span data-ttu-id="4cf74-122">ネットワーク アダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="4cf74-122">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="4cf74-123">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-123">string</span></span> | <span data-ttu-id="4cf74-124">ネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="4cf74-124">Network adapter type.</span></span> <span data-ttu-id="4cf74-125">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="4cf74-125">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="4cf74-126">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-126">string</span></span> | <span data-ttu-id="4cf74-127">ネットワーク アダプターの運用状態。</span><span class="sxs-lookup"><span data-stu-id="4cf74-127">Operational status of the network adapter.</span></span> <span data-ttu-id="4cf74-128">使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="4cf74-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="4cf74-129">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-129">string</span></span> | <span data-ttu-id="4cf74-130">トンネリング プロトコル (インターフェイスが 6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) に使用されている場合</span><span class="sxs-lookup"><span data-stu-id="4cf74-130">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="4cf74-131">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-131">string</span></span> | <span data-ttu-id="4cf74-132">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="4cf74-132">Networks that the adapter is connected to.</span></span> <span data-ttu-id="4cf74-133">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="4cf74-133">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="4cf74-134">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-134">string</span></span> | <span data-ttu-id="4cf74-135">JSON 配列形式の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="4cf74-135">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="4cf74-136">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-136">string</span></span> | <span data-ttu-id="4cf74-137">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="4cf74-137">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="4cf74-138">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-138">string</span></span> | <span data-ttu-id="4cf74-139">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="4cf74-139">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="4cf74-140">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-140">string</span></span> | <span data-ttu-id="4cf74-141">JSON 配列形式の既定のゲートウェイ アドレス</span><span class="sxs-lookup"><span data-stu-id="4cf74-141">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="4cf74-142">文字列</span><span class="sxs-lookup"><span data-stu-id="4cf74-142">string</span></span> | <span data-ttu-id="4cf74-143">アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス空間 (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列</span><span class="sxs-lookup"><span data-stu-id="4cf74-143">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="4cf74-144">long</span><span class="sxs-lookup"><span data-stu-id="4cf74-144">long</span></span> | <span data-ttu-id="4cf74-145">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="4cf74-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4cf74-146">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cf74-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4cf74-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cf74-147">Related topics</span></span>
- [<span data-ttu-id="4cf74-148">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="4cf74-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4cf74-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="4cf74-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4cf74-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="4cf74-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4cf74-151">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="4cf74-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4cf74-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="4cf74-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4cf74-153">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="4cf74-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)