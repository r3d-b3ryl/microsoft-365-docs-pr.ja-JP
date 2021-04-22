---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルに記載される、脅威および脆弱性管理により評価されるさまざまなセキュリティ構成について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、セキュリティ構成、MITRE ATT&CK フレームワーク、ナレッジ ベース、KB、DeviceTvmSecureConfigurationAssesmentKBSmentKB
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
ms.openlocfilehash: a387d917e5ae93a6289aa2af527d52f1ce1195f4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934870"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="010bb-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="010bb-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="010bb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="010bb-105">**Applies to:**</span></span>
- <span data-ttu-id="010bb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="010bb-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="010bb-107">高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="010bb-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="010bb-108">このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。</span><span class="sxs-lookup"><span data-stu-id="010bb-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="010bb-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="010bb-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="010bb-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="010bb-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="010bb-111">列名</span><span class="sxs-lookup"><span data-stu-id="010bb-111">Column name</span></span> | <span data-ttu-id="010bb-112">データ型</span><span class="sxs-lookup"><span data-stu-id="010bb-112">Data type</span></span> | <span data-ttu-id="010bb-113">説明</span><span class="sxs-lookup"><span data-stu-id="010bb-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="010bb-114">string</span><span class="sxs-lookup"><span data-stu-id="010bb-114">string</span></span> | <span data-ttu-id="010bb-115">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="010bb-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="010bb-116">string</span><span class="sxs-lookup"><span data-stu-id="010bb-116">string</span></span> | <span data-ttu-id="010bb-117">構成が全体の構成スコアに与える影響の評価 (1-10)</span><span class="sxs-lookup"><span data-stu-id="010bb-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="010bb-118">string</span><span class="sxs-lookup"><span data-stu-id="010bb-118">string</span></span> | <span data-ttu-id="010bb-119">構成の表示名</span><span class="sxs-lookup"><span data-stu-id="010bb-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="010bb-120">string</span><span class="sxs-lookup"><span data-stu-id="010bb-120">string</span></span> | <span data-ttu-id="010bb-121">構成の説明</span><span class="sxs-lookup"><span data-stu-id="010bb-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="010bb-122">string</span><span class="sxs-lookup"><span data-stu-id="010bb-122">string</span></span> | <span data-ttu-id="010bb-123">関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="010bb-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="010bb-124">string</span><span class="sxs-lookup"><span data-stu-id="010bb-124">string</span></span> | <span data-ttu-id="010bb-125">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="010bb-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="010bb-126">string</span><span class="sxs-lookup"><span data-stu-id="010bb-126">string</span></span> |<span data-ttu-id="010bb-127">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="010bb-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="010bb-128">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="010bb-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="010bb-129">string</span><span class="sxs-lookup"><span data-stu-id="010bb-129">string</span></span> | <span data-ttu-id="010bb-130">同じ構成または類似した構成を推奨する業界ベンチマークの一覧</span><span class="sxs-lookup"><span data-stu-id="010bb-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="010bb-131">string</span><span class="sxs-lookup"><span data-stu-id="010bb-131">string</span></span> | <span data-ttu-id="010bb-132">セキュリティ構成を識別または分類するために使用されるさまざまな属性を表すラベル</span><span class="sxs-lookup"><span data-stu-id="010bb-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="010bb-133">string</span><span class="sxs-lookup"><span data-stu-id="010bb-133">string</span></span> | <span data-ttu-id="010bb-134">関連するリスクを軽減または対処するために推奨されるアクション</span><span class="sxs-lookup"><span data-stu-id="010bb-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="010bb-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="010bb-135">Related topics</span></span>

- [<span data-ttu-id="010bb-136">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="010bb-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="010bb-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="010bb-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="010bb-138">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="010bb-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="010bb-139">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="010bb-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="010bb-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="010bb-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="010bb-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="010bb-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="010bb-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="010bb-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)