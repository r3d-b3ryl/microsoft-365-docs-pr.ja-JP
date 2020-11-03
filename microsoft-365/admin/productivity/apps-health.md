---
title: Microsoft プロダクティビティスコア-Microsoft 365 アプリの正常性
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Microsoft 365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Microsoft 365 apps health-テクノロジエクスペリエンスの生産性スコアの詳細。
ms.openlocfilehash: 9497118f4ebfb1cb2b64670638ce939da21eb261
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841191"
---
# <a name="microsoft-365-apps-health--technology-experiences"></a><span data-ttu-id="e941a-103">Microsoft 365 アプリの正常性–テクノロジエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e941a-103">Microsoft 365 apps health – Technology experiences</span></span>

<span data-ttu-id="e941a-104">生産性スコアは、ユーザーが Microsoft 365 アプリを使用する方法と、テクノロジエクスペリエンスをサポートする方法について測定基準を使用して作業を行う方法を変革するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e941a-104">Productivity Score helps organizations transform how work gets done with metrics about how people use Microsoft 365 apps and the supporting technology experiences.</span></span> <span data-ttu-id="e941a-105">スコアは、ユーザーとテクノロジの分野のための組織&#39;のパフォーマンスを反映し、自分のスコアを自分のような組織と比較します。</span><span class="sxs-lookup"><span data-stu-id="e941a-105">The score reflects your organization&#39;s performance for people and technology experience categories and compares your score with organizations like yours.</span></span> <span data-ttu-id="e941a-106">アプリの正常性カテゴリは、ユーザーエクスペリエンスの下にある測定値の一部です。</span><span class="sxs-lookup"><span data-stu-id="e941a-106">The apps health category is part of the measurements that falls under people experiences.</span></span> <span data-ttu-id="e941a-107">詳細については、「 [生産性スコアの概要](productivity-score.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e941a-107">See the [Productivity Score overview](productivity-score.md) to learn more.</span></span>

## <a name="why-your-organization39s-microsoft-365-apps-health-score-matters"></a><span data-ttu-id="e941a-108">組織&#39;Microsoft 365 アプリの正常性スコアが重要である理由</span><span class="sxs-lookup"><span data-stu-id="e941a-108">Why your organization&#39;s Microsoft 365 apps health score matters</span></span>

<span data-ttu-id="e941a-109">組織の生産性は、正常なアプリケーション環境に依存します。</span><span class="sxs-lookup"><span data-stu-id="e941a-109">Your organizational productivity is dependent on healthy application environment.</span></span> <span data-ttu-id="e941a-110">最新バージョンの Microsoft 365 アプリを実行しているデバイスは、推奨チャネルでより安全になり、組織内のユーザーが Microsoft 365 の機能を最大限に活用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e941a-110">Devices running most current versions of Microsoft 365 apps on recommended channel are more secure and help people in your organization get the most out of the features in Microsoft 365.</span></span>

## <a name="how-we-calculate-the-microsoft-365-apps-health-score"></a><span data-ttu-id="e941a-111">Microsoft 365 アプリの正常性スコアを計算する方法</span><span class="sxs-lookup"><span data-stu-id="e941a-111">How we calculate the Microsoft 365 apps health score</span></span>

<span data-ttu-id="e941a-112">Microsoft 365 アプリの正常性スコアを計算するには、各更新プログラムチャネルのデバイスの数を測定します。</span><span class="sxs-lookup"><span data-stu-id="e941a-112">We calculate your Microsoft 365 apps health score by measuring the number of devices on each update channel.</span></span> <span data-ttu-id="e941a-113">また、デバイスでサポートされているバージョンが実行されているかどうか、および Microsoft 365 アプリの最新のリリースを確認します。</span><span class="sxs-lookup"><span data-stu-id="e941a-113">We also determine whether the devices are running a supported version, and the most current release of Microsoft 365 apps.</span></span>

