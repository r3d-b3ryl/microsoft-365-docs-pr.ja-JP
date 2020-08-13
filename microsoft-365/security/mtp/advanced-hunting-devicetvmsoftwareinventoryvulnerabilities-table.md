---
title: 高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブル
description: お使いのデバイスのソフトウェアのインベントリと、その脆弱性の詳細については、高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブルを参照してください。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、threat & 脆弱性管理、TVM、device management、software、inventory、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 70b687a185538b11cf0a8975eebf2a5d8b53ec11
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648955"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="ef016-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="ef016-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="ef016-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ef016-105">**Applies to:**</span></span>
- <span data-ttu-id="ef016-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ef016-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ef016-107">高度な検索スキーマの `DeviceTvmSoftwareInventoryVulnerabilities` のテーブルには、お使いのデバイス上のソフトウェアの [ の脅威および脆弱性管理 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のインベントリと、これらのソフトウェア製品の既知の脆弱性に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef016-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="ef016-108">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef016-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="ef016-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef016-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ef016-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef016-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ef016-111">列名</span><span class="sxs-lookup"><span data-stu-id="ef016-111">Column name</span></span> | <span data-ttu-id="ef016-112">データ型</span><span class="sxs-lookup"><span data-stu-id="ef016-112">Data type</span></span> | <span data-ttu-id="ef016-113">説明</span><span class="sxs-lookup"><span data-stu-id="ef016-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="ef016-114">string</span><span class="sxs-lookup"><span data-stu-id="ef016-114">string</span></span> | <span data-ttu-id="ef016-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ef016-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ef016-116">string</span><span class="sxs-lookup"><span data-stu-id="ef016-116">string</span></span> | <span data-ttu-id="ef016-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ef016-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="ef016-118">string</span><span class="sxs-lookup"><span data-stu-id="ef016-118">string</span></span> | <span data-ttu-id="ef016-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ef016-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="ef016-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="ef016-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="ef016-121">string</span><span class="sxs-lookup"><span data-stu-id="ef016-121">string</span></span> | <span data-ttu-id="ef016-122">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="ef016-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="ef016-123">string</span><span class="sxs-lookup"><span data-stu-id="ef016-123">string</span></span> | <span data-ttu-id="ef016-124">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="ef016-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="ef016-125">string</span><span class="sxs-lookup"><span data-stu-id="ef016-125">string</span></span> | <span data-ttu-id="ef016-126">ソフトウェアベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="ef016-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="ef016-127">string</span><span class="sxs-lookup"><span data-stu-id="ef016-127">string</span></span> | <span data-ttu-id="ef016-128">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="ef016-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="ef016-129">string</span><span class="sxs-lookup"><span data-stu-id="ef016-129">string</span></span> | <span data-ttu-id="ef016-130">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="ef016-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="ef016-131">string</span><span class="sxs-lookup"><span data-stu-id="ef016-131">string</span></span> | <span data-ttu-id="ef016-132">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="ef016-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="ef016-133">string</span><span class="sxs-lookup"><span data-stu-id="ef016-133">string</span></span> | <span data-ttu-id="ef016-134">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="ef016-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="ef016-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef016-135">Related topics</span></span>

- [<span data-ttu-id="ef016-136">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ef016-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ef016-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ef016-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ef016-138">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ef016-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ef016-139">デバイス、メール、アプリ、および id の間でのハント</span><span class="sxs-lookup"><span data-stu-id="ef016-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ef016-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ef016-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ef016-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ef016-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ef016-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="ef016-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
