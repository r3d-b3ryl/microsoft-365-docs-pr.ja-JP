---
title: Microsoft Defender for Office 365 の新機能
description: Microsoft Defender for Office 365 の最新リリースで利用できる新機能について説明します。
keywords: Microsoft Defender for Office 365、ga、一般提供、機能、利用可能、新しい
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4bb1450790883deec295f554ddf9614c0f01fe2d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930485"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd09d-104">Microsoft Defender for Office 365 の新機能</span><span class="sxs-lookup"><span data-stu-id="fd09d-104">What's new in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fd09d-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fd09d-105">**Applies to**</span></span>
- [<span data-ttu-id="fd09d-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fd09d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fd09d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd09d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fd09d-108">この記事では、Microsoft Defender for microsoft Defender の最新リリースの新機能をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="fd09d-108">This article lists new features in the latest release of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="fd09d-109">現在プレビュー中の機能は (プレビュー) **で示されます**。</span><span class="sxs-lookup"><span data-stu-id="fd09d-109">Features that are currently in preview are denoted with **(preview)**.</span></span>

<span data-ttu-id="fd09d-110">[このビデオ](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)を見て詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="fd09d-110">Learn more by watching [this video](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).</span></span>
> [!TIP]
> <span data-ttu-id="fd09d-111">Microsoft Defender for Office 365ありませんか?</span><span class="sxs-lookup"><span data-stu-id="fd09d-111">Don't have Microsoft Defender for Office 365 yet?</span></span> <span data-ttu-id="fd09d-112">[試用版を開始するために販売に問い合わせ。](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)</span><span class="sxs-lookup"><span data-stu-id="fd09d-112">[Contact sales to start a trial](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html).</span></span>

## <a name="februarymarch-2021"></a><span data-ttu-id="fd09d-113">2021 年 2 月/3 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-113">February/March 2021</span></span> 

- <span data-ttu-id="fd09d-114">検索エクスペリエンスでのアラート ID の統合 (アラート ID とAlert-Explorerナビゲーションを使用[した検索](threat-explorer.md))</span><span class="sxs-lookup"><span data-stu-id="fd09d-114">Alert ID integration (search using Alert ID and Alert-Explorer navigation) in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="fd09d-115">狩猟エクスペリエンスでのレコードのエクスポートの制限を 9990 から 200,000 に [増やす](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="fd09d-115">Increasing the limits for Export of records from 9990 to 200,000 in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="fd09d-116">試用版テナントのエクスプローラー (およびリアルタイム検出) データの保持と検索の制限を 7 (前の制限) から 30 日間のハンティング エクスペリエンス [に拡張する](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="fd09d-116">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 (previous limit) to 30 days in [hunting experiences](threat-explorer.md)</span></span>
- <span data-ttu-id="fd09d-117">保護されたユーザーまたはドメインに対する偽装攻撃を検索するための、エクスプローラー内の偽装ドメインと偽装ユーザー (およびリアルタイムの検出) と呼ばれる新しい検索ピボット。</span><span class="sxs-lookup"><span data-stu-id="fd09d-117">New hunting pivots called **Impersonated domain** and **Impersonated user** within the Explorer (and Real-time detections) to search for impersonation attacks against protected users or domains.</span></span> <span data-ttu-id="fd09d-118">詳細については、「詳細」を [参照してください](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。</span><span class="sxs-lookup"><span data-stu-id="fd09d-118">For more information, see [details](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains).</span></span> <span data-ttu-id="fd09d-119">(Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-119">(Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="december-2020"></a><span data-ttu-id="fd09d-120">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-120">December 2020</span></span>

- [<span data-ttu-id="fd09d-121">既定ではセキュリティで保護Office 365</span><span class="sxs-lookup"><span data-stu-id="fd09d-121">Secure by default in Office 365</span></span>](secure-by-default.md)
- <span data-ttu-id="fd09d-122">自動調査の機能強化: 手動でトリガーされた電子メール調査に関する一般的なアラート、メールボックスの変更を別のエンティティ カテゴリとして扱い、冗長な URL ブロック アクションを削除し、ユーザーが侵害された調査のために送信メール クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd09d-122">Automated investigation improvements to: general alerts for manually triggered email investigations, treat mailbox changes as a separate entity category, remove redundant URL block actions, and create outbound email clusters for user compromised investigations.</span></span>

## <a name="november-2020"></a><span data-ttu-id="fd09d-123">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-123">November 2020</span></span>

- <span data-ttu-id="fd09d-124">Review > アクション センター >メール送信とアクション ログからの修復のエクスポート制限を更新しました (Defender for Office 365 プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-124">Updated export limits in Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)</span></span>

## <a name="septemberoctober-2020"></a><span data-ttu-id="fd09d-125">2020 年 9 月/10 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-125">September/October 2020</span></span>

- [<span data-ttu-id="fd09d-126">Configuration Analyzer を使用してポリシーを確認する</span><span class="sxs-lookup"><span data-stu-id="fd09d-126">Check your policies using Configuration Analyzer</span></span>](configuration-analyzer-for-security-policies.md)
- <span data-ttu-id="fd09d-127">トップ ターゲットユーザー、トランスポート ルール、コネクタを含む脅威エクスプローラーの拡張機能[(Threat](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) [Explorer](threat-explorer.md)の Office 365 の Defender 情報 (テナント/ユーザー ポリシーによって電子メールが許可/ブロックされました) (Defender for Office 365 Plan 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-127">[Extended capabilities in Threat Explorer including top targeted users, transport rules, and connectors](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Defender for Office 365 information in [Threat Explorer](threat-explorer.md) (email was allowed/blocked by tenant/user policy) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="fd09d-128">脅威エクスプローラー (マルウェア、フィッシング、スパム、またはなし) で URL の脅威を検出する[(Defender](threat-explorer.md#threats-in-urls) for Office 365 プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-128">Surfacing URL threats in [Threat Explorer](threat-explorer.md#threats-in-urls) (malware, phish, spam, or none) (Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="fd09d-129">[脅威、追加アクション](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming)、配信場所、および更新されたタイムライン ビューに関する更新プログラムを含むハンティング エクスペリエンス脅威エクスプローラーの機能強化 (Defender for Office 365 プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-129">[Improvements to Hunting Experience Threat Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) with updates around Threats, Additional Actions, Delivery locations and Updated timeline view (Defender for Office 365 Plan 2)</span></span>

## <a name="julyaugust-2020"></a><span data-ttu-id="fd09d-130">2020 年 7 月/8 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-130">July/August 2020</span></span>

- <span data-ttu-id="fd09d-131">[ハンティング エクスペリエンスの改善点](threat-explorer.md#improvements-to-threat-hunting-experience)(Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-131">[Experience improvements to the hunting experience](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>
- [<span data-ttu-id="fd09d-132">事前設定されたセキュリティ ポリシーを使用して推奨設定を簡単に適用する</span><span class="sxs-lookup"><span data-stu-id="fd09d-132">Easily apply recommended settings using preset security policies</span></span>](preset-security-policies.md)

## <a name="marchapril-2020"></a><span data-ttu-id="fd09d-133">2020 年 3 月/4 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-133">March/April 2020</span></span>

- <span data-ttu-id="fd09d-134">調査と対応 [を自動化](address-compromised-users-quickly.md) して、侵害されたユーザー アカウントに対処する機能が一般に利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fd09d-134">The ability to [address compromised user accounts with automated investigation and response](address-compromised-users-quickly.md) is now generally available.</span></span> <span data-ttu-id="fd09d-135">(Microsoft Defender for Office 365プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-135">(Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="januaryfebruary-2020"></a><span data-ttu-id="fd09d-136">2020 年 1 月/2 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-136">January/February 2020</span></span>

- <span data-ttu-id="fd09d-137">[Microsoft Defender for microsoft Defender for](campaigns.md) Office 365のキャンペーン ビューの一Office 365利用可能 ( プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-137">[General availability of Campaign Views in Microsoft Defender for Office 365](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>
- <span data-ttu-id="fd09d-138">セキュリティ[運用チームが](threat-explorer.md)電子メールの調査中に複数のフィールドを検索およびフィルター処理できる脅威エクスプローラーの機能強化[:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender for Office 365 プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-138">Enhancements to [Threat Explorer](threat-explorer.md) to enable security operations teams to search and filter on multiple fields while [investigating email](investigate-malicious-email-that-was-delivered.md): (Microsoft Defender for Office 365 Plan 2)</span></span>
  - <span data-ttu-id="fd09d-139">配信場所と特別なアクション</span><span class="sxs-lookup"><span data-stu-id="fd09d-139">Delivery location and special actions</span></span>
  - <span data-ttu-id="fd09d-140">方向性 (受信、送信、または組織内)</span><span class="sxs-lookup"><span data-stu-id="fd09d-140">Directionality (inbound, outbound, or intra-org)</span></span>
  - <span data-ttu-id="fd09d-141">高度な NOT フィルター (これらは、含まれているか、含めない、などを含む高度なフィルター オプションです)</span><span class="sxs-lookup"><span data-stu-id="fd09d-141">Advanced NOT filters (these are advanced filtering options that include does not contain, does not include, etc.)</span></span>
  - <span data-ttu-id="fd09d-142">詳細な時間フィルター (日、時間、30 分)</span><span class="sxs-lookup"><span data-stu-id="fd09d-142">Granular time filters (day, hour, half-hour)</span></span>

- <span data-ttu-id="fd09d-143">インシデント **ウィジェットが** アクション センター **ウィジェットに変更** されました。</span><span class="sxs-lookup"><span data-stu-id="fd09d-143">The **Incidents** widget is now the **Action Center** widget.</span></span> <span data-ttu-id="fd09d-144">(セキュリティ ウィジェットを表示するには、セキュリティ &コンプライアンス センターで、[脅威の管理]**に移動します。** \>**レビュー**.)(Microsoft Defender for Office 365プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-144">(To view your security widgets, in the Security & Compliance Center, go to **Threat management** \> **Review**.) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="fd09d-145">[セーフドキュメントのMicrosoft 365](safe-docs.md) **(プレビュー)**</span><span class="sxs-lookup"><span data-stu-id="fd09d-145">[Safe Documents in Microsoft 365](safe-docs.md) **(preview)**</span></span>

## <a name="december-2019"></a><span data-ttu-id="fd09d-146">2019 年 12 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-146">December 2019</span></span>

- <span data-ttu-id="fd09d-147">[オフライン分析用の URL クリック データ](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections)のエクスポート (Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-147">[Export URL click data for offline analysis](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

- <span data-ttu-id="fd09d-148">[Microsoft Defender のキャンペーン ビューを使用して、Office 365 (**プレビュー**)](campaigns.md) (Microsoft Defender for Office 365 プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-148">[Use Campaign Views in Microsoft Defender for Office 365 (**preview**)](campaigns.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="november-2019"></a><span data-ttu-id="fd09d-149">2019 年 11 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-149">November 2019</span></span>

- <span data-ttu-id="fd09d-150">[侵害された新しいユーザー検出](address-compromised-users-quickly.md)および応答機能 (**プレビュー**) (Microsoft Defender for Office 365プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-150">[Check out new compromised user detection and response capabilities](address-compromised-users-quickly.md) (**preview**) (Microsoft Defender for Office 365 Plan 2)</span></span>

## <a name="september-2019"></a><span data-ttu-id="fd09d-151">2019 年 9 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-151">September 2019</span></span>

- <span data-ttu-id="fd09d-152">[自動調査と対応機能を採用](automated-investigation-response-office.md)する (Microsoft Defender for Office 365プラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-152">[Employ automated investigation and response capabilities](automated-investigation-response-office.md) (Microsoft Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="fd09d-153">[Microsoft Defender と統合して、Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)管理アクティビティ API (Defender for Office 365 プラン 2) を使用して、Office 365調査および応答イベントを自動化します。</span><span class="sxs-lookup"><span data-stu-id="fd09d-153">[Integrate with Microsoft Defender for Office 365 automated investigation and response events using the Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender for Office 365 Plan 2)</span></span>

- <span data-ttu-id="fd09d-154">[電子メール ヘッダーを表示し、電子メール本文](investigate-malicious-email-that-was-delivered.md)をダウンロードする (Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-154">[View the email headers and download the email body](investigate-malicious-email-that-was-delivered.md) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="august-2019"></a><span data-ttu-id="fd09d-155">2019 年 8 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-155">August 2019</span></span>

- <span data-ttu-id="fd09d-156">[メールのタイムラインを表示](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email)する (Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-156">[View the timeline of email](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="july-2019"></a><span data-ttu-id="fd09d-157">2019 年 7 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-157">July 2019</span></span>

- <span data-ttu-id="fd09d-158">[メール メッセージの配信アクションと場所を](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location)確認する (Microsoft Defender for Office 365プラン 1 または 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-158">[Check the delivery action and location of email messages](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) (Microsoft Defender for Office 365 Plan 1 or 2)</span></span>

## <a name="june-2019"></a><span data-ttu-id="fd09d-159">2019 年 6 月</span><span class="sxs-lookup"><span data-stu-id="fd09d-159">June 2019</span></span>

- <span data-ttu-id="fd09d-160">[フィッシング URL を表示し、[評](threat-explorer.md#view-phishing-url-and-click-verdict-data)決データ] をクリックします (Microsoft Defender for Office 365プラン 1 またはプラン 2)</span><span class="sxs-lookup"><span data-stu-id="fd09d-160">[View phishing URLs and click verdict data](threat-explorer.md#view-phishing-url-and-click-verdict-data) (Microsoft Defender for Office 365 Plan 1 or Plan 2)</span></span>

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a><span data-ttu-id="fd09d-161">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fd09d-161">Microsoft Defender for Office 365 Plan 1 and Plan 2</span></span>

<span data-ttu-id="fd09d-162">Microsoft Defender for Office 365プランが 2 つ用意されていますか?</span><span class="sxs-lookup"><span data-stu-id="fd09d-162">Did you know that Microsoft Defender for Office 365 is available in two plans?</span></span> <span data-ttu-id="fd09d-163">[各プランに含まれる内容の詳細については、以下を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。</span><span class="sxs-lookup"><span data-stu-id="fd09d-163">[Learn more about what each plan includes](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd09d-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd09d-164">See also</span></span>

[<span data-ttu-id="fd09d-165">Microsoft 365ロードマップ</span><span class="sxs-lookup"><span data-stu-id="fd09d-165">Microsoft 365 roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap)

[<span data-ttu-id="fd09d-166">Microsoft Defender for Office 365 サービスの説明</span><span class="sxs-lookup"><span data-stu-id="fd09d-166">Microsoft Defender for Office 365 Service Description</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
