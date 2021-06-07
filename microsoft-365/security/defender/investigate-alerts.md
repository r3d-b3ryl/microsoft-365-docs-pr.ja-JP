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
ms.openlocfilehash: a6e11aea14a7b8d99c0098b68951790328ec593e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782911"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="4a0ea-104">Defender でアラートをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4a0ea-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4a0ea-105">**Applies to:**</span></span>
- <span data-ttu-id="4a0ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a0ea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4a0ea-107">アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="4a0ea-108">アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="4a0ea-109">Defender Microsoft 365関連するアラートは、インシデントを形成するために[まとめて集計されます](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="4a0ea-110">インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの分析は、より深い分析が必要な場合に有用です。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="4a0ea-111">アラート **キューには、** 現在の一連のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="4a0ea-112">[インシデント] からアラートキューにアクセスし&>セキュリティ センター (security.microsoft.com) のMicrosoft 365アラートを[security.microsoft.com。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4a0ea-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="アラート キューの例":::

<span data-ttu-id="4a0ea-114">Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Defender など、さまざまな Microsoft Microsoft 365からの通知がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="4a0ea-115">既定では、セキュリティ センターのMicrosoft 365キューには、過去 30 日間の新しいアラートと進行中のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="4a0ea-116">最新のアラートはリストの一番上に表示されます。最初に確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="4a0ea-117">既定のアラート キューから [フィルター] を選択 **すると、[** フィルター] ウィンドウが表示され、そこからアラートのサブセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="4a0ea-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="アラート キューのフィルター ウィンドウの例":::

<span data-ttu-id="4a0ea-120">次の条件に従ってアラートをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="4a0ea-121">重要度</span><span class="sxs-lookup"><span data-stu-id="4a0ea-121">Severity</span></span>
- <span data-ttu-id="4a0ea-122">状態</span><span class="sxs-lookup"><span data-stu-id="4a0ea-122">Status</span></span>
- <span data-ttu-id="4a0ea-123">Category</span><span class="sxs-lookup"><span data-stu-id="4a0ea-123">Category</span></span>
- <span data-ttu-id="4a0ea-124">検出ソース</span><span class="sxs-lookup"><span data-stu-id="4a0ea-124">Detection source</span></span>
- <span data-ttu-id="4a0ea-125">タグ</span><span class="sxs-lookup"><span data-stu-id="4a0ea-125">Tags</span></span>
- <span data-ttu-id="4a0ea-126">ポリシー</span><span class="sxs-lookup"><span data-stu-id="4a0ea-126">Policy</span></span>
- <span data-ttu-id="4a0ea-127">影響を受け取ったアセット</span><span class="sxs-lookup"><span data-stu-id="4a0ea-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="4a0ea-128">アラートの分析</span><span class="sxs-lookup"><span data-stu-id="4a0ea-128">Analyze an alert</span></span>

<span data-ttu-id="4a0ea-129">メインのアラート ページを表示するには、アラートの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="4a0ea-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="セキュリティ センターのアラートの詳細ページMicrosoft 365例":::

<span data-ttu-id="4a0ea-132">[警告の管理] ウィンドウ **から [メインのアラート ページを開** く] **アクションを選択** することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="4a0ea-133">アラート ページは、次のセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="4a0ea-134">アラート ストーリー(このアラートに関連するイベントとアラートの連鎖を時系列順に示す)</span><span class="sxs-lookup"><span data-stu-id="4a0ea-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="4a0ea-135">概要の詳細</span><span class="sxs-lookup"><span data-stu-id="4a0ea-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="セキュリティ センターのアラートの詳細ページMicrosoft 365例":::

<span data-ttu-id="4a0ea-137">アラート ページ全体で、任意のエンティティの横にある省略記号 (**...**) を選択して、アラート ページを開く、またはアラートを別のインシデントにリンクするなどの使用可能なアクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="4a0ea-138">アラート ソース</span><span class="sxs-lookup"><span data-stu-id="4a0ea-138">Alert sources</span></span>
<span data-ttu-id="4a0ea-139">Microsoft 365Defender アラートは、Microsoft Defender for Endpoint、Microsoft Defender for endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="4a0ea-140">警告の先頭に文字が付加されたアラートが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="4a0ea-141">次の表は、アラートの先頭に付加された文字に基づくアラート ソースのマッピングを理解するのに役立つガイダンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="4a0ea-142">付加された GUID は、統合アラート キュー、統合アラート ページ、統合調査、統合インシデントなどの統合エクスペリエンスにのみ固有です。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="4a0ea-143">先頭に付加された文字は、アラートの GUID を変更しない。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="4a0ea-144">GUID に対する唯一の変更は、先頭に追加されたコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="4a0ea-145">アラート ソース</span><span class="sxs-lookup"><span data-stu-id="4a0ea-145">Alert source</span></span> | <span data-ttu-id="4a0ea-146">先頭文字</span><span class="sxs-lookup"><span data-stu-id="4a0ea-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="4a0ea-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4a0ea-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="4a0ea-148">例: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="4a0ea-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="4a0ea-149">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a0ea-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="4a0ea-150">`da` または `ed` カスタム検出アラートの場合</span><span class="sxs-lookup"><span data-stu-id="4a0ea-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="4a0ea-151">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="4a0ea-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="4a0ea-152">例: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="4a0ea-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="4a0ea-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4a0ea-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="4a0ea-154">例: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="4a0ea-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="4a0ea-155">影響を受けるアセットを分析する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-155">Analyze affected assets</span></span>

<span data-ttu-id="4a0ea-156">[ **実行されたアクション** ] セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受けるアセットの一覧があります。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="4a0ea-157">[アクション センターで **表示] を選択して**、セキュリティ センターの [アクション センター] の [履歴] タブMicrosoft 365することもできます。 </span><span class="sxs-lookup"><span data-stu-id="4a0ea-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="4a0ea-158">アラート ストーリー内のアラートの役割を追跡する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="4a0ea-159">アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="4a0ea-160">タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="4a0ea-161">アラート ストーリー内のアセットは展開可能でクリック可能です。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="4a0ea-162">アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="4a0ea-163">[アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="4a0ea-164">詳細ページでアラートの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-164">View more alert information on the details page</span></span>

<span data-ttu-id="4a0ea-165">[詳細] ページには、選択したアラートの詳細と、そのアラートに関連する詳細とアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="4a0ea-166">アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="4a0ea-167">目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="4a0ea-168">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="4a0ea-168">Manage alerts</span></span>

<span data-ttu-id="4a0ea-169">アラートを管理するには、その行のアラート キューでアラートを選択して、[警告の管理] **ウィンドウを表示** します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="4a0ea-170">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="アラートの概要ウィンドウの例":::

<span data-ttu-id="4a0ea-172">[ **警告の管理]** ウィンドウでは、次の項目を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="4a0ea-173">アラートの状態 (新規、解決済み、進行中)。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="4a0ea-174">アラートの分類 (設定されていない、True アラート、False Alert)。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="4a0ea-175">真のアラートとして分類する場合は、[決定] フィールドのアラートの脅威の種類 **を指定** します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="4a0ea-176">アラートに関するコメント。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="4a0ea-177">タグを使用してアラートを管理する方法の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="4a0ea-178">Microsoft Defender for microsoft Defender for Office 365段階的に展開中で、現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="4a0ea-179">現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="4a0ea-180">変更前に生成されたアラートには、更新されたタグ名は反映されません。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="4a0ea-181">このウィンドウから、次の追加アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="4a0ea-182">メインアラート ページを開く</span><span class="sxs-lookup"><span data-stu-id="4a0ea-182">Open the main alert page</span></span>
- <span data-ttu-id="4a0ea-183">Microsoft 脅威の専門家に相談する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="4a0ea-184">提出の表示</span><span class="sxs-lookup"><span data-stu-id="4a0ea-184">View submission</span></span>
- <span data-ttu-id="4a0ea-185">別のインシデントへのリンク</span><span class="sxs-lookup"><span data-stu-id="4a0ea-185">Link to another incident</span></span>
- <span data-ttu-id="4a0ea-186">タイムラインでアラートを表示する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-186">See the alert in a timeline</span></span>
- <span data-ttu-id="4a0ea-187">抑制ルールの作成</span><span class="sxs-lookup"><span data-stu-id="4a0ea-187">Create a suppression rule</span></span>

<span data-ttu-id="4a0ea-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="セキュリティ センターのアラートに対するアクションMicrosoft 365例":::

<span data-ttu-id="4a0ea-190">追加のアクションの一覧は、アラートの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="4a0ea-191">アラートを解決する</span><span class="sxs-lookup"><span data-stu-id="4a0ea-191">Resolve an alert</span></span>

<span data-ttu-id="4a0ea-192">アラートの分析が完了し、解決したら、[アラートの管理] ウィンドウに移動し、その状態を [解決済み] としてマークし、False アラートまたは **True** アラートとして分類します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="4a0ea-193">true アラートの場合は、[決定] フィールドにアラートの脅威の種類 **を指定** します。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="4a0ea-194">アラートを分類し、その決定を指定すると、Defender Microsoft 365を調整して、より多くの真のアラートと少ない誤ったアラートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a0ea-195">次の手順</span><span class="sxs-lookup"><span data-stu-id="4a0ea-195">Next steps</span></span>

<span data-ttu-id="4a0ea-196">インプロセス インシデントの必要に応じて、調査を続行 [します](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="4a0ea-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a0ea-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a0ea-197">See also</span></span>

- [<span data-ttu-id="4a0ea-198">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="4a0ea-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="4a0ea-199">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="4a0ea-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="4a0ea-200">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="4a0ea-200">Investigate incidents</span></span>](investigate-incidents.md)