<span data-ttu-id="e941a-114">ここでは、このカテゴリの主要な指標が含まれている経験について、主な洞察を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e941a-114">We provide a primary insight in the experience that contains the key metrics for this category.</span></span> <span data-ttu-id="e941a-115">次に、スコアを計算するために、以下のセクションで詳細なスコアリングフレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="e941a-115">Then, a scoring framework, detailed in the following sections, is used to calculate your score.</span></span>

### <a name="primary-insight"></a><span data-ttu-id="e941a-116">主要な洞察</span><span class="sxs-lookup"><span data-stu-id="e941a-116">Primary insight</span></span>

<span data-ttu-id="e941a-117">プライマリ洞察は、更新された推奨チャネルで Microsoft 365 アプリを実行しているデバイスから計算されます。</span><span class="sxs-lookup"><span data-stu-id="e941a-117">The primary insight is calculated from devices that are running Microsoft 365 Apps on recommended updated channel.</span></span>

:::image type="content" source="../../media/appshealth-primary.png" alt-text="Microsoft 365 アプリの表示が主に可視化されています。":::

<span data-ttu-id="e941a-119">このことを考慮した情報には、Microsoft 365 アプリチャネル、ビルド、デバイス上で実行されているバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="e941a-119">Information considered for this include Microsoft 365 apps channel, build, and version that is running on the device.</span></span>

1. <span data-ttu-id="e941a-120">**ヘッダー:**  推奨される更新プログラムチャネルのデバイスのパーセンテージを示します</span><span class="sxs-lookup"><span data-stu-id="e941a-120">**Header:**  Shows percentage of devices on recommended update channel</span></span>
1. <span data-ttu-id="e941a-121">**本文:**  推奨される更新プログラムチャネルでデバイスを実行することにより、最新の更新プログラムを取得し、デバイス上の現在のバージョンを実行する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e941a-121">**Body:**  Provides more information on how running the devices on recommended update channel will help getting latest update and running current versions on devices.</span></span>
1. <span data-ttu-id="e941a-122">**視覚エフェクト (現在の状態):**</span><span class="sxs-lookup"><span data-stu-id="e941a-122">**Visualization (current state):**</span></span>
    - <span data-ttu-id="e941a-123">青の色の部分が、推奨される更新されたチャネルを実行しているデバイスの割合を表す横棒。</span><span class="sxs-lookup"><span data-stu-id="e941a-123">Horizontal bars where the blue-colored portions represent the percentage of devices running recommended updated channel.</span></span>
    - <span data-ttu-id="e941a-124">横棒で表されるパーセンテージの計算に使用される分数の (分子または分母) を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="e941a-124">Highlight the (numerator/denominator) of the fraction used to calculate the percentage expressed in horizontal bars.</span></span>
    - <span data-ttu-id="e941a-125">推奨更新チャネルで実行されているデバイスのピアベンチマーク値も、パーセンテージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e941a-125">Peer Benchmark value for devices running on recommended updated channel is also shown as a percentage.</span></span>

#### <a name="trend-visualization-of-the-primary-insight"></a><span data-ttu-id="e941a-126">主要な洞察の傾向を視覚化</span><span class="sxs-lookup"><span data-stu-id="e941a-126">Trend visualization of the primary insight</span></span>

<span data-ttu-id="e941a-127">次のグラフは、推奨される更新プログラムチャネルのうち、過去180日間のデバイスの数を示しています。</span><span class="sxs-lookup"><span data-stu-id="e941a-127">The following chart shows the number of devices in the recommended update channel over the last 180 days.</span></span> <span data-ttu-id="e941a-128">折れ線グラフのデータポイントは、過去28日間のアクティビティの集計です。</span><span class="sxs-lookup"><span data-stu-id="e941a-128">The data point on the line chart is an aggregate of activity for the last 28 days.</span></span>

