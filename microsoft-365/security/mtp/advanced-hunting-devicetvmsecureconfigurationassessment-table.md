---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブルにあるセキュリティ評価イベントについて説明します。 これらの脅威 & 脆弱性管理イベントは、デバイス情報だけでなく、セキュリティ構成の詳細、影響、およびコンプライアンス情報を提供します。
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770075"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="2f851-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="2f851-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2f851-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2f851-106">**Applies to:**</span></span>
- <span data-ttu-id="2f851-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2f851-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="2f851-108">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f851-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="2f851-109">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f851-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="2f851-110">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f851-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2f851-111">列名</span><span class="sxs-lookup"><span data-stu-id="2f851-111">Column name</span></span> | <span data-ttu-id="2f851-112">データ型</span><span class="sxs-lookup"><span data-stu-id="2f851-112">Data type</span></span> | <span data-ttu-id="2f851-113">説明</span><span class="sxs-lookup"><span data-stu-id="2f851-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2f851-114">string</span><span class="sxs-lookup"><span data-stu-id="2f851-114">string</span></span> | <span data-ttu-id="2f851-115">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2f851-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2f851-116">string</span><span class="sxs-lookup"><span data-stu-id="2f851-116">string</span></span> | <span data-ttu-id="2f851-117">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2f851-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="2f851-118">string</span><span class="sxs-lookup"><span data-stu-id="2f851-118">string</span></span> | <span data-ttu-id="2f851-119">デバイス上で実行されているオペレーティングシステムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="2f851-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2f851-120">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="2f851-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="2f851-121">datetime</span><span class="sxs-lookup"><span data-stu-id="2f851-121">datetime</span></span> | <span data-ttu-id="2f851-122">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="2f851-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="2f851-123">文字列</span><span class="sxs-lookup"><span data-stu-id="2f851-123">string</span></span> | <span data-ttu-id="2f851-124">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="2f851-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2f851-125">string</span><span class="sxs-lookup"><span data-stu-id="2f851-125">string</span></span> | <span data-ttu-id="2f851-126">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="2f851-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="2f851-127">string</span><span class="sxs-lookup"><span data-stu-id="2f851-127">string</span></span> | <span data-ttu-id="2f851-128">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="2f851-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2f851-129">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="2f851-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2f851-130">文字列</span><span class="sxs-lookup"><span data-stu-id="2f851-130">string</span></span> | <span data-ttu-id="2f851-131">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="2f851-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="2f851-132">ブール値</span><span class="sxs-lookup"><span data-stu-id="2f851-132">boolean</span></span> | <span data-ttu-id="2f851-133">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="2f851-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="2f851-134">ブール値</span><span class="sxs-lookup"><span data-stu-id="2f851-134">boolean</span></span> | <span data-ttu-id="2f851-135">構成またはポリシーがデバイスに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2f851-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="2f851-136">string</span><span class="sxs-lookup"><span data-stu-id="2f851-136">string</span></span> | <span data-ttu-id="2f851-137">構成またはポリシーに関するその他のコンテキスト情報</span><span class="sxs-lookup"><span data-stu-id="2f851-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="2f851-138">ブール値</span><span class="sxs-lookup"><span data-stu-id="2f851-138">boolean</span></span> | <span data-ttu-id="2f851-139">構成またはポリシーが適用されている場合にユーザーに影響があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2f851-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2f851-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f851-140">Related topics</span></span>

- [<span data-ttu-id="2f851-141">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="2f851-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2f851-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2f851-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2f851-143">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2f851-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2f851-144">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="2f851-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2f851-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2f851-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2f851-146">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2f851-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2f851-147">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="2f851-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
