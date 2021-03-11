---
title: Microsoft 365 Defender の新機能
description: Microsoft 365 Defender の新機能と機能の一覧
keywords: microsoft Threat Protection の新機能、ga、一般提供、機能、利用可能、新しい
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
ms.openlocfilehash: 1f5fa231c371ca7a8d6a22ca0b4ff388fd89004c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711918"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="a69a9-104">Microsoft 365 Defender の新機能</span><span class="sxs-lookup"><span data-stu-id="a69a9-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="a69a9-105">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a69a9-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="a69a9-106">ラボ環境 [で評価したり、パイロット](https://aka.ms/mtp-trial-lab) プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="a69a9-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="a69a9-107">次の機能は、Microsoft 365 Defender の最新リリースで一般公開 (GA) されています。</span><span class="sxs-lookup"><span data-stu-id="a69a9-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="a69a9-108">RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a69a9-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a><span data-ttu-id="a69a9-109">2021 年 3 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-109">March 2021</span></span>
- [<span data-ttu-id="a69a9-110">CloudAppEvents テーブル</span><span class="sxs-lookup"><span data-stu-id="a69a9-110">CloudAppEvents table</span></span>](advanced-hunting-cloudappevents-table.md) <br><span data-ttu-id="a69a9-111">Microsoft Cloud App Security の対象となるさまざまなクラウド アプリとサービスのイベントに関する情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-111">Find information about events in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="a69a9-112">この表には、以前に使用した情報も含まれています `AppFileEvents` 。</span><span class="sxs-lookup"><span data-stu-id="a69a9-112">This table also includes information previously available in `AppFileEvents`.</span></span>
## <a name="february-2021"></a><span data-ttu-id="a69a9-113">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-113">February 2021</span></span>
- <span data-ttu-id="a69a9-114">(プレビュー)強化された[Microsoft 365 https://security.microsoft.com) セキュリティ センター (](https://security.microsoft.com)はパブリック プレビューで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="a69a9-114">(Preview) The enhanced [Microsoft 365 security center (https://security.microsoft.com)](https://security.microsoft.com) is now available in public preview.</span></span> <span data-ttu-id="a69a9-115">この新しいエクスペリエンスにより、Defender for Endpoint と Defender for Office 365 が中央に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a69a9-115">This new experience brings Defender for Endpoint and Defender for Office 365 to the center.</span></span> <span data-ttu-id="a69a9-116">[変更された情報の詳細については、次のリンクを参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="a69a9-116">[Learn more about what's changed](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).</span></span>

## <a name="september-2020"></a><span data-ttu-id="a69a9-117">2020 年 9 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-117">September 2020</span></span>
- [<span data-ttu-id="a69a9-118">IdentityDirectoryEvents テーブル</span><span class="sxs-lookup"><span data-stu-id="a69a9-118">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="a69a9-119">Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベントを検索します (AD)。</span><span class="sxs-lookup"><span data-stu-id="a69a9-119">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="a69a9-120">この [高度な検索](advanced-hunting-overview.md) スキーマ テーブルでは、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲について説明します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-120">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="a69a9-121">AssignedIPAddresses() 関数</span><span class="sxs-lookup"><span data-stu-id="a69a9-121">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="a69a9-122">高度な検索クエリでこの関数を使用すると、デバイスに割り当てられた最新の IP アドレスや、特定の時刻から最新の IP アドレスをすばやく取得できます。</span><span class="sxs-lookup"><span data-stu-id="a69a9-122">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="a69a9-123">2020 年 7 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-123">July 2020</span></span>
- [<span data-ttu-id="a69a9-124">FileProfile() 関数</span><span class="sxs-lookup"><span data-stu-id="a69a9-124">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="a69a9-125">高度な検索クエリでこの関数を使用して、包括的なファイル情報で結果を強化します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-125">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="a69a9-126">ID テーブルとアプリ テーブル</span><span class="sxs-lookup"><span data-stu-id="a69a9-126">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="a69a9-127">高度なハンティング スキーマの[IdentityLogonEvents、IdentityQueryEvents、](advanced-hunting-identitylogonevents-table.md)[および AppFileEvents](advanced-hunting-appfileevents-table.md)テーブルを使用して、認証イベント、Active Directory クエリ、およびアプリ関連のアクティビティを表示します。 [](advanced-hunting-identityqueryevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="a69a9-127">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="a69a9-128">検出する</span><span class="sxs-lookup"><span data-stu-id="a69a9-128">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="a69a9-129">インシデントの調査から、高度な検索で特定のイベント、ユーザー、デバイス、または他のエンティティの種類を調べにすばやくピボットします。</span><span class="sxs-lookup"><span data-stu-id="a69a9-129">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="a69a9-130">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-130">June 2020</span></span>
- <span data-ttu-id="a69a9-131">Twitter フィード</span><span class="sxs-lookup"><span data-stu-id="a69a9-131">Twitter feed</span></span> <br> <span data-ttu-id="a69a9-132">ダッシュボード内で、最新のセキュリティ調査、脅威インテリジェンス、製品ニュースなどをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a69a9-132">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="a69a9-133">EmailPostDeliveryEvents スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="a69a9-133">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="a69a9-134">高度な検索クエリに、電子メール メッセージに対して実行される配信後のアクションに関する情報を組み込む。</span><span class="sxs-lookup"><span data-stu-id="a69a9-134">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="a69a9-135">高度な検索でレコードを検査する</span><span class="sxs-lookup"><span data-stu-id="a69a9-135">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="a69a9-136">新しい詳細パネルを使用して、クエリ結果のレコードをすばやく検査します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-136">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="a69a9-137">2020 年 5 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-137">May 2020</span></span>
- [<span data-ttu-id="a69a9-138">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="a69a9-138">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="a69a9-139">高度な検索クエリを使用して、セキュリティ イベントとシステム状態を自動的に監視して対応するカスタム検出ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-139">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="a69a9-140">2020 年 2 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-140">February 2020</span></span>
- [<span data-ttu-id="a69a9-141">インシデント</span><span class="sxs-lookup"><span data-stu-id="a69a9-141">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="a69a9-142">攻撃の開始場所と、攻撃の範囲を確認するためのその他の詳細を正確に知る。</span><span class="sxs-lookup"><span data-stu-id="a69a9-142">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="a69a9-143">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="a69a9-143">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="a69a9-144">セキュリティ運用チームは AIR を使用することで、セキュリティの警告やインシデントへの組織の対応能力を大幅に向上させることが可能です。</span><span class="sxs-lookup"><span data-stu-id="a69a9-144">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="a69a9-145">高度なハンティング機能の強化</span><span class="sxs-lookup"><span data-stu-id="a69a9-145">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="a69a9-146">Kusto クエリ言語とセキュリティに最適化されたスキーマを使用して、モダン ワークスペース全体で脅威を事前に検出します。</span><span class="sxs-lookup"><span data-stu-id="a69a9-146">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="a69a9-147">2019 年 3 月</span><span class="sxs-lookup"><span data-stu-id="a69a9-147">March 2019</span></span>
- <span data-ttu-id="a69a9-148">高度な検出</span><span class="sxs-lookup"><span data-stu-id="a69a9-148">Advanced hunting</span></span> <br> <span data-ttu-id="a69a9-149">電子メールやデータ、デバイス、および ID に影響を与える脅威を積極的に検出できるさまざまな検索機能へのランディング ページ。</span><span class="sxs-lookup"><span data-stu-id="a69a9-149">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="a69a9-150">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="a69a9-150">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="a69a9-151">組織のセキュリティ体制を測定し、より多くの改善アクションを示す数値が大きい。</span><span class="sxs-lookup"><span data-stu-id="a69a9-151">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="a69a9-152">セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。</span><span class="sxs-lookup"><span data-stu-id="a69a9-152">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="a69a9-153">レポート</span><span class="sxs-lookup"><span data-stu-id="a69a9-153">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="a69a9-154">セキュリティ アナリストや管理者が毎日の操作の一環として追跡するさまざまな領域をカバーするカードのホストを備えます。</span><span class="sxs-lookup"><span data-stu-id="a69a9-154">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
