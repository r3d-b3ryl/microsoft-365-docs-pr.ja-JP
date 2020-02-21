---
title: バッテリインサイト
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170597"
---
# <a name="battery-insights"></a><span data-ttu-id="7b25e-103">バッテリインサイト</span><span class="sxs-lookup"><span data-stu-id="7b25e-103">Battery insights</span></span>
<span data-ttu-id="7b25e-104">このビューでは、Microsoft マネージドデスクトップデバイスの電力、バッテリ、アプリの使用状況の測定基準が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7b25e-105">このような目的で、アプリが実行中で、フォーカスがある場合、アプリは "使用中" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="7b25e-106">利用状況データを表示するには、[**バッテリ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-106">To view usage data, select the **Battery** tab.</span></span>

![バッテリウィンドウ: 左上にあるデバイスごとのバッテリの寿命、右上のエネルギー消費者 (アプリごと) は、下にある insights の表で予測されます。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="7b25e-109">バッテリ寿命の予測</span><span class="sxs-lookup"><span data-stu-id="7b25e-109">Predicted battery life</span></span>

<span data-ttu-id="7b25e-110">[予測された**バッテリの寿命**] 領域で、デバイスモデルごとに構成された、デバイスの予想されるバッテリ寿命を予測します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="7b25e-111">このデータは、Microsoft マネージドデスクトップ展開でデータを報告するランダムなデバイスを<em>選択</em>することによって、サンプリングエネルギー使用率、使用時間、バッテリ容量から導き出されます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="7b25e-112">表は、予想されるバッテリ寿命 (時間単位)、その他の Microsoft マネージデスクトップ展開における同じモデルの平均バッテリ寿命、環境内でこのデータを報告しているデバイスの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b25e-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="7b25e-113">列見出しを選択して、データを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="7b25e-114">最高消費電力</span><span class="sxs-lookup"><span data-stu-id="7b25e-114">Top energy consumers</span></span>

<span data-ttu-id="7b25e-115">[ **Top energy コンシューマ**] 領域には、MilliWatt (mWh) で最も多くのエネルギーを消費している環境内のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="7b25e-116">表示されるアプリは、左側の [**バッテリ寿命の予測**] セクションで選択した、特定のデバイスごとにあります。</span><span class="sxs-lookup"><span data-stu-id="7b25e-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="7b25e-117">たとえば、Microsoft Surface Book 2 デバイスのアプリごとの使用量を確認するには、バッテリの寿命領域でその行を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="7b25e-118">モデルを選択しない場合、表示されるアプリの利用状況データは、データが含まれるすべてのアプリについて、すべてのアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="7b25e-119">各アプリについて、色分けされたセグメントは、このカテゴリにおけるアプリのエネルギー使用の配分を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b25e-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="7b25e-120">CPU</span><span class="sxs-lookup"><span data-stu-id="7b25e-120">CPU</span></span>
- <span data-ttu-id="7b25e-121">表示</span><span class="sxs-lookup"><span data-stu-id="7b25e-121">Display</span></span>
- <span data-ttu-id="7b25e-122">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="7b25e-122">Network</span></span>
- <span data-ttu-id="7b25e-123">その他</span><span class="sxs-lookup"><span data-stu-id="7b25e-123">Other</span></span>

<span data-ttu-id="7b25e-124">"その他" には、ディスクアクティビティ、モバイルブロードバンド使用状況、内部抵抗に対するエネルギー損失など、さまざまなソースによる電力消費が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b25e-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="7b25e-125">このビューにフィルターを適用して、フォアグラウンドアプリ、バックグラウンドアプリ、またはその両方を表示することができます。右上のメニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="7b25e-126">フォアグラウンドアプリは、マウスを使用して何かを選択するなど、過去28日以内にユーザーが操作したものです。</span><span class="sxs-lookup"><span data-stu-id="7b25e-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="7b25e-127">分析情報</span><span class="sxs-lookup"><span data-stu-id="7b25e-127">Insights</span></span>

<span data-ttu-id="7b25e-128">[ **Insights** ] 領域には、CPU およびネットワークカテゴリの上位3つのエネルギーコンシューマーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="7b25e-129">これらのアイテムは、Microsoft のすべての管理対象デスクトップ展開に比べて、平均エネルギーよりも高い時間を消費しています。</span><span class="sxs-lookup"><span data-stu-id="7b25e-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="7b25e-130">ディスプレイリソースは、デバイスの使用時間と画面の明るさの設定に大きく依存しているため、表示されません。</span><span class="sxs-lookup"><span data-stu-id="7b25e-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="7b25e-131">詳細については、[**詳細**] 列の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="7b25e-132">バッテリの最適化</span><span class="sxs-lookup"><span data-stu-id="7b25e-132">Battery optimization</span></span>

<span data-ttu-id="7b25e-133">Windows 10 では、電力使用率を向上させ、Microsoft マネージドデスクトップデバイスのバッテリ寿命を向上させるためのさまざまな[デバイス設定](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)が提供されています。</span><span class="sxs-lookup"><span data-stu-id="7b25e-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7b25e-134">これらの設定の一部は、他の Windows 機能を減らすことができるため、組織内のデバイスの役割など、他の要因も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b25e-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="7b25e-135">Windows サポートは、これらの[バッテリー節約のヒント](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="7b25e-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="7b25e-136">ユーザーは、管理者昇格やサポートを必要とせずに、自分の設定を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="7b25e-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="7b25e-137">その他の設定には、組織の IT 管理者のサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b25e-137">Other settings require support from your organization's IT administrator.</span></span>
