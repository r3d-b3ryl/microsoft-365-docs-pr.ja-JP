---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルに記載される、脅威および脆弱性管理により評価されるさまざまなセキュリティ構成について説明します。
keywords: '高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、threat & 脆弱性管理、TVM、デバイス管理、セキュリティの構成、MITRE ATT&DeviceTvmSecureConfigurationAssessmentKB: サポート技術情報、KB、'
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ee232d74d2426513073b3684f3656f0cbc9b22f4
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429861"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="decfe-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="decfe-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="decfe-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="decfe-105">**Applies to:**</span></span>
- <span data-ttu-id="decfe-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="decfe-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="decfe-107">高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="decfe-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="decfe-108">このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。</span><span class="sxs-lookup"><span data-stu-id="decfe-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="decfe-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="decfe-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="decfe-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="decfe-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="decfe-111">列名</span><span class="sxs-lookup"><span data-stu-id="decfe-111">Column name</span></span> | <span data-ttu-id="decfe-112">データ型</span><span class="sxs-lookup"><span data-stu-id="decfe-112">Data type</span></span> | <span data-ttu-id="decfe-113">説明</span><span class="sxs-lookup"><span data-stu-id="decfe-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="decfe-114">string</span><span class="sxs-lookup"><span data-stu-id="decfe-114">string</span></span> | <span data-ttu-id="decfe-115">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="decfe-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="decfe-116">string</span><span class="sxs-lookup"><span data-stu-id="decfe-116">string</span></span> | <span data-ttu-id="decfe-117">構成が全体の構成スコアに与える影響の評価 (1-10)</span><span class="sxs-lookup"><span data-stu-id="decfe-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="decfe-118">string</span><span class="sxs-lookup"><span data-stu-id="decfe-118">string</span></span> | <span data-ttu-id="decfe-119">構成の表示名</span><span class="sxs-lookup"><span data-stu-id="decfe-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="decfe-120">string</span><span class="sxs-lookup"><span data-stu-id="decfe-120">string</span></span> | <span data-ttu-id="decfe-121">構成の説明</span><span class="sxs-lookup"><span data-stu-id="decfe-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="decfe-122">string</span><span class="sxs-lookup"><span data-stu-id="decfe-122">string</span></span> | <span data-ttu-id="decfe-123">関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="decfe-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="decfe-124">string</span><span class="sxs-lookup"><span data-stu-id="decfe-124">string</span></span> | <span data-ttu-id="decfe-125">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="decfe-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="decfe-126">string</span><span class="sxs-lookup"><span data-stu-id="decfe-126">string</span></span> |<span data-ttu-id="decfe-127">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="decfe-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="decfe-128">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="decfe-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="decfe-129">string</span><span class="sxs-lookup"><span data-stu-id="decfe-129">string</span></span> | <span data-ttu-id="decfe-130">同じ構成または類似した構成を推奨する業界ベンチマークの一覧</span><span class="sxs-lookup"><span data-stu-id="decfe-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="decfe-131">string</span><span class="sxs-lookup"><span data-stu-id="decfe-131">string</span></span> | <span data-ttu-id="decfe-132">構成に関連する Mitre ATT&CK フレームワーク テクニックの一覧</span><span class="sxs-lookup"><span data-stu-id="decfe-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="decfe-133">string</span><span class="sxs-lookup"><span data-stu-id="decfe-133">string</span></span> | <span data-ttu-id="decfe-134">構成に関連する Mitre ATT&CK フレームワーク戦術の一覧</span><span class="sxs-lookup"><span data-stu-id="decfe-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="decfe-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="decfe-135">Related topics</span></span>

- [<span data-ttu-id="decfe-136">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="decfe-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="decfe-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="decfe-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="decfe-138">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="decfe-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="decfe-139">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="decfe-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="decfe-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="decfe-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="decfe-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="decfe-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="decfe-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="decfe-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
