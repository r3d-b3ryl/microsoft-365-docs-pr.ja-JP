---
title: Microsoft Defender for Endpoint から高度なハンティング クエリを移行する
description: Microsoft 365 Defender で使用できるよう、Microsoft Defender for Endpoint クエリを調整する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威の保護、microsoft 365、mtp、m365、microsoft Defender atp、mdatp、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、マッピング
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
ms.openlocfilehash: 4d29f4f3df3d65ad72a19f059763523d7f7cba31
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597004"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="9c4ce-104">Microsoft Defender for Endpoint から高度なハンティング クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="9c4ce-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9c4ce-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9c4ce-105">**Applies to:**</span></span>
- <span data-ttu-id="9c4ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c4ce-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9c4ce-107">高度なハンティング ワークフローを Microsoft Defender for Endpoint から移動して、より広範なデータセットを使用して脅威を積極的に検出します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="9c4ce-108">Microsoft 365 Defender では、次を含む他の Microsoft 365 セキュリティ ソリューションからデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="9c4ce-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9c4ce-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="9c4ce-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9c4ce-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="9c4ce-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9c4ce-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9c4ce-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="9c4ce-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="9c4ce-113">ほとんどの Microsoft Defender for Endpoint のお客様は、追加のライセンスなしで [Microsoft 365 Defender を使用できます](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="9c4ce-114">Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには [、Microsoft 365 Defender をオンにしてください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="9c4ce-115">既存の Defender for Endpoint ワークフローに影響を与えることなく移行できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="9c4ce-116">保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="9c4ce-117">ただし、Microsoft 365 Defender に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="9c4ce-118">Microsoft 365 Defender のスキーマ テーブルのみ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="9c4ce-119">[Microsoft 365 Defender の](advanced-hunting-schema-tables.md)高度なハンティング スキーマには、さまざまな Microsoft 365 セキュリティ ソリューションのデータを含む追加のテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="9c4ce-120">次の表は、Microsoft 365 Defender でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="9c4ce-121">テーブル名</span><span class="sxs-lookup"><span data-stu-id="9c4ce-121">Table name</span></span> | <span data-ttu-id="9c4ce-122">説明</span><span class="sxs-lookup"><span data-stu-id="9c4ce-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="9c4ce-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9c4ce-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="9c4ce-124">アラートに関連付けられたファイル、IP アドレス、URL、ユーザー、またはデバイス</span><span class="sxs-lookup"><span data-stu-id="9c4ce-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="9c4ce-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="9c4ce-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="9c4ce-126">Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity からのアラート (重大度情報と脅威カテゴリを含む)</span><span class="sxs-lookup"><span data-stu-id="9c4ce-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="9c4ce-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="9c4ce-128">クラウド アプリとサービスでのファイル関連のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="9c4ce-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="9c4ce-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="9c4ce-130">メールに添付されているファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="9c4ce-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="9c4ce-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="9c4ce-132">Microsoft 365 の電子メール イベント (メール配信イベントやブロック イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="9c4ce-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="9c4ce-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="9c4ce-134">Microsoft 365 が受信者メールボックスにメールを配信した後に配信後に発生するセキュリティ イベント</span><span class="sxs-lookup"><span data-stu-id="9c4ce-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="9c4ce-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="9c4ce-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="9c4ce-136">メールの URL に関する情報</span><span class="sxs-lookup"><span data-stu-id="9c4ce-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="9c4ce-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="9c4ce-138">Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9c4ce-139">次の表では、ドメイン コントローラー上の ID 関連イベントとシステム イベントの範囲について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="9c4ce-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9c4ce-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="9c4ce-141">Azure Active Directory を含むさまざまなソースからのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="9c4ce-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="9c4ce-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="9c4ce-143">Active Directory および Microsoft オンライン サービスでの認証イベント</span><span class="sxs-lookup"><span data-stu-id="9c4ce-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="9c4ce-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9c4ce-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="9c4ce-145">ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="9c4ce-146">Microsoft 365 Defender でのみ使用できるスキーマ テーブルを使用するクエリとカスタム検出は、Microsoft 365 Defender でのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="9c4ce-147">DeviceAlertEvents テーブルのマップ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="9c4ce-148">テーブル `AlertInfo` と `AlertEvidence` テーブルは `DeviceAlertEvents` 、Microsoft Defender for Endpoint スキーマのテーブルを置き換える。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9c4ce-149">デバイス通知に関するデータに加えて、これら 2 つのテーブルには、ID、アプリ、および電子メールのアラートに関するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="9c4ce-150">次の表を使用して、列 `DeviceAlertEvents` が列とテーブルの列にマップされる方法 `AlertInfo` を確認 `AlertEvidence` します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="9c4ce-151">次の表の列に加えて、さまざまなソースからのアラートの全体的な画像を提供する他の多くの列 `AlertEvidence` も含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-151">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="9c4ce-152">すべての AlertEvidence 列を表示する</span><span class="sxs-lookup"><span data-stu-id="9c4ce-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="9c4ce-153">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="9c4ce-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="9c4ce-154">Microsoft 365 Defender で同じデータを見つける場所</span><span class="sxs-lookup"><span data-stu-id="9c4ce-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="9c4ce-155">`AlertInfo` テーブル  `AlertEvidence` とテーブル</span><span class="sxs-lookup"><span data-stu-id="9c4ce-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="9c4ce-156">`AlertInfo` テーブル  `AlertEvidence` とテーブル</span><span class="sxs-lookup"><span data-stu-id="9c4ce-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="9c4ce-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="9c4ce-158">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="9c4ce-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="9c4ce-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="9c4ce-161">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="9c4ce-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="9c4ce-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="9c4ce-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="9c4ce-165">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="9c4ce-166">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9c4ce-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="9c4ce-167">この列は、通常、Microsoft Defender for Endpoint で他のテーブル内の関連レコードを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="9c4ce-168">Microsoft 365 Defender では、関連するデータをテーブルから直接取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="9c4ce-169">この列は、通常、Microsoft Defender for Endpoint で他のテーブルの追加イベント情報として使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="9c4ce-170">Microsoft 365 Defender では、関連するデータをテーブルから直接取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="9c4ce-171">既存の Microsoft Defender for Endpoint クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="9c4ce-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="9c4ce-172">Microsoft Defender for Endpoint クエリは、テーブルを参照しない限り、現在通り動作 `DeviceAlertEvents` します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="9c4ce-173">Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="9c4ce-174">に `DeviceAlertEvents` 置き換える `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="9c4ce-175">テーブルとテーブル `AlertInfo` を `AlertEvidence` 結合して `AlertId` 同等のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="9c4ce-176">元のクエリ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-176">Original query</span></span>
<span data-ttu-id="9c4ce-177">次のクエリは `DeviceAlertEvents` 、Microsoft Defender for Endpoint で使用して、エンドポイントに関連するアラートをpowershell.exe。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="9c4ce-178">変更されたクエリ</span><span class="sxs-lookup"><span data-stu-id="9c4ce-178">Modified query</span></span>
<span data-ttu-id="9c4ce-179">次のクエリは、Microsoft 365 Defender での使用に合わせて調整されています。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="9c4ce-180">ファイル名を直接からチェックする代わりに、そのテーブル内のファイル名を結合 `DeviceAlertEvents` `AlertEvidence` してチェックします。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="9c4ce-181">カスタム検出ルールの移行</span><span class="sxs-lookup"><span data-stu-id="9c4ce-181">Migrate custom detection rules</span></span>

<span data-ttu-id="9c4ce-182">Microsoft Defender for Endpoint ルールが Microsoft 365 Defender で編集されている場合、結果のクエリでデバイス テーブルのみを参照する場合、以前と同様に機能し続ける。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="9c4ce-183">たとえば、デバイス テーブルのみをクエリするカスタム検出ルールによって生成されたアラートは、Microsoft Defender for Endpoint での構成方法に応じて、引き続き SIEM に配信され、電子メール通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9c4ce-184">Defender for Endpoint の既存の抑制ルールも引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="9c4ce-185">Defender for Endpoint ルールを編集して、Microsoft 365 Defender でのみ使用できる ID テーブルと電子メール テーブルを照会すると、そのルールは自動的に Microsoft 365 Defender に移動されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="9c4ce-186">移行されたルールによって生成されるアラート:</span><span class="sxs-lookup"><span data-stu-id="9c4ce-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="9c4ce-187">Defender for Endpoint ポータルに表示されなくなりました (Microsoft Defender セキュリティ センター)</span><span class="sxs-lookup"><span data-stu-id="9c4ce-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="9c4ce-188">SIEM への配信を停止するか、電子メール通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="9c4ce-189">この変更を回避するには、Microsoft 365 Defender を使用して通知を構成して、アラートを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="9c4ce-190">[Microsoft 365 Defender API を使用して](api-incident.md)、顧客検出アラートまたは関連インシデントに関する通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="9c4ce-191">Microsoft Defender for Endpoint 抑制ルールでは抑制されません。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="9c4ce-192">特定のユーザー、デバイス、またはメールボックスに対してアラートが生成されるのを防ぐために、対応するクエリを変更して、それらのエンティティを明示的に除外します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="9c4ce-193">この方法でルールを編集すると、そのような変更が適用される前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="9c4ce-194">Microsoft 365 Defender ポータルのカスタム検出ルールによって生成された新しいアラートは、次の情報を提供するアラート ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="9c4ce-195">アラートのタイトルと説明</span><span class="sxs-lookup"><span data-stu-id="9c4ce-195">Alert title and description</span></span> 
- <span data-ttu-id="9c4ce-196">影響を受け取ったアセット</span><span class="sxs-lookup"><span data-stu-id="9c4ce-196">Impacted assets</span></span>
- <span data-ttu-id="9c4ce-197">アラートに応答して実行されるアクション</span><span class="sxs-lookup"><span data-stu-id="9c4ce-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="9c4ce-198">アラートをトリガーしたクエリ結果</span><span class="sxs-lookup"><span data-stu-id="9c4ce-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="9c4ce-199">カスタム検出ルールに関する情報</span><span class="sxs-lookup"><span data-stu-id="9c4ce-199">Information on the custom detection rule</span></span> 
 
![新しいアラート ページのイメージ](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="9c4ce-201">DeviceAlertEvents を使用せずにクエリを書き込む</span><span class="sxs-lookup"><span data-stu-id="9c4ce-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="9c4ce-202">Microsoft 365 Defender スキーマでは、さまざまなソースからのアラートに付随する多様な情報セットに対応するために、テーブル `AlertInfo` `AlertEvidence` とテーブルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="9c4ce-203">Microsoft Defender for Endpoint スキーマのテーブルから取得したのと同じアラート情報を取得するには、テーブルをフィルター処理し、各一意 `DeviceAlertEvents` `AlertInfo` の `ServiceSource` ID `AlertEvidence` をテーブルに結合して、詳細なイベントとエンティティ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="9c4ce-204">以下のサンプル クエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="9c4ce-205">このクエリは、Microsoft Defender for Endpoint スキーマよりも `DeviceAlertEvents` 多くの列を生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9c4ce-206">結果を管理し続けるには、関心 `project` のある列のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="9c4ce-207">次の例では、調査で PowerShell アクティビティが検出された場合に関心のある列をプロジェクトします。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="9c4ce-208">アラートに関連する特定のエンティティをフィルター処理する場合は、エンティティの種類とフィルター処理する値を指定します `EntityType` 。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="9c4ce-209">次の例では、特定の IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="9c4ce-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="9c4ce-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c4ce-210">See also</span></span>
- [<span data-ttu-id="9c4ce-211">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="9c4ce-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9c4ce-212">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="9c4ce-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9c4ce-213">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="9c4ce-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9c4ce-214">エンドポイント向け Microsoft Defender での高度な検索</span><span class="sxs-lookup"><span data-stu-id="9c4ce-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)