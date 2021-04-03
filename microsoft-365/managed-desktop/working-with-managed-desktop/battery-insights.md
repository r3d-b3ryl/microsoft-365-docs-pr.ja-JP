---
title: バッテリーの分析情報
description: 予測バッテリ寿命とトップパワーコンシューマに関するデータを示すレポート
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579712"
---
# <a name="battery-insights"></a><span data-ttu-id="d929b-104">バッテリーの分析情報</span><span class="sxs-lookup"><span data-stu-id="d929b-104">Battery insights</span></span>
<span data-ttu-id="d929b-105">このビューは、Microsoft Managed Desktop デバイスの電源、バッテリー、アプリの使用状況の指標を提供します。</span><span class="sxs-lookup"><span data-stu-id="d929b-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d929b-106">これらの目的のために、アプリが実行中でフォーカスがある場合、アプリは "使用中" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="d929b-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="d929b-107">使用状況データを表示するには、[バッテリー] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d929b-107">To view usage data, select the **Battery** tab.</span></span>

![バッテリー ウィンドウ: 左上のデバイス モデルごとの予測バッテリ寿命、右上の上位エネルギーコンシューマ (アプリ別)、下部の分析情報テーブル。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="d929b-110">予測バッテリ寿命</span><span class="sxs-lookup"><span data-stu-id="d929b-110">Predicted battery life</span></span>

<span data-ttu-id="d929b-111">[予測 **バッテリ寿命] 領域** では、デバイス モデル別に整理された、デバイスの予想されるバッテリ寿命の予測を提供します。</span><span class="sxs-lookup"><span data-stu-id="d929b-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="d929b-112">このデータは、データも報告している Microsoft Managed Desktop 展開内の<em></em>デバイスのランダムな選択から、サンプリング エネルギー使用量、使用時間、およびバッテリー容量から派生します。</span><span class="sxs-lookup"><span data-stu-id="d929b-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="d929b-113">次の表は、予測されるバッテリ寿命 (時間)、他の Microsoft Managed Desktop 展開の同じモデルの平均バッテリ寿命、および環境内のこのデータを報告するデバイスの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="d929b-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="d929b-114">列見出しを選択してデータを並べ替える。</span><span class="sxs-lookup"><span data-stu-id="d929b-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="d929b-115">トップエネルギーコンシューマ</span><span class="sxs-lookup"><span data-stu-id="d929b-115">Top energy consumers</span></span>

<span data-ttu-id="d929b-116">[トップ **エネルギーコンシューマ** ] 領域には、milliWatt-hours (mWh) で最もエネルギーを消費する環境内のアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d929b-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="d929b-117">表示されるアプリは、特定のデバイスごとに表示され、左側の [予測バッテリ寿命] **セクションで** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d929b-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="d929b-118">たとえば、Microsoft Surface Book 2 デバイスのアプリごとの消費量を確認するには、バッテリー寿命領域でその行を選択します。</span><span class="sxs-lookup"><span data-stu-id="d929b-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="d929b-119">モデルを選択しない場合、表示されるアプリ消費データは、まとめてデータを持つすべてのアプリに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="d929b-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="d929b-120">各アプリについて、色付きセグメントには、次のカテゴリ間でのアプリのエネルギー使用の分布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d929b-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="d929b-121">CPU</span><span class="sxs-lookup"><span data-stu-id="d929b-121">CPU</span></span>
- <span data-ttu-id="d929b-122">ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="d929b-122">Display</span></span>
- <span data-ttu-id="d929b-123">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="d929b-123">Network</span></span>
- <span data-ttu-id="d929b-124">その他</span><span class="sxs-lookup"><span data-stu-id="d929b-124">Other</span></span>

<span data-ttu-id="d929b-125">"その他" には、ディスクアクティビティ、モバイル ブロードバンドの使用、内部抵抗に失われたエネルギーなど、さまざまなソースによるエネルギー消費量が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d929b-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="d929b-126">このビューをフィルター処理して、右上のメニューを使用してフォアグラウンド アプリ、バックグラウンド アプリ、または両方のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d929b-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="d929b-127">フォアグラウンド アプリは、マウスで何かを選択するなど、過去 28 日間にユーザー操作を行ったアプリです。</span><span class="sxs-lookup"><span data-stu-id="d929b-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="d929b-128">分析情報</span><span class="sxs-lookup"><span data-stu-id="d929b-128">Insights</span></span>

<span data-ttu-id="d929b-129">[ **インサイト] 領域には** 、CPU およびネットワーク カテゴリの上位 3 つのエネルギー コンシューマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d929b-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="d929b-130">これらのアイテムは、すべての Microsoft Managed Desktop 展開に比べて平均的なエネルギーよりも高く消費されています。</span><span class="sxs-lookup"><span data-stu-id="d929b-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="d929b-131">表示リソースは、デバイスの使用時間と画面の明るさの設定に大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="d929b-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="d929b-132">詳細については、[詳細] 列 **の** リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="d929b-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="d929b-133">バッテリーの最適化</span><span class="sxs-lookup"><span data-stu-id="d929b-133">Battery optimization</span></span>

<span data-ttu-id="d929b-134">Windows 10 には [、電力使用量](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) を改善し、Microsoft Managed Desktop デバイスのバッテリ寿命を上げするための多数のデバイス設定が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d929b-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d929b-135">これらの設定の中には、他の Windows 機能が低下する場合があります。そのため、組織内のデバイスの役割など、他の要因も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d929b-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="d929b-136">Windows サポートは、これらのバッテリー節約のヒント [の一覧を維持します](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)。</span><span class="sxs-lookup"><span data-stu-id="d929b-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="d929b-137">ユーザーは、管理者の昇格やサポートを必要とせずに、一部の設定を自分で調整できます。</span><span class="sxs-lookup"><span data-stu-id="d929b-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="d929b-138">その他の設定では、組織の IT 管理者からのサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="d929b-138">Other settings require support from your organization's IT administrator.</span></span>
