---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブルの脅威および脆弱性管理セキュリティ評価イベントについて説明します。 これらのイベントは、コンピューターの情報とセキュリティ構成の詳細、影響、コンプライアンス情報を提供します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、検索、クエリ、テレメトリ、スキーマ リファレンス、Kusto、テーブル、列、データ型、説明、脅威および脆弱性管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d03b278fbf029b08b476f20292315807a3f5e32a
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808622"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="cda07-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="cda07-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="cda07-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cda07-106">**Applies to:**</span></span>
- <span data-ttu-id="cda07-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cda07-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="cda07-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cda07-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="cda07-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cda07-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="cda07-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cda07-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cda07-111">列名</span><span class="sxs-lookup"><span data-stu-id="cda07-111">Column name</span></span> | <span data-ttu-id="cda07-112">データ型</span><span class="sxs-lookup"><span data-stu-id="cda07-112">Data type</span></span> | <span data-ttu-id="cda07-113">説明</span><span class="sxs-lookup"><span data-stu-id="cda07-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="cda07-114">string</span><span class="sxs-lookup"><span data-stu-id="cda07-114">string</span></span> | <span data-ttu-id="cda07-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="cda07-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="cda07-116">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-116">string</span></span> | <span data-ttu-id="cda07-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cda07-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="cda07-118">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-118">string</span></span> | <span data-ttu-id="cda07-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="cda07-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="cda07-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="cda07-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="cda07-121">datetime</span><span class="sxs-lookup"><span data-stu-id="cda07-121">datetime</span></span> | <span data-ttu-id="cda07-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="cda07-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="cda07-123">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-123">string</span></span> | <span data-ttu-id="cda07-124">特定の構成における一意の識別子</span><span class="sxs-lookup"><span data-stu-id="cda07-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="cda07-125">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-125">string</span></span> | <span data-ttu-id="cda07-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="cda07-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="cda07-127">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-127">string</span></span> | <span data-ttu-id="cda07-128">構成が属する下位カテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="cda07-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="cda07-129">多くの場合、これは特定の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cda07-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="cda07-130">文字列</span><span class="sxs-lookup"><span data-stu-id="cda07-130">string</span></span> | <span data-ttu-id="cda07-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="cda07-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="cda07-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="cda07-132">boolean</span></span> | <span data-ttu-id="cda07-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="cda07-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cda07-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="cda07-134">Related topics</span></span>

- [<span data-ttu-id="cda07-135">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="cda07-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cda07-136">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="cda07-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cda07-137">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="cda07-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cda07-138">デバイスとメールの脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="cda07-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cda07-139">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="cda07-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cda07-140">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="cda07-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cda07-141">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="cda07-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
