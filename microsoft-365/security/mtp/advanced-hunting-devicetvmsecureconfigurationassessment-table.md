---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブルのセキュリティ評価イベントについて説明します。 これらの脅威&管理イベントは、デバイス情報だけでなく、セキュリティ構成の詳細、影響、コンプライアンス情報も提供します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931100"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="06ad9-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="06ad9-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="06ad9-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="06ad9-106">**Applies to:**</span></span>
- <span data-ttu-id="06ad9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06ad9-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="06ad9-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06ad9-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="06ad9-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="06ad9-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="06ad9-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06ad9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="06ad9-111">列名</span><span class="sxs-lookup"><span data-stu-id="06ad9-111">Column name</span></span> | <span data-ttu-id="06ad9-112">データ型</span><span class="sxs-lookup"><span data-stu-id="06ad9-112">Data type</span></span> | <span data-ttu-id="06ad9-113">説明</span><span class="sxs-lookup"><span data-stu-id="06ad9-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="06ad9-114">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-114">string</span></span> | <span data-ttu-id="06ad9-115">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="06ad9-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="06ad9-116">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-116">string</span></span> | <span data-ttu-id="06ad9-117">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="06ad9-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="06ad9-118">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-118">string</span></span> | <span data-ttu-id="06ad9-119">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="06ad9-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="06ad9-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="06ad9-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="06ad9-121">datetime</span><span class="sxs-lookup"><span data-stu-id="06ad9-121">datetime</span></span> | <span data-ttu-id="06ad9-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="06ad9-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="06ad9-123">文字列</span><span class="sxs-lookup"><span data-stu-id="06ad9-123">string</span></span> | <span data-ttu-id="06ad9-124">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="06ad9-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="06ad9-125">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-125">string</span></span> | <span data-ttu-id="06ad9-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="06ad9-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="06ad9-127">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-127">string</span></span> | <span data-ttu-id="06ad9-128">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="06ad9-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="06ad9-129">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="06ad9-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="06ad9-130">文字列</span><span class="sxs-lookup"><span data-stu-id="06ad9-130">string</span></span> | <span data-ttu-id="06ad9-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="06ad9-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="06ad9-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="06ad9-132">boolean</span></span> | <span data-ttu-id="06ad9-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="06ad9-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="06ad9-134">ブール値</span><span class="sxs-lookup"><span data-stu-id="06ad9-134">boolean</span></span> | <span data-ttu-id="06ad9-135">構成またはポリシーがデバイスに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="06ad9-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="06ad9-136">string</span><span class="sxs-lookup"><span data-stu-id="06ad9-136">string</span></span> | <span data-ttu-id="06ad9-137">構成またはポリシーに関するその他のコンテキスト情報</span><span class="sxs-lookup"><span data-stu-id="06ad9-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="06ad9-138">ブール値</span><span class="sxs-lookup"><span data-stu-id="06ad9-138">boolean</span></span> | <span data-ttu-id="06ad9-139">構成またはポリシーが適用された場合にユーザーに影響を与えるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="06ad9-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="06ad9-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="06ad9-140">Related topics</span></span>

- [<span data-ttu-id="06ad9-141">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="06ad9-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06ad9-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="06ad9-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06ad9-143">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="06ad9-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06ad9-144">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="06ad9-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06ad9-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="06ad9-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06ad9-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="06ad9-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="06ad9-147">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="06ad9-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