:::image type="content" source="../../media/appshealth-primarytrend.png" alt-text="推奨される更新プログラムチャネルを実行しているデバイスの傾向を示すグラフ。":::

### <a name="scoring-framework"></a><span data-ttu-id="e941a-130">スコアリングフレームワーク</span><span class="sxs-lookup"><span data-stu-id="e941a-130">Scoring framework</span></span>

<span data-ttu-id="e941a-131">Microsoft 365 アプリの正常性スコアは、推奨チャネルおよび最新バージョンのデバイスで Microsoft 365 アプリが実行されているかどうかを測定します。</span><span class="sxs-lookup"><span data-stu-id="e941a-131">The Microsoft 365 apps health score measures whether devices are running Microsoft 365 apps on recommended channel and on latest versions.</span></span>

## <a name="explore-your-organization-microsoft-365-app-channels-and-versions"></a><span data-ttu-id="e941a-132">組織を探索する Microsoft 365 アプリのチャネルとバージョン</span><span class="sxs-lookup"><span data-stu-id="e941a-132">Explore your organization Microsoft 365 app channels and versions</span></span>

<span data-ttu-id="e941a-133">また、組織内で現在実行されているチャネルとバージョンデバイスの詳細を表示するのに役立つサポート情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="e941a-133">We also provide supporting information that helps you gain additional visibility into what channels and versions devices in your organization are currently running.</span></span> <span data-ttu-id="e941a-134">これらの追加指標は、生産性スコアに寄与しませんが、推奨チャネルで Microsoft 365 アプリを実行するようにデバイスを決定することで、Microsoft 365 アプリの正常性スコアを向上させるアクションプランを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e941a-134">These additional metrics do not contribute to your Productivity Score but can help you create an action plan to increase your Microsoft 365 apps health score by making sure devices run Microsoft 365 apps on recommended channels.</span></span>

### <a name="devices-on-current-channel-and-running-supported-versions"></a><span data-ttu-id="e941a-135">現在のチャネルのデバイスとサポートされているバージョンの実行</span><span class="sxs-lookup"><span data-stu-id="e941a-135">Devices on current channel and running supported versions</span></span>

:::image type="content" source="../../media/devices-current-suppported-channel.png" alt-text="現在サポートされているチャネル内のデバイスの数を示す図。":::

1. <span data-ttu-id="e941a-137">**ヘッダー:**  強調表示現在のチャネル上のデバイスのうち、サポートされているバージョンの Microsoft 365 アプリを実行している割合</span><span class="sxs-lookup"><span data-stu-id="e941a-137">**Header:**  Highlights the percentage of devices on the Current Channel are running supported versions of Microsoft 365 Apps</span></span>
1. <span data-ttu-id="e941a-138">**本文:**  推奨チャネルで Microsoft 365 アプリを実行しているデバイスの価値に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e941a-138">**Body:**  Provides information about the value of devices running Microsoft 365 apps on recommended channel.</span></span>
1. <span data-ttu-id="e941a-139">**視覚エフェクト:**  視覚エフェクトのブレークダウンは、次のように、Microsoft 365 アプリの最新バージョンとサポートされているバージョンのデバイスの割合を表しています。</span><span class="sxs-lookup"><span data-stu-id="e941a-139">**Visualization:**  The breakdown in the visualization represents the extent to what percentage of devices on latest and supported versions of Microsoft 365 apps across different channel), as follows:</span></span>
    - <span data-ttu-id="e941a-140">**サポートされているバージョン:** 青いバーは、Microsoft 365 アプリのサポートされているバージョンで実行されているデバイスのパーセンテージを表します。</span><span class="sxs-lookup"><span data-stu-id="e941a-140">**Supported versions:** The blue bar represents the percentage of devices running on supported version of Microsoft 365 apps.</span></span>
    - <span data-ttu-id="e941a-141">**最新リリース:** 青緑色のカラーバーは、最新のリリース上のデバイスの割合を表します。</span><span class="sxs-lookup"><span data-stu-id="e941a-141">**Latest releases:** The teal color bar represents percentage of devices on latest releases.</span></span>
