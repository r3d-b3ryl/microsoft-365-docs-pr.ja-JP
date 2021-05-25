---
title: Defender でアラートをMicrosoft 365する
description: デバイス、ユーザー、メールボックス間で表示されるアラートを調査します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651353"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="c2d89-104">Defender でアラートをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="c2d89-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c2d89-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c2d89-105">**Applies to:**</span></span>
- <span data-ttu-id="c2d89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2d89-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c2d89-107">アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="c2d89-108">アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="c2d89-109">Defender Microsoft 365関連するアラートは、インシデントを形成するために[まとめて集計されます](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="c2d89-110">インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの分析は、より深い分析が必要な場合に有用です。</span><span class="sxs-lookup"><span data-stu-id="c2d89-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="c2d89-111">アラート **キューには、** 現在の一連のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="c2d89-112">[インシデント] からアラートキューにアクセスし&>セキュリティ センター (security.microsoft.com) のMicrosoft 365アラートを[security.microsoft.com。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c2d89-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="アラート キューの例":::

<span data-ttu-id="c2d89-114">Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Defender など、さまざまな Microsoft Microsoft 365からの通知がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="c2d89-115">既定では、セキュリティ センターのMicrosoft 365キューには、過去 30 日間の新しいアラートと進行中のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="c2d89-116">最新のアラートはリストの一番上に表示されます。最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="c2d89-117">既定のアラート キューから [フィルター] を選択 **すると、[** フィルター] ウィンドウが表示され、そこからアラートのサブセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="c2d89-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="アラート キューのフィルター ウィンドウの例":::

<span data-ttu-id="c2d89-120">次の条件に従ってアラートをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="c2d89-121">重要度</span><span class="sxs-lookup"><span data-stu-id="c2d89-121">Severity</span></span>
- <span data-ttu-id="c2d89-122">状態</span><span class="sxs-lookup"><span data-stu-id="c2d89-122">Status</span></span>
- <span data-ttu-id="c2d89-123">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c2d89-123">Category</span></span>
- <span data-ttu-id="c2d89-124">検出ソース</span><span class="sxs-lookup"><span data-stu-id="c2d89-124">Detection source</span></span>
- <span data-ttu-id="c2d89-125">タグ</span><span class="sxs-lookup"><span data-stu-id="c2d89-125">Tags</span></span>
- <span data-ttu-id="c2d89-126">ポリシー</span><span class="sxs-lookup"><span data-stu-id="c2d89-126">Policy</span></span>
- <span data-ttu-id="c2d89-127">影響を受け取ったアセット</span><span class="sxs-lookup"><span data-stu-id="c2d89-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="c2d89-128">アラートの分析</span><span class="sxs-lookup"><span data-stu-id="c2d89-128">Analyze an alert</span></span>

<span data-ttu-id="c2d89-129">メインのアラート ページを表示するには、アラートの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="c2d89-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="セキュリティ センターのアラートの詳細ページMicrosoft 365例":::

<span data-ttu-id="c2d89-132">[警告の管理] ウィンドウ **から [メインのアラート ページを開** く] **アクションを選択** することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="c2d89-133">アラート ページは、次のセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="c2d89-134">アラート ストーリー(このアラートに関連するイベントとアラートの連鎖を時系列順に示す)</span><span class="sxs-lookup"><span data-stu-id="c2d89-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="c2d89-135">概要の詳細</span><span class="sxs-lookup"><span data-stu-id="c2d89-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="セキュリティ センターのアラートの詳細ページMicrosoft 365例":::

<span data-ttu-id="c2d89-137">アラート ページ全体で、任意のエンティティの横にある省略記号 (**...**) を選択して、アラート ページを開く、またはアラートを別のインシデントにリンクするなどの使用可能なアクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="c2d89-138">影響を受けるアセットを分析する</span><span class="sxs-lookup"><span data-stu-id="c2d89-138">Analyze affected assets</span></span>

<span data-ttu-id="c2d89-139">[ **実行されたアクション** ] セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受けるアセットの一覧があります。</span><span class="sxs-lookup"><span data-stu-id="c2d89-139">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="c2d89-140">[アクション センターで **表示] を選択して**、セキュリティ センターの [アクション センター] の [履歴] タブMicrosoft 365することもできます。 </span><span class="sxs-lookup"><span data-stu-id="c2d89-140">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="c2d89-141">アラート ストーリー内のアラートの役割を追跡する</span><span class="sxs-lookup"><span data-stu-id="c2d89-141">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="c2d89-142">アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-142">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="c2d89-143">タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。</span><span class="sxs-lookup"><span data-stu-id="c2d89-143">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="c2d89-144">アラート ストーリー内のアセットは展開可能でクリック可能です。</span><span class="sxs-lookup"><span data-stu-id="c2d89-144">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="c2d89-145">アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-145">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="c2d89-146">[アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-146">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="c2d89-147">詳細ページでアラートの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c2d89-147">View more alert information on the details page</span></span>

<span data-ttu-id="c2d89-148">[詳細] ページには、選択したアラートの詳細と、そのアラートに関連する詳細とアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-148">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="c2d89-149">アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-149">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="c2d89-150">目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-150">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="c2d89-151">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="c2d89-151">Manage alerts</span></span>

<span data-ttu-id="c2d89-152">アラートを管理するには、その行のアラート キューでアラートを選択して、[警告の管理] **ウィンドウを表示** します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-152">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="c2d89-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-153">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="アラートの概要ウィンドウの例":::

<span data-ttu-id="c2d89-155">[ **警告の管理]** ウィンドウでは、次の項目を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-155">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="c2d89-156">アラートの状態 (新規、解決済み、進行中)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-156">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="c2d89-157">アラートの分類 (設定されていない、True アラート、False Alert)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-157">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="c2d89-158">真のアラートとして分類する場合は、[決定] フィールドのアラートの脅威の種類 **を指定** します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-158">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="c2d89-159">アラートに関するコメント。</span><span class="sxs-lookup"><span data-stu-id="c2d89-159">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="c2d89-160">タグを使用してアラートを管理する方法の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="c2d89-160">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="c2d89-161">Microsoft Defender for microsoft Defender for Office 365段階的に展開中で、現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="c2d89-161">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="c2d89-162">現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-162">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="c2d89-163">変更前に生成されたアラートには、更新されたタグ名は反映されません。</span><span class="sxs-lookup"><span data-stu-id="c2d89-163">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="c2d89-164">このウィンドウから、次の追加アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-164">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="c2d89-165">メインアラート ページを開く</span><span class="sxs-lookup"><span data-stu-id="c2d89-165">Open the main alert page</span></span>
- <span data-ttu-id="c2d89-166">Microsoft 脅威の専門家に相談する</span><span class="sxs-lookup"><span data-stu-id="c2d89-166">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="c2d89-167">提出の表示</span><span class="sxs-lookup"><span data-stu-id="c2d89-167">View submission</span></span>
- <span data-ttu-id="c2d89-168">別のインシデントへのリンク</span><span class="sxs-lookup"><span data-stu-id="c2d89-168">Link to another incident</span></span>
- <span data-ttu-id="c2d89-169">タイムラインでアラートを表示する</span><span class="sxs-lookup"><span data-stu-id="c2d89-169">See the alert in a timeline</span></span>
- <span data-ttu-id="c2d89-170">抑制ルールの作成</span><span class="sxs-lookup"><span data-stu-id="c2d89-170">Create a suppression rule</span></span>

<span data-ttu-id="c2d89-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="セキュリティ センターのアラートに対するアクションMicrosoft 365例":::

<span data-ttu-id="c2d89-173">追加のアクションの一覧は、アラートの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c2d89-173">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="c2d89-174">アラートを解決する</span><span class="sxs-lookup"><span data-stu-id="c2d89-174">Resolve an alert</span></span>

<span data-ttu-id="c2d89-175">アラートの分析が完了し、解決したら、[アラートの管理] ウィンドウに移動し、その状態を [解決済み] としてマークし、False アラートまたは **True** アラートとして分類します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-175">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="c2d89-176">true アラートの場合は、[決定] フィールドにアラートの脅威の種類 **を指定** します。</span><span class="sxs-lookup"><span data-stu-id="c2d89-176">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="c2d89-177">アラートを分類し、その決定を指定すると、Defender Microsoft 365を調整して、より多くの真のアラートと少ない誤ったアラートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c2d89-177">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c2d89-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="c2d89-178">Next steps</span></span>

<span data-ttu-id="c2d89-179">インプロセス インシデントの必要に応じて、調査を続行 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d89-179">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d89-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d89-180">See also</span></span>

- [<span data-ttu-id="c2d89-181">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="c2d89-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c2d89-182">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="c2d89-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="c2d89-183">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="c2d89-183">Investigate incidents</span></span>](investigate-incidents.md)
