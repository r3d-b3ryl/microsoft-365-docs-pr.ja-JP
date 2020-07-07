---
title: Microsoft Threat Protection で高度な捜索のクエリ言語について学習する
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、language、advanced、first query、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、operators、データ型、powershell ダウンロード、クエリの例
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 26b376fe3e804a3ebaa478e484807bea4c33d38b
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049699"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="cea21-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="cea21-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="cea21-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cea21-105">**Applies to:**</span></span>
- <span data-ttu-id="cea21-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cea21-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cea21-107">高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="cea21-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="cea21-108">Kusto 構文および演算子を使用して、高度な捜索用に特別に構造化された[スキーマ](advanced-hunting-schema-tables.md)内の情報を検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cea21-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="cea21-109">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="cea21-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="cea21-110">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="cea21-110">Try your first query</span></span>

<span data-ttu-id="cea21-111">Microsoft 365 セキュリティセンターで、「検索 **」に移動**して最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="cea21-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="cea21-112">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cea21-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="cea21-113">これは、高度な捜索でどのように見えるかを示します。</span><span class="sxs-lookup"><span data-stu-id="cea21-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Threat Protection の高度な検索クエリの画像](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="cea21-115">クエリについて説明し、検索するテーブルを指定する</span><span class="sxs-lookup"><span data-stu-id="cea21-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="cea21-116">クエリの先頭に短いコメントが追加されました。その目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="cea21-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="cea21-117">これは、後でクエリを保存して組織内の他のユーザーと共有する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cea21-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="cea21-118">通常、クエリ自体はテーブル名から始まり、続いてパイプ (`|`) で始まる一連の要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="cea21-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="cea21-119">この例では、まず、2つのテーブルのユニオンを作成し、 `DeviceProcessEvents` `DeviceNetworkEvents` を、必要に応じてパイプライン処理された要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="cea21-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="cea21-120">時間の範囲を設定する</span><span class="sxs-lookup"><span data-stu-id="cea21-120">Set the time range</span></span>
<span data-ttu-id="cea21-121">最初のパイプライン処理された要素は、前の7日間を対象範囲とする時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="cea21-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="cea21-122">時間範囲をできる限り狭くすることで、クエリが適切に実行され、管理可能な結果が返され、タイムアウトが回避されます。</span><span class="sxs-lookup"><span data-stu-id="cea21-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="cea21-123">特定のプロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="cea21-123">Check specific processes</span></span>
<span data-ttu-id="cea21-124">時間範囲の直後には、PowerShell アプリケーションを表すプロセスファイル名の検索が続きます。</span><span class="sxs-lookup"><span data-stu-id="cea21-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="cea21-125">特定のコマンド文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="cea21-125">Search for specific command strings</span></span>
<span data-ttu-id="cea21-126">その後、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンドラインの文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="cea21-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
    "DownloadFile",
    "DownloadData",
    "DownloadString",
    "WebRequest",
    "Shellcode",
    "http",
    "https")
