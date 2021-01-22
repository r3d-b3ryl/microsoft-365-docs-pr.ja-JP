---
title: Microsoft 365 Defender の新機能
description: Microsoft 365 Defender の新機能の一覧
keywords: Microsoft Threat Protection の新機能, ga, 一般提供, 機能, 利用可能, 新規
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932024"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="5f264-104">Microsoft 365 Defender の新機能</span><span class="sxs-lookup"><span data-stu-id="5f264-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="5f264-105">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="5f264-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5f264-106">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="5f264-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="5f264-107">次の機能は、Microsoft 365 Defender の最新リリースで一般公開 (GA) されます。</span><span class="sxs-lookup"><span data-stu-id="5f264-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="5f264-108">RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5f264-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> <span data-ttu-id="5f264-109">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="5f264-109">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5f264-110">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) 実稼働 [環境でパイロット プロジェクトを実行することができます。](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="5f264-110">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook)</span></span>
>

## <a name="september-2020"></a><span data-ttu-id="5f264-111">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="5f264-111">September 2020</span></span>
- [<span data-ttu-id="5f264-112">IdentityDirectoryEvents テーブル</span><span class="sxs-lookup"><span data-stu-id="5f264-112">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="5f264-113">Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベントを検索します (AD)。</span><span class="sxs-lookup"><span data-stu-id="5f264-113">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="5f264-114">この [高度な検索](advanced-hunting-overview.md) スキーマの表では、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f264-114">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="5f264-115">AssignedIPAddresses() 関数</span><span class="sxs-lookup"><span data-stu-id="5f264-115">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="5f264-116">高度な検索クエリでこの関数を使用して、デバイスに割り当てられた最新の IP アドレスまたは最新の IP アドレスを特定の時間から迅速に取得します。</span><span class="sxs-lookup"><span data-stu-id="5f264-116">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="5f264-117">2020 年7 月</span><span class="sxs-lookup"><span data-stu-id="5f264-117">July 2020</span></span>
- [<span data-ttu-id="5f264-118">FileProfile() 関数</span><span class="sxs-lookup"><span data-stu-id="5f264-118">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="5f264-119">この関数は、高度な検索クエリで使用して、包括的なファイル情報で結果を充実します。</span><span class="sxs-lookup"><span data-stu-id="5f264-119">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="5f264-120">ID テーブルとアプリ テーブル</span><span class="sxs-lookup"><span data-stu-id="5f264-120">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="5f264-121">高度な検索スキーマの[IdentityLogonEvents、IdentityQueryEvents、](advanced-hunting-identitylogonevents-table.md)[および AppFileEvents](advanced-hunting-appfileevents-table.md)テーブル[](advanced-hunting-identityqueryevents-table.md)を使用して、認証イベント、Active Directory クエリ、およびアプリ関連のアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5f264-121">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="5f264-122">検出する</span><span class="sxs-lookup"><span data-stu-id="5f264-122">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="5f264-123">インシデントの調査から、特定のイベント、ユーザー、デバイス、または高度な検索に関するその他のエンティティの種類の検査にすばやくピボットできます。</span><span class="sxs-lookup"><span data-stu-id="5f264-123">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="5f264-124">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="5f264-124">June 2020</span></span>
- <span data-ttu-id="5f264-125">Twitter フィード</span><span class="sxs-lookup"><span data-stu-id="5f264-125">Twitter feed</span></span> <br> <span data-ttu-id="5f264-126">ダッシュボード内で最新のセキュリティ調査、脅威インテリジェンス、製品ニュースなどをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="5f264-126">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="5f264-127">EmailPostDeliveryEvents スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="5f264-127">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="5f264-128">高度な検索クエリに、電子メール メッセージに対して実行された配信後の操作に関する情報を組み込む。</span><span class="sxs-lookup"><span data-stu-id="5f264-128">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="5f264-129">高度な検索でレコードを検査する</span><span class="sxs-lookup"><span data-stu-id="5f264-129">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="5f264-130">新しい詳細パネルを使用して、クエリ結果のレコードをすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="5f264-130">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="5f264-131">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="5f264-131">May 2020</span></span>
- [<span data-ttu-id="5f264-132">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="5f264-132">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="5f264-133">高度な検索クエリを使用して、セキュリティ イベントとシステム状態を自動的に監視および応答するカスタム検出ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f264-133">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="5f264-134">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="5f264-134">February 2020</span></span>
- [<span data-ttu-id="5f264-135">インシデント</span><span class="sxs-lookup"><span data-stu-id="5f264-135">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="5f264-136">攻撃が開始された場所と、攻撃の程度を確認するのに役立つその他の詳細を正確に知る。</span><span class="sxs-lookup"><span data-stu-id="5f264-136">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="5f264-137">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="5f264-137">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="5f264-138">セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。</span><span class="sxs-lookup"><span data-stu-id="5f264-138">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="5f264-139">高度な検索機能の強化</span><span class="sxs-lookup"><span data-stu-id="5f264-139">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="5f264-140">Kusto クエリ言語とセキュリティに最適化されたスキーマを使用して、モダン ワークスペース全体で脅威を事前に検出します。</span><span class="sxs-lookup"><span data-stu-id="5f264-140">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="5f264-141">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="5f264-141">March 2019</span></span>
- <span data-ttu-id="5f264-142">高度な検出</span><span class="sxs-lookup"><span data-stu-id="5f264-142">Advanced hunting</span></span> <br> <span data-ttu-id="5f264-143">電子メールとデータ、デバイス、ID に影響を与える脅威を事前に検出できる、さまざまな検索機能へのランディング ページ。</span><span class="sxs-lookup"><span data-stu-id="5f264-143">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="5f264-144">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="5f264-144">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="5f264-145">組織のセキュリティ体制の測定。数値が大きいほど、改善の取り組みにより多くのことを示します。</span><span class="sxs-lookup"><span data-stu-id="5f264-145">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="5f264-146">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="5f264-146">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="5f264-147">レポート</span><span class="sxs-lookup"><span data-stu-id="5f264-147">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="5f264-148">セキュリティ アナリストや管理者が毎日の業務の一環として追跡するさまざまな領域をカバーするカードのホストを備えます。</span><span class="sxs-lookup"><span data-stu-id="5f264-148">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
