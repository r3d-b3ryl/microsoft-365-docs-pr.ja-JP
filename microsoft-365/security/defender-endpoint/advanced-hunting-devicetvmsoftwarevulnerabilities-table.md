---
title: 高度な狩猟スキーマの DeviceTvmSoftwareVulnerabilities テーブル
description: デバイスで見つかったソフトウェアの脆弱性と、高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilities テーブルの各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威& 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067996"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="3abc9-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="3abc9-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3abc9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3abc9-105">**Applies to:**</span></span>
- [<span data-ttu-id="3abc9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3abc9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="3abc9-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3abc9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3abc9-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3abc9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3abc9-109">高度 `DeviceTvmSoftwareVulnerabilities` な検索スキーマの表には、インストールされている [ソフトウェア製品の&](next-gen-threat-and-vuln-mgt.md) の脅威と脆弱性管理の一覧が記載されています。</span><span class="sxs-lookup"><span data-stu-id="3abc9-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="3abc9-110">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="3abc9-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="3abc9-111">たとえば、この表を使用して、ソフトウェアに重大な脆弱性を持つデバイスに関連するイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="3abc9-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="3abc9-112">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3abc9-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="3abc9-113">テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。</span><span class="sxs-lookup"><span data-stu-id="3abc9-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="3abc9-114">最初の 2 つの表には、脆弱性管理アクティビティの通知に使用できる列が追加されています。</span><span class="sxs-lookup"><span data-stu-id="3abc9-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="3abc9-115">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3abc9-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="3abc9-116">列名</span><span class="sxs-lookup"><span data-stu-id="3abc9-116">Column name</span></span> | <span data-ttu-id="3abc9-117">データ型</span><span class="sxs-lookup"><span data-stu-id="3abc9-117">Data type</span></span> | <span data-ttu-id="3abc9-118">説明</span><span class="sxs-lookup"><span data-stu-id="3abc9-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3abc9-119">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-119">string</span></span> | <span data-ttu-id="3abc9-120">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="3abc9-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3abc9-121">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-121">string</span></span> | <span data-ttu-id="3abc9-122">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3abc9-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="3abc9-123">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-123">string</span></span> | <span data-ttu-id="3abc9-124">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="3abc9-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3abc9-125">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="3abc9-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="3abc9-126">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-126">string</span></span> | <span data-ttu-id="3abc9-127">デバイスで実行されているオペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="3abc9-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="3abc9-128">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-128">string</span></span> | <span data-ttu-id="3abc9-129">デバイスで実行されているオペレーティング システムのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="3abc9-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="3abc9-130">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-130">string</span></span> | <span data-ttu-id="3abc9-131">ソフトウェア ベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="3abc9-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="3abc9-132">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-132">string</span></span> | <span data-ttu-id="3abc9-133">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="3abc9-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="3abc9-134">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-134">string</span></span> | <span data-ttu-id="3abc9-135">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="3abc9-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="3abc9-136">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-136">string</span></span> | <span data-ttu-id="3abc9-137">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="3abc9-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="3abc9-138">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-138">string</span></span> | <span data-ttu-id="3abc9-139">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="3abc9-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="3abc9-140">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-140">string</span></span> | <span data-ttu-id="3abc9-141">ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明</span><span class="sxs-lookup"><span data-stu-id="3abc9-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="3abc9-142">string</span><span class="sxs-lookup"><span data-stu-id="3abc9-142">string</span></span> | <span data-ttu-id="3abc9-143">対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子</span><span class="sxs-lookup"><span data-stu-id="3abc9-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="3abc9-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3abc9-144">Related topics</span></span>

- [<span data-ttu-id="3abc9-145">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3abc9-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3abc9-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3abc9-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3abc9-147">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3abc9-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="3abc9-148">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="3abc9-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
