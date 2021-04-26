---
title: 高度な捜索スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブル
description: 高度な捜索スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブルで、脅威と脆弱性の管理によって追跡されるソフトウェアの脆弱性について説明します。
keywords: 高度なハンティング、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ、リファレンス、kusto、table、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、CVSS、DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023799"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="86202-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="86202-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="86202-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="86202-105">**Applies to:**</span></span>
- <span data-ttu-id="86202-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86202-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="86202-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86202-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="86202-108">高度な捜索スキーマの `DeviceTvmSoftwareVulnerabilitiesKB` テーブルには、[脅威と脆弱性の管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)が評価するデバイスの脆弱性リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="86202-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="86202-109">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="86202-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="86202-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86202-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="86202-111">列名</span><span class="sxs-lookup"><span data-stu-id="86202-111">Column name</span></span> | <span data-ttu-id="86202-112">データ型</span><span class="sxs-lookup"><span data-stu-id="86202-112">Data type</span></span> | <span data-ttu-id="86202-113">説明</span><span class="sxs-lookup"><span data-stu-id="86202-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="86202-114">string</span><span class="sxs-lookup"><span data-stu-id="86202-114">string</span></span> | <span data-ttu-id="86202-115">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="86202-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="86202-116">文字列型</span><span class="sxs-lookup"><span data-stu-id="86202-116">string</span></span> | <span data-ttu-id="86202-117">共通脆弱性評価システム (CVSS) でセキュリティの脆弱性に割り当てられている重大度スコア</span><span class="sxs-lookup"><span data-stu-id="86202-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="86202-118">ブール型</span><span class="sxs-lookup"><span data-stu-id="86202-118">boolean</span></span> | <span data-ttu-id="86202-119">脆弱性の悪用コードが公開されているかどうかを示す</span><span class="sxs-lookup"><span data-stu-id="86202-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="86202-120">文字列型</span><span class="sxs-lookup"><span data-stu-id="86202-120">string</span></span> | <span data-ttu-id="86202-121">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="86202-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="86202-122">日付型</span><span class="sxs-lookup"><span data-stu-id="86202-122">datetime</span></span> | <span data-ttu-id="86202-123">アイテムまたは関連するメタデータが最後に変更された日付</span><span class="sxs-lookup"><span data-stu-id="86202-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="86202-124">日付型</span><span class="sxs-lookup"><span data-stu-id="86202-124">datetime</span></span> | <span data-ttu-id="86202-125">脆弱性が一般に公開された日付</span><span class="sxs-lookup"><span data-stu-id="86202-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="86202-126">文字列型</span><span class="sxs-lookup"><span data-stu-id="86202-126">string</span></span> | <span data-ttu-id="86202-127">脆弱性と関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="86202-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="86202-128">文字列型</span><span class="sxs-lookup"><span data-stu-id="86202-128">string</span></span> | <span data-ttu-id="86202-129">脆弱性の影響を受けるすべてのソフトウェア製品の一覧</span><span class="sxs-lookup"><span data-stu-id="86202-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="86202-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="86202-130">Related topics</span></span>

- [<span data-ttu-id="86202-131">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="86202-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="86202-132">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="86202-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="86202-133">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="86202-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="86202-134">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="86202-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="86202-135">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="86202-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="86202-136">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="86202-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="86202-137">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="86202-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)