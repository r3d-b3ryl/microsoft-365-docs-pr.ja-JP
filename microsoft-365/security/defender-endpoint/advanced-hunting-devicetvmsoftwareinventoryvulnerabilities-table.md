---
title: 高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブル
description: お使いのデバイスのソフトウェアのインベントリと、その脆弱性の詳細については、高度な検索スキーマの DeviceTvmSoftwareInventoryVulnerabilities テーブルを参照してください。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威& 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163461"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="d5e31-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="d5e31-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d5e31-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d5e31-105">**Applies to:**</span></span>

- [<span data-ttu-id="d5e31-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5e31-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="d5e31-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d5e31-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d5e31-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d5e31-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d5e31-109">高度な検索スキーマの `DeviceTvmSoftwareInventoryVulnerabilities` のテーブルには、お使いのデバイス上のソフトウェアの [ の脅威および脆弱性管理 ](next-gen-threat-and-vuln-mgt.md) のインベントリと、これらのソフトウェア製品の既知の脆弱性に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5e31-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="d5e31-110">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5e31-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="d5e31-111">このテーブルの情報を返すクエリを作成するには、この参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5e31-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d5e31-112">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e31-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="d5e31-113">列名</span><span class="sxs-lookup"><span data-stu-id="d5e31-113">Column name</span></span> | <span data-ttu-id="d5e31-114">データ型</span><span class="sxs-lookup"><span data-stu-id="d5e31-114">Data type</span></span> | <span data-ttu-id="d5e31-115">説明</span><span class="sxs-lookup"><span data-stu-id="d5e31-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="d5e31-116">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-116">string</span></span> | <span data-ttu-id="d5e31-117">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="d5e31-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d5e31-118">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-118">string</span></span> | <span data-ttu-id="d5e31-119">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d5e31-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="d5e31-120">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-120">string</span></span> | <span data-ttu-id="d5e31-121">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="d5e31-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d5e31-122">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="d5e31-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="d5e31-123">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-123">string</span></span> | <span data-ttu-id="d5e31-124">デバイスで実行されているオペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="d5e31-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="d5e31-125">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-125">string</span></span> | <span data-ttu-id="d5e31-126">デバイスで実行されているオペレーティング システムのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d5e31-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="d5e31-127">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-127">string</span></span> | <span data-ttu-id="d5e31-128">ソフトウェア ベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="d5e31-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="d5e31-129">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-129">string</span></span> | <span data-ttu-id="d5e31-130">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="d5e31-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="d5e31-131">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-131">string</span></span> | <span data-ttu-id="d5e31-132">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="d5e31-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="d5e31-133">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-133">string</span></span> | <span data-ttu-id="d5e31-134">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="d5e31-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d5e31-135">string</span><span class="sxs-lookup"><span data-stu-id="d5e31-135">string</span></span> | <span data-ttu-id="d5e31-136">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="d5e31-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="d5e31-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5e31-137">Related topics</span></span>

- [<span data-ttu-id="d5e31-138">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="d5e31-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d5e31-139">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d5e31-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d5e31-140">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d5e31-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d5e31-141">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="d5e31-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
