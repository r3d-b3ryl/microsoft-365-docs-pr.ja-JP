---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、machineinfo、DeviceInfo、デバイス、コンピューター、OS、プラットフォーム、ユーザー
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
ms.openlocfilehash: b5baf4adf9c9abaf746c1d6c3ea1c29c3b471b0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498596"
---
# <a name="deviceinfo"></a><span data-ttu-id="affa4-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="affa4-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="affa4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="affa4-105">**Applies to:**</span></span>
- <span data-ttu-id="affa4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="affa4-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="affa4-107">高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="affa4-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="affa4-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="affa4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="affa4-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="affa4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="affa4-110">列名</span><span class="sxs-lookup"><span data-stu-id="affa4-110">Column name</span></span> | <span data-ttu-id="affa4-111">データ型</span><span class="sxs-lookup"><span data-stu-id="affa4-111">Data type</span></span> | <span data-ttu-id="affa4-112">説明</span><span class="sxs-lookup"><span data-stu-id="affa4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="affa4-113">日付型</span><span class="sxs-lookup"><span data-stu-id="affa4-113">datetime</span></span> | <span data-ttu-id="affa4-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="affa4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="affa4-115">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-115">string</span></span> | <span data-ttu-id="affa4-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="affa4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="affa4-117">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-117">string</span></span> | <span data-ttu-id="affa4-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="affa4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="affa4-119">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-119">string</span></span> | <span data-ttu-id="affa4-120">コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="affa4-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="affa4-121">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-121">string</span></span> | <span data-ttu-id="affa4-122">オンボード コンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="affa4-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="affa4-123">これは、コンピューター自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="affa4-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="affa4-124">string</span><span class="sxs-lookup"><span data-stu-id="affa4-124">string</span></span> | <span data-ttu-id="affa4-125">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="affa4-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="affa4-126">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-126">string</span></span> | <span data-ttu-id="affa4-127">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="affa4-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="affa4-128">これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="affa4-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="affa4-129">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-129">string</span></span> | <span data-ttu-id="affa4-130">コンピューターで実行されているオペレーティング システムのバージョンをビルドする</span><span class="sxs-lookup"><span data-stu-id="affa4-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="affa4-131">boolean</span><span class="sxs-lookup"><span data-stu-id="affa4-131">boolean</span></span> | <span data-ttu-id="affa4-132">コンピューターが Azure Active Directory に参加するかどうかを示すブール値インジケーター</span><span class="sxs-lookup"><span data-stu-id="affa4-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="affa4-133">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-133">string</span></span> | <span data-ttu-id="affa4-134">Azure のデバイスの一意の識別子AD</span><span class="sxs-lookup"><span data-stu-id="affa4-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="affa4-135">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-135">string</span></span> | <span data-ttu-id="affa4-136">JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="affa4-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="affa4-137">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-137">string</span></span> | <span data-ttu-id="affa4-138">レジストリを介して追加されたコンピューター タグ</span><span class="sxs-lookup"><span data-stu-id="affa4-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="affa4-139">string</span><span class="sxs-lookup"><span data-stu-id="affa4-139">string</span></span> | <span data-ttu-id="affa4-140">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="affa4-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="affa4-141">string</span><span class="sxs-lookup"><span data-stu-id="affa4-141">string</span></span> | <span data-ttu-id="affa4-142">コンピューターのコンピューター グループ。</span><span class="sxs-lookup"><span data-stu-id="affa4-142">Machine group of the machine.</span></span> <span data-ttu-id="affa4-143">このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="affa4-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="affa4-144">long</span><span class="sxs-lookup"><span data-stu-id="affa4-144">long</span></span> | <span data-ttu-id="affa4-145">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="affa4-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="affa4-146">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="affa4-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="affa4-147">文字列</span><span class="sxs-lookup"><span data-stu-id="affa4-147">string</span></span> | <span data-ttu-id="affa4-148">JSON 配列形式のイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="affa4-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="affa4-149">この表は、定期的なレポートまたはデバイスからの信号であるハートビートに基づくデバイス `DeviceInfo` 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="affa4-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="affa4-150">15 分ごとに、デバイスは頻繁に変更される属性を含む部分的なハートビートを送信します `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="affa4-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="affa4-151">1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="affa4-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="affa4-152">次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="affa4-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="affa4-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="affa4-153">Related topics</span></span>
- [<span data-ttu-id="affa4-154">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="affa4-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="affa4-155">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="affa4-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="affa4-156">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="affa4-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="affa4-157">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="affa4-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="affa4-158">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="affa4-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="affa4-159">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="affa4-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
