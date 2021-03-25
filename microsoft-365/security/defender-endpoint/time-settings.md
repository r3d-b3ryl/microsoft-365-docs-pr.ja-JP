---
title: Microsoft Defender セキュリティ センターのタイム ゾーン設定
description: ここに示す情報を使用して、Microsoft Defender セキュリティ センターのタイム ゾーン設定を構成し、ライセンス情報を表示します。
keywords: 設定, Microsoft Defender, サイバーセキュリティ脅威インテリジェンス, 高度な脅威保護, タイム ゾーン, utc, 現地時間, ライセンス
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c6338155aae3605ac5721958363b8c2d86618d9b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183851"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a><span data-ttu-id="0d0af-104">Microsoft Defender セキュリティ センターのタイム ゾーン設定</span><span class="sxs-lookup"><span data-stu-id="0d0af-104">Microsoft Defender Security Center time zone settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0d0af-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0d0af-105">**Applies to:**</span></span>
- [<span data-ttu-id="0d0af-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0d0af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0d0af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d0af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)




><span data-ttu-id="0d0af-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="0d0af-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0d0af-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="0d0af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

<span data-ttu-id="0d0af-110">[タイム ゾーン **] メニュー** の [タイム ゾーン設定] アイコン 1 を使用して、タイム ゾーンを構成し、ライセンス ![ ](images/atp-time-zone.png) 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-110">Use the **Time zone** menu ![Time zone settings icon1](images/atp-time-zone.png) to configure the time zone and view license information.</span></span>

## <a name="time-zone-settings"></a><span data-ttu-id="0d0af-111">タイム ゾーンの設定</span><span class="sxs-lookup"><span data-stu-id="0d0af-111">Time zone settings</span></span>
<span data-ttu-id="0d0af-112">時間の側面は、知覚されたサイバー攻撃と実際のサイバー攻撃の評価と分析において重要です。</span><span class="sxs-lookup"><span data-stu-id="0d0af-112">The aspect of time is important in the assessment and analysis of perceived and actual cyberattacks.</span></span>

<span data-ttu-id="0d0af-113">Cyberforensic の調査では、多くの場合、タイム スタンプを使用して一連のイベントをまとめます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-113">Cyberforensic investigations often rely on time stamps to piece together the sequence of events.</span></span> <span data-ttu-id="0d0af-114">システムが正しいタイム ゾーン設定を反映することが重要です。</span><span class="sxs-lookup"><span data-stu-id="0d0af-114">It’s important that your system reflects the correct time zone settings.</span></span>

<span data-ttu-id="0d0af-115">Microsoft Defender for Endpoint では、協定世界時 (UTC) または現地時間を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-115">Microsoft Defender for Endpoint can display either Coordinated Universal Time (UTC) or local time.</span></span>

<span data-ttu-id="0d0af-116">現在のタイム ゾーン設定は、[エンドポイント用 Microsoft Defender] メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-116">Your current time zone setting is shown in the Microsoft Defender for Endpoint menu.</span></span> <span data-ttu-id="0d0af-117">表示されるタイム ゾーンは、[タイム ゾーン] メニュー **で変更** できます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-117">You can change the displayed time zone in the **Time zone** menu.</span></span>

![タイム ゾーン設定アイコン2](images/atp-time-zone-menu.png)<span data-ttu-id="0d0af-119">.</span><span class="sxs-lookup"><span data-stu-id="0d0af-119">.</span></span>

### <a name="utc-time-zone"></a><span data-ttu-id="0d0af-120">UTC タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="0d0af-120">UTC time zone</span></span>
<span data-ttu-id="0d0af-121">Microsoft Defender for Endpoint では、既定で UTC 時間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-121">Microsoft Defender for Endpoint uses UTC time by default.</span></span>

<span data-ttu-id="0d0af-122">Microsoft Defender for Endpoint タイム ゾーンを UTC に設定すると、すべてのユーザーのシステム タイムスタンプ (アラート、イベントなど) が UTC で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-122">Setting the Microsoft Defender for Endpoint time zone to UTC will display all system timestamps (alerts, events, and others) in UTC for all users.</span></span> <span data-ttu-id="0d0af-123">これにより、世界中の異なる場所で作業しているセキュリティ アナリストが、イベントの調査中に同じタイム スタンプを使用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-123">This can help security analysts working in different locations across the globe to use the same time stamps while investigating events.</span></span>

### <a name="local-time-zone"></a><span data-ttu-id="0d0af-124">ローカル タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="0d0af-124">Local time zone</span></span>
<span data-ttu-id="0d0af-125">Microsoft Defender for Endpoint でローカル タイム ゾーン設定を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-125">You can choose to have Microsoft Defender for Endpoint use local time zone settings.</span></span> <span data-ttu-id="0d0af-126">すべてのアラートとイベントは、ローカル タイム ゾーンを使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-126">All alerts and events will be displayed using your local time zone.</span></span>

<span data-ttu-id="0d0af-127">ローカル タイム ゾーンは、デバイスの地域設定から取られます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-127">The local time zone is taken from your device’s regional settings.</span></span> <span data-ttu-id="0d0af-128">地域設定を変更すると、Microsoft Defender for Endpoint タイム ゾーンも変更されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-128">If you change your regional settings, the Microsoft Defender for Endpoint time zone will also change.</span></span> <span data-ttu-id="0d0af-129">この設定を選択すると、Microsoft Defender for Endpoint に表示されるタイムスタンプは、すべての Microsoft Defender for Endpoint ユーザーの現地時間に合わせて配置されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-129">Choosing this setting means that the timestamps displayed in Microsoft Defender for Endpoint will be aligned to local time for all Microsoft Defender for Endpoint users.</span></span> <span data-ttu-id="0d0af-130">さまざまなグローバルな場所にあるアナリストに、地域の設定に従って Microsoft Defender for Endpoint アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-130">Analysts located in different global locations will now see the Microsoft Defender for Endpoint alerts according to their regional settings.</span></span>

<span data-ttu-id="0d0af-131">アナリストが 1 つの場所にある場合は、現地時間の使用を選択すると便利です。</span><span class="sxs-lookup"><span data-stu-id="0d0af-131">Choosing to use local time can be useful if the analysts are located in a single location.</span></span> <span data-ttu-id="0d0af-132">この場合、ローカル ユーザーが不審なメール リンクをクリックした場合など、イベントをローカル時間に関連付ける方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d0af-132">In this case it might be easier to correlate events to local time, for example – when a local user clicked on a suspicious email link.</span></span>

### <a name="set-the-time-zone"></a><span data-ttu-id="0d0af-133">タイム ゾーンの設定</span><span class="sxs-lookup"><span data-stu-id="0d0af-133">Set the time zone</span></span>
<span data-ttu-id="0d0af-134">Microsoft Defender for Endpoint タイム ゾーンは、既定では UTC に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0d0af-134">The Microsoft Defender for Endpoint time zone is set by default to UTC.</span></span>
<span data-ttu-id="0d0af-135">タイム ゾーンを設定すると、すべての Microsoft Defender for Endpoint ビューの時間も変更されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-135">Setting the time zone also changes the times for all Microsoft Defender for Endpoint views.</span></span>
<span data-ttu-id="0d0af-136">タイム ゾーンを設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-136">To set the time zone:</span></span>

1. <span data-ttu-id="0d0af-137">[タイム ゾーン **] メニューの** ![ [タイム ゾーン設定] アイコン 3 をクリックします ](images/atp-time-zone.png) 。</span><span class="sxs-lookup"><span data-stu-id="0d0af-137">Click the **Time zone** menu ![Time zone settings icon3](images/atp-time-zone.png).</span></span>
2. <span data-ttu-id="0d0af-138">タイム ゾーン **UTC インジケーターを選択** します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-138">Select the **Timezone UTC** indicator.</span></span>
3. <span data-ttu-id="0d0af-139">[ **タイム ゾーン UTC]** またはローカル タイム ゾーン (-7:00 など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-139">Select **Timezone UTC** or your local time zone, for example -7:00.</span></span>

### <a name="regional-settings"></a><span data-ttu-id="0d0af-140">地域の設定</span><span class="sxs-lookup"><span data-stu-id="0d0af-140">Regional settings</span></span>
<span data-ttu-id="0d0af-141">Microsoft Defender for Endpoint に異なる日付形式を適用するには、Microsoft Defender (IE) と Microsoft Edge (Edge) の地域Internet Explorer設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-141">To apply different date formats for Microsoft Defender for Endpoint, use regional settings for Internet Explorer (IE) and Microsoft Edge (Edge).</span></span> <span data-ttu-id="0d0af-142">Google Chrome などの別のブラウザーを使用している場合は、必要な手順に従って、そのブラウザーの時刻と日付の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-142">If you're using another browser such as Google Chrome, follow the required steps to change the time and date settings for that browser.</span></span> 


<span data-ttu-id="0d0af-143">**Internet Explorer (IE) と Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="0d0af-143">**Internet Explorer (IE) and Microsoft Edge**</span></span>

<span data-ttu-id="0d0af-144">IE と Microsoft Edge では、コントロール **パネルの** [時計、言語、地域] オプションで構成された **地域** 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-144">IE and Microsoft Edge use the **Region** settings configured in the **Clocks, Language, and Region** option in the Control panel.</span></span> 


#### <a name="known-issues-with-regional-formats"></a><span data-ttu-id="0d0af-145">地域の形式に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="0d0af-145">Known issues with regional formats</span></span>

<span data-ttu-id="0d0af-146">**日付と時刻の形式**</span><span class="sxs-lookup"><span data-stu-id="0d0af-146">**Date and time formats**</span></span><br>
<span data-ttu-id="0d0af-147">時刻と日付の形式にはいくつかの既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="0d0af-147">There are some known issues with the time and date formats.</span></span> <span data-ttu-id="0d0af-148">サポートされている形式以外の地域設定を構成すると、ポータルが設定を正しく反映しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d0af-148">If you configure your regional settings to anything other than the supported formats, the portal may not correctly reflect your settings.</span></span>

<span data-ttu-id="0d0af-149">次の日付と時刻の形式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d0af-149">The following date and time formats are supported:</span></span>
- <span data-ttu-id="0d0af-150">日付形式 MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="0d0af-150">Date format MM/dd/yyyy</span></span>
- <span data-ttu-id="0d0af-151">日付形式 dd/MM/yyyyy</span><span class="sxs-lookup"><span data-stu-id="0d0af-151">Date format dd/MM/yyyy</span></span>
- <span data-ttu-id="0d0af-152">時間形式 hh:mm:ss (12 時間形式)</span><span class="sxs-lookup"><span data-stu-id="0d0af-152">Time format hh:mm:ss (12 hour format)</span></span>

<span data-ttu-id="0d0af-153">現在、次の日付と時刻の形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0af-153">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="0d0af-154">日付形式 yyyy-MM-dd</span><span class="sxs-lookup"><span data-stu-id="0d0af-154">Date format yyyy-MM-dd</span></span>
- <span data-ttu-id="0d0af-155">日付形式 dd-MMM-yyy</span><span class="sxs-lookup"><span data-stu-id="0d0af-155">Date format dd-MMM-yy</span></span>
- <span data-ttu-id="0d0af-156">日付形式 dd/MM/yyy</span><span class="sxs-lookup"><span data-stu-id="0d0af-156">Date format dd/MM/yy</span></span>
- <span data-ttu-id="0d0af-157">日付形式 MM/dd/yy</span><span class="sxs-lookup"><span data-stu-id="0d0af-157">Date format MM/dd/yy</span></span>
- <span data-ttu-id="0d0af-158">yy の日付形式。</span><span class="sxs-lookup"><span data-stu-id="0d0af-158">Date format with yy.</span></span> <span data-ttu-id="0d0af-159">yyyy のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="0d0af-159">Will only show yyyy.</span></span>
- <span data-ttu-id="0d0af-160">時間形式 HH:mm:ss (24 時間形式)</span><span class="sxs-lookup"><span data-stu-id="0d0af-160">Time format HH:mm:ss (24 hour format)</span></span>

<span data-ttu-id="0d0af-161">**数値で使用される 10 進記号**</span><span class="sxs-lookup"><span data-stu-id="0d0af-161">**Decimal symbol used in numbers**</span></span><br>
<span data-ttu-id="0d0af-162">使用される 10 進記号は、地域設定の Numbers形式設定でコンマが選択されている場合でも、常に **ドット** です。</span><span class="sxs-lookup"><span data-stu-id="0d0af-162">Decimal symbol used is always a dot, even if a comma is selected in  the **Numbers** format settings in **Region** settings.</span></span> <span data-ttu-id="0d0af-163">たとえば、15,5K は 15.5K と表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0af-163">For example, 15,5K is displayed as 15.5K.</span></span>


