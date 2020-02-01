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
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6084f64838903a40d9b7c827efb182e6927a15db
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600304"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="25d26-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="25d26-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="25d26-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25d26-106">**Applies to:**</span></span>
- <span data-ttu-id="25d26-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="25d26-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="25d26-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="25d26-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="25d26-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25d26-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="25d26-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25d26-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="25d26-111">列名</span><span class="sxs-lookup"><span data-stu-id="25d26-111">Column name</span></span> | <span data-ttu-id="25d26-112">データ型</span><span class="sxs-lookup"><span data-stu-id="25d26-112">Data type</span></span> | <span data-ttu-id="25d26-113">説明</span><span class="sxs-lookup"><span data-stu-id="25d26-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="25d26-114">string</span><span class="sxs-lookup"><span data-stu-id="25d26-114">string</span></span> | <span data-ttu-id="25d26-115">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="25d26-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="25d26-116">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-116">string</span></span> | <span data-ttu-id="25d26-117">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="25d26-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="25d26-118">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-118">string</span></span> | <span data-ttu-id="25d26-119">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="25d26-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="25d26-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="25d26-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="25d26-121">datetime</span><span class="sxs-lookup"><span data-stu-id="25d26-121">datetime</span></span> | <span data-ttu-id="25d26-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="25d26-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="25d26-123">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-123">string</span></span> | <span data-ttu-id="25d26-124">特定の構成における一意の識別子</span><span class="sxs-lookup"><span data-stu-id="25d26-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="25d26-125">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-125">string</span></span> | <span data-ttu-id="25d26-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="25d26-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="25d26-127">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-127">string</span></span> | <span data-ttu-id="25d26-128">構成が属する下位カテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="25d26-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="25d26-129">多くの場合、これは特定の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="25d26-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="25d26-130">文字列</span><span class="sxs-lookup"><span data-stu-id="25d26-130">string</span></span> | <span data-ttu-id="25d26-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="25d26-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="25d26-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="25d26-132">boolean</span></span> | <span data-ttu-id="25d26-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="25d26-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="25d26-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="25d26-134">Related topics</span></span>

- [<span data-ttu-id="25d26-135">積極的に脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="25d26-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="25d26-136">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="25d26-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="25d26-137">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="25d26-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="25d26-138">デバイスとメールの脅威を検索する</span><span class="sxs-lookup"><span data-stu-id="25d26-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="25d26-139">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="25d26-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="25d26-140">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="25d26-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="25d26-141">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="25d26-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
