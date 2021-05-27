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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689111"
---
# <a name="deviceinfo"></a><span data-ttu-id="f6f9f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="f6f9f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6f9f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f6f9f-105">**Applies to:**</span></span>
- <span data-ttu-id="f6f9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6f9f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f6f9f-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f6f9f-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="f6f9f-108">高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="f6f9f-109">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f6f9f-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f6f9f-111">列名</span><span class="sxs-lookup"><span data-stu-id="f6f9f-111">Column name</span></span> | <span data-ttu-id="f6f9f-112">データ型</span><span class="sxs-lookup"><span data-stu-id="f6f9f-112">Data type</span></span> | <span data-ttu-id="f6f9f-113">説明</span><span class="sxs-lookup"><span data-stu-id="f6f9f-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f6f9f-114">日付型</span><span class="sxs-lookup"><span data-stu-id="f6f9f-114">datetime</span></span> | <span data-ttu-id="f6f9f-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="f6f9f-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f6f9f-116">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-116">string</span></span> | <span data-ttu-id="f6f9f-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f6f9f-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f6f9f-118">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-118">string</span></span> | <span data-ttu-id="f6f9f-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f6f9f-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="f6f9f-120">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-120">string</span></span> | <span data-ttu-id="f6f9f-121">コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="f6f9f-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="f6f9f-122">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-122">string</span></span> | <span data-ttu-id="f6f9f-123">オンボード コンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="f6f9f-124">これは、コンピューター自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="f6f9f-125">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-125">string</span></span> | <span data-ttu-id="f6f9f-126">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="f6f9f-127">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-127">string</span></span> | <span data-ttu-id="f6f9f-128">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="f6f9f-129">これは、特定のオペレーティング システム (同じファミリ内のバリエーション (Windows 10および Windows 7 など) を示します。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="f6f9f-130">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-130">string</span></span> | <span data-ttu-id="f6f9f-131">コンピューターで実行されているオペレーティング システムのバージョンをビルドする</span><span class="sxs-lookup"><span data-stu-id="f6f9f-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="f6f9f-132">boolean</span><span class="sxs-lookup"><span data-stu-id="f6f9f-132">boolean</span></span> | <span data-ttu-id="f6f9f-133">コンピューターがコンピューターに参加しているかどうかを示すブールAzure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f6f9f-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="f6f9f-134">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-134">string</span></span> | <span data-ttu-id="f6f9f-135">Azure のデバイスの一意の識別子AD</span><span class="sxs-lookup"><span data-stu-id="f6f9f-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="f6f9f-136">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-136">string</span></span> | <span data-ttu-id="f6f9f-137">JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="f6f9f-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="f6f9f-138">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-138">string</span></span> | <span data-ttu-id="f6f9f-139">レジストリを介して追加されたコンピューター タグ</span><span class="sxs-lookup"><span data-stu-id="f6f9f-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="f6f9f-140">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-140">string</span></span> | <span data-ttu-id="f6f9f-141">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="f6f9f-142">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-142">string</span></span> | <span data-ttu-id="f6f9f-143">コンピューターのコンピューター グループ。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-143">Machine group of the machine.</span></span> <span data-ttu-id="f6f9f-144">このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="f6f9f-145">long</span><span class="sxs-lookup"><span data-stu-id="f6f9f-145">long</span></span> | <span data-ttu-id="f6f9f-146">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f6f9f-147">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="f6f9f-148">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-148">string</span></span> | <span data-ttu-id="f6f9f-149">デバイスが現在オンボードされているかどうかを示す Microsoft Defender For Endpoint またはデバイスがサポートされていない場合</span><span class="sxs-lookup"><span data-stu-id="f6f9f-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="f6f9f-150">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-150">string</span></span> | <span data-ttu-id="f6f9f-151">JSON 配列形式のイベントに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="f6f9f-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="f6f9f-152">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-152">string</span></span> | <span data-ttu-id="f6f9f-153">特定のデバイスの種類を次のカテゴリにグループ化する広範な分類: エンドポイント、ネットワーク デバイス、IoT、不明</span><span class="sxs-lookup"><span data-stu-id="f6f9f-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="f6f9f-154">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-154">string</span></span> | <span data-ttu-id="f6f9f-155">目的と機能に基づくデバイスの種類 (ネットワーク デバイス、ワークステーション、サーバー、モバイル、ゲーム コンソール、プリンターなど)</span><span class="sxs-lookup"><span data-stu-id="f6f9f-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="f6f9f-156">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-156">string</span></span> | <span data-ttu-id="f6f9f-157">特定の種類のデバイスの追加修飾子 (たとえば、モバイル デバイスはタブレットまたはスマートフォンなど)</span><span class="sxs-lookup"><span data-stu-id="f6f9f-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="f6f9f-158">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-158">string</span></span> | <span data-ttu-id="f6f9f-159">ベンダーまたは製造元の製品のモデル名または番号</span><span class="sxs-lookup"><span data-stu-id="f6f9f-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="f6f9f-160">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-160">string</span></span> | <span data-ttu-id="f6f9f-161">製品ベンダーまたは製造元の名前</span><span class="sxs-lookup"><span data-stu-id="f6f9f-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="f6f9f-162">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-162">string</span></span> | <span data-ttu-id="f6f9f-163">Linux プラットフォーム用の Ubuntu や RedHat などの OS プラットフォームの配布</span><span class="sxs-lookup"><span data-stu-id="f6f9f-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="f6f9f-164">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-164">string</span></span> | <span data-ttu-id="f6f9f-165">OS バージョンに関する追加情報 (一般的な名前、コード名、バージョン番号など)</span><span class="sxs-lookup"><span data-stu-id="f6f9f-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="f6f9f-166">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-166">string</span></span> | <span data-ttu-id="f6f9f-167">同じデバイスに割り当てられている以前のデバイス ID</span><span class="sxs-lookup"><span data-stu-id="f6f9f-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="f6f9f-168">string</span><span class="sxs-lookup"><span data-stu-id="f6f9f-168">string</span></span> | <span data-ttu-id="f6f9f-169">デバイスに割り当てられた最新のデバイス ID</span><span class="sxs-lookup"><span data-stu-id="f6f9f-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="f6f9f-170">この表は、定期的なレポートまたはデバイスからの信号であるハートビートに基づくデバイス `DeviceInfo` 情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="f6f9f-171">15 分ごとに、デバイスは頻繁に変更される属性を含む部分的なハートビートを送信します `LoggedOnUsers` 。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="f6f9f-172">1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="f6f9f-173">次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f6f9f-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="f6f9f-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6f9f-174">Related topics</span></span>
- [<span data-ttu-id="f6f9f-175">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="f6f9f-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f6f9f-176">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f6f9f-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f6f9f-177">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="f6f9f-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f6f9f-178">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="f6f9f-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f6f9f-179">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f6f9f-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f6f9f-180">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="f6f9f-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
