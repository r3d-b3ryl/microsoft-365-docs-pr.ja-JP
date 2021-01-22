---
title: Microsoft Defender for Endpoint から高度な検索クエリを移行する
description: Microsoft 365 Defender で使用できるよう、エンドポイント用 Microsoft Defender クエリを調整する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、Microsoft Defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、マッピング
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932312"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="3900d-104">Microsoft Defender for Endpoint から高度な検索クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="3900d-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3900d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3900d-105">**Applies to:**</span></span>
- <span data-ttu-id="3900d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3900d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3900d-107">高度なハンティング ワークフローを Microsoft Defender for Endpoint から移動し、広範なデータセットを使用して脅威を事前に検出します。</span><span class="sxs-lookup"><span data-stu-id="3900d-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="3900d-108">Microsoft 365 Defender では、次を含む他の Microsoft 365 セキュリティ ソリューションからデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3900d-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="3900d-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3900d-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="3900d-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3900d-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="3900d-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3900d-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="3900d-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="3900d-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="3900d-113">ほとんどの Microsoft Defender for Endpoint のお客様は、追加のライセンスなしで [Microsoft 365 Defender を使用できます](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3900d-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="3900d-114">Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには [、Microsoft 365 Defender をオンにしてください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="3900d-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="3900d-115">既存の Defender for Endpoint ワークフローに影響を与えることなく移行できます。</span><span class="sxs-lookup"><span data-stu-id="3900d-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="3900d-116">保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3900d-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="3900d-117">ただし、Microsoft 365 Defender に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3900d-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="3900d-118">Microsoft 365 Defender のスキーマ テーブルのみ</span><span class="sxs-lookup"><span data-stu-id="3900d-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="3900d-119">[Microsoft 365 Defender 高度な](advanced-hunting-schema-tables.md)検索スキーマには、さまざまな Microsoft 365 セキュリティ ソリューションのデータを含む追加のテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3900d-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="3900d-120">次の表は、Microsoft 365 Defender でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3900d-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="3900d-121">テーブル名</span><span class="sxs-lookup"><span data-stu-id="3900d-121">Table name</span></span> | <span data-ttu-id="3900d-122">説明</span><span class="sxs-lookup"><span data-stu-id="3900d-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="3900d-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="3900d-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="3900d-124">アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス</span><span class="sxs-lookup"><span data-stu-id="3900d-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="3900d-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="3900d-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="3900d-126">エンドポイント用 Microsoft Defender、Office 365 用 Microsoft Defender、Microsoft Cloud App Security、Id 用 Microsoft Defender からのアラート (重大度情報と脅威カテゴリを含む)</span><span class="sxs-lookup"><span data-stu-id="3900d-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="3900d-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="3900d-128">クラウド アプリとサービスでのファイル関連のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="3900d-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="3900d-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="3900d-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="3900d-130">メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="3900d-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="3900d-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="3900d-132">Microsoft 365 電子メール イベント (メール配信イベントとブロック イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="3900d-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="3900d-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="3900d-134">Microsoft 365 が受信者のメールボックスにメールを配信した後に、配信後に発生するセキュリティ イベント</span><span class="sxs-lookup"><span data-stu-id="3900d-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="3900d-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="3900d-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="3900d-136">メールの URL に関する情報</span><span class="sxs-lookup"><span data-stu-id="3900d-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="3900d-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="3900d-138">Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。</span><span class="sxs-lookup"><span data-stu-id="3900d-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="3900d-139">次の表に、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="3900d-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="3900d-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="3900d-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="3900d-141">Azure Active Directory など、さまざまなソースからのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="3900d-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="3900d-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="3900d-143">Active Directory および Microsoft オンライン サービスの認証イベント</span><span class="sxs-lookup"><span data-stu-id="3900d-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="3900d-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="3900d-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="3900d-145">ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ</span><span class="sxs-lookup"><span data-stu-id="3900d-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="3900d-146">DeviceAlertEvents テーブルのマップ</span><span class="sxs-lookup"><span data-stu-id="3900d-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="3900d-147">The `AlertInfo` and tables replace the table in the Microsoft Defender for Endpoint `AlertEvidence` `DeviceAlertEvents` schema.</span><span class="sxs-lookup"><span data-stu-id="3900d-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="3900d-148">デバイス通知に関するデータに加えて、これら 2 つの表には、ID、アプリ、メールのアラートに関するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3900d-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="3900d-149">次の表を使用して、列とテーブルの列のマップ `DeviceAlertEvents` 方法を `AlertInfo` 確認 `AlertEvidence` します。</span><span class="sxs-lookup"><span data-stu-id="3900d-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="3900d-150">次の表の列に加えて、この表には、さまざまなソースからのアラートのより包括的な画像を提供する他の多くの列 `AlertEvidence` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3900d-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="3900d-151">AlertEvidence のすべての列を表示する</span><span class="sxs-lookup"><span data-stu-id="3900d-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="3900d-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="3900d-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="3900d-153">Microsoft 365 Defender で同じデータを検索する場所</span><span class="sxs-lookup"><span data-stu-id="3900d-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="3900d-154">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="3900d-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="3900d-155">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="3900d-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="3900d-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="3900d-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="3900d-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="3900d-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="3900d-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="3900d-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="3900d-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="3900d-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="3900d-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="3900d-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="3900d-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="3900d-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="3900d-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="3900d-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="3900d-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="3900d-166">この列は、通常、Microsoft Defender for Endpoint で他のテーブル内の関連レコードを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3900d-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="3900d-167">Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="3900d-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="3900d-168">この列は、通常、他の表の追加のイベント情報のために Microsoft Defender for Endpoint で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3900d-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="3900d-169">Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="3900d-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="3900d-170">エンドポイント用の既存の Microsoft Defender クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="3900d-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="3900d-171">Microsoft Defender for Endpoint のクエリは、テーブルを参照しない限り、同じ方法で動作 `DeviceAlertEvents` します。</span><span class="sxs-lookup"><span data-stu-id="3900d-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="3900d-172">Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="3900d-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="3900d-173">置換 `DeviceAlertEvents` 後 `AlertInfo` の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3900d-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="3900d-174">テーブルとテーブル `AlertInfo` を `AlertEvidence` 結合して `AlertId` 、同等のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="3900d-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="3900d-175">元のクエリ</span><span class="sxs-lookup"><span data-stu-id="3900d-175">Original query</span></span>
<span data-ttu-id="3900d-176">次のクエリは `DeviceAlertEvents` 、Microsoft Defender for Endpoint で使用して、エンドポイントに関連するアラート _をpowershell.exe。_</span><span class="sxs-lookup"><span data-stu-id="3900d-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="3900d-177">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="3900d-177">Modified query</span></span>
<span data-ttu-id="3900d-178">次のクエリは、Microsoft 365 Defender での使用に合わせて調整されています。</span><span class="sxs-lookup"><span data-stu-id="3900d-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="3900d-179">ファイル名を直接チェックする代わりに、テーブル内のファイル名を結合 `DeviceAlertEvents` `AlertEvidence` して確認します。</span><span class="sxs-lookup"><span data-stu-id="3900d-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="3900d-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="3900d-180">Related topics</span></span>
- [<span data-ttu-id="3900d-181">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="3900d-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3900d-182">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="3900d-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3900d-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3900d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3900d-184">Microsoft Defender for Endpoint での高度な検索</span><span class="sxs-lookup"><span data-stu-id="3900d-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)