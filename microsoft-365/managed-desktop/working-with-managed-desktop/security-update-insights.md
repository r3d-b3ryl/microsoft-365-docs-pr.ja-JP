---
title: Windows セキュリティ更新プログラムの分析情報
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941443"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="c63bc-103">Windows セキュリティ更新プログラムの分析情報</span><span class="sxs-lookup"><span data-stu-id="c63bc-103">Windows security update insights</span></span>
<span data-ttu-id="c63bc-104">このビューでは、デバイスのセキュリティ更新プログラムの状態のMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="c63bc-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="c63bc-105">使用状況データを表示するには、[セキュリティ更新プログラム] <strong>Windowsを選択</strong>します。</span><span class="sxs-lookup"><span data-stu-id="c63bc-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Windowsのセキュリティ更新ウィンドウ: 左側の列のデバイスの状態と更新バージョンの棒グラフ、中央列での時間の経過に合った展開の進捗状況、展開グループ別のアクティブ なデバイスの割合、および右側の列の 95% 展開ターゲットに達するまでの日数。](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="c63bc-107">デバイスの状態</span><span class="sxs-lookup"><span data-stu-id="c63bc-107">Device status</span></span>

<span data-ttu-id="c63bc-108">Windows Update でデバイスを更新するには、少なくとも 6 時間休止状態ではなく、インターネットに接続する必要があります。この 2 つが連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c63bc-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="c63bc-109">これらの要件を満たしないデバイスが更新される可能性はあり得るが、それらの要件を満たすデバイスは更新される可能性が最も高い。</span><span class="sxs-lookup"><span data-stu-id="c63bc-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="c63bc-110">デバイスアクティビティは、次の用語を使用Windows更新プログラムのコンテキストで分類します。</span><span class="sxs-lookup"><span data-stu-id="c63bc-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="c63bc-111"><strong>アクティブ:</strong>最新のセキュリティ更新プログラムリリースの最小アクティビティ条件 (6 時間、連続 2 回) を満たしたデバイスで、少なくとも 5 日ごとに Microsoft Intuneにチェックインしたデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="c63bc-112"><strong>同期:</strong> 過去 28 日以内に Intune にチェックインしたデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="c63bc-113"><strong>同期が切れ:</strong> 過去 28 <i>日間</i> に Intune にチェックインしていないデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="c63bc-114">バージョンの状態を更新する</span><span class="sxs-lookup"><span data-stu-id="c63bc-114">Update version status</span></span>

<span data-ttu-id="c63bc-115">Microsoft は、毎月第 2 火曜日にセキュリティ更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="c63bc-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="c63bc-116">各リリースでは、既知のセキュリティの脆弱性に関する重要な更新プログラムが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="c63bc-117">Microsoft マネージド デスクトップ、管理対象デバイスの 95% が毎月最新の利用可能なセキュリティ更新プログラムで更新されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="c63bc-118">セキュリティ更新プログラムは、新しい脅威に緊急に対処するために、他の時点でリリースされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c63bc-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="c63bc-119">Microsoft マネージド デスクトップ同様の方法でこれらの更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="c63bc-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="c63bc-120">次の用語を使用して、セキュリティ更新プログラムのバージョンの状態を分類します。</span><span class="sxs-lookup"><span data-stu-id="c63bc-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="c63bc-121"><strong>Current:</strong> 現在の月にリリースされた更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="c63bc-122"><strong>前:</strong> 前月にリリースされた更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="c63bc-123"><strong>古い:</strong> 前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="c63bc-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="c63bc-124">[古い] カテゴリに<strong></strong>表示されるデバイスは少なく、人口が多い場合や人口が増加している場合は、調査を行う際に報告する必要があるMicrosoft マネージド デスクトップシステム上の問題を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c63bc-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="c63bc-125">展開の進行状況</span><span class="sxs-lookup"><span data-stu-id="c63bc-125">Deployment progress</span></span>

<span data-ttu-id="c63bc-126">各セキュリティ更新プログラムのリリース サイクルの開始時に、Microsoft マネージド デスクトップはデバイスの人口のスナップショットを取得し、展開ターゲットをその人口の 95% に設定します。</span><span class="sxs-lookup"><span data-stu-id="c63bc-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="c63bc-127">[ <strong>展開の進行状況]</strong> 領域には、更新プログラムの展開がリリースごとにこのターゲットをどれだけ満たしたのか追跡する、毎日更新された履歴傾向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="c63bc-128">このグラフには、アクティブな状態のデバイスだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="c63bc-129">このデータは、右上のドロップダウン メニューを使用して、以前の更新サイクルで表示できます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="c63bc-130">このメニューで選択した期間は、ページ全体のすべての情報に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="c63bc-131">[<strong>展開グループ別にアクティブ</strong>なデバイスを更新しました] 領域では、展開グループごとに更新プログラムのインストールの進行状況を示Microsoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="c63bc-132">[ <strong>対象となる日数]</strong> 領域には、現在のセキュリティ更新プログラムで更新されるデバイスの総数の 95% にかかった時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="c63bc-133">展開が進行中の間、この領域には<strong></strong>、選択した更新プログラムの 95% のターゲットに達するまで更新中が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="c63bc-134">デバイスの詳細領域</span><span class="sxs-lookup"><span data-stu-id="c63bc-134">Device details area</span></span>

<span data-ttu-id="c63bc-135">ダッシュボードの下部には、デバイスの状態やバージョンの更新の状態など、デバイスの[](#device-status)詳細情報を示[す表があります](#update-version-status)。</span><span class="sxs-lookup"><span data-stu-id="c63bc-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="c63bc-136">このリストを検索するか、リストに表示されている値でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="c63bc-136">You can search this list or filter it by any listed value.</span></span>


![デバイス名、割り当てられたユーザー、デバイスの状態、更新プログラムのバージョン、オペレーティング システムのバージョン、およびデバイスが最後に同期された日付の列を示すデバイスの詳細テーブル。](../../media/security-update-insights-device-table-sterile.png)
