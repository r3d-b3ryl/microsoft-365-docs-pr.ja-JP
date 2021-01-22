---
title: Microsoft 365 Defender で高度な検索クエリ結果を処理する
description: Microsoft 365 Defender の高度な検索によって返されるクエリ結果を利用する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection、視覚化、グラフ、フィルター、ドリルダウン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932324"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="e4a59-104">高度な検索クエリ結果を処理する</span><span class="sxs-lookup"><span data-stu-id="e4a59-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e4a59-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e4a59-105">**Applies to:**</span></span>
- <span data-ttu-id="e4a59-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4a59-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e4a59-107">高度な検索クエリを[](advanced-hunting-overview.md)作成して非常に正確な情報を返す一方で、クエリ結果を使用して詳細な洞察を得て、特定のアクティビティとインジケーターを調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="e4a59-108">クエリ結果に対して次のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="e4a59-109">結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="e4a59-109">View results as a table or chart</span></span>
- <span data-ttu-id="e4a59-110">表とグラフをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e4a59-110">Export tables and charts</span></span>
- <span data-ttu-id="e4a59-111">詳細なエンティティ情報へのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="e4a59-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="e4a59-112">結果からクエリを直接調整するか、フィルターを適用する</span><span class="sxs-lookup"><span data-stu-id="e4a59-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="e4a59-113">クエリ結果をテーブルまたはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="e4a59-113">View query results as a table or chart</span></span>
<span data-ttu-id="e4a59-114">既定では、高度な検索ではクエリ結果が表形式データとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="e4a59-115">グラフと同じデータを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="e4a59-116">高度な検索では、次のビューがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="e4a59-117">ビューの種類</span><span class="sxs-lookup"><span data-stu-id="e4a59-117">View type</span></span> | <span data-ttu-id="e4a59-118">説明</span><span class="sxs-lookup"><span data-stu-id="e4a59-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="e4a59-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="e4a59-119">**Table**</span></span> | <span data-ttu-id="e4a59-120">クエリ結果を表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="e4a59-121">**縦棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="e4a59-121">**Column chart**</span></span> | <span data-ttu-id="e4a59-122">x 軸上の一連の一意の項目を、高さが別のフィールドの数値を表す垂直バーとしてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="e4a59-123">**積み上げ棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="e4a59-123">**Stacked column chart**</span></span> | <span data-ttu-id="e4a59-124">x 軸上の一連の一意の項目を、高さが 1 つ以上の他のフィールドの数値を表す積み上げ縦棒としてレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="e4a59-125">**円グラフ**</span><span class="sxs-lookup"><span data-stu-id="e4a59-125">**Pie chart**</span></span> | <span data-ttu-id="e4a59-126">一意の項目を表すパイをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="e4a59-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="e4a59-127">各円グラフのサイズは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="e4a59-128">**ドーナツ グラフ**</span><span class="sxs-lookup"><span data-stu-id="e4a59-128">**Donut chart**</span></span> | <span data-ttu-id="e4a59-129">一意のアイテムを表す円弧をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="e4a59-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="e4a59-130">各円弧の長さは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="e4a59-131">**折れ線グラフ**</span><span class="sxs-lookup"><span data-stu-id="e4a59-131">**Line chart**</span></span> | <span data-ttu-id="e4a59-132">一連の一意のアイテムの数値をプロットし、プロットされた値を接続します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="e4a59-133">**散布図**</span><span class="sxs-lookup"><span data-stu-id="e4a59-133">**Scatter chart**</span></span> | <span data-ttu-id="e4a59-134">一連の一意のアイテムの数値をプロットします。</span><span class="sxs-lookup"><span data-stu-id="e4a59-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="e4a59-135">**エリア チャート**</span><span class="sxs-lookup"><span data-stu-id="e4a59-135">**Area chart**</span></span> | <span data-ttu-id="e4a59-136">一連の一意のアイテムの数値をプロットし、プロットされた値の下のセクションを塗りつぶしる</span><span class="sxs-lookup"><span data-stu-id="e4a59-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="e4a59-137">効果的なグラフのクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="e4a59-137">Construct queries for effective charts</span></span>
<span data-ttu-id="e4a59-138">グラフをレンダリングする場合、高度な検索では、関心のある列と集計する数値が自動的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="e4a59-139">意味のあるグラフを取得するには、視覚化する特定の値を返すクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="e4a59-140">次に、サンプル クエリと結果のグラフを示します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="e4a59-141">重大度別のアラート</span><span class="sxs-lookup"><span data-stu-id="e4a59-141">Alerts by severity</span></span>
<span data-ttu-id="e4a59-142">演算子を `summarize` 使用して、グラフを作成する値の数値カウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="e4a59-143">次のクエリでは、演算子 `summarize` を使用して重大度別のアラート数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="e4a59-144">結果をレンダリングする場合、列グラフには各重要度の値が個別の列として表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="e4a59-145">![高度な検索クエリ結果が、重大度別のアラートに対する列グラフクエリ結果として表示された、列 ](../../media/advanced-hunting-column-chart.jpg)
 *グラフとして表示される画像*</span><span class="sxs-lookup"><span data-stu-id="e4a59-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="e4a59-146">オペレーティング システム別のアラートの重要度</span><span class="sxs-lookup"><span data-stu-id="e4a59-146">Alert severity by operating system</span></span>
