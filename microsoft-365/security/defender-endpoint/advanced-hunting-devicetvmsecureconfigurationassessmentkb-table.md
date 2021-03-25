---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: Advanced ハンティング スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルで、Threat & の脆弱性管理によって評価されるさまざまなセキュリティで保護された構成について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、セキュリティ構成、MITRE ATT&CK フレームワーク、ナレッジ ベース、KB、DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067004"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="a2f8c-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="a2f8c-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2f8c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a2f8c-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2f8c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2f8c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a2f8c-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a2f8c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2f8c-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a2f8c-109">高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](next-gen-threat-and-vuln-mgt.md)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="a2f8c-110">このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="a2f8c-111">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a2f8c-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="a2f8c-113">列名</span><span class="sxs-lookup"><span data-stu-id="a2f8c-113">Column name</span></span> | <span data-ttu-id="a2f8c-114">データ型</span><span class="sxs-lookup"><span data-stu-id="a2f8c-114">Data type</span></span> | <span data-ttu-id="a2f8c-115">説明</span><span class="sxs-lookup"><span data-stu-id="a2f8c-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="a2f8c-116">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-116">string</span></span> | <span data-ttu-id="a2f8c-117">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="a2f8c-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="a2f8c-118">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-118">string</span></span> | <span data-ttu-id="a2f8c-119">構成が全体の構成スコアに与える影響の評価 (1-10)</span><span class="sxs-lookup"><span data-stu-id="a2f8c-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="a2f8c-120">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-120">string</span></span> | <span data-ttu-id="a2f8c-121">構成の表示名</span><span class="sxs-lookup"><span data-stu-id="a2f8c-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="a2f8c-122">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-122">string</span></span> | <span data-ttu-id="a2f8c-123">構成の説明</span><span class="sxs-lookup"><span data-stu-id="a2f8c-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="a2f8c-124">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-124">string</span></span> | <span data-ttu-id="a2f8c-125">関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="a2f8c-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="a2f8c-126">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-126">string</span></span> | <span data-ttu-id="a2f8c-127">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="a2f8c-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="a2f8c-128">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-128">string</span></span> |<span data-ttu-id="a2f8c-129">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="a2f8c-130">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2f8c-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="a2f8c-131">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-131">string</span></span> | <span data-ttu-id="a2f8c-132">同じ構成または類似した構成を推奨する業界ベンチマークの一覧</span><span class="sxs-lookup"><span data-stu-id="a2f8c-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="a2f8c-133">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-133">string</span></span> | <span data-ttu-id="a2f8c-134">構成に関連する Mitre ATT&CK フレームワーク テクニックの一覧</span><span class="sxs-lookup"><span data-stu-id="a2f8c-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="a2f8c-135">string</span><span class="sxs-lookup"><span data-stu-id="a2f8c-135">string</span></span> | <span data-ttu-id="a2f8c-136">構成に関連する Mitre ATT&CK フレームワーク戦術の一覧</span><span class="sxs-lookup"><span data-stu-id="a2f8c-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a2f8c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2f8c-137">Related topics</span></span>

- [<span data-ttu-id="a2f8c-138">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="a2f8c-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2f8c-139">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="a2f8c-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a2f8c-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="a2f8c-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="a2f8c-141">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="a2f8c-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
