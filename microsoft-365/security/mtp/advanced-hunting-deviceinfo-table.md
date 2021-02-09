---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルにある OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、machineinfo、DeviceInfo、デバイス、コンピューター、OS、プラットフォーム、ユーザー
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145369"
---
# <a name="deviceinfo"></a><span data-ttu-id="81ca8-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="81ca8-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81ca8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="81ca8-105">**Applies to:**</span></span>
- <span data-ttu-id="81ca8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81ca8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="81ca8-107">高度 `DeviceInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のコンピューターに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="81ca8-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="81ca8-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="81ca8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="81ca8-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ca8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="81ca8-110">列名</span><span class="sxs-lookup"><span data-stu-id="81ca8-110">Column name</span></span> | <span data-ttu-id="81ca8-111">データ型</span><span class="sxs-lookup"><span data-stu-id="81ca8-111">Data type</span></span> | <span data-ttu-id="81ca8-112">説明</span><span class="sxs-lookup"><span data-stu-id="81ca8-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="81ca8-113">日付型</span><span class="sxs-lookup"><span data-stu-id="81ca8-113">datetime</span></span> | <span data-ttu-id="81ca8-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="81ca8-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="81ca8-115">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-115">string</span></span> | <span data-ttu-id="81ca8-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="81ca8-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="81ca8-117">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-117">string</span></span> | <span data-ttu-id="81ca8-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="81ca8-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="81ca8-119">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-119">string</span></span> | <span data-ttu-id="81ca8-120">コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="81ca8-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="81ca8-121">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-121">string</span></span> | <span data-ttu-id="81ca8-122">オンボードしたコンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="81ca8-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="81ca8-123">コンピューター自体の IP アドレス、NAT デバイス、プロキシなどです。</span><span class="sxs-lookup"><span data-stu-id="81ca8-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="81ca8-124">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-124">string</span></span> | <span data-ttu-id="81ca8-125">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="81ca8-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="81ca8-126">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-126">string</span></span> | <span data-ttu-id="81ca8-127">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="81ca8-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="81ca8-128">これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="81ca8-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="81ca8-129">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-129">string</span></span> | <span data-ttu-id="81ca8-130">コンピューターで実行されているオペレーティング システムのビルド バージョン</span><span class="sxs-lookup"><span data-stu-id="81ca8-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="81ca8-131">boolean</span><span class="sxs-lookup"><span data-stu-id="81ca8-131">boolean</span></span> | <span data-ttu-id="81ca8-132">コンピューターが Azure Active Directory に参加しているかどうかを示すブールインジケーター</span><span class="sxs-lookup"><span data-stu-id="81ca8-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `DeviceObjectId` | <span data-ttu-id="81ca8-133">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-133">string</span></span> | <span data-ttu-id="81ca8-134">Azure AD のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="81ca8-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="81ca8-135">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-135">string</span></span> | <span data-ttu-id="81ca8-136">イベントの時点でコンピューターにログオンしているすべてのユーザーの一覧 (JSON 配列形式)</span><span class="sxs-lookup"><span data-stu-id="81ca8-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="81ca8-137">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-137">string</span></span> | <span data-ttu-id="81ca8-138">レジストリを介して追加されたコンピューター タグ</span><span class="sxs-lookup"><span data-stu-id="81ca8-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="81ca8-139">long</span><span class="sxs-lookup"><span data-stu-id="81ca8-139">long</span></span> | <span data-ttu-id="81ca8-140">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="81ca8-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="81ca8-141">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ca8-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="81ca8-142">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-142">string</span></span> | <span data-ttu-id="81ca8-143">JSON 配列形式でのイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="81ca8-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="81ca8-144">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-144">string</span></span> | <span data-ttu-id="81ca8-145">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="81ca8-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="81ca8-146">string</span><span class="sxs-lookup"><span data-stu-id="81ca8-146">string</span></span> | <span data-ttu-id="81ca8-147">コンピューターのコンピューター グループ。</span><span class="sxs-lookup"><span data-stu-id="81ca8-147">Machine group of the machine.</span></span> <span data-ttu-id="81ca8-148">このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="81ca8-148">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="81ca8-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="81ca8-149">Related topics</span></span>
- [<span data-ttu-id="81ca8-150">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="81ca8-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81ca8-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="81ca8-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="81ca8-152">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="81ca8-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="81ca8-153">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="81ca8-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="81ca8-154">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="81ca8-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="81ca8-155">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="81ca8-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
