---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルに記載される、脅威および脆弱性管理により評価されるさまざまなセキュリティ構成について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、検索、クエリ、テレメトリ、スキーマ リファレンス、Kusto、テーブル、列、データ型、説明、脅威および脆弱性管理、TVM、デバイス管理、セキュリティ構成、MITRE ATT&CK フレームワーク、サポート技術情報、KB、 DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806936"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="0461f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="0461f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="0461f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0461f-105">**Applies to:**</span></span>
- <span data-ttu-id="0461f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0461f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0461f-107">高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0461f-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="0461f-108">このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。</span><span class="sxs-lookup"><span data-stu-id="0461f-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="0461f-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0461f-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0461f-110">高度な検索スキーマのその他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0461f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0461f-111">列名</span><span class="sxs-lookup"><span data-stu-id="0461f-111">Column name</span></span> | <span data-ttu-id="0461f-112">データ型</span><span class="sxs-lookup"><span data-stu-id="0461f-112">Data type</span></span> | <span data-ttu-id="0461f-113">説明</span><span class="sxs-lookup"><span data-stu-id="0461f-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="0461f-114">string</span><span class="sxs-lookup"><span data-stu-id="0461f-114">string</span></span> | <span data-ttu-id="0461f-115">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="0461f-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="0461f-116">string</span><span class="sxs-lookup"><span data-stu-id="0461f-116">string</span></span> | <span data-ttu-id="0461f-117">構成が全体の構成スコアに与える影響の評価 (1-10)</span><span class="sxs-lookup"><span data-stu-id="0461f-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="0461f-118">string</span><span class="sxs-lookup"><span data-stu-id="0461f-118">string</span></span> | <span data-ttu-id="0461f-119">構成の表示名</span><span class="sxs-lookup"><span data-stu-id="0461f-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="0461f-120">string</span><span class="sxs-lookup"><span data-stu-id="0461f-120">string</span></span> | <span data-ttu-id="0461f-121">構成の説明</span><span class="sxs-lookup"><span data-stu-id="0461f-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="0461f-122">string</span><span class="sxs-lookup"><span data-stu-id="0461f-122">string</span></span> | <span data-ttu-id="0461f-123">関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="0461f-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="0461f-124">string</span><span class="sxs-lookup"><span data-stu-id="0461f-124">string</span></span> | <span data-ttu-id="0461f-125">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="0461f-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="0461f-126">string</span><span class="sxs-lookup"><span data-stu-id="0461f-126">string</span></span> |<span data-ttu-id="0461f-127">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="0461f-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="0461f-128">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="0461f-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="0461f-129">string</span><span class="sxs-lookup"><span data-stu-id="0461f-129">string</span></span> | <span data-ttu-id="0461f-130">同じ構成または類似した構成を推奨する業界ベンチマークの一覧</span><span class="sxs-lookup"><span data-stu-id="0461f-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="0461f-131">string</span><span class="sxs-lookup"><span data-stu-id="0461f-131">string</span></span> | <span data-ttu-id="0461f-132">構成に関連する Mitre ATT&CK フレームワーク テクニックの一覧</span><span class="sxs-lookup"><span data-stu-id="0461f-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="0461f-133">string</span><span class="sxs-lookup"><span data-stu-id="0461f-133">string</span></span> | <span data-ttu-id="0461f-134">構成に関連する Mitre ATT&CK フレームワーク戦術の一覧</span><span class="sxs-lookup"><span data-stu-id="0461f-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0461f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0461f-135">Related topics</span></span>

- [<span data-ttu-id="0461f-136">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="0461f-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0461f-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="0461f-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0461f-138">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="0461f-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0461f-139">デバイスとメール全体で脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="0461f-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0461f-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="0461f-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0461f-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="0461f-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0461f-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="0461f-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
