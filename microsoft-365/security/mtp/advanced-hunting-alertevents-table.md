---
title: 高度な検索スキーマの AlertEvents テーブル
description: 高度な検索スキーマの AlertEvents テーブル内のアラート発生イベントについて
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、alertevents、alert、severity、category
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235096"
---
# <a name="alertevents"></a><span data-ttu-id="b0664-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="b0664-104">AlertEvents</span></span>

<span data-ttu-id="b0664-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b0664-105">**Applies to:**</span></span>
- <span data-ttu-id="b0664-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b0664-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b0664-107">[高度な検索](advanced-hunting-overview.md) スキーマの `AlertEvents` テーブルには、Microsoft Defender ATP アラートに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0664-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="b0664-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0664-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b0664-109">高度な検索スキーマのその他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0664-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b0664-110">列名</span><span class="sxs-lookup"><span data-stu-id="b0664-110">Column name</span></span> | <span data-ttu-id="b0664-111">データ型</span><span class="sxs-lookup"><span data-stu-id="b0664-111">Data type</span></span> | <span data-ttu-id="b0664-112">説明</span><span class="sxs-lookup"><span data-stu-id="b0664-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="b0664-113">string</span><span class="sxs-lookup"><span data-stu-id="b0664-113">string</span></span> | <span data-ttu-id="b0664-114">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b0664-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="b0664-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b0664-115">datetime</span></span> | <span data-ttu-id="b0664-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="b0664-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b0664-117">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-117">string</span></span> | <span data-ttu-id="b0664-118">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="b0664-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b0664-119">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-119">string</span></span> | <span data-ttu-id="b0664-120">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b0664-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="b0664-121">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-121">string</span></span> | <span data-ttu-id="b0664-122">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="b0664-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="b0664-123">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-123">string</span></span> | <span data-ttu-id="b0664-124">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="b0664-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="b0664-125">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-125">string</span></span> | <span data-ttu-id="b0664-126">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="b0664-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="b0664-127">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-127">string</span></span> | <span data-ttu-id="b0664-128">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="b0664-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="b0664-129">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-129">string</span></span> | <span data-ttu-id="b0664-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="b0664-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="b0664-131">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-131">string</span></span> | <span data-ttu-id="b0664-132">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="b0664-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="b0664-133">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-133">string</span></span> | <span data-ttu-id="b0664-134">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b0664-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="b0664-135">long</span><span class="sxs-lookup"><span data-stu-id="b0664-135">long</span></span> | <span data-ttu-id="b0664-136">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="b0664-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b0664-137">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0664-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="b0664-138">文字列</span><span class="sxs-lookup"><span data-stu-id="b0664-138">string</span></span> | <span data-ttu-id="b0664-139">イベントの詳細を含むテーブル</span><span class="sxs-lookup"><span data-stu-id="b0664-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b0664-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0664-140">Related topics</span></span>
- [<span data-ttu-id="b0664-141">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="b0664-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0664-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="b0664-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0664-143">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="b0664-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b0664-144">デバイスとメール全体で脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="b0664-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b0664-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="b0664-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b0664-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="b0664-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
