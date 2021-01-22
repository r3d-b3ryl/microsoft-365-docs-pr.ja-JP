---
title: 高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブル
description: お使いのデバイスのソフトウェアのインベントリと、その脆弱性の詳細については、高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブルを参照してください。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931076"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="c4fbe-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="c4fbe-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c4fbe-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c4fbe-105">**Applies to:**</span></span>
- <span data-ttu-id="c4fbe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4fbe-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c4fbe-107">高度な検索スキーマの `DeviceTvmSoftwareInventoryVulnerabilities` のテーブルには、お使いのデバイス上のソフトウェアの [ の脅威および脆弱性管理 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のインベントリと、これらのソフトウェア製品の既知の脆弱性に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="c4fbe-108">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="c4fbe-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c4fbe-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c4fbe-111">列名</span><span class="sxs-lookup"><span data-stu-id="c4fbe-111">Column name</span></span> | <span data-ttu-id="c4fbe-112">データ型</span><span class="sxs-lookup"><span data-stu-id="c4fbe-112">Data type</span></span> | <span data-ttu-id="c4fbe-113">説明</span><span class="sxs-lookup"><span data-stu-id="c4fbe-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c4fbe-114">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-114">string</span></span> | <span data-ttu-id="c4fbe-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="c4fbe-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c4fbe-116">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-116">string</span></span> | <span data-ttu-id="c4fbe-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c4fbe-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c4fbe-118">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-118">string</span></span> | <span data-ttu-id="c4fbe-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c4fbe-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="c4fbe-121">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-121">string</span></span> | <span data-ttu-id="c4fbe-122">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="c4fbe-123">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-123">string</span></span> | <span data-ttu-id="c4fbe-124">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="c4fbe-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="c4fbe-125">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-125">string</span></span> | <span data-ttu-id="c4fbe-126">ソフトウェア ベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="c4fbe-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="c4fbe-127">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-127">string</span></span> | <span data-ttu-id="c4fbe-128">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="c4fbe-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="c4fbe-129">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-129">string</span></span> | <span data-ttu-id="c4fbe-130">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="c4fbe-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="c4fbe-131">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-131">string</span></span> | <span data-ttu-id="c4fbe-132">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="c4fbe-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c4fbe-133">string</span><span class="sxs-lookup"><span data-stu-id="c4fbe-133">string</span></span> | <span data-ttu-id="c4fbe-134">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="c4fbe-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="c4fbe-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4fbe-135">Related topics</span></span>

- [<span data-ttu-id="c4fbe-136">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="c4fbe-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c4fbe-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="c4fbe-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c4fbe-138">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="c4fbe-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c4fbe-139">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="c4fbe-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c4fbe-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="c4fbe-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c4fbe-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="c4fbe-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c4fbe-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="c4fbe-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
