---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブルの脅威および脆弱性管理セキュリティ評価イベントについて説明します。 これらのイベントは、コンピューターの情報とセキュリティ構成の詳細、影響、コンプライアンス情報を提供します。
keywords: 高度な検索、脅威の調査、サイバー脅威の調査、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、threat & 脆弱性管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 3d58ba24aa3ad2226cfae3ee96a8f0ed3a1c9566
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210302"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="372a9-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="372a9-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="372a9-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="372a9-106">**Applies to:**</span></span>
- <span data-ttu-id="372a9-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="372a9-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="372a9-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="372a9-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="372a9-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="372a9-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="372a9-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="372a9-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="372a9-111">列名</span><span class="sxs-lookup"><span data-stu-id="372a9-111">Column name</span></span> | <span data-ttu-id="372a9-112">データ型</span><span class="sxs-lookup"><span data-stu-id="372a9-112">Data type</span></span> | <span data-ttu-id="372a9-113">説明</span><span class="sxs-lookup"><span data-stu-id="372a9-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="372a9-114">string</span><span class="sxs-lookup"><span data-stu-id="372a9-114">string</span></span> | <span data-ttu-id="372a9-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="372a9-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="372a9-116">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-116">string</span></span> | <span data-ttu-id="372a9-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="372a9-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="372a9-118">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-118">string</span></span> | <span data-ttu-id="372a9-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="372a9-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="372a9-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="372a9-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="372a9-121">datetime</span><span class="sxs-lookup"><span data-stu-id="372a9-121">datetime</span></span> | <span data-ttu-id="372a9-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="372a9-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="372a9-123">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-123">string</span></span> | <span data-ttu-id="372a9-124">特定の構成における一意の識別子</span><span class="sxs-lookup"><span data-stu-id="372a9-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="372a9-125">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-125">string</span></span> | <span data-ttu-id="372a9-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="372a9-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="372a9-127">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-127">string</span></span> | <span data-ttu-id="372a9-128">構成が属する下位カテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="372a9-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="372a9-129">多くの場合、これは特定の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="372a9-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="372a9-130">文字列</span><span class="sxs-lookup"><span data-stu-id="372a9-130">string</span></span> | <span data-ttu-id="372a9-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="372a9-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="372a9-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="372a9-132">boolean</span></span> | <span data-ttu-id="372a9-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="372a9-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="372a9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="372a9-134">Related topics</span></span>

- [<span data-ttu-id="372a9-135">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="372a9-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="372a9-136">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="372a9-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="372a9-137">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="372a9-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="372a9-138">デバイスとメールの脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="372a9-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="372a9-139">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="372a9-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="372a9-140">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="372a9-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="372a9-141">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="372a9-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
