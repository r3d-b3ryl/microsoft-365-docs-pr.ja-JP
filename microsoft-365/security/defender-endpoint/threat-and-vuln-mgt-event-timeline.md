---
title: イベントタイムライン (脅威と脆弱性の管理
description: イベントタイムラインは、リスクが組織に導入される方法と、リスクを軽減するために発生した軽減策を解釈するのに役立つリスクニュースフィードです。
keywords: イベント タイムライン, Microsoft Defender for Endpoint イベント タイムライン, Microsoft Defender for Endpoint tvm イベント タイムライン, 脅威と脆弱性の管理, Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933483"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="50ece-104">イベントタイムライン - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="50ece-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50ece-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="50ece-105">**Applies to:**</span></span>
- [<span data-ttu-id="50ece-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="50ece-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="50ece-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50ece-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="50ece-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="50ece-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50ece-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="50ece-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="50ece-110">イベントタイムラインは、新しい脆弱性や悪用を通じて組織にリスクがどのように導入されるのかを解釈するのに役立つリスクニュースフィードです。</span><span class="sxs-lookup"><span data-stu-id="50ece-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="50ece-111">組織のリスクに影響を与える可能性があるイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="50ece-112">たとえば、導入された新しい脆弱性、悪用可能になった脆弱性、エクスプロイト キットに追加された悪用などがあります。</span><span class="sxs-lookup"><span data-stu-id="50ece-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="50ece-113">イベント タイムラインには、露出スコアと[](tvm-exposure-score.md)Microsoft [Secure Score for Devices](tvm-microsoft-secure-score-devices.md)のストーリーも示され、大きな変更の原因を特定できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="50ece-114">イベントは、デバイスまたはデバイスのスコアに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50ece-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="50ece-115">優先順位付けされたセキュリティ推奨事項に基づいて修復する必要があるものに対処することで、露出 [を減らします](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="50ece-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="50ece-116">新しい脆弱性イベントに関する電子メールを取得するには [、「Configure vulnerability email notifications in Microsoft Defender for Endpoint」を参照してください。](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="50ece-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="50ece-117">[イベント タイムライン] ページに移動する</span><span class="sxs-lookup"><span data-stu-id="50ece-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="50ece-118">また、ダッシュボードから 3 つの[脅威と脆弱性の管理があります](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="50ece-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="50ece-119">**組織の露出スコア カード**: [時間の間の露出スコア] グラフのイベント ドットにカーソルを合わせると、[この日のすべてのイベントを表示する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ece-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="50ece-120">このイベントは、ソフトウェアの脆弱性を表します。</span><span class="sxs-lookup"><span data-stu-id="50ece-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="50ece-121">**デバイスの Microsoft Secure Score**: [デバイスの時間のスコア] グラフのイベント ドットにカーソルを合わせると、[この日のすべてのイベントを表示する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ece-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="50ece-122">イベントは、新しい構成評価を表します。</span><span class="sxs-lookup"><span data-stu-id="50ece-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="50ece-123">**トップ イベント カード**: トップ イベント テーブルの下部にある [詳細を表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ece-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="50ece-124">カードには、過去 7 日間の 3 つの最も影響の大きなイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="50ece-125">影響を受けるイベントには、イベントが多数のデバイスに影響を与える場合、または重大な脆弱性が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="50ece-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="50ece-126">デバイスの露出スコアと Microsoft Secure Score のグラフ</span><span class="sxs-lookup"><span data-stu-id="50ece-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="50ece-127">このダッシュボード脅威と脆弱性の管理[露出スコア] グラフにカーソルを合わせると、デバイスに影響を与えたその日のソフトウェアの脆弱性の上位イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="50ece-128">Microsoft Secure Score for Devices グラフにカーソルを合わせると、スコアに影響する新しいセキュリティ構成評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="50ece-129">デバイスやデバイスのスコアに影響するイベントがない場合は、何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="50ece-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="50ece-130">![露出スコアホバー ](images/tvm-event-timeline-exposure-score350.png) 
 ![ Microsoft Secure Score for Devices ホバー](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="50ece-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="50ece-131">その日のイベントにドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="50ece-131">Drill down to events from that day</span></span>

<span data-ttu-id="50ece-132">[この **日のすべてのイベントを表示** する] を選択すると、その日のカスタム日付範囲を持つ [イベント タイムライン] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="50ece-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![イベント タイムラインで選択されたカスタム日付範囲](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="50ece-134">[ **カスタム範囲] を** 選択して、日付範囲を別のカスタム範囲または事前設定された時間範囲に変更します。</span><span class="sxs-lookup"><span data-stu-id="50ece-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![イベント タイムラインの日付範囲のオプション](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="50ece-136">イベント タイムラインの概要</span><span class="sxs-lookup"><span data-stu-id="50ece-136">Event timeline overview</span></span>

<span data-ttu-id="50ece-137">[イベント タイムライン] ページで、イベントに関連する必要なすべての情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="50ece-138">機能: </span><span class="sxs-lookup"><span data-stu-id="50ece-138">Features:</span></span>

- <span data-ttu-id="50ece-139">列のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="50ece-139">Customize columns</span></span>
- <span data-ttu-id="50ece-140">イベントの種類または影響を受け取ったデバイスの割合でフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="50ece-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="50ece-141">ページごとに 30、50、または 100 アイテムを表示する</span><span class="sxs-lookup"><span data-stu-id="50ece-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="50ece-142">ページの上部にある 2 つの大きな数字は、イベントではなく、新しい脆弱性と悪用可能な脆弱性の数を示しています。</span><span class="sxs-lookup"><span data-stu-id="50ece-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="50ece-143">一部のイベントには複数の脆弱性が存在する可能性があります。また、一部の脆弱性には複数のイベントが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50ece-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![イベント タイムライン ページ](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="50ece-145">Columns</span><span class="sxs-lookup"><span data-stu-id="50ece-145">Columns</span></span>

- <span data-ttu-id="50ece-146">**日付**: 月、日、年</span><span class="sxs-lookup"><span data-stu-id="50ece-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="50ece-147">**イベント**: 影響を受けのあるイベント (コンポーネント、種類、影響を受け取ったデバイスの数を含む)</span><span class="sxs-lookup"><span data-stu-id="50ece-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="50ece-148">**関連コンポーネント**: ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="50ece-148">**Related component**: software</span></span>
- <span data-ttu-id="50ece-149">**もともと影響を受け取** ったデバイス : このイベントが最初に発生した場合の、影響を受け取ったデバイスの数と割合です。</span><span class="sxs-lookup"><span data-stu-id="50ece-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="50ece-150">また、最初に影響を受け取ったデバイスの割合を、デバイスの総数からフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="50ece-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="50ece-151">**現在影響を受けるデバイス**: このイベントが現在影響しているデバイスの現在の数と割合。</span><span class="sxs-lookup"><span data-stu-id="50ece-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="50ece-152">[列のカスタマイズ] を選択すると、このフィールド **を検索できます**。</span><span class="sxs-lookup"><span data-stu-id="50ece-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="50ece-153">**種類**: スコアに影響を与えるタイムスタンプ付きイベントを反映します。</span><span class="sxs-lookup"><span data-stu-id="50ece-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="50ece-154">フィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-154">They can be filtered.</span></span>
    - <span data-ttu-id="50ece-155">エクスプロイト キットに追加されたエクスプロイト</span><span class="sxs-lookup"><span data-stu-id="50ece-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="50ece-156">エクスプロイトが検証されました</span><span class="sxs-lookup"><span data-stu-id="50ece-156">Exploit was verified</span></span>
    - <span data-ttu-id="50ece-157">新しいパブリックエクスプロイト</span><span class="sxs-lookup"><span data-stu-id="50ece-157">New public exploit</span></span>
    - <span data-ttu-id="50ece-158">新しい脆弱性</span><span class="sxs-lookup"><span data-stu-id="50ece-158">New vulnerability</span></span>
    - <span data-ttu-id="50ece-159">新しい構成評価</span><span class="sxs-lookup"><span data-stu-id="50ece-159">New configuration assessment</span></span>
- <span data-ttu-id="50ece-160">**スコアの傾向**: 露出スコアの傾向</span><span class="sxs-lookup"><span data-stu-id="50ece-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="50ece-161">アイコン</span><span class="sxs-lookup"><span data-stu-id="50ece-161">Icons</span></span>

<span data-ttu-id="50ece-162">イベントの横に次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-162">The following icons show up next to events:</span></span>

- ![バグ アイコン](images/tvm-black-bug-icon.png) <span data-ttu-id="50ece-164">新しいパブリックエクスプロイト</span><span class="sxs-lookup"><span data-stu-id="50ece-164">New public exploit</span></span>
- ![レポートの警告アイコン](images/report-warning-icon.png) <span data-ttu-id="50ece-166">新しい脆弱性が公開されました</span><span class="sxs-lookup"><span data-stu-id="50ece-166">New vulnerability was published</span></span>
- ![エクスプロイト キット](images/bug-lightning-icon2.png) <span data-ttu-id="50ece-168">エクスプロイト キットで見つかったエクスプロイト</span><span class="sxs-lookup"><span data-stu-id="50ece-168">Exploit found in exploit kit</span></span>
- ![警告アイコン付きバグ アイコン](images/bug-caution-icon2.png) <span data-ttu-id="50ece-170">エクスプロイトの検証</span><span class="sxs-lookup"><span data-stu-id="50ece-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="50ece-171">特定のイベントにドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="50ece-171">Drill down to a specific event</span></span>

<span data-ttu-id="50ece-172">イベントを選択すると、デバイスに影響を与える詳細と現在の CVEs の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="50ece-173">より多くの CVEs を表示するか、関連する推奨事項を表示できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="50ece-174">[スコアの傾向] の下の矢印は、このイベントが組織の露出スコアを上げたり下げたりする可能性があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50ece-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="50ece-175">露出スコアが高いほど、デバイスは悪用に対してより脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="50ece-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![イベント タイムラインのフライアウト](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="50ece-177">そこから、[関連する **セキュリティの推奨事項** に移動] を選択し、[セキュリティの推奨事項] ページで、新しいソフトウェアの脆弱性に関する推奨事項 [を表示します](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="50ece-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="50ece-178">セキュリティ推奨事項の説明と脆弱性の詳細を確認した後、修復要求を送信し、修復ページで要求を [追跡できます](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="50ece-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="50ece-179">ソフトウェア ページでイベントのタイムラインを表示する</span><span class="sxs-lookup"><span data-stu-id="50ece-179">View Event timelines in software pages</span></span>

<span data-ttu-id="50ece-180">ソフトウェア ページを開く場合は、イベント > を選択し、フライアウトの 「関連コンポーネント」というセクションでハイパーリンクされたソフトウェア名 (Visual Studio 2017 など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="50ece-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="50ece-181">ソフトウェア ページの詳細</span><span class="sxs-lookup"><span data-stu-id="50ece-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="50ece-182">特定のソフトウェアのすべての詳細が表示された完全なページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="50ece-183">グラフの上にマウスを移動すると、その特定のソフトウェアのイベントのタイムラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50ece-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![イベント タイムライン グラフを含むソフトウェア ページ](images/tvm-event-timeline-software2.png)

<span data-ttu-id="50ece-185">[イベント タイムライン] タブに移動して、そのソフトウェアに関連付けられたすべてのイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="50ece-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="50ece-186">セキュリティに関する推奨事項、検出された脆弱性、インストールされているデバイス、バージョンの配布も確認できます。</span><span class="sxs-lookup"><span data-stu-id="50ece-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![[イベント タイムライン] タブを含むソフトウェア ページ](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="50ece-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="50ece-188">Related topics</span></span>

- [<span data-ttu-id="50ece-189">脅威と脆弱性の管理概要</span><span class="sxs-lookup"><span data-stu-id="50ece-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="50ece-190">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="50ece-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="50ece-191">暴露スコア</span><span class="sxs-lookup"><span data-stu-id="50ece-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="50ece-192">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="50ece-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="50ece-193">脆弱性を修復する</span><span class="sxs-lookup"><span data-stu-id="50ece-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="50ece-194">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="50ece-194">Software inventory</span></span>](tvm-software-inventory.md)

