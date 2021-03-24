---
title: Microsoft Defender ATP で Web の脅威に対応する
description: 悪意のある Web サイトや望ましくない Web サイトに関連するアラートに応答します。 Web 脅威保護が Web ブラウザーと Windows 通知を通じてエンド ユーザーに通知する方法を理解する
keywords: Web 保護、Web 脅威保護、Web 閲覧、アラート、応答、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー、通知、エンド ユーザー、Windows 通知、ブロック ページ、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 339944b94ca55c5d73fafaabfe3f7bc26dafe7bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063676"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="ad5bd-105">Web の脅威に対応する</span><span class="sxs-lookup"><span data-stu-id="ad5bd-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ad5bd-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ad5bd-106">**Applies to:**</span></span>
- [<span data-ttu-id="ad5bd-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad5bd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ad5bd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad5bd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ad5bd-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ad5bd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad5bd-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="ad5bd-111">Microsoft Defender for Endpoint の Web 保護を使用すると、カスタム インジケーター リスト内の悪意のある Web サイトや Web サイトに関連するアラートを効率的に調査して対応できます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="ad5bd-112">Web 脅威アラートの表示</span><span class="sxs-lookup"><span data-stu-id="ad5bd-112">View web threat alerts</span></span>
<span data-ttu-id="ad5bd-113">Microsoft Defender for Endpoint は、悪意のある Web アクティビティまたは疑 [わしい](manage-alerts.md) Web アクティビティに関する次のアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="ad5bd-114">**ネットワーク保護によって** ブロックされる疑わしい接続 - このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内のWeb サイトへのアクセスがブロック モードでネットワーク保護によって停止された場合 *に生成* されます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="ad5bd-115">**ネットワーク保護によって検出** された疑わしい接続 - このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトにアクセスしようとした場合に、監査専用モードでネットワーク保護によって *検出された場合に生成* されます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="ad5bd-116">各アラートは、次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="ad5bd-117">ブロックされた Web サイトにアクセスしようとしたデバイス</span><span class="sxs-lookup"><span data-stu-id="ad5bd-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="ad5bd-118">Web 要求の送信に使用されるアプリケーションまたはプログラム</span><span class="sxs-lookup"><span data-stu-id="ad5bd-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="ad5bd-119">カスタム インジケーター リスト内の悪意のある URL または URL</span><span class="sxs-lookup"><span data-stu-id="ad5bd-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="ad5bd-120">レスポンダーに推奨されるアクション</span><span class="sxs-lookup"><span data-stu-id="ad5bd-120">Recommended actions for responders</span></span>

![Web 脅威保護に関連するアラートのイメージ](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="ad5bd-122">Microsoft Defender for Endpoint は、アラートの量を減らすために、同じデバイス上の同じドメインの Web 脅威検出を毎日 1 つのアラートに統合します。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="ad5bd-123">1 つのアラートだけが生成され [、Web 保護レポートにカウントされます](web-protection-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="ad5bd-124">Web サイトの詳細を検査する</span><span class="sxs-lookup"><span data-stu-id="ad5bd-124">Inspect website details</span></span>
<span data-ttu-id="ad5bd-125">アラートで Web サイトの URL またはドメインを選択すると、より深く掘り下げできます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="ad5bd-126">これにより、次に示すさまざまな情報を含む特定の URL またはドメインに関するページが開きます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="ad5bd-127">Web サイトにアクセスしようとしたデバイス</span><span class="sxs-lookup"><span data-stu-id="ad5bd-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="ad5bd-128">Web サイトに関連するインシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="ad5bd-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="ad5bd-129">組織のイベントで Web サイトが表示された頻度</span><span class="sxs-lookup"><span data-stu-id="ad5bd-129">How frequent the website was seen in events in your organization</span></span>

    ![ドメインまたは URL エンティティの詳細ページのイメージ](images/wtp-website-details.png)

[<span data-ttu-id="ad5bd-131">URL またはドメイン エンティティ ページの詳細</span><span class="sxs-lookup"><span data-stu-id="ad5bd-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="ad5bd-132">デバイスを検査する</span><span class="sxs-lookup"><span data-stu-id="ad5bd-132">Inspect the device</span></span>
<span data-ttu-id="ad5bd-133">ブロックされた URL にアクセスしようとしたデバイスを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="ad5bd-134">アラート ページでデバイスの名前を選択すると、デバイスに関する包括的な情報を含むページが開きます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="ad5bd-135">デバイス エンティティ ページの詳細</span><span class="sxs-lookup"><span data-stu-id="ad5bd-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="ad5bd-136">エンド ユーザー向け Web ブラウザーと Windows 通知</span><span class="sxs-lookup"><span data-stu-id="ad5bd-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="ad5bd-137">Microsoft Defender for Endpoint の Web 保護を使用すると、エンド ユーザーが Microsoft Edge や他のブラウザーを使用して悪意のある Web サイトや望ましくない Web サイトにアクセスすることを防止できます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="ad5bd-138">ブロックはネットワーク保護によって実行されます [の](network-protection.md)で、Web ブラウザーから一般的なエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="ad5bd-139">また、Windows からの通知も表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad5bd-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="ad5bd-140">![403 エラーと Microsoft Edge でブロックされている Windows 通知 Web の脅威を示す ](images/wtp-browser-blocking-page.png)
 *Microsoft Edge の画像*</span><span class="sxs-lookup"><span data-stu-id="ad5bd-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="ad5bd-141">![Chrome でセキュリティで保護された接続警告と Windows 通知 Web の脅威がブロックされている ](images/wtp-chrome-browser-blocking-page.png)
 *Chrome Web ブラウザーの画像*</span><span class="sxs-lookup"><span data-stu-id="ad5bd-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad5bd-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad5bd-142">Related topics</span></span>
- [<span data-ttu-id="ad5bd-143">Web 保護の概要</span><span class="sxs-lookup"><span data-stu-id="ad5bd-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="ad5bd-144">Web コンテンツ のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="ad5bd-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="ad5bd-145">Web 脅威保護</span><span class="sxs-lookup"><span data-stu-id="ad5bd-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="ad5bd-146">Web セキュリティの監視</span><span class="sxs-lookup"><span data-stu-id="ad5bd-146">Monitor web security</span></span>](web-protection-monitoring.md)