```

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="cea21-127">結果の列と長さをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cea21-127">Customize result columns and length</span></span> 
<span data-ttu-id="cea21-128">クエリによって、検索するデータが明確に識別されるようになったので、結果の見た目を定義する要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="cea21-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="cea21-129">`project`特定の列を返し、 `top` 結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="cea21-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="cea21-130">これらの演算子を使用すると、結果が適切に書式設定されており、処理がかなり簡単になります。</span><span class="sxs-lookup"><span data-stu-id="cea21-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="cea21-131">[**クエリの実行**] をクリックして結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="cea21-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="cea21-132">クエリエディターの右上にある展開アイコンを選択して、お探しのクエリと結果にフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="cea21-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高度な検索クエリエディターの展開コントロールのイメージ](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="cea21-134">クエリ結果をグラフとして表示し、フィルターをすばやく調整することができます。</span><span class="sxs-lookup"><span data-stu-id="cea21-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="cea21-135">ガイダンスについては、「[クエリ結果の使用方法](advanced-hunting-query-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea21-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="cea21-136">高度な捜索のための一般的なクエリ演算子を学習する</span><span class="sxs-lookup"><span data-stu-id="cea21-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="cea21-137">最初のクエリを実行し、そのコンポーネントの一般的な概念を理解したので、少しだけ遡って基本的なことを学習しましょう。</span><span class="sxs-lookup"><span data-stu-id="cea21-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="cea21-138">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cea21-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="cea21-139">演算子</span><span class="sxs-lookup"><span data-stu-id="cea21-139">Operator</span></span> | <span data-ttu-id="cea21-140">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="cea21-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="cea21-141">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cea21-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="cea21-142">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cea21-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="cea21-143">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cea21-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="cea21-144">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="cea21-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="cea21-145">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="cea21-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="cea21-146">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="cea21-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="cea21-147">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="cea21-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="cea21-148">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="cea21-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="cea21-149">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="cea21-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="cea21-150">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="cea21-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="cea21-151">これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="cea21-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="cea21-152">データ型とクエリ構文の意味を理解する</span><span class="sxs-lookup"><span data-stu-id="cea21-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="cea21-153">高度な捜索テーブルのデータは、通常、次のデータ型に分類されます。</span><span class="sxs-lookup"><span data-stu-id="cea21-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="cea21-154">データ型</span><span class="sxs-lookup"><span data-stu-id="cea21-154">Data type</span></span> | <span data-ttu-id="cea21-155">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="cea21-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="cea21-156">通常、イベントのタイムスタンプを表すデータおよび時間の情報</span><span class="sxs-lookup"><span data-stu-id="cea21-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="cea21-157">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="cea21-157">Character string</span></span> |
| `bool` | <span data-ttu-id="cea21-158">True または False</span><span class="sxs-lookup"><span data-stu-id="cea21-158">True or false</span></span> |
| `int` | <span data-ttu-id="cea21-159">32 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="cea21-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="cea21-160">64 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="cea21-160">64-bit numeric value</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="cea21-161">クエリを記述するときにヘルプを参照する</span><span class="sxs-lookup"><span data-stu-id="cea21-161">Get help as you write queries</span></span>
<span data-ttu-id="cea21-162">次の機能を利用して、クエリをより速く記述します。</span><span class="sxs-lookup"><span data-stu-id="cea21-162">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="cea21-163">**Autosuggest** : クエリを作成すると、高度な検索によって IntelliSense から候補が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cea21-163">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="cea21-164">**スキーマツリー** -テーブルとその列のリストを含むスキーマ表現は、作業領域の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cea21-164">**Schema tree** — a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="cea21-165">詳細については、アイテムにカーソルを合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cea21-165">For more information, hover over an item.</span></span> <span data-ttu-id="cea21-166">アイテムをダブルクリックして、クエリ エディターに挿入します。</span><span class="sxs-lookup"><span data-stu-id="cea21-166">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="cea21-167">**[スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: テーブルと列の説明、およびサポートされるイベントの種類 ( `ActionType` 値) とサンプルクエリを含むポータル内のリファレンス</span><span class="sxs-lookup"><span data-stu-id="cea21-167">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="cea21-168">エディターで複数のクエリを操作する</span><span class="sxs-lookup"><span data-stu-id="cea21-168">Work with multiple queries in the editor</span></span>
<span data-ttu-id="cea21-169">クエリエディターは、複数のクエリを試すために、スクラッチパッドとして機能することができます。</span><span class="sxs-lookup"><span data-stu-id="cea21-169">The query editor can serve as your scratch pad for experimenting with multiple queries.</span></span> <span data-ttu-id="cea21-170">複数のクエリを使用するには</span><span class="sxs-lookup"><span data-stu-id="cea21-170">To use multiple queries:</span></span>

- <span data-ttu-id="cea21-171">各クエリは空の行で区切ります。</span><span class="sxs-lookup"><span data-stu-id="cea21-171">Separate each query with an empty line.</span></span>
- <span data-ttu-id="cea21-172">クエリの任意の部分にカーソルを置き、クエリを実行する前に選択します。</span><span class="sxs-lookup"><span data-stu-id="cea21-172">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="cea21-173">これは、選択したクエリのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="cea21-173">This will run only the selected query.</span></span> <span data-ttu-id="cea21-174">別のクエリを実行するには、必要に応じてカーソルを移動して、[**クエリの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cea21-174">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![複数のクエリを使用したクエリエディターのイメージ](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="cea21-176">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="cea21-176">Use sample queries</span></span>

<span data-ttu-id="cea21-177">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="cea21-177">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="cea21-178">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="cea21-178">Try running these queries and making small modifications to them.</span></span>

![高度な捜索ウィンドウの画像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="cea21-180">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cea21-180">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="cea21-181">ページ左側の共有クエリまたは GitHub クエリ リポジトリを探します。</span><span class="sxs-lookup"><span data-stu-id="cea21-181">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="cea21-182">クエリ言語のドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="cea21-182">Access query language documentation</span></span>

<span data-ttu-id="cea21-183">Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/kusto/query/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea21-183">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cea21-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="cea21-184">Related topics</span></span>
- [<span data-ttu-id="cea21-185">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="cea21-185">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cea21-186">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="cea21-186">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="cea21-187">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="cea21-187">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cea21-188">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="cea21-188">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cea21-189">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="cea21-189">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cea21-190">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="cea21-190">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
