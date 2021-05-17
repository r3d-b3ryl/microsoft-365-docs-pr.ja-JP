---
title: Microsoft Defender for Endpoint ドメインの調査
description: 調査オプションを使用して、デバイスとサーバーが悪意のあるドメインと通信しているのを確認します。
keywords: ドメイン、ドメイン、悪意のあるドメイン、Microsoft Defender for Endpoint、アラート、URL を調査する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933471"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="bc954-104">Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="bc954-104">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bc954-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bc954-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc954-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bc954-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc954-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc954-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bc954-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bc954-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc954-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bc954-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

<span data-ttu-id="bc954-110">ドメインを調査して、エンタープライズ ネットワーク内のデバイスとサーバーが既知の悪意のあるドメインと通信しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc954-110">Investigate a domain to see if devices and servers in your enterprise network have been communicating with a known malicious domain.</span></span>

<span data-ttu-id="bc954-111">検索機能を使用するか、デバイス タイムラインからドメイン リンクをクリックして、ドメインを **調査できます**。</span><span class="sxs-lookup"><span data-stu-id="bc954-111">You can investigate a domain by using the search feature or by clicking on a domain link from the **Device timeline**.</span></span>

<span data-ttu-id="bc954-112">URL ビューでは、次のセクションから情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bc954-112">You can see information from the following sections in the URL view:</span></span>

- <span data-ttu-id="bc954-113">URL の詳細、連絡先、ネームサーバー</span><span class="sxs-lookup"><span data-stu-id="bc954-113">URL details, Contacts, Nameservers</span></span>
- <span data-ttu-id="bc954-114">この URL に関連するアラート</span><span class="sxs-lookup"><span data-stu-id="bc954-114">Alerts related to this URL</span></span> 
- <span data-ttu-id="bc954-115">組織内の URL</span><span class="sxs-lookup"><span data-stu-id="bc954-115">URL in organization</span></span>
- <span data-ttu-id="bc954-116">URL を含む最新の観測デバイス</span><span class="sxs-lookup"><span data-stu-id="bc954-116">Most recent observed devices with URL</span></span>

## <a name="url-worldwide"></a><span data-ttu-id="bc954-117">世界中の URL</span><span class="sxs-lookup"><span data-stu-id="bc954-117">URL worldwide</span></span>

<span data-ttu-id="bc954-118">[URL **Worldwide]** セクションには、URL、Whois の詳細情報へのリンク、関連する開いているインシデントの数、アクティブなアラートの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-118">The **URL Worldwide** section lists the URL, a link to further details at Whois, the number of related open incidents, and the number of active alerts.</span></span>

## <a name="incident"></a><span data-ttu-id="bc954-119">インシデント</span><span class="sxs-lookup"><span data-stu-id="bc954-119">Incident</span></span>

<span data-ttu-id="bc954-120">インシデント **カード** には、過去 180 日間のインシデントでアクティブなすべてのアラートの棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-120">The **Incident** card displays a bar chart of all active alerts in incidents over the past 180 days.</span></span>

## <a name="prevalence"></a><span data-ttu-id="bc954-121">有病率</span><span class="sxs-lookup"><span data-stu-id="bc954-121">Prevalence</span></span>

<span data-ttu-id="bc954-122">[ **有病率** ] カードは、指定した期間に組織内の URL の普及率に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc954-122">The **Prevalence** card provides details on the prevalence of the URL within the organization, over a specified period of time.</span></span>

<span data-ttu-id="bc954-123">既定の期間は過去 30 日間ですが、カードの隅にある下向きの矢印を選択して範囲をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bc954-123">Although the default time period is the past 30 days, you can customize the range by selecting the downward-pointing arrow in the corner of the card.</span></span> <span data-ttu-id="bc954-124">利用可能な最短の範囲は、過去 1 日の有病率の範囲ですが、最も長い範囲は過去 6 か月間です。</span><span class="sxs-lookup"><span data-stu-id="bc954-124">The shortest range available is for prevalence over the past day, while the longest range is over the past 6 months.</span></span>

## <a name="alerts"></a><span data-ttu-id="bc954-125">アラート</span><span class="sxs-lookup"><span data-stu-id="bc954-125">Alerts</span></span>

