---
title: Microsoft 365 Defender で高度な検索クエリ結果を操作する
description: Microsoft 365 Defender で高度な検索によって返されるクエリ結果の大部分を作成する
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection、視覚エフェクト、グラフ、フィルター、ドリルダウン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: de26989b9092b783a45d27ad2a529720d21169f8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844130"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="d48a6-104">高度な検索クエリの結果を操作する</span><span class="sxs-lookup"><span data-stu-id="d48a6-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d48a6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d48a6-105">**Applies to:**</span></span>
- <span data-ttu-id="d48a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d48a6-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d48a6-107">[高度な](advanced-hunting-overview.md)検索クエリを作成して非常に正確な情報を返すことができますが、クエリ結果を使用して、特定のアクティビティとインジケーターをより詳細に把握し、調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="d48a6-108">クエリ結果に対して次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="d48a6-109">結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="d48a6-109">View results as a table or chart</span></span>
- <span data-ttu-id="d48a6-110">テーブルとグラフをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d48a6-110">Export tables and charts</span></span>
- <span data-ttu-id="d48a6-111">詳細なエンティティ情報へのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="d48a6-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="d48a6-112">結果から直接、またはフィルターを適用してクエリを微調整する</span><span class="sxs-lookup"><span data-stu-id="d48a6-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="d48a6-113">クエリ結果を表またはグラフとして表示する</span><span class="sxs-lookup"><span data-stu-id="d48a6-113">View query results as a table or chart</span></span>
<span data-ttu-id="d48a6-114">既定では、高度な検索では、クエリ結果が表形式データとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="d48a6-115">同じデータをグラフとして表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="d48a6-116">高度な検索では、次のビューがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="d48a6-117">ビューの種類</span><span class="sxs-lookup"><span data-stu-id="d48a6-117">View type</span></span> | <span data-ttu-id="d48a6-118">説明</span><span class="sxs-lookup"><span data-stu-id="d48a6-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="d48a6-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="d48a6-119">**Table**</span></span> | <span data-ttu-id="d48a6-120">クエリの結果を表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="d48a6-121">**縦棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-121">**Column chart**</span></span> | <span data-ttu-id="d48a6-122">X 軸に一連の一意のアイテムを垂直バーとしてレンダリングし、高さが別のフィールドの数値を表すようにします。</span><span class="sxs-lookup"><span data-stu-id="d48a6-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="d48a6-123">**積み上げ縦棒グラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-123">**Stacked column chart**</span></span> | <span data-ttu-id="d48a6-124">X 軸上の一連の一意のアイテムを、1つまたは複数の他のフィールドからの数値で表される垂直な積み上げ縦棒グラフで描画します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="d48a6-125">**円グラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-125">**Pie chart**</span></span> | <span data-ttu-id="d48a6-126">一意のアイテムを表す、断面パイをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="d48a6-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="d48a6-127">各円グラフのサイズは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="d48a6-128">**ドーナツグラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-128">**Donut chart**</span></span> | <span data-ttu-id="d48a6-129">一意の項目を表す各弧をレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="d48a6-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="d48a6-130">各弧の長さは、別のフィールドの数値を表します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="d48a6-131">**折れ線グラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-131">**Line chart**</span></span> | <span data-ttu-id="d48a6-132">一連の固有のアイテムの数値をプロットし、プロットされた値を接続します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="d48a6-133">**散布図**</span><span class="sxs-lookup"><span data-stu-id="d48a6-133">**Scatter chart**</span></span> | <span data-ttu-id="d48a6-134">一連の固有のアイテムの数値をプロットします。</span><span class="sxs-lookup"><span data-stu-id="d48a6-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="d48a6-135">**面グラフ**</span><span class="sxs-lookup"><span data-stu-id="d48a6-135">**Area chart**</span></span> | <span data-ttu-id="d48a6-136">一連の固有のアイテムの数値をプロットし、プロットされた値の下にセクションを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="d48a6-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="d48a6-137">効果的なグラフのクエリを作成する</span><span class="sxs-lookup"><span data-stu-id="d48a6-137">Construct queries for effective charts</span></span>
<span data-ttu-id="d48a6-138">グラフを表示する場合、高度な検索では、目的の列と集計する数値を自動的に識別します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="d48a6-139">意味のあるグラフを取得するには、表示する特定の値を返すようにクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="d48a6-140">いくつかのサンプルクエリと結果のグラフを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="d48a6-141">重要度別のアラート</span><span class="sxs-lookup"><span data-stu-id="d48a6-141">Alerts by severity</span></span>
<span data-ttu-id="d48a6-142">演算子を使用して、 `summarize` グラフにする値の数値の個数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="d48a6-143">次のクエリは、オペレーターを使用し `summarize` てアラートの数を重要度別に取得します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="d48a6-144">結果を表示するときに、縦棒グラフにそれぞれの重要度の値が個別の列として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="d48a6-145">![重要度別のアラートの列グラフクエリ結果として表示されている高度な検索クエリ結果の画像 ](../../media/advanced-hunting-column-chart.jpg)
 *列のグラフとして表示され* ます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="d48a6-146">オペレーティングシステムによるアラートの重要度</span><span class="sxs-lookup"><span data-stu-id="d48a6-146">Alert severity by operating system</span></span>
