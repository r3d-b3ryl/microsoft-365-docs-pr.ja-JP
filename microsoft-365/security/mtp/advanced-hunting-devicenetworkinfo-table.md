---
title: 高度な検索スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、machinenetworkinfo、DeviceNetworkInfo、デバイス、コンピューター、mac、ip、アダプター、dns、dhcp、ゲートウェイ、トンネル
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931208"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="6138f-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="6138f-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6138f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6138f-105">**Applies to:**</span></span>
- <span data-ttu-id="6138f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6138f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6138f-107">高度 `DeviceNetworkInfo` な検索スキーマ[](advanced-hunting-overview.md)の表には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、コンピューターのネットワーク構成に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6138f-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="6138f-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6138f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6138f-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6138f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6138f-110">列名</span><span class="sxs-lookup"><span data-stu-id="6138f-110">Column name</span></span> | <span data-ttu-id="6138f-111">データ型</span><span class="sxs-lookup"><span data-stu-id="6138f-111">Data type</span></span> | <span data-ttu-id="6138f-112">説明</span><span class="sxs-lookup"><span data-stu-id="6138f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6138f-113">日付型</span><span class="sxs-lookup"><span data-stu-id="6138f-113">datetime</span></span> | <span data-ttu-id="6138f-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="6138f-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6138f-115">string</span><span class="sxs-lookup"><span data-stu-id="6138f-115">string</span></span> | <span data-ttu-id="6138f-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="6138f-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6138f-117">string</span><span class="sxs-lookup"><span data-stu-id="6138f-117">string</span></span> | <span data-ttu-id="6138f-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6138f-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="6138f-119">long</span><span class="sxs-lookup"><span data-stu-id="6138f-119">long</span></span> | <span data-ttu-id="6138f-120">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="6138f-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6138f-121">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6138f-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="6138f-122">string</span><span class="sxs-lookup"><span data-stu-id="6138f-122">string</span></span> | <span data-ttu-id="6138f-123">ネットワーク アダプターの名前</span><span class="sxs-lookup"><span data-stu-id="6138f-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="6138f-124">string</span><span class="sxs-lookup"><span data-stu-id="6138f-124">string</span></span> | <span data-ttu-id="6138f-125">ネットワーク アダプターの MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="6138f-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="6138f-126">string</span><span class="sxs-lookup"><span data-stu-id="6138f-126">string</span></span> | <span data-ttu-id="6138f-127">ネットワーク アダプターの種類。</span><span class="sxs-lookup"><span data-stu-id="6138f-127">Network adapter type.</span></span> <span data-ttu-id="6138f-128">使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="6138f-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="6138f-129">string</span><span class="sxs-lookup"><span data-stu-id="6138f-129">string</span></span> | <span data-ttu-id="6138f-130">ネットワーク アダプターの動作状態。</span><span class="sxs-lookup"><span data-stu-id="6138f-130">Operational status of the network adapter.</span></span> <span data-ttu-id="6138f-131">使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="6138f-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="6138f-132">string</span><span class="sxs-lookup"><span data-stu-id="6138f-132">string</span></span> | <span data-ttu-id="6138f-133">トンネリング プロトコル (この目的でインターフェイスを使用する場合(6to4、Teredo、ISATAP、PPTP、SSTP、SSH など)</span><span class="sxs-lookup"><span data-stu-id="6138f-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="6138f-134">string</span><span class="sxs-lookup"><span data-stu-id="6138f-134">string</span></span> | <span data-ttu-id="6138f-135">アダプターが接続されているネットワーク。</span><span class="sxs-lookup"><span data-stu-id="6138f-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="6138f-136">各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびそれがインターネットに一般に接続されていることを示すフラグが含まれる</span><span class="sxs-lookup"><span data-stu-id="6138f-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="6138f-137">string</span><span class="sxs-lookup"><span data-stu-id="6138f-137">string</span></span> | <span data-ttu-id="6138f-138">JSON 配列形式の DNS サーバー アドレス</span><span class="sxs-lookup"><span data-stu-id="6138f-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="6138f-139">string</span><span class="sxs-lookup"><span data-stu-id="6138f-139">string</span></span> | <span data-ttu-id="6138f-140">DHCP サーバーの IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="6138f-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="6138f-141">string</span><span class="sxs-lookup"><span data-stu-id="6138f-141">string</span></span> | <span data-ttu-id="6138f-142">DHCP サーバーの IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="6138f-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="6138f-143">string</span><span class="sxs-lookup"><span data-stu-id="6138f-143">string</span></span> | <span data-ttu-id="6138f-144">JSON 配列形式の既定のゲートウェイ アドレス</span><span class="sxs-lookup"><span data-stu-id="6138f-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="6138f-145">string</span><span class="sxs-lookup"><span data-stu-id="6138f-145">string</span></span> | <span data-ttu-id="6138f-146">アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス スペース (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列</span><span class="sxs-lookup"><span data-stu-id="6138f-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6138f-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="6138f-147">Related topics</span></span>
- [<span data-ttu-id="6138f-148">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="6138f-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6138f-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="6138f-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6138f-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="6138f-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6138f-151">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="6138f-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6138f-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="6138f-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6138f-153">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="6138f-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
