---
title: Microsoft 365 Defender で高度な検索クエリ結果を処理する
description: Microsoft 365 Defender での高度な検索によって返されるクエリ結果を利用する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、視覚化、グラフ、フィルター、ドリルダウン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952598"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="57f42-104">高度な検索クエリの結果を処理する</span><span class="sxs-lookup"><span data-stu-id="57f42-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57f42-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="57f42-105">**Applies to:**</span></span>
- <span data-ttu-id="57f42-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57f42-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="57f42-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="57f42-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="57f42-108">高度な検索クエリを[](advanced-hunting-overview.md)作成して非常に正確な情報を取得することもできますが、クエリの結果を処理して、さらに詳しい分析情報を得て、特定のアクティビティとインジケーターを調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="57f42-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="57f42-109">クエリ結果に対して次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="57f42-110">結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="57f42-110">View results as a table or chart</span></span>
- <span data-ttu-id="57f42-111">表とグラフのエクスポート</span><span class="sxs-lookup"><span data-stu-id="57f42-111">Export tables and charts</span></span>
- <span data-ttu-id="57f42-112">詳細なエンティティ情報にドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="57f42-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="57f42-113">結果から直接クエリを調整するか、フィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="57f42-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="57f42-114">クエリ結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="57f42-114">View query results as a table or chart</span></span>
<span data-ttu-id="57f42-115">既定では、高度な検索ではクエリ結果が表形式データとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="57f42-116">グラフと同じデータを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="57f42-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="57f42-117">高度な検索では、次のビューがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57f42-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="57f42-118">ビューの種類</span><span class="sxs-lookup"><span data-stu-id="57f42-118">View type</span></span> | <span data-ttu-id="57f42-119">説明</span><span class="sxs-lookup"><span data-stu-id="57f42-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="57f42-120">**表**</span><span class="sxs-lookup"><span data-stu-id="57f42-120">**Table**</span></span> | <span data-ttu-id="57f42-121">クエリ結果を表形式で表示する</span><span class="sxs-lookup"><span data-stu-id="57f42-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="57f42-122">**縦棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-122">**Column chart**</span></span> | <span data-ttu-id="57f42-123">X 軸上の一連の一意の項目を、高さが別のフィールドの数値を表す垂直バーとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="57f42-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="57f42-124">**積み上げ列グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-124">**Stacked column chart**</span></span> | <span data-ttu-id="57f42-125">x 軸上の一連の一意のアイテムを、高さが 1 つ以上の他のフィールドの数値を表す積み上げ縦棒としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="57f42-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="57f42-126">**円グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-126">**Pie chart**</span></span> | <span data-ttu-id="57f42-127">一意のアイテムを表す断面円グラフをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="57f42-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="57f42-128">各円グラフのサイズは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="57f42-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="57f42-129">**ドーナツ グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-129">**Donut chart**</span></span> | <span data-ttu-id="57f42-130">一意のアイテムを表す断面円弧をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="57f42-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="57f42-131">各円弧の長さは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="57f42-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="57f42-132">**折れ線グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-132">**Line chart**</span></span> | <span data-ttu-id="57f42-133">一連の一意の項目の数値をプロットし、プロットされた値を接続する</span><span class="sxs-lookup"><span data-stu-id="57f42-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="57f42-134">**散布図**</span><span class="sxs-lookup"><span data-stu-id="57f42-134">**Scatter chart**</span></span> | <span data-ttu-id="57f42-135">一連の一意の項目の数値をプロットする</span><span class="sxs-lookup"><span data-stu-id="57f42-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="57f42-136">**エリア グラフ**</span><span class="sxs-lookup"><span data-stu-id="57f42-136">**Area chart**</span></span> | <span data-ttu-id="57f42-137">一連の一意の項目の数値をプロットし、プロットされた値の下のセクションを塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="57f42-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="57f42-138">効果的なグラフのクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="57f42-138">Construct queries for effective charts</span></span>
<span data-ttu-id="57f42-139">グラフをレンダリングする場合、高度な検索では、関心のある列と集計する数値が自動的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="57f42-140">意味のあるグラフを取得するには、表示する特定の値を返すクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="57f42-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="57f42-141">サンプル クエリと結果のグラフを次に示します。</span><span class="sxs-lookup"><span data-stu-id="57f42-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="57f42-142">重大度別のアラート</span><span class="sxs-lookup"><span data-stu-id="57f42-142">Alerts by severity</span></span>
<span data-ttu-id="57f42-143">グラフを `summarize` 作成する値の数値カウントを取得するには、演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="57f42-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="57f42-144">以下のクエリでは、演算子 `summarize` を使用して重大度別のアラート数を取得します。</span><span class="sxs-lookup"><span data-stu-id="57f42-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="57f42-145">結果をレンダリングすると、各重大度値が個別の列として列グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="57f42-146">![列グラフとして表示される高度な検索クエリ結果の画像 重要度別のアラートのクエリ結果を列グラフ ](../../media/advanced-hunting-column-chart.jpg)
 *として表示する*</span><span class="sxs-lookup"><span data-stu-id="57f42-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="57f42-147">オペレーティング システムによるアラートの重大度</span><span class="sxs-lookup"><span data-stu-id="57f42-147">Alert severity by operating system</span></span>
