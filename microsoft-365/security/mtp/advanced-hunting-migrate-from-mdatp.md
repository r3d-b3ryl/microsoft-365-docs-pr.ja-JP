---
title: エンドポイントの Microsoft Defender から高度な検索クエリを移行する
description: Microsoft 365 Defender で使用できるように Microsoft Defender をエンドポイントクエリ用に調整する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft の脅威の防止、microsoft 365、mtp、m365、microsoft defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、マッピング
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846858"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="22ac7-104">エンドポイントの Microsoft Defender から高度な検索クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="22ac7-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="22ac7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="22ac7-105">**Applies to:**</span></span>
- <span data-ttu-id="22ac7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22ac7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="22ac7-107">より広範なデータセットを使用して脅威を事前にハントするために、Microsoft Defender から高度な検索ワークフローを移動します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="22ac7-108">Microsoft 365 Defender では、次のような他の Microsoft 365 セキュリティソリューションからデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="22ac7-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22ac7-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="22ac7-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="22ac7-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="22ac7-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="22ac7-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="22ac7-112">Id の Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22ac7-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="22ac7-113">エンドポイントのお客様のための Microsoft Defender の多くは、ライセンスを追加すること [なく microsoft 365 Defender を使用](prerequisites.md#licensing-requirements)できます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="22ac7-114">エンドポイントの Defender から高度な検索ワークフローへの移行を開始するには、 [Microsoft 365 Defender をオン](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="22ac7-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="22ac7-115">エンドポイントワークフローの既存の Defender に影響を与えることなく移行できます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="22ac7-116">保存されたクエリはそのまま残り、カスタムの検出ルールは引き続き実行され、通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="22ac7-117">ただし、これらは Microsoft 365 Defender に表示されます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="22ac7-118">Microsoft 365 Defender のスキーマテーブルのみ</span><span class="sxs-lookup"><span data-stu-id="22ac7-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="22ac7-119">[Microsoft 365 Defender の高度な検索スキーマ](advanced-hunting-schema-tables.md)では、microsoft 365 のさまざまなセキュリティソリューションからのデータを含むテーブルが追加されています。</span><span class="sxs-lookup"><span data-stu-id="22ac7-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="22ac7-120">次の表は、Microsoft 365 Defender でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="22ac7-121">テーブル名</span><span class="sxs-lookup"><span data-stu-id="22ac7-121">Table name</span></span> | <span data-ttu-id="22ac7-122">説明</span><span class="sxs-lookup"><span data-stu-id="22ac7-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="22ac7-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="22ac7-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="22ac7-124">アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス</span><span class="sxs-lookup"><span data-stu-id="22ac7-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="22ac7-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="22ac7-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="22ac7-126">エンドポイントの Microsoft Defender、microsoft Defender for Office 365、Microsoft Cloud App Security、および Id (重要度情報や脅威カテゴリを含む) に関する microsoft defender からの通知</span><span class="sxs-lookup"><span data-stu-id="22ac7-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="22ac7-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="22ac7-128">クラウドアプリとサービスのファイル関連アクティビティ</span><span class="sxs-lookup"><span data-stu-id="22ac7-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="22ac7-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="22ac7-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="22ac7-130">電子メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="22ac7-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="22ac7-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="22ac7-132">Microsoft 365 の電子メールイベント (電子メール配信およびブロックイベントを含む)</span><span class="sxs-lookup"><span data-stu-id="22ac7-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="22ac7-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="22ac7-134">Microsoft 365 がメールを受信者のメールボックスに配信した後の、配信後に発生するセキュリティイベント</span><span class="sxs-lookup"><span data-stu-id="22ac7-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="22ac7-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="22ac7-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="22ac7-136">メールの Url に関する情報</span><span class="sxs-lookup"><span data-stu-id="22ac7-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="22ac7-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="22ac7-138">Active Directory (AD) を実行しているオンプレミスのドメインコントローラーに関係するイベント。</span><span class="sxs-lookup"><span data-stu-id="22ac7-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="22ac7-139">この表は、ドメインコントローラーの id 関連イベントとシステムイベントの範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="22ac7-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="22ac7-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="22ac7-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="22ac7-141">Azure Active Directory を含む、さまざまなソースからのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="22ac7-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="22ac7-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="22ac7-143">Active Directory と Microsoft online services の認証イベント</span><span class="sxs-lookup"><span data-stu-id="22ac7-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="22ac7-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="22ac7-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="22ac7-145">ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="22ac7-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="22ac7-146">DeviceAlertEvents テーブルのマップ</span><span class="sxs-lookup"><span data-stu-id="22ac7-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="22ac7-147">`AlertInfo` `AlertEvidence` エンドポイントスキーマでは、Microsoft Defender のテーブルがとテーブルに置き換えられ `DeviceAlertEvents` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="22ac7-148">デバイス通知に関するデータに加えて、これらの2つのテーブルには、id、アプリ、電子メールの警告に関するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22ac7-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="22ac7-149">次の表を使用し `DeviceAlertEvents` て、列とテーブル内の列をどのようにマッピングするかを確認し `AlertInfo` `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="22ac7-150">表には、次の表に加えて、 `AlertEvidence` さまざまなソースからのアラートの全体的な概要を提供する、他の多くの列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22ac7-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="22ac7-151">すべての AlertEvidence 列を表示する</span><span class="sxs-lookup"><span data-stu-id="22ac7-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="22ac7-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="22ac7-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="22ac7-153">Microsoft 365 Defender で同じデータを検索する場所</span><span class="sxs-lookup"><span data-stu-id="22ac7-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="22ac7-154">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="22ac7-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="22ac7-155">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="22ac7-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="22ac7-156">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="22ac7-157">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="22ac7-158">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="22ac7-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="22ac7-159">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="22ac7-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="22ac7-160">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="22ac7-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="22ac7-161">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="22ac7-162">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="22ac7-163">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="22ac7-164">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="22ac7-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="22ac7-165">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="22ac7-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="22ac7-166">この列は、通常、エンドポイントの Microsoft Defender で、他のテーブル内の関連レコードを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="22ac7-167">Microsoft 365 Defender では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="22ac7-168">この列は、通常、他のテーブルの追加のイベント情報をエンドポイントとして Microsoft Defender で使用します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="22ac7-169">Microsoft 365 Defender では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="22ac7-170">エンドポイントクエリ用に既存の Microsoft Defender を調整する</span><span class="sxs-lookup"><span data-stu-id="22ac7-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="22ac7-171">エンドポイントクエリの場合、Microsoft Defender は、そのテーブルを参照していない限り、として機能し `DeviceAlertEvents` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="22ac7-172">Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="22ac7-173">`DeviceAlertEvents`をに置き換え `AlertInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="22ac7-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="22ac7-174">とのテーブルを結合して、 `AlertInfo` `AlertEvidence` 同等の `AlertId` データを取得します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="22ac7-175">元のクエリ</span><span class="sxs-lookup"><span data-stu-id="22ac7-175">Original query</span></span>
<span data-ttu-id="22ac7-176">次のクエリは、 `DeviceAlertEvents` エンドポイントの Microsoft Defender で、 _powershell.exe_ に関連する警告を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="22ac7-177">変更されたクエリ</span><span class="sxs-lookup"><span data-stu-id="22ac7-177">Modified query</span></span>
<span data-ttu-id="22ac7-178">次のクエリは、Microsoft 365 Defender で使用するように調整されています。</span><span class="sxs-lookup"><span data-stu-id="22ac7-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="22ac7-179">ファイル名をから直接チェックする代わりに `DeviceAlertEvents` 、その `AlertEvidence` テーブル内のファイル名を結合して確認します。</span><span class="sxs-lookup"><span data-stu-id="22ac7-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="22ac7-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="22ac7-180">Related topics</span></span>
- [<span data-ttu-id="22ac7-181">Microsoft 365 Defender をオンにする</span><span class="sxs-lookup"><span data-stu-id="22ac7-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="22ac7-182">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="22ac7-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="22ac7-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="22ac7-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="22ac7-184">エンドポイントの Microsoft Defender での高度な検索</span><span class="sxs-lookup"><span data-stu-id="22ac7-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)