1. <span data-ttu-id="e941a-142">**詳細情報:**   ヘルプコンテンツを表示するには、このリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e941a-142">**Learn more:**   Select this link to view help content.</span></span>

### <a name="devices-running-latest-and-supported-versions"></a><span data-ttu-id="e941a-143">最新およびサポートされているバージョンを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="e941a-143">Devices running latest and supported versions</span></span>

:::image type="content" source="../../media/device-supported-versions.png" alt-text="最新バージョンおよびサポートされているバージョンのアプリを実行しているデバイスの数を示す図。":::

1. <span data-ttu-id="e941a-145">**ヘッダー:**  サポートされているバージョンと最新のバージョンを実行しているデバイスのパーセンテージを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="e941a-145">**Header:**  Highlights the percentage of devices running supported versions and devices running the most recent versions.</span></span>
1. <span data-ttu-id="e941a-146">**本文:**  推奨チャネルおよびサポートされている最新バージョンのデバイスを実行しているデバイスの値に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e941a-146">**Body:**  Provides information about the value running devices on recommended channels and supported/latest versions.</span></span>
1. <span data-ttu-id="e941a-147">**視覚エフェクト:** この視覚エフェクトのブレークダウンは、サポートされているバージョンと Microsoft 365 アプリの最新バージョンを実行しているデバイスの数を表示するための範囲を表すことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="e941a-147">**Visualization:** The breakdown in the visualization is meant to represent the extent to show how many devices running supported versions and most recent versions of Microsoft 365 apps):</span></span>
    - <span data-ttu-id="e941a-148">**サポートされているバージョン:** バーの青 (色付き) 部分と分数 (分子/分母) は、サポートされているバージョンの Microsoft 365 アプリを実行しているデバイスの割合を表します。</span><span class="sxs-lookup"><span data-stu-id="e941a-148">**Supported versions:** The blue (colored) portion of the bar and the fraction (numerator/denominator) on the bar represents the percentage of devices running supported version of Microsoft 365 apps.</span></span>
        - <span data-ttu-id="e941a-149">分子: 過去28日以内に Microsoft 365 アプリのサポートされているバージョンのデバイスの数</span><span class="sxs-lookup"><span data-stu-id="e941a-149">Numerator: The number of devices on supported versions of Microsoft 365 apps within the last 28 days</span></span>
        - <span data-ttu-id="e941a-150">分母: 過去28日以内に Microsoft 365 アプリを使用しているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="e941a-150">Denominator: The number of devices using Microsoft 365 apps within the last 28 days</span></span>
    - <span data-ttu-id="e941a-151">**最新のバージョン:** バーの青緑色 (カラー) 部分と分数 (分子/分母) は、Microsoft 365 アプリの最新バージョンを実行しているデバイスの割合を表します。</span><span class="sxs-lookup"><span data-stu-id="e941a-151">**Most recent versions:** The teal (colored) portion of the bar and the fraction (numerator/denominator) on the bar represents the percentage of devices running recent versions of Microsoft 365 apps.</span></span>
        - <span data-ttu-id="e941a-152">分子: 過去28日以内の Microsoft 365 アプリの最新バージョンのデバイスの数</span><span class="sxs-lookup"><span data-stu-id="e941a-152">Numerator: The number of devices on recent versions of Microsoft 365 apps within the last 28 days</span></span>
        - <span data-ttu-id="e941a-153">分母: 過去28日以内に Microsoft 365 アプリを使用しているデバイスの数</span><span class="sxs-lookup"><span data-stu-id="e941a-153">Denominator: The number of devices using Microsoft 365 apps within the last 28 days</span></span>
