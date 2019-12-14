---
title: 高度な検索スキーマの AlertEvents テーブル
description: 高度な検索スキーマの AlertEvents テーブル内のアラート発生イベントについて
keywords: 高度な検索、脅威ハンティング、サイバー脅威ハンティング、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、alertevents、アラート、重要度、カテゴリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911333"
---
# <a name="alertevents"></a><span data-ttu-id="86766-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="86766-104">AlertEvents</span></span>

<span data-ttu-id="86766-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="86766-105">**Applies to:**</span></span>
- <span data-ttu-id="86766-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="86766-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="86766-107">[高度な検索](advanced-hunting-overview.md) スキーマの `AlertEvents` テーブルには、Microsoft Defender ATP アラートに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="86766-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="86766-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="86766-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="86766-109">高度な検索スキーマのその他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86766-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="86766-110">列名</span><span class="sxs-lookup"><span data-stu-id="86766-110">Column name</span></span> | <span data-ttu-id="86766-111">データ型</span><span class="sxs-lookup"><span data-stu-id="86766-111">Data type</span></span> | <span data-ttu-id="86766-112">説明</span><span class="sxs-lookup"><span data-stu-id="86766-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="86766-113">string</span><span class="sxs-lookup"><span data-stu-id="86766-113">string</span></span> | <span data-ttu-id="86766-114">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="86766-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="86766-115">datetime</span><span class="sxs-lookup"><span data-stu-id="86766-115">dateTime</span></span> | <span data-ttu-id="86766-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="86766-116">Date and time the report was recorded.</span></span> |
| `MachineId` | <span data-ttu-id="86766-117">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-117">string</span></span> | <span data-ttu-id="86766-118">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="86766-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="86766-119">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-119">string</span></span> | <span data-ttu-id="86766-120">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="86766-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="86766-121">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-121">string</span></span> | <span data-ttu-id="86766-122">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="86766-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="86766-123">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-123">string</span></span> | <span data-ttu-id="86766-124">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="86766-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="86766-125">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-125">string</span></span> | <span data-ttu-id="86766-126">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="86766-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="86766-127">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-127">string</span></span> | <span data-ttu-id="86766-128">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="86766-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="86766-129">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-129">string</span></span> | <span data-ttu-id="86766-130">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="86766-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="86766-131">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-131">string</span></span> | <span data-ttu-id="86766-132">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="86766-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="86766-133">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-133">string</span></span> | <span data-ttu-id="86766-134">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="86766-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="86766-135">long</span><span class="sxs-lookup"><span data-stu-id="86766-135">long</span></span> | <span data-ttu-id="86766-136">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="86766-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="86766-137">一意のイベントを特定するには、この列を ComputerName 列と EventTime 列と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86766-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="86766-138">文字列</span><span class="sxs-lookup"><span data-stu-id="86766-138">string</span></span> | <span data-ttu-id="86766-139">イベントの詳細を含むテーブル</span><span class="sxs-lookup"><span data-stu-id="86766-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="86766-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="86766-140">Related topics</span></span>
- [<span data-ttu-id="86766-141">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="86766-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="86766-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="86766-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="86766-143">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="86766-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="86766-144">デバイスとメール全体で脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="86766-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="86766-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="86766-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="86766-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="86766-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
