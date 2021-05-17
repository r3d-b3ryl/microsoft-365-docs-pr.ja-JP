---
title: Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグ
description: Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグを使用して、
keywords: Defender for Endpoint デバイスのタイムライン、イベント フラグ
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165155"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="7458a-104">Microsoft Defender for Endpoint デバイスのタイムライン イベント フラグ</span><span class="sxs-lookup"><span data-stu-id="7458a-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7458a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7458a-105">**Applies to:**</span></span>
- [<span data-ttu-id="7458a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7458a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7458a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7458a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7458a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7458a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7458a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7458a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="7458a-110">Defender for Endpoint デバイス タイムラインのイベント フラグは、潜在的な攻撃を調査するときに特定のイベントをフィルター処理して整理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7458a-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="7458a-111">Defender for Endpoint デバイスのタイムラインは、デバイスで観察されるイベントと関連するアラートの時系列ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="7458a-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="7458a-112">このイベントの一覧は、デバイスで観察されたイベント、ファイル、および IP アドレスを完全に表示します。</span><span class="sxs-lookup"><span data-stu-id="7458a-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="7458a-113">リストには長い場合があります。</span><span class="sxs-lookup"><span data-stu-id="7458a-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="7458a-114">デバイス タイムラインイベント フラグは、関連する可能性があるイベントを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7458a-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="7458a-115">デバイスのタイムラインを通過した後、フラグを設定した特定のイベントを並べ替え、フィルター処理、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7458a-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="7458a-116">デバイスのタイムラインを移動するときに、特定のイベントを検索してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="7458a-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="7458a-117">イベント フラグは、次の方法で設定できます。</span><span class="sxs-lookup"><span data-stu-id="7458a-117">You can set event flags by:</span></span> 

- <span data-ttu-id="7458a-118">最も重要なイベントの強調表示</span><span class="sxs-lookup"><span data-stu-id="7458a-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="7458a-119">深く掘り下げが必要なイベントのマーキング</span><span class="sxs-lookup"><span data-stu-id="7458a-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="7458a-120">クリーンな違反タイムラインの構築</span><span class="sxs-lookup"><span data-stu-id="7458a-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="7458a-121">イベントにフラグを設定する</span><span class="sxs-lookup"><span data-stu-id="7458a-121">Flag an event</span></span>
1. <span data-ttu-id="7458a-122">フラグを設定するイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="7458a-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="7458a-123">[フラグ] 列のフラグ アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7458a-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="7458a-124">![デバイスのタイムライン フラグのイメージ](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="7458a-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="7458a-125">フラグが設定されたイベントを表示する</span><span class="sxs-lookup"><span data-stu-id="7458a-125">View flagged events</span></span>  
1. <span data-ttu-id="7458a-126">[タイムライン のフィルター **] セクション** で、[フラグ付 **きイベント] を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="7458a-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="7458a-127">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7458a-127">Click **Apply**.</span></span> <span data-ttu-id="7458a-128">フラグが設定されたイベントだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7458a-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="7458a-129">タイム バーをクリックすると、追加のフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7458a-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="7458a-130">これにより、フラグが設定されたイベントより前のイベントだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7458a-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="7458a-131">![フィルターがオンのデバイス タイムライン フラグのイメージ](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="7458a-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
