---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machineinfo、DeviceInfo、デバイス、マシン、OS、プラットフォーム、ユーザー
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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023131"
---
# <a name="deviceinfo"></a><span data-ttu-id="b87c4-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="b87c4-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b87c4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b87c4-105">**Applies to:**</span></span>
- <span data-ttu-id="b87c4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b87c4-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b87c4-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b87c4-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="b87c4-108">高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="b87c4-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="b87c4-109">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b87c4-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b87c4-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b87c4-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b87c4-111">列名</span><span class="sxs-lookup"><span data-stu-id="b87c4-111">Column name</span></span> | <span data-ttu-id="b87c4-112">データ型</span><span class="sxs-lookup"><span data-stu-id="b87c4-112">Data type</span></span> | <span data-ttu-id="b87c4-113">説明</span><span class="sxs-lookup"><span data-stu-id="b87c4-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b87c4-114">日付型</span><span class="sxs-lookup"><span data-stu-id="b87c4-114">datetime</span></span> | <span data-ttu-id="b87c4-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="b87c4-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b87c4-116">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-116">string</span></span> | <span data-ttu-id="b87c4-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b87c4-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b87c4-118">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-118">string</span></span> | <span data-ttu-id="b87c4-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b87c4-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="b87c4-120">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-120">string</span></span> | <span data-ttu-id="b87c4-121">コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="b87c4-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="b87c4-122">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-122">string</span></span> | <span data-ttu-id="b87c4-123">オンボード コンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="b87c4-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="b87c4-124">これは、コンピューター自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b87c4-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="b87c4-125">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-125">string</span></span> | <span data-ttu-id="b87c4-126">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="b87c4-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b87c4-127">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-127">string</span></span> | <span data-ttu-id="b87c4-128">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="b87c4-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b87c4-129">これは、特定のオペレーティング システム (同じファミリ内のバリエーション (Windows 10および Windows 7 など) を示します。</span><span class="sxs-lookup"><span data-stu-id="b87c4-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="b87c4-130">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-130">string</span></span> | <span data-ttu-id="b87c4-131">コンピューターで実行されているオペレーティング システムのバージョンをビルドする</span><span class="sxs-lookup"><span data-stu-id="b87c4-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="b87c4-132">boolean</span><span class="sxs-lookup"><span data-stu-id="b87c4-132">boolean</span></span> | <span data-ttu-id="b87c4-133">コンピューターがコンピューターに参加しているかどうかを示すブールAzure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b87c4-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="b87c4-134">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-134">string</span></span> | <span data-ttu-id="b87c4-135">Azure のデバイスの一意の識別子AD</span><span class="sxs-lookup"><span data-stu-id="b87c4-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="b87c4-136">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-136">string</span></span> | <span data-ttu-id="b87c4-137">JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="b87c4-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="b87c4-138">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-138">string</span></span> | <span data-ttu-id="b87c4-139">レジストリを介して追加されたコンピューター タグ</span><span class="sxs-lookup"><span data-stu-id="b87c4-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="b87c4-140">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-140">string</span></span> | <span data-ttu-id="b87c4-141">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="b87c4-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="b87c4-142">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-142">string</span></span> | <span data-ttu-id="b87c4-143">コンピューターのコンピューター グループ。</span><span class="sxs-lookup"><span data-stu-id="b87c4-143">Machine group of the machine.</span></span> <span data-ttu-id="b87c4-144">このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b87c4-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="b87c4-145">long</span><span class="sxs-lookup"><span data-stu-id="b87c4-145">long</span></span> | <span data-ttu-id="b87c4-146">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="b87c4-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b87c4-147">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b87c4-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="b87c4-148">string</span><span class="sxs-lookup"><span data-stu-id="b87c4-148">string</span></span> | <span data-ttu-id="b87c4-149">JSON 配列形式のイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="b87c4-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="b87c4-150">この表は、定期的なレポートまたはデバイスからの信号であるハートビートに基づくデバイス `DeviceInfo` 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b87c4-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="b87c4-151">15 分ごとに、デバイスは頻繁に変更される属性を含む部分的なハートビートを送信します `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="b87c4-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="b87c4-152">1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b87c4-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="b87c4-153">次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b87c4-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="b87c4-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b87c4-154">Related topics</span></span>
- [<span data-ttu-id="b87c4-155">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="b87c4-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b87c4-156">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="b87c4-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b87c4-157">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="b87c4-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b87c4-158">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="b87c4-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b87c4-159">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="b87c4-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b87c4-160">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="b87c4-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
