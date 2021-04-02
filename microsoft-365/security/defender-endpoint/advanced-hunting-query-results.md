---
title: Microsoft Defender ATP で高度な検索クエリ結果を処理する
description: Microsoft Defender ATP での高度な検索によって返されるクエリ結果を有効にする
keywords: 高度な狩猟、脅威狩り、サイバー脅威の狩猟、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、視覚化、グラフ、フィルター、ドリルダウン
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
ms.openlocfilehash: 4abec618a79704804b5e3349f5c4c5a4827d35ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499440"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="8bfa6-104">高度な検索クエリの結果を処理する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bfa6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-105">**Applies to:**</span></span>
- [<span data-ttu-id="8bfa6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8bfa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="8bfa6-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8bfa6-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8bfa6-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="8bfa6-109">高度な検索クエリを[](advanced-hunting-overview.md)作成して非常に正確な情報を取得することもできますが、クエリの結果を処理して、さらに詳しい分析情報を得て、特定のアクティビティとインジケーターを調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-109">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="8bfa6-110">クエリ結果に対して次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-110">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="8bfa6-111">結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-111">View results as a table or chart</span></span>
- <span data-ttu-id="8bfa6-112">表とグラフのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8bfa6-112">Export tables and charts</span></span>
- <span data-ttu-id="8bfa6-113">詳細なエンティティ情報にドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="8bfa6-113">Drill down to detailed entity information</span></span>
- <span data-ttu-id="8bfa6-114">結果から直接クエリを調整するか、フィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-114">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="8bfa6-115">クエリ結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-115">View query results as a table or chart</span></span>
<span data-ttu-id="8bfa6-116">既定では、高度な検索ではクエリ結果が表形式データとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-116">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="8bfa6-117">グラフと同じデータを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-117">You can also display the same data as a chart.</span></span> <span data-ttu-id="8bfa6-118">高度な検索では、次のビューがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-118">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="8bfa6-119">ビューの種類</span><span class="sxs-lookup"><span data-stu-id="8bfa6-119">View type</span></span> | <span data-ttu-id="8bfa6-120">説明</span><span class="sxs-lookup"><span data-stu-id="8bfa6-120">Description</span></span> |
| -- | -- |
| <span data-ttu-id="8bfa6-121">**表**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-121">**Table**</span></span> | <span data-ttu-id="8bfa6-122">クエリ結果を表形式で表示する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-122">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="8bfa6-123">**縦棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-123">**Column chart**</span></span> | <span data-ttu-id="8bfa6-124">X 軸上の一連の一意の項目を、高さが別のフィールドの数値を表す垂直バーとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-124">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="8bfa6-125">**積み上げ列グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-125">**Stacked column chart**</span></span> | <span data-ttu-id="8bfa6-126">x 軸上の一連の一意のアイテムを、高さが 1 つ以上の他のフィールドの数値を表す積み上げ縦棒としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-126">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="8bfa6-127">**円グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-127">**Pie chart**</span></span> | <span data-ttu-id="8bfa6-128">一意のアイテムを表す断面円グラフをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-128">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="8bfa6-129">各円グラフのサイズは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-129">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="8bfa6-130">**ドーナツ グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-130">**Donut chart**</span></span> | <span data-ttu-id="8bfa6-131">一意のアイテムを表す断面円弧をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-131">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="8bfa6-132">各円弧の長さは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-132">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="8bfa6-133">**折れ線グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-133">**Line chart**</span></span> | <span data-ttu-id="8bfa6-134">一連の一意の項目の数値をプロットし、プロットされた値を接続する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-134">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="8bfa6-135">**散布図**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-135">**Scatter chart**</span></span> | <span data-ttu-id="8bfa6-136">一連の一意の項目の数値をプロットする</span><span class="sxs-lookup"><span data-stu-id="8bfa6-136">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="8bfa6-137">**エリア グラフ**</span><span class="sxs-lookup"><span data-stu-id="8bfa6-137">**Area chart**</span></span> | <span data-ttu-id="8bfa6-138">一連の一意の項目の数値をプロットし、プロットされた値の下のセクションを塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="8bfa6-138">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="8bfa6-139">効果的なグラフのクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-139">Construct queries for effective charts</span></span>
<span data-ttu-id="8bfa6-140">グラフをレンダリングする場合、高度な検索では、関心のある列と集計する数値が自動的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-140">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="8bfa6-141">意味のあるグラフを取得するには、表示する特定の値を返すクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-141">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="8bfa6-142">サンプル クエリと結果のグラフを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-142">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="8bfa6-143">重大度別のアラート</span><span class="sxs-lookup"><span data-stu-id="8bfa6-143">Alerts by severity</span></span>
<span data-ttu-id="8bfa6-144">グラフを `summarize` 作成する値の数値カウントを取得するには、演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-144">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="8bfa6-145">以下のクエリでは、演算子 `summarize` を使用して重大度別のアラート数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-145">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
<span data-ttu-id="8bfa6-146">結果をレンダリングすると、各重大度値が個別の列として列グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-146">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="8bfa6-147">![列グラフとして表示される高度な検索クエリ結果の画像 重要度別のアラートのクエリ結果を列グラフ ](images/advanced-hunting-column-chart.jpg)
 *として表示する*</span><span class="sxs-lookup"><span data-stu-id="8bfa6-147">![Image of advanced hunting query results displayed as a column chart](images/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="8bfa6-148">オペレーティング システムによるアラートの重大度</span><span class="sxs-lookup"><span data-stu-id="8bfa6-148">Alert severity by operating system</span></span>
<span data-ttu-id="8bfa6-149">演算子を使用して、 `summarize` 複数のフィールドの値をグラフ化する結果を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-149">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="8bfa6-150">たとえば、アラートの重大度がオペレーティング システム (OS) 全体に分散される方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-150">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="8bfa6-151">次のクエリでは、演算子を使用してテーブルから OS 情報を取得し、列と列の両方の値をカウント `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-151">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
<span data-ttu-id="8bfa6-152">これらの結果は、積み上げ列グラフを使用して最適に視覚化されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-152">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="8bfa6-153">![積み上げグラフとして表示される高度な検索クエリ結果のイメージ OS によるアラートのクエリ結果と、積み上げグラフとして ](images/advanced-hunting-stacked-chart.jpg)
 *表示* される重大度</span><span class="sxs-lookup"><span data-stu-id="8bfa6-153">![Image of advanced hunting query results displayed as a stacked chart](images/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="top-ten-device-groups-with-alerts"></a><span data-ttu-id="8bfa6-154">アラートを含む上位 10 個のデバイス グループ</span><span class="sxs-lookup"><span data-stu-id="8bfa6-154">Top ten device groups with alerts</span></span>
<span data-ttu-id="8bfa6-155">有限ではない値のリストを扱う場合は、演算子を使用して、最も多くのインスタンスを持つ値のみを `Top` グラフ化できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-155">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="8bfa6-156">たとえば、アラートが最も多い上位 10 個のデバイス グループを取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-156">For example, to get the top ten device groups with the most alerts, use the query below:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
<span data-ttu-id="8bfa6-157">上位グループ間の分布を効果的に表示するには、円グラフ ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-157">Use the pie chart view to effectively show distribution across the top groups:</span></span>

<span data-ttu-id="8bfa6-158">![デバイス グループ間のアラートの分布を示す円グラフとして表示される高度な検索 ](images/advanced-hunting-pie-chart.jpg)
 *クエリ結果のイメージ*</span><span class="sxs-lookup"><span data-stu-id="8bfa6-158">![Image of advanced hunting query results displayed as a pie chart](images/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of alerts across device groups*</span></span>

#### <a name="malware-detections-over-time"></a><span data-ttu-id="8bfa6-159">マルウェアの検出時間の過ぎ</span><span class="sxs-lookup"><span data-stu-id="8bfa6-159">Malware detections over time</span></span>
<span data-ttu-id="8bfa6-160">演算子を `summarize` 関数と一緒に使用すると、時間のとともに特定のインジケーター `bin()` に関連するイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-160">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="8bfa6-161">以下のクエリは、EICAR テスト ファイルの検出を 30 分間隔でカウントし、そのファイルの検出のスパイクを示します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-161">The query below counts detections of an EICAR test file at 30 minute intervals to show spikes in detections of that file:</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="8bfa6-162">以下の線グラフは、テスト マルウェアの検出が多い期間を明確に強調表示しています。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-162">The line chart below clearly highlights time periods with more detections of the test malware:</span></span> 

<span data-ttu-id="8bfa6-163">![時間の間にテスト マルウェアの検出数を示す線グラフとして表示される高度な検索クエリ結果 ](images/advanced-hunting-line-chart.jpg)
 *の画像*</span><span class="sxs-lookup"><span data-stu-id="8bfa6-163">![Image of advanced hunting query results displayed as a line chart](images/advanced-hunting-line-chart.jpg)
*Line chart showing the number of detections of a test malware over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="8bfa6-164">表とグラフのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8bfa6-164">Export tables and charts</span></span>
<span data-ttu-id="8bfa6-165">クエリを実行した後、[エクスポート] **を選択** して、結果をローカル ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-165">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="8bfa6-166">選択したビューは、結果のエクスポート方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-166">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="8bfa6-167">**テーブル ビュー** - クエリ結果は表形式で Microsoft Excel ブックとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-167">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="8bfa6-168">**任意のグラフ** - クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-168">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="8bfa6-169">クエリ結果からドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="8bfa6-169">Drill down from query results</span></span>
<span data-ttu-id="8bfa6-170">クエリ結果で、デバイス、ファイル、ユーザー、IP アドレス、URL などのエンティティに関する詳細を表示するには、エンティティ識別子をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-170">To view more information about entities, such as devices, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="8bfa6-171">これにより、選択したエンティティの詳細なプロファイル ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-171">This opens a detailed profile page for the selected entity.</span></span>

<span data-ttu-id="8bfa6-172">クエリ結果のレコードをすばやく検査するには、対応する行を選択して [レコードの検査] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-172">To quickly inspect a record in your query results, select the corresponding row to open the Inspect record panel.</span></span> <span data-ttu-id="8bfa6-173">パネルには、選択したレコードに基づいて次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-173">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="8bfa6-174">**アセット** - レコード内に見つかった主な資産 (メールボックス、デバイス、およびユーザー) の要約ビューで、リスクや露出レベルなどの利用可能な情報が充実しています。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-174">**Assets** — A summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="8bfa6-175">**プロセス ツリー** : プロセス情報を含むレコード用に生成され、利用可能なコンテキスト情報を使用して強化されたグラフ。一般に、より多くの列を返すクエリを実行すると、より豊富なプロセス ツリーが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-175">**Process tree** — A chart generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="8bfa6-176">**[すべての詳細** ] - レコード内の列のすべての値を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-176">**All details** — Lists all the values from the columns in the record</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="8bfa6-177">結果からクエリを絞り込む</span><span class="sxs-lookup"><span data-stu-id="8bfa6-177">Tweak your queries from the results</span></span>
<span data-ttu-id="8bfa6-178">結果セットの値を右クリックすると、クエリがすばやく強化されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-178">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="8bfa6-179">次のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-179">You can use the options to:</span></span>

- <span data-ttu-id="8bfa6-180">選択した値 (`==`) を明示的に検索する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-180">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="8bfa6-181">選択した値をクエリ (`!=`) から除外する </span><span class="sxs-lookup"><span data-stu-id="8bfa6-181">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="8bfa6-182">クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-182">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高度な検索結果セットのイメージ](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="8bfa6-184">クエリ結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-184">Filter the query results</span></span>
<span data-ttu-id="8bfa6-185">右側のウィンドウに表示されるフィルターは、結果セットの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-185">The filters displayed in the right pane provide a summary of the result set.</span></span> <span data-ttu-id="8bfa6-186">各列には、ウィンドウ内に独自のセクションが含まれます。各列には、その列にある値とインスタンスの数が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-186">Every column has its own section in the pane, each of which lists the values found in that column, and the number of instances.</span></span>

<span data-ttu-id="8bfa6-187">含める値または除外する値のボタンを選択して、クエリ `+` `-` を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-187">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude.</span></span> <span data-ttu-id="8bfa6-188">次に、[クエリの **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-188">Then select **Run query**.</span></span>

![高度な捜索フィルターの画像](images/advanced-hunting-filter.png)

<span data-ttu-id="8bfa6-190">フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="8bfa6-190">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bfa6-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfa6-191">Related topics</span></span>
- [<span data-ttu-id="8bfa6-192">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="8bfa6-192">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8bfa6-193">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="8bfa6-193">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8bfa6-194">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-194">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8bfa6-195">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-195">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="8bfa6-196">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="8bfa6-196">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8bfa6-197">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="8bfa6-197">Custom detections overview</span></span>](overview-custom-detections.md)
