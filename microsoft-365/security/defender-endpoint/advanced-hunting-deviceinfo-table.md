---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のデバイス情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、deviceinfo、deviceinfo、デバイス、OS、プラットフォーム、ユーザー、DeviceInfo
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
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067067"
---
# <a name="deviceinfo"></a><span data-ttu-id="733eb-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="733eb-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="733eb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="733eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="733eb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="733eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="733eb-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="733eb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="733eb-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="733eb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="733eb-109">高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、組織内のデバイスに関する情報 (OS バージョン、アクティブ ユーザー、コンピューター名など) が含まれている。</span><span class="sxs-lookup"><span data-stu-id="733eb-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="733eb-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="733eb-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="733eb-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="733eb-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="733eb-112">列名</span><span class="sxs-lookup"><span data-stu-id="733eb-112">Column name</span></span> | <span data-ttu-id="733eb-113">データ型</span><span class="sxs-lookup"><span data-stu-id="733eb-113">Data type</span></span> | <span data-ttu-id="733eb-114">説明</span><span class="sxs-lookup"><span data-stu-id="733eb-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="733eb-115">日付型</span><span class="sxs-lookup"><span data-stu-id="733eb-115">datetime</span></span> | <span data-ttu-id="733eb-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="733eb-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="733eb-117">string</span><span class="sxs-lookup"><span data-stu-id="733eb-117">string</span></span> | <span data-ttu-id="733eb-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="733eb-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="733eb-119">string</span><span class="sxs-lookup"><span data-stu-id="733eb-119">string</span></span> | <span data-ttu-id="733eb-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="733eb-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="733eb-121">string</span><span class="sxs-lookup"><span data-stu-id="733eb-121">string</span></span> | <span data-ttu-id="733eb-122">デバイスで実行されているエンドポイント エージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="733eb-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="733eb-123">string</span><span class="sxs-lookup"><span data-stu-id="733eb-123">string</span></span> | <span data-ttu-id="733eb-124">オンボード デバイスが Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="733eb-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="733eb-125">これは、デバイス自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="733eb-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="733eb-126">string</span><span class="sxs-lookup"><span data-stu-id="733eb-126">string</span></span> | <span data-ttu-id="733eb-127">デバイスで実行されているオペレーティング システムのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="733eb-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="733eb-128">string</span><span class="sxs-lookup"><span data-stu-id="733eb-128">string</span></span> | <span data-ttu-id="733eb-129">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="733eb-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="733eb-130">これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="733eb-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="733eb-131">string</span><span class="sxs-lookup"><span data-stu-id="733eb-131">string</span></span> | <span data-ttu-id="733eb-132">デバイスで実行されているオペレーティング システムのバージョンをビルドする</span><span class="sxs-lookup"><span data-stu-id="733eb-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="733eb-133">boolean</span><span class="sxs-lookup"><span data-stu-id="733eb-133">boolean</span></span> | <span data-ttu-id="733eb-134">デバイスが Azure Active Directory に参加するかどうかを示すブール値インジケーター</span><span class="sxs-lookup"><span data-stu-id="733eb-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="733eb-135">string</span><span class="sxs-lookup"><span data-stu-id="733eb-135">string</span></span> | <span data-ttu-id="733eb-136">JSON 配列形式のイベント時にデバイスにログオンしているすべてのユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="733eb-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="733eb-137">string</span><span class="sxs-lookup"><span data-stu-id="733eb-137">string</span></span> | <span data-ttu-id="733eb-138">レジストリを介して追加されたデバイス タグ</span><span class="sxs-lookup"><span data-stu-id="733eb-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="733eb-139">long</span><span class="sxs-lookup"><span data-stu-id="733eb-139">long</span></span> | <span data-ttu-id="733eb-140">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="733eb-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="733eb-141">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="733eb-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="733eb-142">string</span><span class="sxs-lookup"><span data-stu-id="733eb-142">string</span></span> | <span data-ttu-id="733eb-143">デバイスで実行されているオペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="733eb-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="733eb-144">string</span><span class="sxs-lookup"><span data-stu-id="733eb-144">string</span></span> | <span data-ttu-id="733eb-145">コンピューターのコンピューター グループ。</span><span class="sxs-lookup"><span data-stu-id="733eb-145">Machine group of the machine.</span></span> <span data-ttu-id="733eb-146">このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="733eb-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="733eb-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="733eb-147">Related topics</span></span>
- [<span data-ttu-id="733eb-148">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="733eb-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="733eb-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="733eb-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="733eb-150">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="733eb-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
