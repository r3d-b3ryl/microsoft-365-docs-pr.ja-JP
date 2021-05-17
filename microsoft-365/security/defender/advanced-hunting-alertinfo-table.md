---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルのアラート生成イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、重大度、カテゴリ、MITRE、ATT&CK、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、MCAS、Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933699"
---
# <a name="alertinfo"></a><span data-ttu-id="a9fe7-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a9fe7-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a9fe7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a9fe7-105">**Applies to:**</span></span>
- <span data-ttu-id="a9fe7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9fe7-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a9fe7-107">高度 `AlertInfo` な検索スキーマの[表](advanced-hunting-overview.md)には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="a9fe7-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="a9fe7-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9fe7-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a9fe7-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9fe7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a9fe7-110">列名</span><span class="sxs-lookup"><span data-stu-id="a9fe7-110">Column name</span></span> | <span data-ttu-id="a9fe7-111">データ型</span><span class="sxs-lookup"><span data-stu-id="a9fe7-111">Data type</span></span> | <span data-ttu-id="a9fe7-112">説明</span><span class="sxs-lookup"><span data-stu-id="a9fe7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a9fe7-113">日付型</span><span class="sxs-lookup"><span data-stu-id="a9fe7-113">datetime</span></span> | <span data-ttu-id="a9fe7-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="a9fe7-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="a9fe7-115">string</span><span class="sxs-lookup"><span data-stu-id="a9fe7-115">string</span></span> | <span data-ttu-id="a9fe7-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="a9fe7-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="a9fe7-117">文字列</span><span class="sxs-lookup"><span data-stu-id="a9fe7-117">string</span></span> | <span data-ttu-id="a9fe7-118">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="a9fe7-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="a9fe7-119">文字列</span><span class="sxs-lookup"><span data-stu-id="a9fe7-119">string</span></span> | <span data-ttu-id="a9fe7-120">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="a9fe7-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="a9fe7-121">文字列</span><span class="sxs-lookup"><span data-stu-id="a9fe7-121">string</span></span> | <span data-ttu-id="a9fe7-122">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="a9fe7-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="a9fe7-123">文字列</span><span class="sxs-lookup"><span data-stu-id="a9fe7-123">string</span></span> | <span data-ttu-id="a9fe7-124">アラート情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="a9fe7-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="a9fe7-125">string</span><span class="sxs-lookup"><span data-stu-id="a9fe7-125">string</span></span> | <span data-ttu-id="a9fe7-126">重要なコンポーネントまたはアクティビティを識別した検出テクノロジまたはセンサー</span><span class="sxs-lookup"><span data-stu-id="a9fe7-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="a9fe7-127">string</span><span class="sxs-lookup"><span data-stu-id="a9fe7-127">string</span></span> | <span data-ttu-id="a9fe7-128">MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9fe7-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a9fe7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9fe7-129">Related topics</span></span>
- [<span data-ttu-id="a9fe7-130">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="a9fe7-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a9fe7-131">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a9fe7-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a9fe7-132">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="a9fe7-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a9fe7-133">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="a9fe7-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a9fe7-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a9fe7-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a9fe7-135">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="a9fe7-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
