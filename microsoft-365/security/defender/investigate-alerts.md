---
title: Microsoft 365 Defender でアラートを調査する
description: デバイス、ユーザー、メールボックス間で表示されるアラートを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500944"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="084c2-104">Microsoft 365 Defender でアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="084c2-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="084c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="084c2-105">**Applies to:**</span></span>
- <span data-ttu-id="084c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="084c2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="084c2-107">アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="084c2-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="084c2-108">アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="084c2-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="084c2-109">Microsoft 365 Defender では、関連するアラートがまとめて集計され、インシデントが発生します。</span><span class="sxs-lookup"><span data-stu-id="084c2-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="084c2-110">インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの調査は、より深い分析が必要な場合に有用です。</span><span class="sxs-lookup"><span data-stu-id="084c2-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="084c2-111">調査でのアラート ページの使用</span><span class="sxs-lookup"><span data-stu-id="084c2-111">Using alert pages in investigations</span></span>

<span data-ttu-id="084c2-112">インシデント ページの [アラート] タブで、アラートを選択すると、個々のアラート ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="084c2-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="084c2-113">アラート ページは、影響を受けるアセット、アラート ストーリー、詳細ウィンドウの 3 つのセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![アラート ページの例のイメージ](../../media/new-alert-page2.png)

<span data-ttu-id="084c2-115">アラート ページ全体で、任意のエンティティの横にある 3 ドット アイコン (**...**) を選択すると、特定のアセット ページを開く、または特定の修復手順を実行するなど、使用可能なアクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="084c2-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="084c2-116">影響を受けるアセットを分析する</span><span class="sxs-lookup"><span data-stu-id="084c2-116">Analyze affected assets</span></span>
<span data-ttu-id="084c2-117">[影響を受ける資産] セクションには、このアラートの影響を受けるメールボックス、デバイス、およびユーザーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="084c2-118">任意のアセット カードを選択すると、詳細サイド ウィンドウに、アセットに関連して発生したその他のアラートを含む情報が入力されます (それがある場合)。</span><span class="sxs-lookup"><span data-stu-id="084c2-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="084c2-119">アラート ストーリー内のアラートの役割を追跡する</span><span class="sxs-lookup"><span data-stu-id="084c2-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="084c2-120">アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。</span><span class="sxs-lookup"><span data-stu-id="084c2-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="084c2-121">タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。</span><span class="sxs-lookup"><span data-stu-id="084c2-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="084c2-122">アラート ストーリー内のアセットは展開可能でクリック可能です。</span><span class="sxs-lookup"><span data-stu-id="084c2-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="084c2-123">アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。</span><span class="sxs-lookup"><span data-stu-id="084c2-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="084c2-124">[アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="084c2-125">詳細ウィンドウでアラートの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="084c2-125">View more alert information in the details pane</span></span>

<span data-ttu-id="084c2-126">詳細ウィンドウには、最初に選択したアラートの詳細が表示され、詳細とアクションが関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="084c2-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="084c2-127">アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ウィンドウが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="084c2-128">目的のエンティティを選択すると、詳細ウィンドウが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="084c2-129">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="084c2-129">Manage alerts</span></span>

<span data-ttu-id="084c2-130">アラートの調査が完了したら、開始したアラートに戻り、アラートの状態を [解決済み] としてマークし、False アラートまたは True アラートとして分類できます。</span><span class="sxs-lookup"><span data-stu-id="084c2-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="084c2-131">アラートを分類すると、製品を調整して、より真のアラートと誤ったアラートを減らします。</span><span class="sxs-lookup"><span data-stu-id="084c2-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="084c2-132">タグを使用してアラートを管理する方法の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="084c2-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="084c2-133">段階的に展開され、現在プレビュー中Office 365 の Microsoft Defender のタグ付け機能。</span><span class="sxs-lookup"><span data-stu-id="084c2-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="084c2-134">現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="084c2-135">変更前に生成されたアラートには、更新されたタグ名は反映されません。</span><span class="sxs-lookup"><span data-stu-id="084c2-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="084c2-136">統合アラート キューの管理</span><span class="sxs-lookup"><span data-stu-id="084c2-136">Manage the unified alert queue</span></span>

<span data-ttu-id="084c2-137">Microsoft 365 セキュリティ センター ナビゲーション ウィンドウ& [インシデントと警告] の下で [通知] を選択すると、統合アラート キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="084c2-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="084c2-138">このセクションには、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft 365 Defender など、さまざまな Microsoft セキュリティ ソリューションからの通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![サンプルアラート ページのイメージ](../../media/unified-alert-queue.png)

<span data-ttu-id="084c2-140">アラート キューには、ネットワークでフラグが設定されたアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="084c2-141">既定では、キューには過去 30 日間に表示されたアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="084c2-142">リストの上部に最新のアラートが表示され、最初に最新のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="084c2-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="084c2-143">起動時に、統合アラート キューには、利用可能な 365 件のアラートに対Office 7 日分しか含められません。</span><span class="sxs-lookup"><span data-stu-id="084c2-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="084c2-144">キューは、時間の長い間、ビルドを続行します。</span><span class="sxs-lookup"><span data-stu-id="084c2-144">The queue will continue to build over time.</span></span> <span data-ttu-id="084c2-145">統合アラート キューを起動する前にアラートをトリアージする必要がある場合は、セキュリティとコンプライアンス センターのアラート キュー [を使用します](https://protection.office.com/viewalerts)。</span><span class="sxs-lookup"><span data-stu-id="084c2-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="084c2-146">上部のナビゲーションでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="084c2-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="084c2-147">フィルターの適用</span><span class="sxs-lookup"><span data-stu-id="084c2-147">Apply filters</span></span>
- <span data-ttu-id="084c2-148">列をカスタマイズして列を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="084c2-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="084c2-149">データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="084c2-149">Export data</span></span>

<span data-ttu-id="084c2-150">また、さまざまな条件に従ってアラートをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="084c2-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="084c2-151">重要度</span><span class="sxs-lookup"><span data-stu-id="084c2-151">Severity</span></span>
- <span data-ttu-id="084c2-152">状態</span><span class="sxs-lookup"><span data-stu-id="084c2-152">Status</span></span>
- <span data-ttu-id="084c2-153">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="084c2-153">Category</span></span>
- <span data-ttu-id="084c2-154">検出ソース</span><span class="sxs-lookup"><span data-stu-id="084c2-154">Detection source</span></span>
- <span data-ttu-id="084c2-155">ポリシー</span><span class="sxs-lookup"><span data-stu-id="084c2-155">Policy</span></span>
- <span data-ttu-id="084c2-156">影響を受け取ったアセット</span><span class="sxs-lookup"><span data-stu-id="084c2-156">Impacted assets</span></span>
- <span data-ttu-id="084c2-157">最初のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="084c2-157">First activity</span></span>
- <span data-ttu-id="084c2-158">[最後のアクティビティ]</span><span class="sxs-lookup"><span data-stu-id="084c2-158">Last activity</span></span>


<span data-ttu-id="084c2-159">インシデントの調査を開始するには[、「Microsoft 365 Defender](investigate-incidents.md)でインシデントを調査する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="084c2-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="084c2-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="084c2-160">See also</span></span>

- [<span data-ttu-id="084c2-161">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="084c2-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="084c2-162">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="084c2-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="084c2-163">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="084c2-163">Manage incidents</span></span>](manage-incidents.md)