<span data-ttu-id="d48a6-147">また、演算子を使用して、 `summarize` 複数のフィールドからのグラフ値の結果を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="d48a6-148">たとえば、オペレーティングシステム (OS) 間でアラートの重大度がどのように分散されているかを理解する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d48a6-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="d48a6-149">次のクエリでは、演算子を使用して `join` テーブルから OS 情報を取得し、を使用して `DeviceInfo` `summarize` と列の両方の値をカウントし `OSPlatform` `Severity` ます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="d48a6-150">これらの結果は、積み上げ縦棒グラフを使用するのが最適です。</span><span class="sxs-lookup"><span data-stu-id="d48a6-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="d48a6-151">![拡張 ](../../media/advanced-hunting-stacked-chart.jpg)
 *グラフとして表示される OS と重要度によって* 、高度な検索クエリ結果が積み上げグラフクエリ結果として表示される画像</span><span class="sxs-lookup"><span data-stu-id="d48a6-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="d48a6-152">上位10人の送信者ドメインでのフィッシング電子メール</span><span class="sxs-lookup"><span data-stu-id="d48a6-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="d48a6-153">限定されていない値のリストを処理する場合は、演算子を使用して、 `Top` インスタンスが最も多い値のみをグラフ化できます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="d48a6-154">たとえば、最もフィッシング詐欺メールで上位10個の送信者ドメインを取得するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="d48a6-155">[円グラフ] ビューを使用して、上位ドメイン間の分散を効果的に表示します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="d48a6-156">![](../../media/advanced-hunting-pie-chart.jpg)
*上位の送信者ドメイン間でのフィッシング電子メールの配布を示す* 円グラフとして表示される高度な検索クエリ結果の画像</span><span class="sxs-lookup"><span data-stu-id="d48a6-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="d48a6-157">時間の経過に伴うファイルアクティビティ</span><span class="sxs-lookup"><span data-stu-id="d48a6-157">File activities over time</span></span>
<span data-ttu-id="d48a6-158">`summarize`関数で演算子を使用 `bin()` すると、特定のインジケーターに関係するイベントを時間の経過とともに確認できます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="d48a6-159">次のクエリは、ファイルに関連するイベントを `invoice.doc` 30 分間隔でカウントし、そのファイルに関連するアクティビティのスパイクを示します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="d48a6-160">下の行は、次のようなアクティビティを伴う期間を明確に強調してい `invoice.doc` ます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="d48a6-161">![](../../media/advanced-hunting-line-chart.jpg)
*時間の経過に伴うファイルに関連するイベントの数を示す* 折れ線グラフの折れ線グラフとして表示される高度な検索クエリ結果の画像</span><span class="sxs-lookup"><span data-stu-id="d48a6-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="d48a6-162">テーブルとグラフをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d48a6-162">Export tables and charts</span></span>
<span data-ttu-id="d48a6-163">クエリを実行した後、[ **エクスポート** ] を選択して結果をローカルファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="d48a6-164">選択したビューによって、結果のエクスポート方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="d48a6-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="d48a6-165">**テーブルビュー** -クエリ結果は、Microsoft Excel ブックとして表形式でエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="d48a6-166">**任意のグラフ** -クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="d48a6-167">クエリ結果からドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="d48a6-167">Drill down from query results</span></span>
<span data-ttu-id="d48a6-168">クエリ結果のレコードをすばやく検査するには、対応する行を選択して [ **レコードの検査** ] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="d48a6-169">パネルには、選択したレコードに基づいて次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="d48a6-170">**アセット** : レコードに含まれているメインアセット (メールボックス、デバイス、ユーザー) の要約されたビューで、リスクや露出レベルなどの利用可能な情報で拡充されています。</span><span class="sxs-lookup"><span data-stu-id="d48a6-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="d48a6-171">**プロセスツリー** —プロセス情報を含むレコードに対して生成され、使用可能なコンテキスト情報を使用して拡充されます。一般に、クエリが多くの列を返すと、より豊富なプロセスツリーになることがあります。</span><span class="sxs-lookup"><span data-stu-id="d48a6-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="d48a6-172">**すべての詳細** : レコード内の列のすべての値</span><span class="sxs-lookup"><span data-stu-id="d48a6-172">**All details** — all the values from the columns in the record</span></span>  

![レコードを検査するためのパネルがある、選択されたレコードのイメージ](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="d48a6-174">コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果内の特定のエンティティに関する詳細情報を表示するには、エンティティ識別子を選択してそのエンティティの詳細なプロファイルページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="d48a6-175">結果からクエリを絞り込む</span><span class="sxs-lookup"><span data-stu-id="d48a6-175">Tweak your queries from the results</span></span>
<span data-ttu-id="d48a6-176">結果セットの値を右クリックすると、クエリがすばやく強化されます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="d48a6-177">次のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-177">You can use the options to:</span></span>

- <span data-ttu-id="d48a6-178">選択した値 (`==`) を明示的に検索する</span><span class="sxs-lookup"><span data-stu-id="d48a6-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="d48a6-179">選択した値をクエリ (`!=`) から除外する </span><span class="sxs-lookup"><span data-stu-id="d48a6-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="d48a6-180">クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する</span><span class="sxs-lookup"><span data-stu-id="d48a6-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高度な検索結果セットの画像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="d48a6-182">クエリ結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="d48a6-182">Filter the query results</span></span>
<span data-ttu-id="d48a6-183">右に表示されるフィルターは、結果セットの要約を提供します。</span><span class="sxs-lookup"><span data-stu-id="d48a6-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="d48a6-184">各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="d48a6-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="d48a6-185">含めるまたは除外する値のまたはボタンを選択し、[クエリの実行] を選択して、クエリの絞り込みを行い `+` `-` ます。 **Run query**</span><span class="sxs-lookup"><span data-stu-id="d48a6-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="d48a6-187">フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="d48a6-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d48a6-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="d48a6-188">Related topics</span></span>
- [<span data-ttu-id="d48a6-189">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="d48a6-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d48a6-190">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d48a6-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d48a6-191">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="d48a6-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d48a6-192">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="d48a6-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d48a6-193">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d48a6-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d48a6-194">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="d48a6-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d48a6-195">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="d48a6-195">Custom detections overview</span></span>](custom-detections-overview.md)
