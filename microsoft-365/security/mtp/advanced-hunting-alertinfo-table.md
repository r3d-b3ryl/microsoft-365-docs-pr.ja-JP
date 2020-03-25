---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルにあるアラート生成イベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、alert、severity、category、MITRE、ATT&の場合、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS、および Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929518"
---
# <a name="alertinfo"></a><span data-ttu-id="082a1-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="082a1-104">AlertInfo</span></span>

<span data-ttu-id="082a1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="082a1-105">**Applies to:**</span></span>
- <span data-ttu-id="082a1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="082a1-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="082a1-107">`AlertInfo` [高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft Defender ATP、Office 365 Atp、microsoft Cloud App SECURITY、および Azure ATP からの通知に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="082a1-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="082a1-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="082a1-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="082a1-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082a1-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="082a1-110">列名</span><span class="sxs-lookup"><span data-stu-id="082a1-110">Column name</span></span> | <span data-ttu-id="082a1-111">データ型</span><span class="sxs-lookup"><span data-stu-id="082a1-111">Data type</span></span> | <span data-ttu-id="082a1-112">説明</span><span class="sxs-lookup"><span data-stu-id="082a1-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="082a1-113">日付型</span><span class="sxs-lookup"><span data-stu-id="082a1-113">datetime</span></span> | <span data-ttu-id="082a1-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="082a1-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="082a1-115">string</span><span class="sxs-lookup"><span data-stu-id="082a1-115">string</span></span> | <span data-ttu-id="082a1-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="082a1-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="082a1-117">文字列</span><span class="sxs-lookup"><span data-stu-id="082a1-117">string</span></span> | <span data-ttu-id="082a1-118">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="082a1-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="082a1-119">文字列</span><span class="sxs-lookup"><span data-stu-id="082a1-119">string</span></span> | <span data-ttu-id="082a1-120">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="082a1-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="082a1-121">string</span><span class="sxs-lookup"><span data-stu-id="082a1-121">string</span></span> | <span data-ttu-id="082a1-122">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="082a1-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="082a1-123">string</span><span class="sxs-lookup"><span data-stu-id="082a1-123">string</span></span> | <span data-ttu-id="082a1-124">通知情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="082a1-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="082a1-125">string</span><span class="sxs-lookup"><span data-stu-id="082a1-125">string</span></span> | <span data-ttu-id="082a1-126">注目のコンポーネントまたはアクティビティを特定した検出テクノロジまたはセンサー</span><span class="sxs-lookup"><span data-stu-id="082a1-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="082a1-127">string</span><span class="sxs-lookup"><span data-stu-id="082a1-127">string</span></span> | <span data-ttu-id="082a1-128">MITRE ATT&の警告をトリガーしたアクティビティに関連付けられた手法</span><span class="sxs-lookup"><span data-stu-id="082a1-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="082a1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="082a1-129">Related topics</span></span>
- [<span data-ttu-id="082a1-130">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="082a1-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="082a1-131">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="082a1-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="082a1-132">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="082a1-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="082a1-133">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="082a1-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="082a1-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="082a1-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="082a1-135">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="082a1-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
