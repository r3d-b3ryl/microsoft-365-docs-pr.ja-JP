---
title: 高度な狩猟スキーマの DeviceTvmSoftwareVulnerabilities テーブル
description: デバイスで見つかったソフトウェアの脆弱性と、高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilities テーブルの各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6911031e3caa27eff80bb83a3a88643cac2b6918
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065924"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="f305e-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="f305e-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f305e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f305e-105">**Applies to:**</span></span>
- <span data-ttu-id="f305e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f305e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f305e-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="f305e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f305e-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="f305e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f305e-109">高度 `DeviceTvmSoftwareVulnerabilities` な検索スキーマの表には、インストールされている [ソフトウェア製品の&](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) の脅威と脆弱性管理の一覧が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f305e-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="f305e-110">このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f305e-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="f305e-111">たとえば、この表を使用して、ソフトウェアに重大な脆弱性を持つデバイスに関連するイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="f305e-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="f305e-112">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f305e-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="f305e-113">テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。</span><span class="sxs-lookup"><span data-stu-id="f305e-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="f305e-114">最初の 2 つのテーブルには、脆弱な管理アクティビティを通知したり、脆弱なデバイスを探したりするのに役立つ列が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f305e-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="f305e-115">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f305e-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f305e-116">列名</span><span class="sxs-lookup"><span data-stu-id="f305e-116">Column name</span></span> | <span data-ttu-id="f305e-117">データ型</span><span class="sxs-lookup"><span data-stu-id="f305e-117">Data type</span></span> | <span data-ttu-id="f305e-118">説明</span><span class="sxs-lookup"><span data-stu-id="f305e-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f305e-119">string</span><span class="sxs-lookup"><span data-stu-id="f305e-119">string</span></span> | <span data-ttu-id="f305e-120">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="f305e-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f305e-121">string</span><span class="sxs-lookup"><span data-stu-id="f305e-121">string</span></span> | <span data-ttu-id="f305e-122">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="f305e-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="f305e-123">string</span><span class="sxs-lookup"><span data-stu-id="f305e-123">string</span></span> | <span data-ttu-id="f305e-124">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="f305e-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="f305e-125">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="f305e-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="f305e-126">string</span><span class="sxs-lookup"><span data-stu-id="f305e-126">string</span></span> | <span data-ttu-id="f305e-127">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="f305e-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="f305e-128">string</span><span class="sxs-lookup"><span data-stu-id="f305e-128">string</span></span> | <span data-ttu-id="f305e-129">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="f305e-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="f305e-130">string</span><span class="sxs-lookup"><span data-stu-id="f305e-130">string</span></span> | <span data-ttu-id="f305e-131">ソフトウェア ベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="f305e-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="f305e-132">string</span><span class="sxs-lookup"><span data-stu-id="f305e-132">string</span></span> | <span data-ttu-id="f305e-133">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="f305e-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="f305e-134">string</span><span class="sxs-lookup"><span data-stu-id="f305e-134">string</span></span> | <span data-ttu-id="f305e-135">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="f305e-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="f305e-136">string</span><span class="sxs-lookup"><span data-stu-id="f305e-136">string</span></span> | <span data-ttu-id="f305e-137">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="f305e-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f305e-138">string</span><span class="sxs-lookup"><span data-stu-id="f305e-138">string</span></span> | <span data-ttu-id="f305e-139">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="f305e-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="f305e-140">string</span><span class="sxs-lookup"><span data-stu-id="f305e-140">string</span></span> | <span data-ttu-id="f305e-141">ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明</span><span class="sxs-lookup"><span data-stu-id="f305e-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="f305e-142">string</span><span class="sxs-lookup"><span data-stu-id="f305e-142">string</span></span> | <span data-ttu-id="f305e-143">対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子</span><span class="sxs-lookup"><span data-stu-id="f305e-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="f305e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f305e-144">Related topics</span></span>

- [<span data-ttu-id="f305e-145">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="f305e-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f305e-146">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="f305e-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f305e-147">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="f305e-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f305e-148">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="f305e-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f305e-149">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="f305e-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f305e-150">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="f305e-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f305e-151">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="f305e-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)