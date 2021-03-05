---
title: Microsoft 365 Defender Advanced Hunting スキーマの名前付け変更
description: 高度な検索スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、データ、名前付けの変更、名前の変更、Microsoft Threat Protection
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
ms.openlocfilehash: cd06286083297d0930270868b99a14f8ddb2f4b2
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461669"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="5fb0a-104">高度な検索スキーマ - 名前付けの変更</span><span class="sxs-lookup"><span data-stu-id="5fb0a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5fb0a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5fb0a-105">**Applies to:**</span></span>
- <span data-ttu-id="5fb0a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fb0a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5fb0a-107">高度 [な検索スキーマは](advanced-hunting-schema-tables.md) 、新しいテーブルと列を追加するために定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="5fb0a-108">ユーザー エクスペリエンスを向上させるために、既存の列名の名前が変更または置き換えられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="5fb0a-109">クエリに影響を与える可能性がある名前の変更を確認するには、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="5fb0a-110">名前付けの変更は、カスタム検出ルールで使用されるクエリなど、セキュリティ センターに保存されるクエリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="5fb0a-111">これらのクエリを手動で更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="5fb0a-112">ただし、次のクエリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="5fb0a-113">API を使用して実行されるクエリ</span><span class="sxs-lookup"><span data-stu-id="5fb0a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="5fb0a-114">セキュリティ センター外の別の場所に保存されるクエリ</span><span class="sxs-lookup"><span data-stu-id="5fb0a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="5fb0a-115">2020年12月</span><span class="sxs-lookup"><span data-stu-id="5fb0a-115">December 2020</span></span>

