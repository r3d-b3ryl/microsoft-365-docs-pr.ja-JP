---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルのアラート生成イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、重大度、カテゴリ、MITRE、ATT&CK、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS、Azure ATP
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bc81c9c8406a6e70df6ec38e3896ef9977a120e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063604"
---
# <a name="alertinfo"></a><span data-ttu-id="08206-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="08206-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08206-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="08206-105">**Applies to:**</span></span>
- <span data-ttu-id="08206-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08206-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="08206-107">高度 `AlertInfo` な検索スキーマ[](advanced-hunting-overview.md)の表には、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity のアラートに関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="08206-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="08206-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="08206-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="08206-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08206-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="08206-110">列名</span><span class="sxs-lookup"><span data-stu-id="08206-110">Column name</span></span> | <span data-ttu-id="08206-111">データ型</span><span class="sxs-lookup"><span data-stu-id="08206-111">Data type</span></span> | <span data-ttu-id="08206-112">説明</span><span class="sxs-lookup"><span data-stu-id="08206-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="08206-113">日付型</span><span class="sxs-lookup"><span data-stu-id="08206-113">datetime</span></span> | <span data-ttu-id="08206-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="08206-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="08206-115">string</span><span class="sxs-lookup"><span data-stu-id="08206-115">string</span></span> | <span data-ttu-id="08206-116">アラートの一意識別子</span><span class="sxs-lookup"><span data-stu-id="08206-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="08206-117">文字列</span><span class="sxs-lookup"><span data-stu-id="08206-117">string</span></span> | <span data-ttu-id="08206-118">アラートのタイトル</span><span class="sxs-lookup"><span data-stu-id="08206-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="08206-119">文字列</span><span class="sxs-lookup"><span data-stu-id="08206-119">string</span></span> | <span data-ttu-id="08206-120">アラートで識別された脅威インジケーターまたは侵害アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="08206-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="08206-121">文字列</span><span class="sxs-lookup"><span data-stu-id="08206-121">string</span></span> | <span data-ttu-id="08206-122">アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。</span><span class="sxs-lookup"><span data-stu-id="08206-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="08206-123">文字列</span><span class="sxs-lookup"><span data-stu-id="08206-123">string</span></span> | <span data-ttu-id="08206-124">アラート情報を提供した製品またはサービス</span><span class="sxs-lookup"><span data-stu-id="08206-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="08206-125">string</span><span class="sxs-lookup"><span data-stu-id="08206-125">string</span></span> | <span data-ttu-id="08206-126">重要なコンポーネントまたはアクティビティを識別した検出テクノロジまたはセンサー</span><span class="sxs-lookup"><span data-stu-id="08206-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="08206-127">string</span><span class="sxs-lookup"><span data-stu-id="08206-127">string</span></span> | <span data-ttu-id="08206-128">MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。</span><span class="sxs-lookup"><span data-stu-id="08206-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="08206-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="08206-129">Related topics</span></span>
- [<span data-ttu-id="08206-130">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="08206-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="08206-131">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="08206-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="08206-132">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="08206-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="08206-133">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="08206-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="08206-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="08206-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="08206-135">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="08206-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)