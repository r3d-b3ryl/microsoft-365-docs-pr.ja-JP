---
title: 高度なハンティング スキーマの DeviceAlertEvents テーブル
description: 高度なハンティング スキーマの DeviceAlertEvents テーブルのアラート生成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft Defender for Endpoint、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、DeviceAlertEvents、アラート、重大度、カテゴリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: bb2350fed5fadee359695743989e02a3b3e44fb2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935343"
---
# <a name="devicealertevents"></a><span data-ttu-id="087c3-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="087c3-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="087c3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="087c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="087c3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="087c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="087c3-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="087c3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="087c3-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="087c3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="087c3-109">高度 `DeviceAlertEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Defender セキュリティ センターのアラートに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="087c3-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="087c3-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="087c3-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="087c3-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="087c3-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="087c3-112">列名</span><span class="sxs-lookup"><span data-stu-id="087c3-112">Column name</span></span> | <span data-ttu-id="087c3-113">データ型</span><span class="sxs-lookup"><span data-stu-id="087c3-113">Data type</span></span> | <span data-ttu-id="087c3-114">説明</span><span class="sxs-lookup"><span data-stu-id="087c3-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="087c3-115">string</span><span class="sxs-lookup"><span data-stu-id="087c3-115">string</span></span> | <span data-ttu-id="087c3-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="087c3-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="087c3-117">datetime</span><span class="sxs-lookup"><span data-stu-id="087c3-117">datetime</span></span> | <span data-ttu-id="087c3-118">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="087c3-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="087c3-119">string</span><span class="sxs-lookup"><span data-stu-id="087c3-119">string</span></span> | <span data-ttu-id="087c3-120">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="087c3-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="087c3-121">string</span><span class="sxs-lookup"><span data-stu-id="087c3-121">string</span></span> | <span data-ttu-id="087c3-122">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="087c3-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="087c3-123">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-123">string</span></span> | <span data-ttu-id="087c3-124">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="087c3-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="087c3-125">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-125">string</span></span> | <span data-ttu-id="087c3-126">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="087c3-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="087c3-127">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-127">string</span></span> | <span data-ttu-id="087c3-128">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="087c3-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="087c3-129">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-129">string</span></span> | <span data-ttu-id="087c3-130">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="087c3-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="087c3-131">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-131">string</span></span> | <span data-ttu-id="087c3-132">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="087c3-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="087c3-133">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-133">string</span></span> | <span data-ttu-id="087c3-134">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="087c3-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="087c3-135">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-135">string</span></span> | <span data-ttu-id="087c3-136">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="087c3-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="087c3-137">string</span><span class="sxs-lookup"><span data-stu-id="087c3-137">string</span></span> | <span data-ttu-id="087c3-138">MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。</span><span class="sxs-lookup"><span data-stu-id="087c3-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="087c3-139">long</span><span class="sxs-lookup"><span data-stu-id="087c3-139">long</span></span> | <span data-ttu-id="087c3-140">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="087c3-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="087c3-141">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="087c3-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="087c3-142">文字列</span><span class="sxs-lookup"><span data-stu-id="087c3-142">string</span></span> | <span data-ttu-id="087c3-143">イベントの詳細を含むテーブル</span><span class="sxs-lookup"><span data-stu-id="087c3-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="087c3-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="087c3-144">Related topics</span></span>
- [<span data-ttu-id="087c3-145">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="087c3-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="087c3-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="087c3-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="087c3-147">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="087c3-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