| <span data-ttu-id="5fb0a-116">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-116">Table name</span></span> | <span data-ttu-id="5fb0a-117">元の列名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-117">Original column name</span></span> | <span data-ttu-id="5fb0a-118">新しい列名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-118">New column name</span></span> | <span data-ttu-id="5fb0a-119">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5fb0a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="5fb0a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5fb0a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="5fb0a-121">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-121">Customer feedback</span></span> |
| [<span data-ttu-id="5fb0a-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5fb0a-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="5fb0a-123">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-123">Customer feedback</span></span> |
| [<span data-ttu-id="5fb0a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5fb0a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="5fb0a-125">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="5fb0a-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="5fb0a-126">January 2021</span></span>

| <span data-ttu-id="5fb0a-127">列名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-127">Column name</span></span> | <span data-ttu-id="5fb0a-128">元の値の名前</span><span class="sxs-lookup"><span data-stu-id="5fb0a-128">Original value name</span></span> | <span data-ttu-id="5fb0a-129">新しい値の名前</span><span class="sxs-lookup"><span data-stu-id="5fb0a-129">New value name</span></span> | <span data-ttu-id="5fb0a-130">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5fb0a-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="5fb0a-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="5fb0a-131">MCAS</span></span> |    <span data-ttu-id="5fb0a-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5fb0a-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5fb0a-133">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="5fb0a-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="5fb0a-135">EDR</span><span class="sxs-lookup"><span data-stu-id="5fb0a-135">EDR</span></span>| <span data-ttu-id="5fb0a-136">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="5fb0a-137">WindowsDefenderAv</span></span> | <span data-ttu-id="5fb0a-138">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="5fb0a-138">Antivirus</span></span> | <span data-ttu-id="5fb0a-139">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="5fb0a-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="5fb0a-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="5fb0a-141">SmartScreen</span></span> | <span data-ttu-id="5fb0a-142">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="5fb0a-143">CustomerTI</span></span> |  <span data-ttu-id="5fb0a-144">カスタム TI</span><span class="sxs-lookup"><span data-stu-id="5fb0a-144">Custom TI</span></span> | <span data-ttu-id="5fb0a-145">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-146">OfficeATP</span></span> | <span data-ttu-id="5fb0a-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fb0a-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5fb0a-148">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-149">MTP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-149">MTP</span></span>   | <span data-ttu-id="5fb0a-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fb0a-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="5fb0a-151">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-152">AzureATP</span></span> |    <span data-ttu-id="5fb0a-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5fb0a-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5fb0a-154">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="5fb0a-155">CustomDetection</span></span>   | <span data-ttu-id="5fb0a-156">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="5fb0a-156">Custom detection</span></span> | <span data-ttu-id="5fb0a-157">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="5fb0a-158">AutomatedInvestigation</span></span> |<span data-ttu-id="5fb0a-159">自動調査</span><span class="sxs-lookup"><span data-stu-id="5fb0a-159">Automated investigation</span></span> | <span data-ttu-id="5fb0a-160">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="5fb0a-161">ThreatExperts</span></span> | <span data-ttu-id="5fb0a-162">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="5fb0a-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="5fb0a-163">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5fb0a-164">サードパーティ TI</span><span class="sxs-lookup"><span data-stu-id="5fb0a-164">3rd party TI</span></span> | <span data-ttu-id="5fb0a-165">サードパーティ製センサー</span><span class="sxs-lookup"><span data-stu-id="5fb0a-165">3rd Party sensors</span></span> | <span data-ttu-id="5fb0a-166">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="5fb0a-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="5fb0a-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fb0a-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="5fb0a-169">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="5fb0a-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5fb0a-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="5fb0a-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fb0a-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="5fb0a-172">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="5fb0a-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-173">Office 365 ATP</span></span>  |<span data-ttu-id="5fb0a-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5fb0a-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5fb0a-175">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="5fb0a-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5fb0a-176">Azure ATP</span></span>    |<span data-ttu-id="5fb0a-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5fb0a-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5fb0a-178">リブランド</span><span class="sxs-lookup"><span data-stu-id="5fb0a-178">Rebranding</span></span> |

<span data-ttu-id="5fb0a-179">`DetectionSource` は [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="5fb0a-180">`ServiceSource` は [、AlertEvidence テーブルと](advanced-hunting-alertevidence-table.md) [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="5fb0a-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="5fb0a-181">February 2021</span></span>

1. <span data-ttu-id="5fb0a-182">[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)および[EmailEvents](advanced-hunting-emailevents-table.md)テーブルでは、列と列を非推奨にし、列 `MalwareFilterVerdict` `PhishFilterVerdict` に置き換 `ThreatTypes` えました。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, we deprecated the `MalwareFilterVerdict`and `PhishFilterVerdict` columns and replaced them with the `ThreatTypes` column.</span></span> <span data-ttu-id="5fb0a-183">また、列と列 `MalwareDetectionMethod` を `PhishDetectionMethod` 非推奨にし、列に置き換 `DetectionMethods` えました。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-183">We also deprecated the `MalwareDetectionMethod` and `PhishDetectionMethod` columns and replaced them with the `DetectionMethods` column.</span></span> <span data-ttu-id="5fb0a-184">この合理化により、新しい列の下に詳細な情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="5fb0a-185">マッピングは以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-185">The mapping is provided below.</span></span>

| <span data-ttu-id="5fb0a-186">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-186">Table name</span></span> | <span data-ttu-id="5fb0a-187">元の列名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-187">Original column name</span></span> | <span data-ttu-id="5fb0a-188">新しい列名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-188">New column name</span></span> | <span data-ttu-id="5fb0a-189">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5fb0a-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="5fb0a-190">その他の検出方法を含める</span><span class="sxs-lookup"><span data-stu-id="5fb0a-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="5fb0a-191">脅威の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="5fb0a-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="5fb0a-192">その他の検出方法を含める</span><span class="sxs-lookup"><span data-stu-id="5fb0a-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="5fb0a-193">脅威の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="5fb0a-193">Include more threat types</span></span> |


2. <span data-ttu-id="5fb0a-194">表と `EmailAttachmentInfo` 表 `EmailEvents` に、電子メールの脅威に関する詳細を示す `ThreatNames` 列を追加しました。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, we added the column `ThreatNames` to give more information about the email threat.</span></span> <span data-ttu-id="5fb0a-195">この列には、スパムやフィッシングのような値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="5fb0a-196">[DeviceInfo テーブルでは](advanced-hunting-deviceinfo-table.md)、顧客からのフィードバックに基づいて `DeviceObjectId` 列 `AadDeviceId` を置き換えました。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, we replaced the `DeviceObjectId` column with `AadDeviceId` based on customer feedback.</span></span>

4. <span data-ttu-id="5fb0a-197">[DeviceEvents テーブルでは](advanced-hunting-deviceevents-table.md)、アクションの説明を反映するようにいくつかの ActionType 名を更新しました。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, we updated several ActionType names to better reflect the description of the action.</span></span> <span data-ttu-id="5fb0a-198">詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5fb0a-198">Details can be found below.</span></span>

| <span data-ttu-id="5fb0a-199">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-199">Table name</span></span> | <span data-ttu-id="5fb0a-200">元の ActionType 名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-200">Original ActionType name</span></span> | <span data-ttu-id="5fb0a-201">新しい ActionType 名</span><span class="sxs-lookup"><span data-stu-id="5fb0a-201">New ActionType name</span></span> | <span data-ttu-id="5fb0a-202">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5fb0a-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="5fb0a-203">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="5fb0a-204">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="5fb0a-205">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="5fb0a-206">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-206">Customer feedback</span></span> |
| `DeviceEvents` | `AntivirusDetection` | `EdrBlock` | <span data-ttu-id="5fb0a-207">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5fb0a-207">Customer feedback</span></span> |





## <a name="related-topics"></a><span data-ttu-id="5fb0a-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb0a-208">Related topics</span></span>
- [<span data-ttu-id="5fb0a-209">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="5fb0a-209">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5fb0a-210">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="5fb0a-210">Understand the schema</span></span>](advanced-hunting-schema-tables.md)