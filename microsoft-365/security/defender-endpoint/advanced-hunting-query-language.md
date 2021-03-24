---
title: 高度な捜索のクエリ言語について学習する
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、言語、学習、最初のクエリ、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、演算子、データ型
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21cea1f661de294aea41ea2c4db21b1aca8a0eec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065124"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="2d3be-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="2d3be-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d3be-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2d3be-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d3be-106">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2d3be-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="2d3be-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="2d3be-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2d3be-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="2d3be-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="2d3be-109">高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2d3be-109">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="2d3be-110">Kusto 演算子とステートメントを使用して、特殊なスキーマ内の情報を検索するクエリを作成 [できます](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="2d3be-110">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-reference.md).</span></span> <span data-ttu-id="2d3be-111">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-111">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="2d3be-112">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="2d3be-112">Try your first query</span></span>

<span data-ttu-id="2d3be-113">Microsoft Defender セキュリティ センターで、[高度な検索 **] に移動して** 、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-113">In Microsoft Defender Security Center, go to **Advanced hunting** to run your first query.</span></span> <span data-ttu-id="2d3be-114">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="2d3be-114">Use the following example:</span></span>

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
<span data-ttu-id="2d3be-115">**[高度な検索でこのクエリを実行する](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="2d3be-115">**[Run this query in advanced hunting](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="2d3be-116">クエリを記述し、検索するテーブルを指定する</span><span class="sxs-lookup"><span data-stu-id="2d3be-116">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="2d3be-117">クエリの先頭に短いコメントが追加され、それが何を行うのかを説明しています。</span><span class="sxs-lookup"><span data-stu-id="2d3be-117">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="2d3be-118">このコメントは、後でクエリを保存し、組織内の他のユーザーと共有する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-118">This comment helps if you later decide to save the query and share it with others in your organization.</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
```
<span data-ttu-id="2d3be-119">クエリ自体は、通常、テーブル名の後にパイプ ( ) で始まる複数の要素で始まる `|` 。</span><span class="sxs-lookup"><span data-stu-id="2d3be-119">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="2d3be-120">この例では、まず 2 つのテーブルの共用体を作成し、必要に応じてパイプ要素  `DeviceProcessEvents` `DeviceNetworkEvents` を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-120">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="2d3be-121">時間範囲を設定する</span><span class="sxs-lookup"><span data-stu-id="2d3be-121">Set the time range</span></span>
<span data-ttu-id="2d3be-122">最初のパイプ処理された要素は、前の 7 日間にスコープ設定された時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="2d3be-122">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="2d3be-123">時間範囲を制限すると、クエリのパフォーマンスが向上し、管理可能な結果が返され、時間が取れなかることができます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-123">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="2d3be-124">特定のプロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="2d3be-124">Check specific processes</span></span>
<span data-ttu-id="2d3be-125">時間範囲の直後に、PowerShell アプリケーションを表すプロセス ファイル名を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-125">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="2d3be-126">特定のコマンド文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="2d3be-126">Search for specific command strings</span></span>
<span data-ttu-id="2d3be-127">その後、クエリは、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンド ライン内の文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-127">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="2d3be-128">結果の列と長さをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="2d3be-128">Customize result columns and length</span></span> 
<span data-ttu-id="2d3be-129">クエリで検索するデータが明確に識別されたので、結果の外観を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-129">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="2d3be-130">`project` 特定の列を返し、 `top` 結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-130">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="2d3be-131">これらの演算子は、結果の形式が適切で、合理的に大きく、処理が容易であることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-131">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="2d3be-132">[クエリ **の実行] を** 選択して結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-132">Select **Run query** to see the results.</span></span> <span data-ttu-id="2d3be-133">クエリ エディターの右上にある展開アイコンを使用して、検索クエリと結果に注目します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-133">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高度な検索クエリ エディターの Expand コントロールのイメージ](images/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="2d3be-135">クエリ結果をグラフとして表示し、フィルターをすばやく調整できます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-135">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="2d3be-136">ガイダンスについては、「 [クエリ結果の操作」を参照してください。](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="2d3be-136">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="2d3be-137">高度な捜索のための一般的なクエリ演算子を学習する</span><span class="sxs-lookup"><span data-stu-id="2d3be-137">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="2d3be-138">最初のクエリを実行し、そのコンポーネントに関する一般的なアイデアを得たばかりです。</span><span class="sxs-lookup"><span data-stu-id="2d3be-138">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="2d3be-139">少しバックトラックし、いくつかの基本を学ぶ時間です。</span><span class="sxs-lookup"><span data-stu-id="2d3be-139">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="2d3be-140">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2d3be-140">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="2d3be-141">演算子</span><span class="sxs-lookup"><span data-stu-id="2d3be-141">Operator</span></span> | <span data-ttu-id="2d3be-142">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="2d3be-142">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="2d3be-143">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-143">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="2d3be-144">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-144">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="2d3be-145">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-145">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="2d3be-146">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-146">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="2d3be-147">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-147">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="2d3be-148">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-148">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="2d3be-149">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-149">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="2d3be-150">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-150">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="2d3be-151">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-151">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="2d3be-152">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-152">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="2d3be-153">これらの演算子の実例を確認するには、高度な検索ページの **[開始** ] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-153">To see a live example of these operators, run them from the **Get started** section of the advanced hunting page.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="2d3be-154">データ型について</span><span class="sxs-lookup"><span data-stu-id="2d3be-154">Understand data types</span></span>

<span data-ttu-id="2d3be-155">高度な検索では、次の一般的な種類を含む Kusto データ型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d3be-155">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="2d3be-156">データ型</span><span class="sxs-lookup"><span data-stu-id="2d3be-156">Data type</span></span> | <span data-ttu-id="2d3be-157">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="2d3be-157">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="2d3be-158">通常、イベントのタイムスタンプを表すデータと時刻の情報。</span><span class="sxs-lookup"><span data-stu-id="2d3be-158">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="2d3be-159">サポートされている日時形式を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3be-159">See supported datetime formats</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="2d3be-160">文字列は、UTF-8 ( ) または二重引用符 ( `'` ) で囲まれます `"` 。</span><span class="sxs-lookup"><span data-stu-id="2d3be-160">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="2d3be-161">文字列の詳細</span><span class="sxs-lookup"><span data-stu-id="2d3be-161">Read more about strings</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="2d3be-162">このデータ型は、サポート `true` または `false` 状態です。</span><span class="sxs-lookup"><span data-stu-id="2d3be-162">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="2d3be-163">サポートされているリテラルと演算子を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3be-163">See supported literals and operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="2d3be-164">32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="2d3be-164">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="2d3be-165">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="2d3be-165">64-bit integer</span></span> |

<span data-ttu-id="2d3be-166">これらのデータ型の詳細については [、「Kusto スカラー データ型」を参照してください](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)。</span><span class="sxs-lookup"><span data-stu-id="2d3be-166">To learn more about these data types, [read about Kusto scalar data types](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="2d3be-167">クエリを記述するときにヘルプを参照する</span><span class="sxs-lookup"><span data-stu-id="2d3be-167">Get help as you write queries</span></span>
<span data-ttu-id="2d3be-168">次の機能を利用して、クエリをより速く記述します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-168">Take advantage of the following functionality to write queries faster:</span></span>

- <span data-ttu-id="2d3be-169">**Autosuggest**-you write queries, advanced hunting providess suggestions from IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2d3be-169">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span>
- <span data-ttu-id="2d3be-170">**スキーマ ツリー**: テーブルの一覧とその列を含むスキーマ表現が、作業領域の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-170">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="2d3be-171">詳細については、アイテムにカーソルを合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2d3be-171">For more information, hover over an item.</span></span> <span data-ttu-id="2d3be-172">アイテムをダブルクリックして、クエリ エディターに挿入します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-172">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="2d3be-173">**[スキーマ参照](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**-テーブルと列の説明、サポートされているイベントの種類 (値) とサンプル クエリを含むポータル `ActionType` 内参照</span><span class="sxs-lookup"><span data-stu-id="2d3be-173">**[Schema reference](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="2d3be-174">エディターで複数のクエリを処理する</span><span class="sxs-lookup"><span data-stu-id="2d3be-174">Work with multiple queries in the editor</span></span>
<span data-ttu-id="2d3be-175">クエリ エディターを使用して、複数のクエリを実験できます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-175">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="2d3be-176">複数のクエリを使用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-176">To use multiple queries:</span></span>

- <span data-ttu-id="2d3be-177">各クエリを空の行で分離します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-177">Separate each query with an empty line.</span></span>
- <span data-ttu-id="2d3be-178">クエリを実行する前に、クエリの任意の部分にカーソルを置き、そのクエリを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-178">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="2d3be-179">これにより、選択したクエリだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-179">This will run only the selected query.</span></span> <span data-ttu-id="2d3be-180">別のクエリを実行するには、カーソルを適切に移動し、[クエリの実行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2d3be-180">To run another query, move the cursor accordingly and select **Run query**.</span></span>

<span data-ttu-id="2d3be-181">![複数のクエリを含む高度な検索クエリ エディターのイメージ 複数のクエリを含 ](images/ah-multi-query.png)
 _むクエリ エディター_</span><span class="sxs-lookup"><span data-stu-id="2d3be-181">![Image of the advanced hunting query editor with multiple queries](images/ah-multi-query.png)
_Query editor with multiple queries_</span></span>

## <a name="use-sample-queries"></a><span data-ttu-id="2d3be-182">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2d3be-182">Use sample queries</span></span>

<span data-ttu-id="2d3be-183">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="2d3be-183">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="2d3be-184">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="2d3be-184">Try running these queries and making small modifications to them.</span></span>

![[高度な検索の開始] タブの画像](images/atp-advanced-hunting.png)

> [!NOTE]
> <span data-ttu-id="2d3be-186">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2d3be-186">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="2d3be-187">ページの左側または GitHub クエリ リポジトリで共有 [クエリを確認します](https://aka.ms/hunting-queries)。</span><span class="sxs-lookup"><span data-stu-id="2d3be-187">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-comprehensive-query-language-reference"></a><span data-ttu-id="2d3be-188">包括的なクエリ言語リファレンスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="2d3be-188">Access comprehensive query language reference</span></span>

<span data-ttu-id="2d3be-189">クエリ言語の詳細については [、「Kusto クエリ言語のドキュメント」を参照してください](https://docs.microsoft.com/azure/kusto/query/)。</span><span class="sxs-lookup"><span data-stu-id="2d3be-189">For detailed information about the query language, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d3be-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d3be-190">Related topics</span></span>
- [<span data-ttu-id="2d3be-191">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="2d3be-191">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2d3be-192">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="2d3be-192">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2d3be-193">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2d3be-193">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2d3be-194">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2d3be-194">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2d3be-195">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2d3be-195">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
