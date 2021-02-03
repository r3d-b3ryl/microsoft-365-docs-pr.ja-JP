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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080744"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="c9d9b-104">Microsoft Defender for Endpoint から高度な検索クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="c9d9b-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c9d9b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c9d9b-105">**Applies to:**</span></span>
- <span data-ttu-id="c9d9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9d9b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c9d9b-107">高度なハンティング ワークフローを Microsoft Defender for Endpoint から移動し、広範なデータセットを使用して脅威を事前に検出します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="c9d9b-108">Microsoft 365 Defender では、次を含む他の Microsoft 365 セキュリティ ソリューションからデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="c9d9b-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c9d9b-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="c9d9b-110">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c9d9b-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="c9d9b-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9d9b-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c9d9b-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="c9d9b-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="c9d9b-113">ほとんどの Microsoft Defender for Endpoint のお客様は、追加のライセンスなしで [Microsoft 365 Defender を使用できます](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="c9d9b-114">Defender for Endpoint から高度なハンティング ワークフローの移行を開始するには [、Microsoft 365 Defender をオンにしてください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="c9d9b-115">既存の Defender for Endpoint ワークフローに影響を与えることなく移行できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="c9d9b-116">保存されたクエリはそのまま残り、カスタム検出ルールは引き続き実行され、アラートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="c9d9b-117">ただし、Microsoft 365 Defender に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="c9d9b-118">Microsoft 365 Defender のスキーマ テーブルのみ</span><span class="sxs-lookup"><span data-stu-id="c9d9b-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="c9d9b-119">[Microsoft 365 Defender 高度](advanced-hunting-schema-tables.md)な検索スキーマには、さまざまな Microsoft 365 セキュリティ ソリューションのデータを含む追加のテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="c9d9b-120">次の表は、Microsoft 365 Defender でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="c9d9b-121">テーブル名</span><span class="sxs-lookup"><span data-stu-id="c9d9b-121">Table name</span></span> | <span data-ttu-id="c9d9b-122">説明</span><span class="sxs-lookup"><span data-stu-id="c9d9b-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="c9d9b-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c9d9b-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="c9d9b-124">アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス</span><span class="sxs-lookup"><span data-stu-id="c9d9b-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="c9d9b-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="c9d9b-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="c9d9b-126">エンドポイント用 Microsoft Defender、Office 365 用 Microsoft Defender、Microsoft Cloud App Security、Id 用 Microsoft Defender からのアラート (重大度情報と脅威カテゴリを含む)</span><span class="sxs-lookup"><span data-stu-id="c9d9b-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="c9d9b-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="c9d9b-128">クラウド アプリとサービスでのファイル関連のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="c9d9b-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="c9d9b-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="c9d9b-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="c9d9b-130">メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="c9d9b-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="c9d9b-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="c9d9b-132">Microsoft 365 電子メール イベント (メール配信イベントとブロック イベントを含む)</span><span class="sxs-lookup"><span data-stu-id="c9d9b-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="c9d9b-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="c9d9b-134">Microsoft 365 が受信者のメールボックスにメールを配信した後に、配信後に発生するセキュリティ イベント</span><span class="sxs-lookup"><span data-stu-id="c9d9b-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="c9d9b-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="c9d9b-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="c9d9b-136">メールの URL に関する情報</span><span class="sxs-lookup"><span data-stu-id="c9d9b-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="c9d9b-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="c9d9b-138">Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="c9d9b-139">次の表に、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="c9d9b-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c9d9b-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="c9d9b-141">Azure Active Directory など、さまざまなソースからのアカウント情報</span><span class="sxs-lookup"><span data-stu-id="c9d9b-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="c9d9b-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="c9d9b-143">Active Directory および Microsoft オンライン サービスの認証イベント</span><span class="sxs-lookup"><span data-stu-id="c9d9b-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="c9d9b-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c9d9b-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="c9d9b-145">ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ</span><span class="sxs-lookup"><span data-stu-id="c9d9b-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="c9d9b-146">DeviceAlertEvents テーブルのマップ</span><span class="sxs-lookup"><span data-stu-id="c9d9b-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="c9d9b-147">The `AlertInfo` and tables replace the table in the Microsoft Defender for Endpoint `AlertEvidence` `DeviceAlertEvents` schema.</span><span class="sxs-lookup"><span data-stu-id="c9d9b-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="c9d9b-148">デバイスアラートに関するデータに加えて、これら 2 つの表には、ID、アプリ、メールのアラートに関するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="c9d9b-149">次の表を使用して、列とテーブルの列のマップ `DeviceAlertEvents` 方法を `AlertInfo` 確認 `AlertEvidence` します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="c9d9b-150">次の表の列に加えて、この表には、さまざまなソースからのアラートのより包括的な画像を提供するその他の多くの列 `AlertEvidence` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="c9d9b-151">AlertEvidence のすべての列を表示する</span><span class="sxs-lookup"><span data-stu-id="c9d9b-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="c9d9b-152">DeviceAlertEvents 列</span><span class="sxs-lookup"><span data-stu-id="c9d9b-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="c9d9b-153">Microsoft 365 Defender で同じデータを検索する場所</span><span class="sxs-lookup"><span data-stu-id="c9d9b-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="c9d9b-154">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="c9d9b-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="c9d9b-155">`AlertInfo` および  `AlertEvidence` テーブル</span><span class="sxs-lookup"><span data-stu-id="c9d9b-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="c9d9b-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="c9d9b-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="c9d9b-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="c9d9b-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="c9d9b-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="c9d9b-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="c9d9b-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="c9d9b-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="c9d9b-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="c9d9b-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="c9d9b-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="c9d9b-166">この列は、通常、Microsoft Defender for Endpoint で他のテーブル内の関連レコードを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="c9d9b-167">Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="c9d9b-168">この列は、通常、他の表の追加のイベント情報のために Microsoft Defender for Endpoint で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="c9d9b-169">Microsoft 365 Defender では、テーブルから直接関連データを取得 `AlertEvidence` できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="c9d9b-170">エンドポイント用の既存の Microsoft Defender クエリを調整する</span><span class="sxs-lookup"><span data-stu-id="c9d9b-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="c9d9b-171">Microsoft Defender for Endpoint のクエリは、テーブルを参照しない限り、同じ方法で動作 `DeviceAlertEvents` します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="c9d9b-172">Microsoft 365 Defender でこれらのクエリを使用するには、次の変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="c9d9b-173">置換 `DeviceAlertEvents` 後 `AlertInfo` の文字列</span><span class="sxs-lookup"><span data-stu-id="c9d9b-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="c9d9b-174">テーブルとテーブル `AlertInfo` を `AlertEvidence` 結合して `AlertId` 、同等のデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="c9d9b-175">元のクエリ</span><span class="sxs-lookup"><span data-stu-id="c9d9b-175">Original query</span></span>
<span data-ttu-id="c9d9b-176">次のクエリは `DeviceAlertEvents` 、Microsoft Defender for Endpoint で使用して、エンドポイントに関連するアラート _をpowershell.exe。_</span><span class="sxs-lookup"><span data-stu-id="c9d9b-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="c9d9b-177">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="c9d9b-177">Modified query</span></span>
<span data-ttu-id="c9d9b-178">次のクエリは、Microsoft 365 Defender での使用に合わせて調整されています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="c9d9b-179">ファイル名を直接チェックする代わりに、テーブル内のファイル名を結合 `DeviceAlertEvents` `AlertEvidence` して確認します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="c9d9b-180">カスタム検出ルールを移行する</span><span class="sxs-lookup"><span data-stu-id="c9d9b-180">Migrate custom detection rules</span></span>

