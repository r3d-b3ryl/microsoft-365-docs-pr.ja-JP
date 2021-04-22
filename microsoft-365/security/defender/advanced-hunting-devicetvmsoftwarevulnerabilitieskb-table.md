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
ms.openlocfilehash: 0c9a29a75b2dc6ea2ae88f84e21ee2ab6455b2b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933015"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="1900d-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="1900d-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1900d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1900d-105">**Applies to:**</span></span>
- <span data-ttu-id="1900d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1900d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="1900d-107">高度な捜索スキーマの `DeviceTvmSoftwareVulnerabilitiesKB` テーブルには、[脅威と脆弱性の管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)が評価するデバイスの脆弱性リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1900d-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="1900d-108">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1900d-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1900d-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1900d-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1900d-110">列名</span><span class="sxs-lookup"><span data-stu-id="1900d-110">Column name</span></span> | <span data-ttu-id="1900d-111">データ型</span><span class="sxs-lookup"><span data-stu-id="1900d-111">Data type</span></span> | <span data-ttu-id="1900d-112">説明</span><span class="sxs-lookup"><span data-stu-id="1900d-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="1900d-113">string</span><span class="sxs-lookup"><span data-stu-id="1900d-113">string</span></span> | <span data-ttu-id="1900d-114">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="1900d-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="1900d-115">文字列型</span><span class="sxs-lookup"><span data-stu-id="1900d-115">string</span></span> | <span data-ttu-id="1900d-116">共通脆弱性評価システム (CVSS) でセキュリティの脆弱性に割り当てられている重大度スコア</span><span class="sxs-lookup"><span data-stu-id="1900d-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="1900d-117">ブール型</span><span class="sxs-lookup"><span data-stu-id="1900d-117">boolean</span></span> | <span data-ttu-id="1900d-118">脆弱性の悪用コードが公開されているかどうかを示す</span><span class="sxs-lookup"><span data-stu-id="1900d-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="1900d-119">文字列型</span><span class="sxs-lookup"><span data-stu-id="1900d-119">string</span></span> | <span data-ttu-id="1900d-120">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="1900d-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="1900d-121">日付型</span><span class="sxs-lookup"><span data-stu-id="1900d-121">datetime</span></span> | <span data-ttu-id="1900d-122">アイテムまたは関連するメタデータが最後に変更された日付</span><span class="sxs-lookup"><span data-stu-id="1900d-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="1900d-123">日付型</span><span class="sxs-lookup"><span data-stu-id="1900d-123">datetime</span></span> | <span data-ttu-id="1900d-124">脆弱性が一般に公開された日付</span><span class="sxs-lookup"><span data-stu-id="1900d-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="1900d-125">文字列型</span><span class="sxs-lookup"><span data-stu-id="1900d-125">string</span></span> | <span data-ttu-id="1900d-126">脆弱性と関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="1900d-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="1900d-127">文字列型</span><span class="sxs-lookup"><span data-stu-id="1900d-127">string</span></span> | <span data-ttu-id="1900d-128">脆弱性の影響を受けるすべてのソフトウェア製品の一覧</span><span class="sxs-lookup"><span data-stu-id="1900d-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1900d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1900d-129">Related topics</span></span>

- [<span data-ttu-id="1900d-130">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="1900d-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1900d-131">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="1900d-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1900d-132">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="1900d-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1900d-133">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="1900d-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1900d-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="1900d-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1900d-135">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="1900d-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1900d-136">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="1900d-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)