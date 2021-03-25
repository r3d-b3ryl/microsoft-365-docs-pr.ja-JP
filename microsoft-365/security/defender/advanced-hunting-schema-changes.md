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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: acb259088717b2772ec9798027545f2ff6dbc5e0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068668"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="5c908-104">高度な検索スキーマ - 名前付けの変更</span><span class="sxs-lookup"><span data-stu-id="5c908-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5c908-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5c908-105">**Applies to:**</span></span>
- <span data-ttu-id="5c908-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c908-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5c908-107">高度 [な検索スキーマは](advanced-hunting-schema-tables.md) 、新しいテーブルと列を追加するために定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="5c908-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="5c908-108">ユーザー エクスペリエンスを向上させるために、既存の列名の名前が変更または置き換えられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c908-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="5c908-109">クエリに影響を与える可能性がある名前の変更を確認するには、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c908-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="5c908-110">名前付けの変更は、カスタム検出ルールで使用されるクエリなど、セキュリティ センターに保存されるクエリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5c908-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="5c908-111">これらのクエリを手動で更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5c908-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="5c908-112">ただし、次のクエリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c908-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="5c908-113">API を使用して実行されるクエリ</span><span class="sxs-lookup"><span data-stu-id="5c908-113">Queries that are run using the API</span></span>
- <span data-ttu-id="5c908-114">セキュリティ センター外の別の場所に保存されるクエリ</span><span class="sxs-lookup"><span data-stu-id="5c908-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="5c908-115">2020年12月</span><span class="sxs-lookup"><span data-stu-id="5c908-115">December 2020</span></span>

