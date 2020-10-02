---
title: Microsoft Defender ATP から高度な検索クエリを移行する
description: Microsoft Defender ATP クエリを調整して Microsoft の脅威保護に使用できるようにする方法について説明します。
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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daa89ebf39f8fc6d2110720f61b8d02c074fb484
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338722"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="8bfa1-104">Microsoft Defender ATP から高度な検索クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="8bfa1-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8bfa1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8bfa1-105">**Applies to:**</span></span>
- <span data-ttu-id="8bfa1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8bfa1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8bfa1-107">高度な検索ワークフローを Microsoft Defender ATP から移動して、より広範なデータセットを使用して脅威を事前に探します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="8bfa1-108">Microsoft の脅威保護では、他の Microsoft 365 セキュリティソリューション (次のものを含む) からデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="8bfa1-109">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8bfa1-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="8bfa1-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8bfa1-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="8bfa1-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8bfa1-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8bfa1-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8bfa1-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="8bfa1-113">多くの Microsoft Defender ATP のお客様は、 [追加のライセンスを持たずに microsoft の脅威保護を使用](prerequisites.md#licensing-requirements)できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="8bfa1-114">Microsoft Defender ATP から高度な検索ワークフローの移行を開始するには、 [microsoft の脅威保護を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="8bfa1-115">既存の Microsoft Defender ATP ワークフローに影響を与えることなく移行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="8bfa1-116">保存されたクエリはそのまま残り、カスタムの検出ルールは引き続き実行され、通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="8bfa1-117">ただし、これらは Microsoft の脅威保護に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="8bfa1-118">Microsoft の脅威保護のスキーマテーブル</span><span class="sxs-lookup"><span data-stu-id="8bfa1-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="8bfa1-119">[Microsoft Threat Protection の高度な検索スキーマ](advanced-hunting-schema-tables.md)は、microsoft 365 のさまざまなセキュリティソリューションからのデータを含むテーブルを追加します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="8bfa1-120">次の表は、Microsoft の脅威保護でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="8bfa1-121">テーブル名</span><span class="sxs-lookup"><span data-stu-id="8bfa1-121">Table name</span></span> | <span data-ttu-id="8bfa1-122">説明</span><span class="sxs-lookup"><span data-stu-id="8bfa1-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="8bfa1-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="8bfa1-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="8bfa1-124">アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス</span><span class="sxs-lookup"><span data-stu-id="8bfa1-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="8bfa1-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="8bfa1-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="8bfa1-126">Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP (重大度情報や脅威カテゴリを含む) からの通知</span><span class="sxs-lookup"><span data-stu-id="8bfa1-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="8bfa1-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="8bfa1-128">クラウドアプリとサービスのファイル関連アクティビティ</span><span class="sxs-lookup"><span data-stu-id="8bfa1-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="8bfa1-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="8bfa1-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="8bfa1-130">電子メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="8bfa1-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="8bfa1-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8bfa1-132">Microsoft 365 の電子メールイベント (電子メール配信およびブロックイベントを含む)</span><span class="sxs-lookup"><span data-stu-id="8bfa1-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="8bfa1-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="8bfa1-134">Microsoft 365 がメールを受信者のメールボックスに配信した後の、配信後に発生するセキュリティイベント</span><span class="sxs-lookup"><span data-stu-id="8bfa1-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="8bfa1-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="8bfa1-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="8bfa1-136">メールの Url に関する情報</span><span class="sxs-lookup"><span data-stu-id="8bfa1-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="8bfa1-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="8bfa1-138">Active Directory (AD) を実行しているオンプレミスのドメインコントローラーに関係するイベント。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="8bfa1-139">この表は、ドメインコントローラーの id 関連イベントとシステムイベントの範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="8bfa1-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="8bfa1-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="8bfa1-141">Azure Active Directory を含む、さまざまなソースからのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="8bfa1-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="8bfa1-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="8bfa1-143">Active Directory と Microsoft online services の認証イベント</span><span class="sxs-lookup"><span data-stu-id="8bfa1-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="8bfa1-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="8bfa1-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="8bfa1-145">ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="8bfa1-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="8bfa1-146">DeviceAlertEvents テーブルのマップ</span><span class="sxs-lookup"><span data-stu-id="8bfa1-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="8bfa1-147">`AlertInfo`とテーブルは、 `AlertEvidence` `DeviceAlertEvents` Microsoft Defender ATP スキーマの表を置換します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="8bfa1-148">デバイス通知に関するデータに加えて、これらの2つのテーブルには、id、アプリ、電子メールの警告に関するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="8bfa1-149">次の表を使用し `DeviceAlertEvents` て、列とテーブル内の列をどのようにマッピングするかを確認し `AlertInfo` `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="8bfa1-150">表には、次の表に加えて、 `AlertEvidence` さまざまなソースからのアラートの全体的な概要を提供する、他の多くの列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="8bfa1-151">すべての AlertEvidence 列を表示する</span><span class="sxs-lookup"><span data-stu-id="8bfa1-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="8bfa1-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="8bfa1-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="8bfa1-153">Microsoft の脅威保護で同じデータを検索する場所</span><span class="sxs-lookup"><span data-stu-id="8bfa1-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="8bfa1-154">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="8bfa1-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="8bfa1-155">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="8bfa1-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="8bfa1-156">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="8bfa1-157">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="8bfa1-158">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="8bfa1-159">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="8bfa1-160">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="8bfa1-161">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="8bfa1-162">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="8bfa1-163">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="8bfa1-164">`AlertEvidence` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="8bfa1-165">`AlertInfo` </span><span class="sxs-lookup"><span data-stu-id="8bfa1-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="8bfa1-166">この列は、通常、Microsoft Defender ATP で他のテーブル内の関連レコードを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="8bfa1-167">Microsoft の脅威保護では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="8bfa1-168">この列は、通常、Microsoft Defender ATP で他のテーブルの追加イベント情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="8bfa1-169">Microsoft の脅威保護では、関連するデータをテーブルから直接取得することができ `AlertEvidence` ます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="8bfa1-170">既存の Microsoft Defender ATP クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="8bfa1-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="8bfa1-171">Microsoft Defender ATP クエリは、テーブルを参照していない限り、として機能し `DeviceAlertEvents` ます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="8bfa1-172">Microsoft の脅威保護でこれらのクエリを使用するには、次の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="8bfa1-173">`DeviceAlertEvents`をに置き換え `AlertInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="8bfa1-174">とのテーブルを結合して、 `AlertInfo` `AlertEvidence` 同等の `AlertId` データを取得します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="8bfa1-175">元のクエリ</span><span class="sxs-lookup"><span data-stu-id="8bfa1-175">Original query</span></span>
<span data-ttu-id="8bfa1-176">次のクエリは、 `DeviceAlertEvents` Microsoft DEFENDER ATP で、 _powershell.exe_に関連する警告を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="8bfa1-177">変更されたクエリ</span><span class="sxs-lookup"><span data-stu-id="8bfa1-177">Modified query</span></span>
<span data-ttu-id="8bfa1-178">次のクエリは、Microsoft の脅威保護で使用するように調整されています。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="8bfa1-179">ファイル名をから直接チェックする代わりに `DeviceAlertEvents` 、その `AlertEvidence` テーブル内のファイル名を結合して確認します。</span><span class="sxs-lookup"><span data-stu-id="8bfa1-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="8bfa1-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfa1-180">Related topics</span></span>
- [<span data-ttu-id="8bfa1-181">Microsoft Threat Protection を有効にする</span><span class="sxs-lookup"><span data-stu-id="8bfa1-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8bfa1-182">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="8bfa1-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8bfa1-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="8bfa1-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8bfa1-184">Microsoft Defender ATP での高度な検索</span><span class="sxs-lookup"><span data-stu-id="8bfa1-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)