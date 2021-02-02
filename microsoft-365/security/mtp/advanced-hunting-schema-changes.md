---
title: Microsoft 365 Defender 高度な検索スキーマでの名前の変更
description: 高度な検索スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ、名前付けの変更、名前の変更、Microsoft Threat Protection
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066871"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="666d6-104">高度な検索スキーマ - 名前の変更</span><span class="sxs-lookup"><span data-stu-id="666d6-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="666d6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="666d6-105">**Applies to:**</span></span>
- <span data-ttu-id="666d6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="666d6-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="666d6-107">高度 [な検索スキーマは定期的](advanced-hunting-schema-tables.md) に更新され、新しいテーブルと列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="666d6-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="666d6-108">場合によっては、既存の列名の名前が変更または置換され、ユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="666d6-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="666d6-109">クエリに影響を与える可能性がある名前付けの変更を確認するには、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="666d6-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="666d6-110">名前付けの変更は、カスタム検出ルールで使用されるクエリを含め、セキュリティ センターに保存されるクエリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="666d6-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="666d6-111">これらのクエリを手動で更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="666d6-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="666d6-112">ただし、次のクエリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="666d6-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="666d6-113">API を使用して実行されるクエリ</span><span class="sxs-lookup"><span data-stu-id="666d6-113">Queries that are run using the API</span></span>
- <span data-ttu-id="666d6-114">セキュリティ センターの外部の別の場所に保存されるクエリ</span><span class="sxs-lookup"><span data-stu-id="666d6-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="666d6-115">2020年12月</span><span class="sxs-lookup"><span data-stu-id="666d6-115">December 2020</span></span>

| <span data-ttu-id="666d6-116">テーブル名</span><span class="sxs-lookup"><span data-stu-id="666d6-116">Table name</span></span> | <span data-ttu-id="666d6-117">元の列名</span><span class="sxs-lookup"><span data-stu-id="666d6-117">Original column name</span></span> | <span data-ttu-id="666d6-118">新しい列名</span><span class="sxs-lookup"><span data-stu-id="666d6-118">New column name</span></span> | <span data-ttu-id="666d6-119">変更理由</span><span class="sxs-lookup"><span data-stu-id="666d6-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="666d6-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="666d6-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="666d6-121">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="666d6-121">Customer feedback</span></span> |
| [<span data-ttu-id="666d6-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="666d6-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="666d6-123">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="666d6-123">Customer feedback</span></span> |
| [<span data-ttu-id="666d6-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="666d6-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="666d6-125">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="666d6-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="666d6-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="666d6-126">January 2021</span></span>

| <span data-ttu-id="666d6-127">列名</span><span class="sxs-lookup"><span data-stu-id="666d6-127">Column name</span></span> | <span data-ttu-id="666d6-128">元の値の名前</span><span class="sxs-lookup"><span data-stu-id="666d6-128">Original value name</span></span> | <span data-ttu-id="666d6-129">新しい値の名前</span><span class="sxs-lookup"><span data-stu-id="666d6-129">New value name</span></span> | <span data-ttu-id="666d6-130">変更理由</span><span class="sxs-lookup"><span data-stu-id="666d6-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="666d6-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="666d6-131">MCAS</span></span> |    <span data-ttu-id="666d6-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="666d6-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="666d6-133">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="666d6-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="666d6-135">EDR</span><span class="sxs-lookup"><span data-stu-id="666d6-135">EDR</span></span>| <span data-ttu-id="666d6-136">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="666d6-137">WindowsDefenderAv</span></span> | <span data-ttu-id="666d6-138">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="666d6-138">Antivirus</span></span> | <span data-ttu-id="666d6-139">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="666d6-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="666d6-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="666d6-141">SmartScreen</span></span> | <span data-ttu-id="666d6-142">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="666d6-143">CustomerTI</span></span> |  <span data-ttu-id="666d6-144">カスタム TI</span><span class="sxs-lookup"><span data-stu-id="666d6-144">Custom TI</span></span> | <span data-ttu-id="666d6-145">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="666d6-146">OfficeATP</span></span> | <span data-ttu-id="666d6-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="666d6-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="666d6-148">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-149">MTP</span><span class="sxs-lookup"><span data-stu-id="666d6-149">MTP</span></span>   | <span data-ttu-id="666d6-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="666d6-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="666d6-151">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="666d6-152">AzureATP</span></span> |    <span data-ttu-id="666d6-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="666d6-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="666d6-154">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="666d6-155">CustomDetection</span></span>   | <span data-ttu-id="666d6-156">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="666d6-156">Custom detection</span></span> | <span data-ttu-id="666d6-157">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="666d6-158">AutomatedInvestigation</span></span> |<span data-ttu-id="666d6-159">自動調査</span><span class="sxs-lookup"><span data-stu-id="666d6-159">Automated investigation</span></span> | <span data-ttu-id="666d6-160">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="666d6-161">ThreatExperts</span></span> | <span data-ttu-id="666d6-162">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="666d6-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="666d6-163">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="666d6-164">サードパーティ TI</span><span class="sxs-lookup"><span data-stu-id="666d6-164">3rd party TI</span></span> | <span data-ttu-id="666d6-165">サードパーティ製センサー</span><span class="sxs-lookup"><span data-stu-id="666d6-165">3rd Party sensors</span></span> | <span data-ttu-id="666d6-166">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="666d6-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="666d6-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="666d6-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="666d6-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="666d6-169">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="666d6-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="666d6-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="666d6-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="666d6-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="666d6-172">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="666d6-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="666d6-173">Office 365 ATP</span></span>  |<span data-ttu-id="666d6-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="666d6-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="666d6-175">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="666d6-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="666d6-176">Azure ATP</span></span>    |<span data-ttu-id="666d6-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="666d6-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="666d6-178">ブランドの再ブランド化</span><span class="sxs-lookup"><span data-stu-id="666d6-178">Rebranding</span></span> |

<span data-ttu-id="666d6-179">`DetectionSource` は [、AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="666d6-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="666d6-180">`ServiceSource` は [、AlertEvidence テーブルと](advanced-hunting-alertevidence-table.md) [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="666d6-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="666d6-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="666d6-181">Related topics</span></span>
- [<span data-ttu-id="666d6-182">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="666d6-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="666d6-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="666d6-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)