1. <span data-ttu-id="e941a-154">**詳細情報:**   ヘルプコンテンツを表示するには、このリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="e941a-154">**Learn more:**   Select this link to view help content.</span></span>

#### <a name="trend-visualization-of-the-devices"></a><span data-ttu-id="e941a-155">デバイスの傾向を視覚化</span><span class="sxs-lookup"><span data-stu-id="e941a-155">Trend visualization of the devices</span></span>

<span data-ttu-id="e941a-156">このグラフは、過去180日間にわたる Microsoft 365 アプリのサポートされているバージョンと最新バージョンを実行しているデバイスの傾向ラインを示しています。</span><span class="sxs-lookup"><span data-stu-id="e941a-156">This chart shows the trend-line of the devices running supported versions and latest versions of Microsoft 365 apps over the last 180 days.</span></span>

:::image type="content" source="../../media/trendline-devices-supportedversions.png" alt-text="サポートされている最新バージョンのアプリを長期間にわたって実行するデバイスの数を showa するグラフ。":::

## <a name="people-in-your-organization"></a><span data-ttu-id="e941a-158">組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="e941a-158">People in your organization</span></span>

<span data-ttu-id="e941a-159">このセクションでは、Microsoft 365 アプリの正常性テクノロジエクスペリエンスに関するすべての指標に関連情報を提供することによって、注目する指標を操作するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e941a-159">This section helps you act on the metrics you want to focus on by providing relevant information to all the metrics for Microsoft 365 apps health - technology experiences.</span></span>

<span data-ttu-id="e941a-160">ユーザーレベルの表には、次の列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e941a-160">The following columns are presented in the table at the user level:</span></span>

- <span data-ttu-id="e941a-161">**Channel** : デバイス上の現在の Microsoft 365 アプリチャネル。</span><span class="sxs-lookup"><span data-stu-id="e941a-161">**Channel** : Current Microsoft 365 apps channel on the devices.</span></span>
- <span data-ttu-id="e941a-162">**状態:**   Microsoft 365 アプリは、現在のチャネルとバージョンに基づくデバイスの状態をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e941a-162">**Status:**   Microsoft 365 apps support state of the devices based on current channel and version.</span></span>
- <span data-ttu-id="e941a-163">**バージョン:**  デバイス上の現在の Microsoft 365 アプリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e941a-163">**Versions:**  Current Microsoft 365 apps versions on the devices.</span></span>
- <span data-ttu-id="e941a-164">**デバイス数:**  デバイスの数。</span><span class="sxs-lookup"><span data-stu-id="e941a-164">**# of devices:**  Number of devices.</span></span>

## <a name="related-content"></a><span data-ttu-id="e941a-165">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e941a-165">Related content</span></span>

<span data-ttu-id="e941a-166">[コミュニケーション–ユーザーエクスペリエンス](communication.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="e941a-166">[Communication – People experiences](communication.md) (article)</span></span>\
<span data-ttu-id="e941a-167">[コンテンツコラボレーション–ユーザーエクスペリエンス](content-collaboration.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="e941a-167">[Content collaboration – People experiences](content-collaboration.md) (article)</span></span>\
<span data-ttu-id="e941a-168">[会議– People エクスペリエンス](meetings.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="e941a-168">[Meetings – People experiences](meetings.md) (article)</span></span>\
<span data-ttu-id="e941a-169">[モビリティ–ユーザーエクスペリエンス](mobility.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="e941a-169">[Mobility – People experiences](mobility.md) (article)</span></span>\
<span data-ttu-id="e941a-170">[生産性スコアのプライバシー統制](privacy.md) (記事) </span><span class="sxs-lookup"><span data-stu-id="e941a-170">[Privacy controls for Productivity Score](privacy.md) (article)</span></span>\
<span data-ttu-id="e941a-171">[チームワーク–ユーザーエクスペリエンス](teamwork.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="e941a-171">[Teamwork – People experiences](teamwork.md) (article)</span></span>