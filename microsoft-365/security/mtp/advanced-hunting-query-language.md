---
title: Microsoft 365 Defender の高度な検索クエリ言語について説明します。
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、言語、学習、最初のクエリ、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、演算子、データ型、powershell ダウンロード、クエリの例
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
ms.openlocfilehash: f996cd00cc2f7a1f1de2540f1d6686d26431c4f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904081"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="7aa5b-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7aa5b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7aa5b-105">**Applies to:**</span></span>
- <span data-ttu-id="7aa5b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7aa5b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7aa5b-107">高度な捜索は、[Kusto クエリ言語](/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-107">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="7aa5b-108">Kusto 演算子とステートメントを使用して、特殊なスキーマ内の情報を検索するクエリを作成 [できます](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="7aa5b-109">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="7aa5b-110">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="7aa5b-110">Try your first query</span></span>

<span data-ttu-id="7aa5b-111">Microsoft 365 セキュリティ センターで、[ハンティング] に **移動して最初** のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="7aa5b-112">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-112">Use the following example:</span></span>

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

<span data-ttu-id="7aa5b-113">**[高度な検索でこのクエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="7aa5b-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="7aa5b-114">クエリを記述し、検索するテーブルを指定する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="7aa5b-115">クエリの先頭に短いコメントが追加され、それが何を行うのかを説明しています。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="7aa5b-116">このコメントは、後でクエリを保存し、組織内の他のユーザーと共有する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="7aa5b-117">クエリ自体は、通常、テーブル名の後にパイプ ( ) で始まる複数の要素で始まる `|` 。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="7aa5b-118">この例では、まず 2 つのテーブルの共用体を作成し、必要に応じてパイプ要素  `DeviceProcessEvents` `DeviceNetworkEvents` を追加します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="7aa5b-119">時間範囲を設定する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-119">Set the time range</span></span>
<span data-ttu-id="7aa5b-120">最初のパイプ処理された要素は、前の 7 日間にスコープ設定された時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="7aa5b-121">時間範囲を制限すると、クエリのパフォーマンスが向上し、管理可能な結果が返され、時間が取れなかることができます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="7aa5b-122">特定のプロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-122">Check specific processes</span></span>
<span data-ttu-id="7aa5b-123">時間範囲の直後に、PowerShell アプリケーションを表すプロセス ファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="7aa5b-124">特定のコマンド文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-124">Search for specific command strings</span></span>
<span data-ttu-id="7aa5b-125">その後、クエリは、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンド ライン内の文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="7aa5b-126">結果の列と長さをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7aa5b-126">Customize result columns and length</span></span> 
<span data-ttu-id="7aa5b-127">クエリで検索するデータが明確に識別されたので、結果の外観を定義できます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="7aa5b-128">`project` 特定の列を返し、 `top` 結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="7aa5b-129">これらの演算子は、結果の形式が適切で、合理的に大きく、処理が容易であることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="7aa5b-130">[クエリ **の実行] を** 選択して結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="7aa5b-131">クエリ エディターの右上にある展開アイコンを使用して、検索クエリと結果に注目します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高度な検索クエリ エディターの Expand コントロールのイメージ](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="7aa5b-133">クエリ結果をグラフとして表示し、フィルターをすばやく調整できます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="7aa5b-134">ガイダンスについては、「 [クエリ結果の操作」を参照してください。](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="7aa5b-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="7aa5b-135">一般的なクエリ演算子の詳細</span><span class="sxs-lookup"><span data-stu-id="7aa5b-135">Learn common query operators</span></span>

<span data-ttu-id="7aa5b-136">最初のクエリを実行し、そのコンポーネントに関する一般的なアイデアを得たばかりです。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="7aa5b-137">少しバックトラックし、いくつかの基本を学ぶ時間です。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="7aa5b-138">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="7aa5b-139">演算子</span><span class="sxs-lookup"><span data-stu-id="7aa5b-139">Operator</span></span> | <span data-ttu-id="7aa5b-140">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="7aa5b-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="7aa5b-141">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="7aa5b-142">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="7aa5b-143">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="7aa5b-144">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="7aa5b-145">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="7aa5b-146">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="7aa5b-147">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="7aa5b-148">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="7aa5b-149">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="7aa5b-150">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="7aa5b-151">これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="7aa5b-152">データ型について</span><span class="sxs-lookup"><span data-stu-id="7aa5b-152">Understand data types</span></span>

<span data-ttu-id="7aa5b-153">高度な検索では、次の一般的な種類を含む Kusto データ型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="7aa5b-154">データ型</span><span class="sxs-lookup"><span data-stu-id="7aa5b-154">Data type</span></span> | <span data-ttu-id="7aa5b-155">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="7aa5b-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="7aa5b-156">通常、イベントのタイムスタンプを表すデータと時刻の情報。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="7aa5b-157">サポートされている日時形式を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-157">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="7aa5b-158">文字列は、UTF-8 ( ) または二重引用符 ( `'` ) で囲まれます `"` 。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="7aa5b-159">文字列の詳細</span><span class="sxs-lookup"><span data-stu-id="7aa5b-159">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="7aa5b-160">このデータ型は、サポート `true` または `false` 状態です。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="7aa5b-161">サポートされているリテラルと演算子を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-161">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="7aa5b-162">32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="7aa5b-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="7aa5b-163">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="7aa5b-163">64-bit integer</span></span> |

<span data-ttu-id="7aa5b-164">これらのデータ型の詳細については [、「Kusto スカラー データ型」を参照してください](/azure/data-explorer/kusto/query/scalar-data-types/)。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-164">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="7aa5b-165">クエリを記述するときにヘルプを参照する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-165">Get help as you write queries</span></span>
<span data-ttu-id="7aa5b-166">次の機能を利用して、クエリをより速く記述します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="7aa5b-167">**Autosuggest**-you write queries, advanced hunting providess suggestions from IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="7aa5b-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="7aa5b-168">**スキーマ ツリー**: テーブルの一覧とその列を含むスキーマ表現が、作業領域の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="7aa5b-169">詳細については、アイテムにカーソルを合わせてください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-169">For more information, hover over an item.</span></span> <span data-ttu-id="7aa5b-170">アイテムをダブルクリックして、クエリ エディターに挿入します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="7aa5b-171">**[スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**-テーブルと列の説明、サポートされているイベントの種類 (値) とサンプル クエリを含むポータル `ActionType` 内参照</span><span class="sxs-lookup"><span data-stu-id="7aa5b-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="7aa5b-172">エディターで複数のクエリを処理する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="7aa5b-173">クエリ エディターを使用して、複数のクエリを実験できます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="7aa5b-174">複数のクエリを使用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-174">To use multiple queries:</span></span>

- <span data-ttu-id="7aa5b-175">各クエリを空の行で分離します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="7aa5b-176">クエリを実行する前に、クエリの任意の部分にカーソルを置き、そのクエリを選択します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="7aa5b-177">これにより、選択したクエリだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-177">This will run only the selected query.</span></span> <span data-ttu-id="7aa5b-178">別のクエリを実行するには、カーソルを適切に移動し、[クエリの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![複数のクエリを含むクエリ エディターのイメージ](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="7aa5b-180">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-180">Use sample queries</span></span>

<span data-ttu-id="7aa5b-181">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="7aa5b-182">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-182">Try running these queries and making small modifications to them.</span></span>

![高度な捜索ウィンドウの画像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="7aa5b-184">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="7aa5b-185">ページの左側または GitHub クエリ リポジトリで共有 [クエリを確認します](https://aka.ms/hunting-queries)。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="7aa5b-186">クエリ言語のドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="7aa5b-186">Access query language documentation</span></span>

<span data-ttu-id="7aa5b-187">Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](/azure/kusto/query/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aa5b-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7aa5b-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aa5b-188">Related topics</span></span>
- [<span data-ttu-id="7aa5b-189">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="7aa5b-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7aa5b-190">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="7aa5b-191">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7aa5b-192">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="7aa5b-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7aa5b-193">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7aa5b-194">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="7aa5b-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)