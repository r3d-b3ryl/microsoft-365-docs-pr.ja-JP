---
title: Microsoft Defender for Endpoint デバイスリストの表示と整理
description: リストの並べ替え、フィルター処理、エクスポートなど、[デバイス] リストから使用できる機能について学習し、調査を強化します。
keywords: 並べ替え、フィルター、エクスポート、csv、デバイス名、ドメイン、最後に見た、内部 IP、正常性状態、アクティブなアラート、アクティブなマルウェア検出、脅威カテゴリ、確認アラート、ネットワーク、接続、マルウェア、種類、パスワード盗み、ランサムウェア、悪用、脅威、一般的なマルウェア、望ましくないソフトウェア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861577"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="e273c-104">Microsoft Defender for Endpoint Devices リストの表示と整理</span><span class="sxs-lookup"><span data-stu-id="e273c-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e273c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e273c-105">**Applies to:**</span></span>
- [<span data-ttu-id="e273c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e273c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e273c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e273c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e273c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e273c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e273c-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e273c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="e273c-110">[ **デバイス] リストには** 、アラートが生成されたネットワーク内のデバイスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e273c-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="e273c-111">既定では、キューには過去 30 日間に表示されたデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e273c-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="e273c-112">ドメイン、リスク レベル、OS プラットフォームなどの情報を一目で確認すると、最も危険にさらされているデバイスを簡単に識別できます。</span><span class="sxs-lookup"><span data-stu-id="e273c-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="e273c-113">デバイス リスト ビューをカスタマイズするために選択できるオプションは複数あります。</span><span class="sxs-lookup"><span data-stu-id="e273c-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="e273c-114">上部のナビゲーションでは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e273c-114">On the top navigation you can:</span></span>

- <span data-ttu-id="e273c-115">列の追加または削除</span><span class="sxs-lookup"><span data-stu-id="e273c-115">Add or remove columns</span></span>
- <span data-ttu-id="e273c-116">リスト全体を CSV 形式でエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e273c-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="e273c-117">ページごとに表示するアイテムの数を選択する</span><span class="sxs-lookup"><span data-stu-id="e273c-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="e273c-118">フィルターの適用</span><span class="sxs-lookup"><span data-stu-id="e273c-118">Apply filters</span></span>

<span data-ttu-id="e273c-119">オンボーディング プロセス中に、[ **デバイス** ] リストには、センサー データの報告を開始するデバイスが徐々に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e273c-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="e273c-120">このビューを使用して、オンボードエンドポイントをオンラインで追跡したり、オフライン分析用の CSV ファイルとして完全なエンドポイント リストをダウンロードしたりします。</span><span class="sxs-lookup"><span data-stu-id="e273c-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="e273c-121">デバイスリストをエクスポートすると、組織内のすべてのデバイスが含まれる。</span><span class="sxs-lookup"><span data-stu-id="e273c-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="e273c-122">組織の規模によっては、ダウンロードにかなりの時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e273c-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="e273c-123">リストを CSV 形式でエクスポートすると、フィルター処理されていない方法でデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e273c-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="e273c-124">CSV ファイルには、ビュー自体に適用されるフィルター処理に関係なく、組織内のすべてのデバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e273c-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![デバイスのリストを含むデバイスリストのイメージ](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="e273c-126">デバイスリストの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="e273c-126">Sort and filter the device list</span></span>

<span data-ttu-id="e273c-127">次のフィルターを適用して、アラートの一覧を制限し、より集中したビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="e273c-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="e273c-128">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="e273c-128">Risk level</span></span>

<span data-ttu-id="e273c-129">リスク レベルは、デバイス上のアクティブなアラートの種類と重大度などの要因の組み合わせに基づいて、デバイスの全体的なリスク評価を反映します。</span><span class="sxs-lookup"><span data-stu-id="e273c-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="e273c-130">アクティブなアラートを解決し、修復アクティビティを承認し、後続のアラートを抑制すると、リスク レベルが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e273c-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="e273c-131">露出レベル</span><span class="sxs-lookup"><span data-stu-id="e273c-131">Exposure level</span></span>

<span data-ttu-id="e273c-132">露出レベルは、保留中のセキュリティ推奨事項の累積的な影響に基づいて、デバイスの現在の露出を反映します。</span><span class="sxs-lookup"><span data-stu-id="e273c-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="e273c-133">可能なレベルは、低、中、高です。</span><span class="sxs-lookup"><span data-stu-id="e273c-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="e273c-134">露出が低いということは、デバイスが悪用の影響を受けやすいという意味です。</span><span class="sxs-lookup"><span data-stu-id="e273c-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="e273c-135">露出レベルに 「データが使用できない」と表示される場合は、次の理由が考えられません。</span><span class="sxs-lookup"><span data-stu-id="e273c-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="e273c-136">デバイスが 30 日以上レポートを停止しました 。その場合は非アクティブと見なされ、露出は計算されません</span><span class="sxs-lookup"><span data-stu-id="e273c-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="e273c-137">デバイス OS はサポートされていません - Microsoft Defender for Endpoint の最小 [要件を参照してください。](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e273c-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="e273c-138">古いエージェントを持つデバイス (非常に可能性が低い)</span><span class="sxs-lookup"><span data-stu-id="e273c-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="e273c-139">OS プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="e273c-139">OS Platform</span></span>

<span data-ttu-id="e273c-140">調査する OS プラットフォームのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="e273c-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="e273c-141">正常性の状態</span><span class="sxs-lookup"><span data-stu-id="e273c-141">Health state</span></span>

<span data-ttu-id="e273c-142">次のデバイスの正常性状態でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e273c-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="e273c-143">**Active** – センサー データをサービスにアクティブに報告しているデバイス。</span><span class="sxs-lookup"><span data-stu-id="e273c-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="e273c-144">**非** アクティブ – 7 日間以上信号の送信を完全に停止したデバイス。</span><span class="sxs-lookup"><span data-stu-id="e273c-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="e273c-145">**正しく構成されていない** – サービスとの通信に障害が生じ、センサー データを送信できないデバイス。</span><span class="sxs-lookup"><span data-stu-id="e273c-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="e273c-146">構成が正しく設定されていないデバイスは、さらに次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="e273c-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="e273c-147">センサー データなし</span><span class="sxs-lookup"><span data-stu-id="e273c-147">No sensor data</span></span>
  - <span data-ttu-id="e273c-148">通信障害</span><span class="sxs-lookup"><span data-stu-id="e273c-148">Impaired communications</span></span>

  <span data-ttu-id="e273c-149">構成が正しく設定されていないデバイスの問題に対処する方法の詳細については、「異常なセンサーを修正する」 [を参照してください](fix-unhealthy-sensors.md)。</span><span class="sxs-lookup"><span data-stu-id="e273c-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="e273c-150">ウイルス対策の状態</span><span class="sxs-lookup"><span data-stu-id="e273c-150">Antivirus status</span></span>

<span data-ttu-id="e273c-151">ウイルス対策の状態でデバイスをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e273c-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="e273c-152">アクティブな Windows 10 デバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e273c-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="e273c-153">**無効** - ウイルス&保護がオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e273c-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="e273c-154">**[報告しない** ] - ウイルス&保護が報告されていない場合。</span><span class="sxs-lookup"><span data-stu-id="e273c-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="e273c-155">**[更新されません** ] - ウイルス&保護が最新ではない場合。</span><span class="sxs-lookup"><span data-stu-id="e273c-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="e273c-156">詳細については、「脅威と [脆弱性管理ダッシュボード&を参照してください](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="e273c-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="e273c-157">脅威の軽減の状態</span><span class="sxs-lookup"><span data-stu-id="e273c-157">Threat mitigation status</span></span>

<span data-ttu-id="e273c-158">特定の脅威の影響を受ける可能性のあるデバイスを表示するには、ドロップダウン メニューから脅威を選択し、軽減する必要がある脆弱性の側面を選択します。</span><span class="sxs-lookup"><span data-stu-id="e273c-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="e273c-159">特定の脅威の詳細については、「Threat [analytics」を参照してください](threat-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="e273c-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="e273c-160">軽減策の詳細については [、「Threat &脆弱性管理」を参照してください](next-gen-threat-and-vuln-mgt.md)。</span><span class="sxs-lookup"><span data-stu-id="e273c-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="e273c-161">Windows 10 バージョン</span><span class="sxs-lookup"><span data-stu-id="e273c-161">Windows 10 version</span></span>

<span data-ttu-id="e273c-162">調査する Windows 10 バージョンのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="e273c-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="e273c-163">タグ & グループ</span><span class="sxs-lookup"><span data-stu-id="e273c-163">Tags & Groups</span></span>

<span data-ttu-id="e273c-164">個々のデバイスに追加したグループ化とタグ付けに基づいてリストをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e273c-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="e273c-165">「デバイス [タグの作成と管理」および「](machine-tags.md) デバイス [グループの作成と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="e273c-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e273c-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="e273c-166">Related topics</span></span>

- [<span data-ttu-id="e273c-167">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="e273c-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