| <span data-ttu-id="5c908-116">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5c908-116">Table name</span></span> | <span data-ttu-id="5c908-117">元の列名</span><span class="sxs-lookup"><span data-stu-id="5c908-117">Original column name</span></span> | <span data-ttu-id="5c908-118">新しい列名</span><span class="sxs-lookup"><span data-stu-id="5c908-118">New column name</span></span> | <span data-ttu-id="5c908-119">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5c908-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="5c908-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5c908-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="5c908-121">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-121">Customer feedback</span></span> |
| [<span data-ttu-id="5c908-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5c908-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="5c908-123">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-123">Customer feedback</span></span> |
| [<span data-ttu-id="5c908-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="5c908-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="5c908-125">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="5c908-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="5c908-126">January 2021</span></span>

| <span data-ttu-id="5c908-127">列名</span><span class="sxs-lookup"><span data-stu-id="5c908-127">Column name</span></span> | <span data-ttu-id="5c908-128">元の値の名前</span><span class="sxs-lookup"><span data-stu-id="5c908-128">Original value name</span></span> | <span data-ttu-id="5c908-129">新しい値の名前</span><span class="sxs-lookup"><span data-stu-id="5c908-129">New value name</span></span> | <span data-ttu-id="5c908-130">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5c908-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="5c908-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="5c908-131">MCAS</span></span> |    <span data-ttu-id="5c908-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5c908-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5c908-133">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="5c908-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="5c908-135">EDR</span><span class="sxs-lookup"><span data-stu-id="5c908-135">EDR</span></span>| <span data-ttu-id="5c908-136">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="5c908-137">WindowsDefenderAv</span></span> | <span data-ttu-id="5c908-138">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="5c908-138">Antivirus</span></span> | <span data-ttu-id="5c908-139">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="5c908-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="5c908-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="5c908-141">SmartScreen</span></span> | <span data-ttu-id="5c908-142">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="5c908-143">CustomerTI</span></span> |  <span data-ttu-id="5c908-144">カスタム TI</span><span class="sxs-lookup"><span data-stu-id="5c908-144">Custom TI</span></span> | <span data-ttu-id="5c908-145">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="5c908-146">OfficeATP</span></span> | <span data-ttu-id="5c908-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5c908-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5c908-148">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-149">MTP</span><span class="sxs-lookup"><span data-stu-id="5c908-149">MTP</span></span>   | <span data-ttu-id="5c908-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c908-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="5c908-151">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="5c908-152">AzureATP</span></span> |    <span data-ttu-id="5c908-153">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5c908-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5c908-154">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="5c908-155">CustomDetection</span></span>   | <span data-ttu-id="5c908-156">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="5c908-156">Custom detection</span></span> | <span data-ttu-id="5c908-157">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="5c908-158">AutomatedInvestigation</span></span> |<span data-ttu-id="5c908-159">自動調査</span><span class="sxs-lookup"><span data-stu-id="5c908-159">Automated investigation</span></span> | <span data-ttu-id="5c908-160">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="5c908-161">ThreatExperts</span></span> | <span data-ttu-id="5c908-162">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="5c908-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="5c908-163">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="5c908-164">サードパーティ TI</span><span class="sxs-lookup"><span data-stu-id="5c908-164">3rd party TI</span></span> | <span data-ttu-id="5c908-165">サードパーティ製センサー</span><span class="sxs-lookup"><span data-stu-id="5c908-165">3rd Party sensors</span></span> | <span data-ttu-id="5c908-166">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="5c908-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5c908-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="5c908-168">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c908-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="5c908-169">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="5c908-170">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5c908-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="5c908-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c908-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="5c908-172">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="5c908-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5c908-173">Office 365 ATP</span></span>  |<span data-ttu-id="5c908-174">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5c908-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5c908-175">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="5c908-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5c908-176">Azure ATP</span></span>    |<span data-ttu-id="5c908-177">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5c908-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5c908-178">リブランド</span><span class="sxs-lookup"><span data-stu-id="5c908-178">Rebranding</span></span> |

<span data-ttu-id="5c908-179">`DetectionSource` は [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="5c908-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="5c908-180">`ServiceSource` は [、AlertEvidence テーブルと](advanced-hunting-alertevidence-table.md) [AlertInfo テーブルで使用](advanced-hunting-alertinfo-table.md) できます。</span><span class="sxs-lookup"><span data-stu-id="5c908-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="5c908-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="5c908-181">February 2021</span></span>

1. <span data-ttu-id="5c908-182">[EmailAttachmentInfo テーブル](advanced-hunting-emailattachmentinfo-table.md)と[EmailEvents](advanced-hunting-emailevents-table.md)テーブルでは、列と列が `MalwareFilterVerdict` `PhishFilterVerdict` 列に置き換 `ThreatTypes` えされています。</span><span class="sxs-lookup"><span data-stu-id="5c908-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="5c908-183">列 `MalwareDetectionMethod` と `PhishDetectionMethod` 列も列に置き換 `DetectionMethods` えました。</span><span class="sxs-lookup"><span data-stu-id="5c908-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="5c908-184">この合理化により、新しい列の下に詳細な情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5c908-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="5c908-185">マッピングは以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5c908-185">The mapping is provided below.</span></span>

| <span data-ttu-id="5c908-186">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5c908-186">Table name</span></span> | <span data-ttu-id="5c908-187">元の列名</span><span class="sxs-lookup"><span data-stu-id="5c908-187">Original column name</span></span> | <span data-ttu-id="5c908-188">新しい列名</span><span class="sxs-lookup"><span data-stu-id="5c908-188">New column name</span></span> | <span data-ttu-id="5c908-189">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5c908-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="5c908-190">その他の検出方法を含める</span><span class="sxs-lookup"><span data-stu-id="5c908-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="5c908-191">脅威の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="5c908-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="5c908-192">その他の検出方法を含める</span><span class="sxs-lookup"><span data-stu-id="5c908-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="5c908-193">脅威の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="5c908-193">Include more threat types</span></span> |


2. <span data-ttu-id="5c908-194">列とテーブルに、電子メールの脅威に関する詳細を示す列 `EmailAttachmentInfo` `EmailEvents` `ThreatNames` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="5c908-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="5c908-195">この列には、スパムやフィッシングのような値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c908-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="5c908-196">[DeviceInfo テーブルの](advanced-hunting-deviceinfo-table.md)列は、顧客からのフィードバックに基 `DeviceObjectId` `AadDeviceId` づいて列に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5c908-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="5c908-197">[DeviceEvents テーブルでは](advanced-hunting-deviceevents-table.md)、アクションの説明を反映するようにいくつかの ActionType 名が変更されました。</span><span class="sxs-lookup"><span data-stu-id="5c908-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="5c908-198">変更の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c908-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="5c908-199">テーブル名</span><span class="sxs-lookup"><span data-stu-id="5c908-199">Table name</span></span> | <span data-ttu-id="5c908-200">元の ActionType 名</span><span class="sxs-lookup"><span data-stu-id="5c908-200">Original ActionType name</span></span> | <span data-ttu-id="5c908-201">新しい ActionType 名</span><span class="sxs-lookup"><span data-stu-id="5c908-201">New ActionType name</span></span> | <span data-ttu-id="5c908-202">変更の理由</span><span class="sxs-lookup"><span data-stu-id="5c908-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="5c908-203">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="5c908-204">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="5c908-205">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="5c908-206">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="5c908-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="5c908-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c908-207">Related topics</span></span>
- [<span data-ttu-id="5c908-208">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="5c908-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5c908-209">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="5c908-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)