---
title: デバイスタイムラインのテクニック
description: Microsoft Defender for Endpoint のデバイス タイムラインについて
keywords: デバイスタイムライン、エンドポイント、MITRE、MITRE ATT&CK、テクニック、戦術
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185469"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="6ffe8-104">デバイスタイムラインのテクニック</span><span class="sxs-lookup"><span data-stu-id="6ffe8-104">Techniques in the device timeline</span></span>


<span data-ttu-id="6ffe8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6ffe8-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ffe8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6ffe8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="6ffe8-107">特定のデバイスで発生したイベントを分析することで、調査に関するより多くの洞察を得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="6ffe8-108">まず、[デバイス] リストから目的のデバイス [を選択します](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="6ffe8-109">デバイス ページで、[タイムライン] タブを **選択** して、デバイスで発生したイベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="6ffe8-110">タイムラインのテクニックを理解する</span><span class="sxs-lookup"><span data-stu-id="6ffe8-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="6ffe8-111">一部の情報は、パブリック プレビューで事前リリースされた製品機能に関連します。これは、商用リリース前に大幅に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6ffe8-112">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6ffe8-113">Microsoft Defender for Endpoint では **、Techniques は** イベント タイムラインの追加データ型です。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="6ffe8-114">技術は [、MITRE ATT](https://attack.mitre.org/) および CK の手法またはサブ&関連するアクティビティに関するより多くの洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="6ffe8-115">この機能は、分析者がデバイスで観察されたアクティビティを理解するのを支援することで、調査エクスペリエンスを簡素化します。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="6ffe8-116">アナリストは、さらに調査を行う場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="6ffe8-117">パブリック プレビューの場合、テクニックは既定で使用できます。デバイスのタイムラインを表示するときにイベントと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![デバイス タイムラインのスクリーンショットのテクニック](images/device-timeline-2.png)

<span data-ttu-id="6ffe8-119">テクニックは太字で強調表示され、左側に青いアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="6ffe8-120">対応する MITRE ATT&CK ID とテクニック名は、[追加情報] の下にタグとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="6ffe8-121">検索オプションとエクスポート オプションは、[テクニック] でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="6ffe8-122">サイド ウィンドウを使用して調査する</span><span class="sxs-lookup"><span data-stu-id="6ffe8-122">Investigate using the side pane</span></span>

<span data-ttu-id="6ffe8-123">[テクニック] を選択して、対応するサイド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="6ffe8-124">ここでは、関連する ATT や CK の手法、&説明など、追加情報と分析情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="6ffe8-125">特定の *攻撃手法を選択* して、関連する ATT&CK テクニック ページを開き、詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="6ffe8-126">右側に青いアイコンが表示されている場合は、エンティティの詳細をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="6ffe8-127">たとえば、関連ファイルの SHA1 をコピーするには、青いページ アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![エンティティの詳細のコピー](images/techniques-side-pane-clickable.png)

<span data-ttu-id="6ffe8-129">コマンド ラインでも同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-129">You can do the same for command lines.</span></span>

![コマンド ラインのコピー](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="6ffe8-131">関連イベントの調査</span><span class="sxs-lookup"><span data-stu-id="6ffe8-131">Investigate related events</span></span>

<span data-ttu-id="6ffe8-132">高度な [検索を使用して](advanced-hunting-overview.md) 、選択したテクニックに関連するイベントを検索するには、[関連イベントのハント **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="6ffe8-133">これにより、テクニックに関連するイベントを検索するクエリを含む高度な検索ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![関連イベントのハント](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="6ffe8-135">[テクニック] **サイド** ウィンドウから [関連イベントのハント] ボタンを使用してクエリを実行すると、特定された手法に関連するイベントはすべて表示されますが、クエリ結果にはテクニック自体は含めされません。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="6ffe8-136">デバイスのタイムラインをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6ffe8-136">Customize your device timeline</span></span>

<span data-ttu-id="6ffe8-137">デバイスタイムラインの右上で、タイムライン内のイベントとテクニックの数を制限する日付範囲を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="6ffe8-138">公開する列をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-138">You can customize which columns to expose.</span></span> <span data-ttu-id="6ffe8-139">データ型またはイベント グループ別にフラグが設定されたイベントをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="6ffe8-140">公開する列を選択する</span><span class="sxs-lookup"><span data-stu-id="6ffe8-140">Choose columns to expose</span></span>
<span data-ttu-id="6ffe8-141">[列の選択] ボタンを選択すると、タイムラインで公開する列 **を選択** できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![列のカスタマイズ](images/filter-customize-columns.png)

<span data-ttu-id="6ffe8-143">そこから、含める情報セットを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="6ffe8-144">フィルターを使用して、手法またはイベントのみを表示する</span><span class="sxs-lookup"><span data-stu-id="6ffe8-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="6ffe8-145">イベントまたは手法のみを表示するには、デバイスタイムラインから [ **フィルター** ] を選択し、表示するデータ型を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ffe8-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![フィルターのスクリーンショット](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="6ffe8-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ffe8-147">See also</span></span>
- <span data-ttu-id="6ffe8-148">[[デバイス] リストの表示と整理](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6ffe8-148">[View and organize the Devices list](machines-view-overview.md)</span></span>
- [<span data-ttu-id="6ffe8-149">Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグ</span><span class="sxs-lookup"><span data-stu-id="6ffe8-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
