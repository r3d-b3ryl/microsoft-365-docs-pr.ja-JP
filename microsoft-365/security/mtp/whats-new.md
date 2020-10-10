---
title: Microsoft Threat Protection の新機能
description: Microsoft の脅威保護の新機能の一覧を掲載しています。
keywords: microsoft の脅威保護、ga、一般提供される機能、利用可能な新機能、新規
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 670b020e3c15ac99b06bc8615b2693ba73497b8a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412036"
---
# <a name="whats-new-in-microsoft-threat-protection"></a><span data-ttu-id="70d30-104">Microsoft Threat Protection の新機能</span><span class="sxs-lookup"><span data-stu-id="70d30-104">What's new in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="70d30-105">Microsoft の脅威保護の最新リリースでは、次の機能が一般公開 (GA) されています。</span><span class="sxs-lookup"><span data-stu-id="70d30-105">The following features are generally available (GA) in the latest release of Microsoft Threat Protection.</span></span>

<span data-ttu-id="70d30-106">RSS フィード: このページが更新されたときに通知を取得するには、次の URL をフィードリーダーにコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="70d30-106">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a><span data-ttu-id="70d30-107">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="70d30-107">September 2020</span></span>
- [<span data-ttu-id="70d30-108">Identity Directoryevents テーブル</span><span class="sxs-lookup"><span data-stu-id="70d30-108">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="70d30-109">Active Directory (AD) を実行しているオンプレミスのドメインコントローラーを含むイベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="70d30-109">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="70d30-110">この [高度な](advanced-hunting-overview.md) 検索スキーマテーブルは、ドメインコントローラー上の id 関連イベントとシステムイベントの範囲をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="70d30-110">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="70d30-111">AssignedIPAddresses () 関数</span><span class="sxs-lookup"><span data-stu-id="70d30-111">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="70d30-112">詳細な検索クエリでこの関数を使用して、デバイスに割り当てられている最新の IP アドレスまたは特定の時刻からの最新の IP アドレスをすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="70d30-112">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="70d30-113">2020 年7 月</span><span class="sxs-lookup"><span data-stu-id="70d30-113">July 2020</span></span>
- [<span data-ttu-id="70d30-114">FileProfile () 関数</span><span class="sxs-lookup"><span data-stu-id="70d30-114">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="70d30-115">高度な検索のクエリでこの関数を使用して、包括的なファイル情報を使用して結果を充実させます。</span><span class="sxs-lookup"><span data-stu-id="70d30-115">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="70d30-116">Id とアプリのテーブル</span><span class="sxs-lookup"><span data-stu-id="70d30-116">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="70d30-117">高度な検索スキーマで、認証イベント、Active Directory クエリ、アプリに関連するアクティビティの可視性を取得します。これには、詳細な検索スキーマのイベントテーブル[、イベント](advanced-hunting-identityqueryevents-table.md)[テーブル、および](advanced-hunting-identitylogonevents-table.md) [appfileevents](advanced-hunting-appfileevents-table.md)テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="70d30-117">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="70d30-118">検出する</span><span class="sxs-lookup"><span data-stu-id="70d30-118">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="70d30-119">高度な検索の際に、特定のイベント、ユーザー、デバイス、またはその他のエンティティの種類を調査するインシデントの調査からすばやくピボットします。</span><span class="sxs-lookup"><span data-stu-id="70d30-119">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="70d30-120">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="70d30-120">June 2020</span></span>
- <span data-ttu-id="70d30-121">Twitter フィード</span><span class="sxs-lookup"><span data-stu-id="70d30-121">Twitter feed</span></span> <br> <span data-ttu-id="70d30-122">最新のセキュリティ研究、脅威インテリジェンス、製品ニュース、およびダッシュボード内部の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="70d30-122">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="70d30-123">EmailPostDeliveryEvents スキーマテーブル</span><span class="sxs-lookup"><span data-stu-id="70d30-123">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="70d30-124">高度な検索クエリで電子メールメッセージに対して実行された配信後の処理に関する情報を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="70d30-124">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="70d30-125">高度な検索でレコードを検査する</span><span class="sxs-lookup"><span data-stu-id="70d30-125">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="70d30-126">新しい [詳細] パネルを使用して、クエリ結果のレコードをすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="70d30-126">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="70d30-127">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="70d30-127">May 2020</span></span>
- [<span data-ttu-id="70d30-128">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="70d30-128">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="70d30-129">高度な検索クエリを使用して、セキュリティイベントやシステム状態を自動的に監視し、応答するカスタムの検出ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="70d30-129">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="70d30-130">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="70d30-130">February 2020</span></span>
- [<span data-ttu-id="70d30-131">インシデント</span><span class="sxs-lookup"><span data-stu-id="70d30-131">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="70d30-132">攻撃が開始された場所とその他の詳細を正確に把握して、攻撃の範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="70d30-132">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="70d30-133">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="70d30-133">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="70d30-134">セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。</span><span class="sxs-lookup"><span data-stu-id="70d30-134">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="70d30-135">高度な検索機能強化</span><span class="sxs-lookup"><span data-stu-id="70d30-135">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="70d30-136">Kusto クエリ言語とセキュリティで最適化されたスキーマを使用して、モダンワークスペース全体にわたる脅威を事前に探します。</span><span class="sxs-lookup"><span data-stu-id="70d30-136">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="70d30-137">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="70d30-137">March 2019</span></span>
- <span data-ttu-id="70d30-138">高度な検出</span><span class="sxs-lookup"><span data-stu-id="70d30-138">Advanced hunting</span></span> <br> <span data-ttu-id="70d30-139">電子メール、データ、デバイス、および id に影響を与える脅威を事前に発見できる、さまざまな検索機能に対するランディングページ。</span><span class="sxs-lookup"><span data-stu-id="70d30-139">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="70d30-140">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="70d30-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="70d30-141">組織のセキュリティ姿勢の測定、向上したアクションが実行されたことを示すより高い数値。</span><span class="sxs-lookup"><span data-stu-id="70d30-141">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="70d30-142">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="70d30-142">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="70d30-143">レポート</span><span class="sxs-lookup"><span data-stu-id="70d30-143">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="70d30-144">セキュリティアナリストや管理者が日常業務の一部として追跡するさまざまな領域をカバーするカードのホストが機能します。</span><span class="sxs-lookup"><span data-stu-id="70d30-144">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