<span data-ttu-id="e4a59-147">演算子を使用して、 `summarize` 複数のフィールドから値をグラフ化する結果を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="e4a59-148">たとえば、警告の重要度がオペレーティング システム (OS) 間でどのように分散されるのかについて理解したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4a59-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="e4a59-149">次のクエリでは、演算子を使用して表から OS 情報を取り込み、列と列の両方の値をカウント `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="e4a59-150">これらの結果は、積み上げされた棒グラフを使用して視覚化すると最適です。</span><span class="sxs-lookup"><span data-stu-id="e4a59-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="e4a59-151">![OS および重大度別のアラートのクエリ結果を積み上げグラフとして表示する高度な検索クエリ結果 ](../../media/advanced-hunting-stacked-chart.jpg)
 *の画像*</span><span class="sxs-lookup"><span data-stu-id="e4a59-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="e4a59-152">上位 10 個の送信者ドメインのフィッシングメール</span><span class="sxs-lookup"><span data-stu-id="e4a59-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="e4a59-153">有限ではない値のリストを扱う場合は、演算子を使用して、最も多くのインスタンスを持つ値のみを `Top` グラフ化できます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="e4a59-154">たとえば、フィッシングメールが最も多い上位 10 個の送信者ドメインを取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="e4a59-155">円グラフ ビューを使用して、上位ドメイン間の分布を効果的に表示します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="e4a59-156">![上位送信者ドメイン間でのフィッシング メールの配布を示す円グラフとして表示された高度な検索クエリ結果 ](../../media/advanced-hunting-pie-chart.jpg)
 *の画像*</span><span class="sxs-lookup"><span data-stu-id="e4a59-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="e4a59-157">時間の過ぎたファイル アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e4a59-157">File activities over time</span></span>
<span data-ttu-id="e4a59-158">演算子を `summarize` 関数と一緒に `bin()` 使用すると、特定のインジケーターに関連するイベントを時間のとともにチェックできます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="e4a59-159">次のクエリは、ファイルに関連するイベントを 30 分間隔でカウントし、そのファイルに関連するアクティビティのスパイク `invoice.doc` を示します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="e4a59-160">次の線グラフは、次のアクティビティを含む期間を明確に強調しています `invoice.doc` 。</span><span class="sxs-lookup"><span data-stu-id="e4a59-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="e4a59-161">![高度な検索クエリの結果が、時間の中でファイルに関係するイベントの数を示す線グラフの線グラフ ](../../media/advanced-hunting-line-chart.jpg)
 *として表示される画像*</span><span class="sxs-lookup"><span data-stu-id="e4a59-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="e4a59-162">表とグラフをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e4a59-162">Export tables and charts</span></span>
<span data-ttu-id="e4a59-163">クエリを実行した後、[エクスポート] **を** 選択して結果をローカル ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="e4a59-164">選択したビューによって、結果のエクスポート方法が決なります。</span><span class="sxs-lookup"><span data-stu-id="e4a59-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="e4a59-165">**テーブル ビュー** - クエリ結果は、Microsoft Excel ブックとして表形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="e4a59-166">**任意の** グラフ — クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="e4a59-167">クエリ結果からドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="e4a59-167">Drill down from query results</span></span>
<span data-ttu-id="e4a59-168">クエリ結果でレコードをすばやく検査するには、対応する行を選択して [レコードの検査] パネル **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="e4a59-169">パネルは、選択したレコードに基づいて次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="e4a59-170">**資産** — レコード内の主な資産 (メールボックス、デバイス、ユーザー) の要約ビューで、リスクや露出レベルなどの利用可能な情報が豊富に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="e4a59-171">**プロセス ツリー** — プロセス情報を持つレコード用に生成され、利用可能なコンテキスト情報を使用して強化されます。一般に、より多くの列を返すクエリを実行すると、より豊富なプロセス ツリーが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4a59-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="e4a59-172">**すべての詳細** - レコード内の列からのすべての値</span><span class="sxs-lookup"><span data-stu-id="e4a59-172">**All details** — all the values from the columns in the record</span></span>  

![レコードを検査するパネルを含む選択されたレコードの画像](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="e4a59-174">コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果の特定のエンティティに関する詳細を表示するには、エンティティ識別子を選択して、そのエンティティの詳細なプロファイル ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="e4a59-175">結果からクエリを絞り込む</span><span class="sxs-lookup"><span data-stu-id="e4a59-175">Tweak your queries from the results</span></span>
<span data-ttu-id="e4a59-176">結果セットの値を右クリックすると、クエリがすばやく強化されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="e4a59-177">次のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-177">You can use the options to:</span></span>

- <span data-ttu-id="e4a59-178">選択した値 (`==`) を明示的に検索する</span><span class="sxs-lookup"><span data-stu-id="e4a59-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="e4a59-179">選択した値をクエリ (`!=`) から除外する </span><span class="sxs-lookup"><span data-stu-id="e4a59-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="e4a59-180">クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する</span><span class="sxs-lookup"><span data-stu-id="e4a59-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高度な検索結果セットの画像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="e4a59-182">クエリ結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e4a59-182">Filter the query results</span></span>
<span data-ttu-id="e4a59-183">右に表示されるフィルターは、結果セットの要約を提供します。</span><span class="sxs-lookup"><span data-stu-id="e4a59-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="e4a59-184">各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="e4a59-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="e4a59-185">クエリを絞り込むには、含める値または除外する値のボタンを選択し、[クエリの実行] を `+` `-` **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e4a59-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="e4a59-187">フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="e4a59-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4a59-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4a59-188">Related topics</span></span>
- [<span data-ttu-id="e4a59-189">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="e4a59-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e4a59-190">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="e4a59-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4a59-191">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="e4a59-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e4a59-192">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="e4a59-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e4a59-193">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="e4a59-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e4a59-194">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="e4a59-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e4a59-195">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="e4a59-195">Custom detections overview</span></span>](custom-detections-overview.md)
