---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 詳細ハンティング スキーマ& DeviceTvmSecureConfigurationAssessment テーブルの脅威の脆弱性管理のセキュリティ評価イベントについて説明します。 これらのイベントは、デバイス情報とセキュリティ構成の詳細、影響、コンプライアンス情報を提供します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、Threat & の脆弱性管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067011"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="de229-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="de229-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de229-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="de229-106">**Applies to:**</span></span>
- [<span data-ttu-id="de229-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="de229-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="de229-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="de229-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="de229-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="de229-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="de229-110">`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](next-gen-threat-and-vuln-mgt.md) からの特定のセキュリティ構成に対する評価イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de229-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="de229-111">このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="de229-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="de229-112">高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de229-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="de229-113">列名</span><span class="sxs-lookup"><span data-stu-id="de229-113">Column name</span></span> | <span data-ttu-id="de229-114">データ型</span><span class="sxs-lookup"><span data-stu-id="de229-114">Data type</span></span> | <span data-ttu-id="de229-115">説明</span><span class="sxs-lookup"><span data-stu-id="de229-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="de229-116">string</span><span class="sxs-lookup"><span data-stu-id="de229-116">string</span></span> | <span data-ttu-id="de229-117">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="de229-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="de229-118">string</span><span class="sxs-lookup"><span data-stu-id="de229-118">string</span></span> | <span data-ttu-id="de229-119">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="de229-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="de229-120">string</span><span class="sxs-lookup"><span data-stu-id="de229-120">string</span></span> | <span data-ttu-id="de229-121">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="de229-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="de229-122">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="de229-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="de229-123">datetime</span><span class="sxs-lookup"><span data-stu-id="de229-123">datetime</span></span> |<span data-ttu-id="de229-124">レコードが作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="de229-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="de229-125">文字列</span><span class="sxs-lookup"><span data-stu-id="de229-125">string</span></span> | <span data-ttu-id="de229-126">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="de229-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="de229-127">string</span><span class="sxs-lookup"><span data-stu-id="de229-127">string</span></span> | <span data-ttu-id="de229-128">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="de229-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="de229-129">string</span><span class="sxs-lookup"><span data-stu-id="de229-129">string</span></span> |<span data-ttu-id="de229-130">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="de229-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="de229-131">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="de229-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="de229-132">文字列</span><span class="sxs-lookup"><span data-stu-id="de229-132">string</span></span> | <span data-ttu-id="de229-133">構成の評価が全体の構成スコア (1-10) に及ぼす影響</span><span class="sxs-lookup"><span data-stu-id="de229-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="de229-134">ブール値</span><span class="sxs-lookup"><span data-stu-id="de229-134">boolean</span></span> | <span data-ttu-id="de229-135">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="de229-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="de229-136">boolean</span><span class="sxs-lookup"><span data-stu-id="de229-136">boolean</span></span> | <span data-ttu-id="de229-137">構成またはポリシーがデバイスに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="de229-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="de229-138">string</span><span class="sxs-lookup"><span data-stu-id="de229-138">string</span></span> | <span data-ttu-id="de229-139">構成またはポリシーに関するその他のコンテキスト情報</span><span class="sxs-lookup"><span data-stu-id="de229-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="de229-140">boolean</span><span class="sxs-lookup"><span data-stu-id="de229-140">boolean</span></span> | <span data-ttu-id="de229-141">構成またはポリシーが適用された場合にユーザーに影響を与えるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="de229-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="de229-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="de229-142">Related topics</span></span>

- [<span data-ttu-id="de229-143">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="de229-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="de229-144">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="de229-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="de229-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="de229-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="de229-146">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="de229-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)