<span data-ttu-id="c9d9b-181">Microsoft Defender for Endpoint ルールが Microsoft 365 Defender で編集された場合、結果のクエリでデバイス テーブルのみを検索する場合と同様に機能し続ける。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="c9d9b-182">たとえば、デバイス テーブルのみを照会するカスタム検出ルールによって生成されたアラートは、Microsoft Defender for Endpoint での構成方法に応じて、SIEM に配信され、電子メール通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c9d9b-183">Defender for Endpoint の既存の抑制ルールも引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="c9d9b-184">Microsoft 365 Defender でのみ使用可能な ID と電子メール テーブルを照会する Defender for Endpoint ルールを編集すると、そのルールは自動的に Microsoft 365 Defender に移動されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="c9d9b-185">移行されたルールによって生成されたアラート:</span><span class="sxs-lookup"><span data-stu-id="c9d9b-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="c9d9b-186">Defender for Endpoint ポータルに表示されなくなりました (Microsoft Defender セキュリティ センター)</span><span class="sxs-lookup"><span data-stu-id="c9d9b-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="c9d9b-187">SIEM への配信を停止するか、メール通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="c9d9b-188">この変更を回避するには、Microsoft 365 Defender 経由で通知を構成してアラートを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="c9d9b-189">[Microsoft 365 Defender API を使用](api-incident.md)して、顧客検出のアラートや関連するインシデントに関する通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="c9d9b-190">Microsoft Defender for Endpoint の抑制ルールでは抑制されません。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="c9d9b-191">特定のユーザー、デバイス、またはメールボックスに対してアラートが生成されるのを防ぐには、対応するクエリを変更して、それらのエンティティを明示的に除外します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="c9d9b-192">この方法でルールを編集すると、そのような変更が適用される前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="c9d9b-193">Microsoft 365 Defender ポータルのカスタム検出ルールによって生成された新しいアラートは、次の情報を提供するアラート ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="c9d9b-194">アラートのタイトルと説明</span><span class="sxs-lookup"><span data-stu-id="c9d9b-194">Alert title and description</span></span> 
- <span data-ttu-id="c9d9b-195">影響を受け資産</span><span class="sxs-lookup"><span data-stu-id="c9d9b-195">Impacted assets</span></span>
- <span data-ttu-id="c9d9b-196">アラートに対して実行されたアクション</span><span class="sxs-lookup"><span data-stu-id="c9d9b-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="c9d9b-197">アラートをトリガーしたクエリ結果</span><span class="sxs-lookup"><span data-stu-id="c9d9b-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="c9d9b-198">カスタム検出ルールに関する情報</span><span class="sxs-lookup"><span data-stu-id="c9d9b-198">Information on the custom detection rule</span></span> 
 
