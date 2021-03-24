---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度なハンティング スキーマの DeviceTvmSecureConfigurationAssessment テーブルのセキュリティ評価イベントについて説明します。 これらの脅威&管理イベントによって、デバイス情報、セキュリティ構成の詳細、影響、コンプライアンス情報が提供されます。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威& 脆弱性管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cf37fe2aeac193c6b45f55fd5f5c850470ba6da4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063460"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="3177b-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="3177b-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3177b-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3177b-106">**Applies to:**</span></span>
- <span data-ttu-id="3177b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3177b-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="3177b-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3177b-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="3177b-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3177b-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="3177b-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3177b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3177b-111">列名</span><span class="sxs-lookup"><span data-stu-id="3177b-111">Column name</span></span> | <span data-ttu-id="3177b-112">データ型</span><span class="sxs-lookup"><span data-stu-id="3177b-112">Data type</span></span> | <span data-ttu-id="3177b-113">説明</span><span class="sxs-lookup"><span data-stu-id="3177b-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="3177b-114">string</span><span class="sxs-lookup"><span data-stu-id="3177b-114">string</span></span> | <span data-ttu-id="3177b-115">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="3177b-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3177b-116">string</span><span class="sxs-lookup"><span data-stu-id="3177b-116">string</span></span> | <span data-ttu-id="3177b-117">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3177b-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="3177b-118">string</span><span class="sxs-lookup"><span data-stu-id="3177b-118">string</span></span> | <span data-ttu-id="3177b-119">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="3177b-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="3177b-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="3177b-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="3177b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="3177b-121">datetime</span></span> | <span data-ttu-id="3177b-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="3177b-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="3177b-123">文字列</span><span class="sxs-lookup"><span data-stu-id="3177b-123">string</span></span> | <span data-ttu-id="3177b-124">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="3177b-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="3177b-125">string</span><span class="sxs-lookup"><span data-stu-id="3177b-125">string</span></span> | <span data-ttu-id="3177b-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="3177b-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="3177b-127">string</span><span class="sxs-lookup"><span data-stu-id="3177b-127">string</span></span> | <span data-ttu-id="3177b-128">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="3177b-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="3177b-129">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="3177b-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="3177b-130">文字列</span><span class="sxs-lookup"><span data-stu-id="3177b-130">string</span></span> | <span data-ttu-id="3177b-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="3177b-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="3177b-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="3177b-132">boolean</span></span> | <span data-ttu-id="3177b-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="3177b-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="3177b-134">boolean</span><span class="sxs-lookup"><span data-stu-id="3177b-134">boolean</span></span> | <span data-ttu-id="3177b-135">構成またはポリシーがデバイスに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3177b-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="3177b-136">string</span><span class="sxs-lookup"><span data-stu-id="3177b-136">string</span></span> | <span data-ttu-id="3177b-137">構成またはポリシーに関するその他のコンテキスト情報</span><span class="sxs-lookup"><span data-stu-id="3177b-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="3177b-138">boolean</span><span class="sxs-lookup"><span data-stu-id="3177b-138">boolean</span></span> | <span data-ttu-id="3177b-139">構成またはポリシーが適用された場合にユーザーに影響を与えるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3177b-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3177b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3177b-140">Related topics</span></span>

- [<span data-ttu-id="3177b-141">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="3177b-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3177b-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3177b-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3177b-143">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3177b-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3177b-144">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="3177b-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3177b-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3177b-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3177b-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="3177b-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3177b-147">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="3177b-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)