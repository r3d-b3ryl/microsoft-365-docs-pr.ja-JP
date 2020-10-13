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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4571b5bb22ef8aa800607f81cc00f15c28172548
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429860"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="9212b-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="9212b-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9212b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9212b-105">**Applies to:**</span></span>
- <span data-ttu-id="9212b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9212b-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="9212b-107">高度な検索スキーマの `DeviceTvmSoftwareInventoryVulnerabilities` のテーブルには、お使いのデバイス上のソフトウェアの [ の脅威および脆弱性管理 ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のインベントリと、これらのソフトウェア製品の既知の脆弱性に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9212b-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="9212b-108">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="9212b-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="9212b-109">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9212b-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9212b-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9212b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9212b-111">列名</span><span class="sxs-lookup"><span data-stu-id="9212b-111">Column name</span></span> | <span data-ttu-id="9212b-112">データ型</span><span class="sxs-lookup"><span data-stu-id="9212b-112">Data type</span></span> | <span data-ttu-id="9212b-113">説明</span><span class="sxs-lookup"><span data-stu-id="9212b-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="9212b-114">string</span><span class="sxs-lookup"><span data-stu-id="9212b-114">string</span></span> | <span data-ttu-id="9212b-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="9212b-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9212b-116">string</span><span class="sxs-lookup"><span data-stu-id="9212b-116">string</span></span> | <span data-ttu-id="9212b-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9212b-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="9212b-118">string</span><span class="sxs-lookup"><span data-stu-id="9212b-118">string</span></span> | <span data-ttu-id="9212b-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="9212b-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="9212b-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="9212b-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="9212b-121">string</span><span class="sxs-lookup"><span data-stu-id="9212b-121">string</span></span> | <span data-ttu-id="9212b-122">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="9212b-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="9212b-123">string</span><span class="sxs-lookup"><span data-stu-id="9212b-123">string</span></span> | <span data-ttu-id="9212b-124">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="9212b-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="9212b-125">string</span><span class="sxs-lookup"><span data-stu-id="9212b-125">string</span></span> | <span data-ttu-id="9212b-126">ソフトウェアベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="9212b-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="9212b-127">string</span><span class="sxs-lookup"><span data-stu-id="9212b-127">string</span></span> | <span data-ttu-id="9212b-128">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="9212b-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="9212b-129">string</span><span class="sxs-lookup"><span data-stu-id="9212b-129">string</span></span> | <span data-ttu-id="9212b-130">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="9212b-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="9212b-131">string</span><span class="sxs-lookup"><span data-stu-id="9212b-131">string</span></span> | <span data-ttu-id="9212b-132">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="9212b-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="9212b-133">string</span><span class="sxs-lookup"><span data-stu-id="9212b-133">string</span></span> | <span data-ttu-id="9212b-134">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="9212b-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="9212b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9212b-135">Related topics</span></span>

- [<span data-ttu-id="9212b-136">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="9212b-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9212b-137">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="9212b-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9212b-138">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="9212b-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9212b-139">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="9212b-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9212b-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9212b-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9212b-141">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="9212b-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9212b-142">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="9212b-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
