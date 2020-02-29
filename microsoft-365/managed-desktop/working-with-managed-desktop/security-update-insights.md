---
title: Windows セキュリティ更新プログラムの分析情報
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341257"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="8fbac-103">Windows セキュリティ更新プログラムの分析情報</span><span class="sxs-lookup"><span data-stu-id="8fbac-103">Windows security update insights</span></span>
<span data-ttu-id="8fbac-104">このビューには、Microsoft マネージドデスクトップデバイスのセキュリティ更新プログラムの状態の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="8fbac-105">利用状況データを表示するには、[ <strong>Windows セキュリティの更新</strong>] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fbac-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![[Windows セキュリティの更新] ウィンドウ: デバイスの状態の棒グラフ、左側の列の更新バージョン、センター列の時間の経過に伴う展開の進行状況の更新、および展開グループ別のアクティブなデバイスの割合、および95% 展開に達するまでの日数。右の列のターゲット。](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="8fbac-107">デバイスの状態</span><span class="sxs-lookup"><span data-stu-id="8fbac-107">Device status</span></span>

<span data-ttu-id="8fbac-108">Windows Update によってデバイスが更新されるようにするには、インターネットに接続して、少なくとも6時間は休止しないようにする必要があります。2つは連続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fbac-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="8fbac-109">デバイスが接続され、休止状態ではない限り、"使用中" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="8fbac-110">これらの要件を満たしていないデバイスは更新される可能性がありますが、それに対応するデバイスが更新される可能性が高いことを示しています。</span><span class="sxs-lookup"><span data-stu-id="8fbac-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="8fbac-111">Windows Update のコンテキストで、次の用語を使用してデバイスアクティビティを分類します。</span><span class="sxs-lookup"><span data-stu-id="8fbac-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="8fbac-112"><strong>アクティブ:</strong>最新のセキュリティ更新プログラムのリリースに対して少なくとも6時間 (連続) 使用されているデバイス。少なくとも5日ごとに Microsoft Intune を使用してチェックインしたデバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="8fbac-113"><strong>同期済み:</strong>過去28日以内に Intune でチェックインされたデバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="8fbac-114"><strong>同期がありません:</strong>過去28日間に Intune でチェックイン<i>されていない</i>デバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="8fbac-115">バージョン状態の更新</span><span class="sxs-lookup"><span data-stu-id="8fbac-115">Update version status</span></span>

<span data-ttu-id="8fbac-116">Microsoft は、毎月第2火曜日にセキュリティ更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="8fbac-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="8fbac-117">各リリースは、既知のセキュリティの脆弱性に対する重要な更新プログラムを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fbac-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="8fbac-118">Microsoft マネージドデスクトップでは、管理対象デバイスの95% が、毎月最新の利用可能なセキュリティ更新プログラムで更新されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="8fbac-119">セキュリティ更新プログラムは、新しい脅威に緊急に対処するために、他の時間にリリースされることがあります。</span><span class="sxs-lookup"><span data-stu-id="8fbac-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="8fbac-120">Microsoft マネージドデスクトップでは、これらの更新プログラムは同様の方法で展開されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="8fbac-121">セキュリティ更新プログラムのバージョンの状態を、次の条項に分類します。</span><span class="sxs-lookup"><span data-stu-id="8fbac-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="8fbac-122"><strong>Current:</strong>現在の月にリリースされた更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="8fbac-123"><strong>以前:</strong>前月にリリースされた更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="8fbac-124"><strong>以前:</strong>前月より前にリリースされたセキュリティ更新プログラムを実行しているデバイス</span><span class="sxs-lookup"><span data-stu-id="8fbac-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="8fbac-125"><strong>古い</strong>カテゴリに含まれるデバイスが少ない--大量または増加している場合は、調査できるように Microsoft マネージドデスクトップに報告する必要がある体系的な問題を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fbac-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="8fbac-126">展開の進行状況</span><span class="sxs-lookup"><span data-stu-id="8fbac-126">Deployment progress</span></span>

<span data-ttu-id="8fbac-127">各セキュリティ更新プログラムのリリースサイクルの開始時に、Microsoft マネージドデスクトップはデバイスの作成のスナップショットを取得し、その展開ターゲットをそのカタログ作成の95% に設定します。</span><span class="sxs-lookup"><span data-stu-id="8fbac-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="8fbac-128">[<strong>展開の進行状況</strong>] 領域には、過去の傾向が表示され、更新プログラムの展開が各リリースのこのターゲットをどれだけ満たしているかが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="8fbac-129">このグラフには、アクティブな状態のデバイスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="8fbac-130">右上のドロップダウンメニューを使用すると、このデータを以前の更新サイクルに対して表示できます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="8fbac-131">このメニューで選択した期間は、ページ全体のすべての情報に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="8fbac-132">「<strong>更新されたアクティブなデバイス別展開グループ</strong>」領域には、Microsoft 管理対象デスクトップ展開グループごとに、更新プログラムのインストールの進行状況が表示されるため、別のビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="8fbac-133">[<strong>ターゲットに</strong>なるまでの日数] 領域には、現在のセキュリティ更新プログラムによって更新されるデバイスの合計数の95% にかかった時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="8fbac-134">展開の進行中は、選択した更新プログラムの95% が達成されるまで、この領域は更新された<strong>まま</strong>になります。</span><span class="sxs-lookup"><span data-stu-id="8fbac-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="8fbac-135">デバイスの詳細領域</span><span class="sxs-lookup"><span data-stu-id="8fbac-135">Device details area</span></span>

<span data-ttu-id="8fbac-136">ダッシュボードの下部には、デバイスの[状態](#device-status)や[更新バージョンの状態](#update-version-status)など、デバイスの詳細情報を示す表が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="8fbac-137">このリストを検索したり、リストされた値でフィルター処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8fbac-137">You can search this list or filter it by any listed value.</span></span>


![デバイスの詳細表。デバイス名、割り当てられているユーザー、デバイスの状態、更新バージョン、オペレーティングシステムのバージョン、およびデバイスが最後に同期された日付が表示されます。](../../media/security-update-insights-device-table-sterile.png)
