---
title: 高度な捜索スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブル
description: 高度な捜索スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブルで、脅威と脆弱性の管理によって追跡されるソフトウェアの脆弱性について説明します。
keywords: 高度なハンティング、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、Threat & の脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、CVSS、DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062884"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="d313a-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="d313a-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d313a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d313a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d313a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d313a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="d313a-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d313a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d313a-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d313a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d313a-109">高度な捜索スキーマの `DeviceTvmSoftwareVulnerabilitiesKB` テーブルには、[脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)が評価するデバイスの脆弱性リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d313a-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="d313a-110">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d313a-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d313a-111">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-reference.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d313a-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="d313a-112">列名</span><span class="sxs-lookup"><span data-stu-id="d313a-112">Column name</span></span> | <span data-ttu-id="d313a-113">データ型</span><span class="sxs-lookup"><span data-stu-id="d313a-113">Data type</span></span> | <span data-ttu-id="d313a-114">説明</span><span class="sxs-lookup"><span data-stu-id="d313a-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="d313a-115">string</span><span class="sxs-lookup"><span data-stu-id="d313a-115">string</span></span> | <span data-ttu-id="d313a-116">共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子 </span><span class="sxs-lookup"><span data-stu-id="d313a-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="d313a-117">文字列型</span><span class="sxs-lookup"><span data-stu-id="d313a-117">string</span></span> | <span data-ttu-id="d313a-118">共通脆弱性評価システム (CVSS) でセキュリティの脆弱性に割り当てられている重大度スコア</span><span class="sxs-lookup"><span data-stu-id="d313a-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="d313a-119">ブール型</span><span class="sxs-lookup"><span data-stu-id="d313a-119">boolean</span></span> | <span data-ttu-id="d313a-120">脆弱性の悪用コードが公開されているかどうかを示す</span><span class="sxs-lookup"><span data-stu-id="d313a-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="d313a-121">文字列型</span><span class="sxs-lookup"><span data-stu-id="d313a-121">string</span></span> | <span data-ttu-id="d313a-122">CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル</span><span class="sxs-lookup"><span data-stu-id="d313a-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="d313a-123">日付型</span><span class="sxs-lookup"><span data-stu-id="d313a-123">datetime</span></span> | <span data-ttu-id="d313a-124">アイテムまたは関連するメタデータが最後に変更された日付</span><span class="sxs-lookup"><span data-stu-id="d313a-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="d313a-125">日付型</span><span class="sxs-lookup"><span data-stu-id="d313a-125">datetime</span></span> | <span data-ttu-id="d313a-126">脆弱性が一般に公開された日付</span><span class="sxs-lookup"><span data-stu-id="d313a-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="d313a-127">文字列型</span><span class="sxs-lookup"><span data-stu-id="d313a-127">string</span></span> | <span data-ttu-id="d313a-128">脆弱性と関連するリスクの説明</span><span class="sxs-lookup"><span data-stu-id="d313a-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="d313a-129">文字列型</span><span class="sxs-lookup"><span data-stu-id="d313a-129">string</span></span> | <span data-ttu-id="d313a-130">脆弱性の影響を受けるすべてのソフトウェア製品の一覧</span><span class="sxs-lookup"><span data-stu-id="d313a-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d313a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d313a-131">Related topics</span></span>

- [<span data-ttu-id="d313a-132">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="d313a-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d313a-133">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d313a-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d313a-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d313a-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d313a-135">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="d313a-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