<span data-ttu-id="57f42-148">演算子を使用して、 `summarize` 複数のフィールドの値をグラフ化する結果を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="57f42-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="57f42-149">たとえば、アラートの重大度がオペレーティング システム (OS) 全体に分散される方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="57f42-150">次のクエリでは、演算子を使用してテーブルから OS 情報を取得し、列と列の両方の値をカウント `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` します。</span><span class="sxs-lookup"><span data-stu-id="57f42-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="57f42-151">これらの結果は、積み上げ列グラフを使用して最適に視覚化されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="57f42-152">![積み上げグラフとして表示される高度な検索クエリ結果のイメージ OS によるアラートのクエリ結果と、積み上げグラフとして ](../../media/advanced-hunting-stacked-chart.jpg)
 *表示* される重大度</span><span class="sxs-lookup"><span data-stu-id="57f42-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="57f42-153">上位 10 個の送信者ドメインのフィッシングメール</span><span class="sxs-lookup"><span data-stu-id="57f42-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="57f42-154">有限ではない値のリストを扱う場合は、演算子を使用して、最も多くのインスタンスを持つ値のみを `Top` グラフ化できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="57f42-155">たとえば、フィッシングメールが最も多い上位 10 個の送信者ドメインを取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="57f42-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="57f42-156">円グラフ ビューを使用して、上位ドメイン全体の分布を効果的に表示します。</span><span class="sxs-lookup"><span data-stu-id="57f42-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="57f42-157">![上位の送信者ドメイン間でのフィッシングメールの配布を示す円グラフとして表示される高度な検索クエリ結果 ](../../media/advanced-hunting-pie-chart.jpg)
 *の画像*</span><span class="sxs-lookup"><span data-stu-id="57f42-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="57f42-158">時間の間のファイル アクティビティ</span><span class="sxs-lookup"><span data-stu-id="57f42-158">File activities over time</span></span>
<span data-ttu-id="57f42-159">演算子を `summarize` 関数と一緒に使用すると、時間のとともに特定のインジケーター `bin()` に関連するイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="57f42-160">以下のクエリは、ファイルに関連するイベントを 30 分間隔でカウントして、そのファイルに関連するアクティビティの `invoice.doc` スパイクを表示します。</span><span class="sxs-lookup"><span data-stu-id="57f42-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="57f42-161">以下の線グラフは、以下を含むより多くのアクティビティを含む期間を明確に強調表示します `invoice.doc` 。</span><span class="sxs-lookup"><span data-stu-id="57f42-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="57f42-162">![ファイルに関連するイベントの時間の数を示す線グラフとして表示される高度な検索クエリ ](../../media/advanced-hunting-line-chart.jpg)
 *結果のイメージ*</span><span class="sxs-lookup"><span data-stu-id="57f42-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="57f42-163">表とグラフのエクスポート</span><span class="sxs-lookup"><span data-stu-id="57f42-163">Export tables and charts</span></span>