![新しいアラート ページの画像](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="c9d9b-200">DeviceAlertEvents を使用せずにクエリを書き込む</span><span class="sxs-lookup"><span data-stu-id="c9d9b-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="c9d9b-201">Microsoft 365 Defender スキーマでは、さまざまなソースからのアラートに付随するさまざまな情報のセットに対応するために、表 `AlertInfo` `AlertEvidence` と表が提供されています。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="c9d9b-202">Microsoft Defender for Endpoint スキーマの表から取得するために使用したのと同じアラート情報を取得するには、テーブルをフィルター処理し、各一意 `DeviceAlertEvents` `AlertInfo` の `ServiceSource` ID `AlertEvidence` をテーブルに結合します。テーブルは、詳細なイベントとエンティティ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="c9d9b-203">以下のサンプル クエリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="c9d9b-204">このクエリは、Microsoft Defender for Endpoint スキーマよりも `DeviceAlertEvents` 多くの列を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="c9d9b-205">結果を管理可能な状態に保つには、関心 `project` のある列のみを取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="c9d9b-206">次の例では、調査で PowerShell アクティビティが検出された場合に関心のある列をプロジェクトします。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="c9d9b-207">通知に関係する特定のエンティティをフィルター処理する場合は、フィルター処理するエンティティの種類と値を指定します `EntityType` 。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="c9d9b-208">次の例では、特定の IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="c9d9b-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="c9d9b-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9d9b-209">See also</span></span>
- [<span data-ttu-id="c9d9b-210">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="c9d9b-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c9d9b-211">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="c9d9b-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c9d9b-212">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="c9d9b-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c9d9b-213">Microsoft Defender for Endpoint での高度な検索</span><span class="sxs-lookup"><span data-stu-id="c9d9b-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)