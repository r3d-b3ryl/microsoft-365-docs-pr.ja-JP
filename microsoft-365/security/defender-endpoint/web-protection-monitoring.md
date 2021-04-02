---
title: Microsoft Defender ATP での Web 閲覧のセキュリティの監視
description: Microsoft Defender ATP で Web 保護を使用して Web 閲覧のセキュリティを監視する
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 629e18c7387f6063254f3482f93a5e17023c7316
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499943"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="ae062-104">Web 閲覧のセキュリティを監視する</span><span class="sxs-lookup"><span data-stu-id="ae062-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae062-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ae062-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae062-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ae062-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae062-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae062-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ae062-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ae062-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ae062-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ae062-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="ae062-110">Web 保護を使用すると、Microsoft Defender セキュリティ センターの [レポートと Web 保護] の>を使用して、組織の **Web** 閲覧セキュリティを監視できます。</span><span class="sxs-lookup"><span data-stu-id="ae062-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ae062-111">レポートには、Web 脅威検出の統計情報を提供するカードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae062-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="ae062-112">**Web 脅威保護の** 検出時間の推移 - この傾向カードには、選択した期間中に種類別に検出された Web 脅威の数が表示されます (過去 30 日間、過去 3 か月、過去 6 か月)</span><span class="sxs-lookup"><span data-stu-id="ae062-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Web 脅威の保護検出を時間の間に示すカードの画像](images/wtp-blocks-over-time.png)

- <span data-ttu-id="ae062-114">**Web 脅威保護の** 概要 - このカードには、過去 30 日間の Web 脅威検出の合計が表示され、さまざまな種類の Web 脅威に対する配布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae062-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="ae062-115">スライスを選択すると、悪意のある Web サイトや望ましくない Web サイトで見つかったドメインの一覧が開きます。</span><span class="sxs-lookup"><span data-stu-id="ae062-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Web 脅威保護の概要を示すカードの画像](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="ae062-117">ブロックがカードまたはドメイン リストに反映されるまで最大 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae062-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="ae062-118">Web の脅威の種類</span><span class="sxs-lookup"><span data-stu-id="ae062-118">Types of web threats</span></span>

<span data-ttu-id="ae062-119">Web 保護は、悪意のある Web サイトと望ましくない Web サイトを次のように分類します。</span><span class="sxs-lookup"><span data-stu-id="ae062-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="ae062-120">**フィッシング -** スプーフィングされた Web フォームや、ユーザーをだまして資格情報などの機密情報を取得するように設計された他のフィッシング メカニズムを含む Web サイト</span><span class="sxs-lookup"><span data-stu-id="ae062-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="ae062-121">**悪意** のある - マルウェアをホストし、コードを悪用する Web サイト</span><span class="sxs-lookup"><span data-stu-id="ae062-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="ae062-122">**カスタム インジケーター** - ブロック用にカスタム インジケーター リストに追加した URL またはドメインを持つ [Web](manage-indicators.md) サイト</span><span class="sxs-lookup"><span data-stu-id="ae062-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="ae062-123">ドメイン リストの表示</span><span class="sxs-lookup"><span data-stu-id="ae062-123">View the domain list</span></span>

<span data-ttu-id="ae062-124">Web 脅威保護の概要カードで特定の Web 脅威カテゴリを **選択して** 、[ドメイン] ページ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="ae062-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="ae062-125">このページには、その脅威カテゴリの下のドメインの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae062-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="ae062-126">このページには、ドメインごとに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae062-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="ae062-127">**アクセス数** - ドメイン内の URL に対する要求の数</span><span class="sxs-lookup"><span data-stu-id="ae062-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="ae062-128">**ブロック** - 要求がブロックされた回数</span><span class="sxs-lookup"><span data-stu-id="ae062-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="ae062-129">**アクセスの傾向** - アクセス試行回数の変更</span><span class="sxs-lookup"><span data-stu-id="ae062-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="ae062-130">**脅威カテゴリ** - Web 脅威の種類</span><span class="sxs-lookup"><span data-stu-id="ae062-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="ae062-131">**デバイス** - アクセス試行を行うデバイスの数</span><span class="sxs-lookup"><span data-stu-id="ae062-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="ae062-132">ドメインを選択して、そのドメイン内の URL にアクセスしようとしたデバイスの一覧と URL の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae062-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae062-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae062-133">Related topics</span></span>

- [<span data-ttu-id="ae062-134">Web 保護の概要</span><span class="sxs-lookup"><span data-stu-id="ae062-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="ae062-135">Web コンテンツ フィルタリング</span><span class="sxs-lookup"><span data-stu-id="ae062-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="ae062-136">Web の脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="ae062-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="ae062-137">Web の脅威への対応</span><span class="sxs-lookup"><span data-stu-id="ae062-137">Respond to web threats</span></span>](web-protection-response.md)