<span data-ttu-id="bc954-126">[ **アラート]** タブには、URL に関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-126">The **Alerts** tab provides a list of alerts that are associated with the URL.</span></span> <span data-ttu-id="bc954-127">次に示す表は、[アラート キュー] 画面に表示されるアラートのフィルター処理されたバージョンで、ドメインに関連付けられたアラート、重大度、状態、関連するインシデント、分類、調査状態などにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-127">The table shown here is a filtered version of the alerts visible on the Alert queue screen, showing only alerts associated with the domain, their severity, status, the associated incident, classification, investigation state, and more.</span></span>

<span data-ttu-id="bc954-128">[アラート] タブは、列ヘッダーの上にあるアクション メニューから[列のカスタマイズ] を選択して、多かれ少なかれ情報を表示するために調整できます。</span><span class="sxs-lookup"><span data-stu-id="bc954-128">The Alerts tab can be adjusted to show more or less information, by selecting **Customize columns** from the action menu above the column headers.</span></span> <span data-ttu-id="bc954-129">同じメニューでページごとにアイテムを選択することで、表示されるアイテムの **数を調整** することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc954-129">The number of items displayed can also be adjusted, by selecting **items per page** on the same menu.</span></span>

## <a name="observed-in-organization"></a><span data-ttu-id="bc954-130">組織内で観察される</span><span class="sxs-lookup"><span data-stu-id="bc954-130">Observed in organization</span></span>

<span data-ttu-id="bc954-131">[ **組織で観察]** タブには、URL で観察されたイベントと関連付けられたアラートに関する時系列ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-131">The **Observed in organization** tab provides a chronological view on the events and associated alerts that were observed on the URL.</span></span> <span data-ttu-id="bc954-132">このタブには、タイムラインと、時間、デバイス、発生した内容の簡単な説明など、イベントの詳細を示すカスタマイズ可能なテーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc954-132">This tab includes a timeline and a customizable table listing event details, such as the time, device, and a brief description of what happened.</span></span> 

<span data-ttu-id="bc954-133">テーブル ヘッダーの上のテキスト フィールドに日付を入力すると、異なる期間のイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="bc954-133">You can view events from different periods of time by entering the dates into the text fields above the table headers.</span></span> <span data-ttu-id="bc954-134">タイムラインの異なる領域を選択して、時間範囲をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bc954-134">You can also customize the time range by selecting different areas of the timeline.</span></span>

<span data-ttu-id="bc954-135">**ドメインを調査します。**</span><span class="sxs-lookup"><span data-stu-id="bc954-135">**Investigate a domain:**</span></span>

1. <span data-ttu-id="bc954-136">[検索] バーの **ドロップダウン メニューから** **[URL]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc954-136">Select **URL** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="bc954-137">[検索] フィールドに URL **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="bc954-137">Enter the URL in the **Search** field.</span></span>
3. <span data-ttu-id="bc954-138">検索アイコンをクリックするか、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="bc954-138">Click the search icon   or press **Enter**.</span></span> <span data-ttu-id="bc954-139">URL の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-139">Details about the URL are displayed.</span></span> <span data-ttu-id="bc954-140">注: 検索結果は、組織内のデバイスからの通信で観察された URL に対してのみ返されます。</span><span class="sxs-lookup"><span data-stu-id="bc954-140">Note: search results will only be returned for URLs observed in communications from devices in the organization.</span></span>
4. <span data-ttu-id="bc954-141">検索条件を定義するには、検索フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc954-141">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="bc954-142">タイムライン検索ボックスを使用して、URL との通信が観察された組織内のすべてのデバイス、通信に関連付けられたファイル、および観測された最後の日付の表示結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc954-142">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the URL, the file associated with the communication and the last date observed.</span></span>
5. <span data-ttu-id="bc954-143">デバイス名をクリックすると、そのデバイスのビューにアクセスし、報告されたアラート、動作、およびイベントを引き続き調査できます。</span><span class="sxs-lookup"><span data-stu-id="bc954-143">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc954-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc954-144">Related topics</span></span>
- [<span data-ttu-id="bc954-145">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="bc954-145">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="bc954-146">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="bc954-146">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="bc954-147">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="bc954-147">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="bc954-148">Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="bc954-148">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="bc954-149">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="bc954-149">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="bc954-150">Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="bc954-150">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="bc954-151">Microsoft Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="bc954-151">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
