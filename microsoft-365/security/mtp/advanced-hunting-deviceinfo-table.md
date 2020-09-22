---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルにある OS、コンピューター名、およびその他のマシン情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machineinfo、DeviceInfo、device、machine、OS、platform、users
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
ms.openlocfilehash: 94302f1b8a4316dec2abec2fc361d82e734549b4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197259"
---
# <a name="deviceinfo"></a><span data-ttu-id="a8eb6-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="a8eb6-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a8eb6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a8eb6-105">**Applies to:**</span></span>
- <span data-ttu-id="a8eb6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8eb6-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="a8eb6-107">`DeviceInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、OS のバージョン、アクティブなユーザー、コンピューター名など、組織内のコンピューターに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="a8eb6-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a8eb6-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a8eb6-110">列名</span><span class="sxs-lookup"><span data-stu-id="a8eb6-110">Column name</span></span> | <span data-ttu-id="a8eb6-111">データ型</span><span class="sxs-lookup"><span data-stu-id="a8eb6-111">Data type</span></span> | <span data-ttu-id="a8eb6-112">説明</span><span class="sxs-lookup"><span data-stu-id="a8eb6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a8eb6-113">日付型</span><span class="sxs-lookup"><span data-stu-id="a8eb6-113">datetime</span></span> | <span data-ttu-id="a8eb6-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a8eb6-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a8eb6-115">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-115">string</span></span> | <span data-ttu-id="a8eb6-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a8eb6-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a8eb6-117">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-117">string</span></span> | <span data-ttu-id="a8eb6-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a8eb6-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="a8eb6-119">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-119">string</span></span> | <span data-ttu-id="a8eb6-120">コンピューター上で実行されているエンドポイントエージェントまたはセンサーのバージョン</span><span class="sxs-lookup"><span data-stu-id="a8eb6-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="a8eb6-121">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-121">string</span></span> | <span data-ttu-id="a8eb6-122">Microsoft Defender ATP サービスに接続するために利用コンピューターによって使用されるパブリック IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="a8eb6-123">これは、マシン自体、NAT デバイス、またはプロキシの IP アドレスである場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="a8eb6-124">string</span><span class="sxs-lookup"><span data-stu-id="a8eb6-124">string</span></span> | <span data-ttu-id="a8eb6-125">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="a8eb6-126">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-126">string</span></span> | <span data-ttu-id="a8eb6-127">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="a8eb6-128">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティングシステムを示します。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="a8eb6-129">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-129">string</span></span> | <span data-ttu-id="a8eb6-130">コンピューター上で実行されているオペレーティングシステムのビルドバージョン</span><span class="sxs-lookup"><span data-stu-id="a8eb6-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="a8eb6-131">boolean</span><span class="sxs-lookup"><span data-stu-id="a8eb6-131">boolean</span></span> | <span data-ttu-id="a8eb6-132">コンピューターが Azure Active Directory に参加しているかどうかを示すブール値のインジケーター</span><span class="sxs-lookup"><span data-stu-id="a8eb6-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="a8eb6-133">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-133">string</span></span> | <span data-ttu-id="a8eb6-134">JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧</span><span class="sxs-lookup"><span data-stu-id="a8eb6-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="a8eb6-135">文字列</span><span class="sxs-lookup"><span data-stu-id="a8eb6-135">string</span></span> | <span data-ttu-id="a8eb6-136">レジストリに追加されたコンピュータータグ</span><span class="sxs-lookup"><span data-stu-id="a8eb6-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="a8eb6-137">long</span><span class="sxs-lookup"><span data-stu-id="a8eb6-137">long</span></span> | <span data-ttu-id="a8eb6-138">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a8eb6-139">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="a8eb6-140">string</span><span class="sxs-lookup"><span data-stu-id="a8eb6-140">string</span></span> | <span data-ttu-id="a8eb6-141">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="a8eb6-142">string</span><span class="sxs-lookup"><span data-stu-id="a8eb6-142">string</span></span> | <span data-ttu-id="a8eb6-143">コンピューターのコンピューターグループ。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-143">Machine group of the machine.</span></span> <span data-ttu-id="a8eb6-144">このグループは、役割ベースのアクセス制御によって、コンピューターへのアクセスを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8eb6-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a8eb6-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8eb6-145">Related topics</span></span>
- [<span data-ttu-id="a8eb6-146">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="a8eb6-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a8eb6-147">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a8eb6-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a8eb6-148">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="a8eb6-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a8eb6-149">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="a8eb6-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a8eb6-150">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a8eb6-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a8eb6-151">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="a8eb6-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
