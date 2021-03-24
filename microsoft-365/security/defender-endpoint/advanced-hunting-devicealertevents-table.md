---
title: 高度なハンティング スキーマの DeviceAlertEvents テーブル
description: 高度なハンティング スキーマの DeviceAlertEvents テーブルのアラート生成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、DeviceAlertEvents、アラート、重大度、カテゴリ
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
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: c22e4b754f9d28156c3d26c567581572e59d718d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064388"
---
# <a name="devicealertevents"></a><span data-ttu-id="bfc73-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="bfc73-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bfc73-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bfc73-105">**Applies to:**</span></span>
- [<span data-ttu-id="bfc73-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bfc73-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="bfc73-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bfc73-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bfc73-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bfc73-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="bfc73-109">高度 `DeviceAlertEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Defender セキュリティ センターのアラートに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="bfc73-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="bfc73-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc73-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bfc73-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc73-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="bfc73-112">列名</span><span class="sxs-lookup"><span data-stu-id="bfc73-112">Column name</span></span> | <span data-ttu-id="bfc73-113">データ型</span><span class="sxs-lookup"><span data-stu-id="bfc73-113">Data type</span></span> | <span data-ttu-id="bfc73-114">説明</span><span class="sxs-lookup"><span data-stu-id="bfc73-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="bfc73-115">string</span><span class="sxs-lookup"><span data-stu-id="bfc73-115">string</span></span> | <span data-ttu-id="bfc73-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="bfc73-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="bfc73-117">datetime</span><span class="sxs-lookup"><span data-stu-id="bfc73-117">datetime</span></span> | <span data-ttu-id="bfc73-118">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="bfc73-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="bfc73-119">string</span><span class="sxs-lookup"><span data-stu-id="bfc73-119">string</span></span> | <span data-ttu-id="bfc73-120">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="bfc73-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="bfc73-121">string</span><span class="sxs-lookup"><span data-stu-id="bfc73-121">string</span></span> | <span data-ttu-id="bfc73-122">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="bfc73-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="bfc73-123">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-123">string</span></span> | <span data-ttu-id="bfc73-124">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="bfc73-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="bfc73-125">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-125">string</span></span> | <span data-ttu-id="bfc73-126">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="bfc73-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="bfc73-127">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-127">string</span></span> | <span data-ttu-id="bfc73-128">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="bfc73-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="bfc73-129">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-129">string</span></span> | <span data-ttu-id="bfc73-130">記録されたアクションが適用されたファイルの名前</span><span class="sxs-lookup"><span data-stu-id="bfc73-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="bfc73-131">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-131">string</span></span> | <span data-ttu-id="bfc73-132">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="bfc73-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="bfc73-133">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-133">string</span></span> | <span data-ttu-id="bfc73-134">に接続されていた URL または完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="bfc73-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="bfc73-135">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-135">string</span></span> | <span data-ttu-id="bfc73-136">に接続されていた IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bfc73-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="bfc73-137">string</span><span class="sxs-lookup"><span data-stu-id="bfc73-137">string</span></span> | <span data-ttu-id="bfc73-138">MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfc73-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="bfc73-139">long</span><span class="sxs-lookup"><span data-stu-id="bfc73-139">long</span></span> | <span data-ttu-id="bfc73-140">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="bfc73-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="bfc73-141">一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。</span><span class="sxs-lookup"><span data-stu-id="bfc73-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="bfc73-142">文字列</span><span class="sxs-lookup"><span data-stu-id="bfc73-142">string</span></span> | <span data-ttu-id="bfc73-143">イベントの詳細を含むテーブル</span><span class="sxs-lookup"><span data-stu-id="bfc73-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bfc73-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfc73-144">Related topics</span></span>
- [<span data-ttu-id="bfc73-145">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="bfc73-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bfc73-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="bfc73-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bfc73-147">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="bfc73-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