<span data-ttu-id="57f42-164">クエリを実行した後、[エクスポート] **を選択** して、結果をローカル ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="57f42-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="57f42-165">選択したビューは、結果のエクスポート方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="57f42-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="57f42-166">**テーブル ビュー** - クエリ結果は表形式で Microsoft Excel ブックとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="57f42-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="57f42-167">**任意のグラフ** - クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="57f42-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="57f42-168">クエリ結果からドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="57f42-168">Drill down from query results</span></span>
<span data-ttu-id="57f42-169">クエリ結果のレコードをすばやく検査するには、対応する行を選択して [レコードの検査] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="57f42-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="57f42-170">パネルには、選択したレコードに基づいて次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="57f42-171">**アセット** - レコード内にある主な資産 (メールボックス、デバイス、およびユーザー) の要約ビューで、リスクや露出レベルなどの利用可能な情報が充実しています。</span><span class="sxs-lookup"><span data-stu-id="57f42-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="57f42-172">**プロセス ツリー** - プロセス情報を含むレコードに対して生成され、利用可能なコンテキスト情報を使用して強化されます。一般に、より多くの列を返すクエリを実行すると、より豊富なプロセス ツリーが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57f42-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="57f42-173">**すべての詳細** - レコード内の列のすべての値</span><span class="sxs-lookup"><span data-stu-id="57f42-173">**All details** — all the values from the columns in the record</span></span>  

![選択したレコードの画像(レコードを検査するパネル付き)](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="57f42-175">コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果内の特定のエンティティに関する詳細情報を表示するには、エンティティ識別子を選択して、そのエンティティの詳細なプロファイル ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="57f42-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="57f42-176">結果からクエリを絞り込む</span><span class="sxs-lookup"><span data-stu-id="57f42-176">Tweak your queries from the results</span></span>
<span data-ttu-id="57f42-177">結果セットの値を右クリックすると、クエリがすばやく強化されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="57f42-178">次のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-178">You can use the options to:</span></span>

- <span data-ttu-id="57f42-179">選択した値 (`==`) を明示的に検索する</span><span class="sxs-lookup"><span data-stu-id="57f42-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="57f42-180">選択した値をクエリ (`!=`) から除外する </span><span class="sxs-lookup"><span data-stu-id="57f42-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="57f42-181">クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する</span><span class="sxs-lookup"><span data-stu-id="57f42-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高度な検索結果セットのイメージ](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="57f42-183">クエリ結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="57f42-183">Filter the query results</span></span>
<span data-ttu-id="57f42-184">右に表示されるフィルターは、結果セットの要約を提供します。</span><span class="sxs-lookup"><span data-stu-id="57f42-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="57f42-185">各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="57f42-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="57f42-186">クエリを絞り込むには、含める値または除外する値のボタンを選択し、[クエリの実行 `+` `-` ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="57f42-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="57f42-188">フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="57f42-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="57f42-189">この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="57f42-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="57f42-190">[Microsoft 365 Defender をオンに](m365d-enable.md) し、より多くのデータ ソースを使用して脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="57f42-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="57f42-191">「Advanced [Hunting queries](advanced-hunting-migrate-from-mde.md)from Microsoft Defender for Endpoint 」 の手順に従って、高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に移動できます。</span><span class="sxs-lookup"><span data-stu-id="57f42-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="57f42-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="57f42-192">Related topics</span></span>
- [<span data-ttu-id="57f42-193">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="57f42-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="57f42-194">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="57f42-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="57f42-195">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="57f42-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="57f42-196">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="57f42-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="57f42-197">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="57f42-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="57f42-198">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="57f42-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="57f42-199">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="57f42-199">Custom detections overview</span></span>](custom-detections-overview.md)
