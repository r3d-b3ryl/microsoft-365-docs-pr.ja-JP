---
title: Microsoft Threat Protection で高度な捜索のクエリ言語について学習する
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な検索、脅威の探し、サイバーの脅威の検出、microsoft の脅威の防止、microsoft 365、mtp、m365、search、query、language、学べ、first query、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、operators、データ型、powershellダウンロード、クエリの例
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
ms.openlocfilehash: 5715baaccd95d975f7d15196906a6326177bbc2e
ms.sourcegitcommit: 242f051c4cf3683f8c1a5da20ceca81bde212cfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982013"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="041db-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="041db-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="041db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="041db-105">**Applies to:**</span></span>
- <span data-ttu-id="041db-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="041db-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="041db-107">高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="041db-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="041db-108">Kusto 構文および演算子を使用して、高度な捜索用に特別に構造化された[スキーマ](advanced-hunting-schema-tables.md)内の情報を検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="041db-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="041db-109">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="041db-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="041db-110">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="041db-110">Try your first query</span></span>

<span data-ttu-id="041db-111">Microsoft 365 セキュリティセンターで、「検索 **」に移動**して最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="041db-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="041db-112">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="041db-112">Use the following example:</span></span>

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

<span data-ttu-id="041db-113">これは、高度な捜索でどのように見えるかを示します。</span><span class="sxs-lookup"><span data-stu-id="041db-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Threat Protection の高度な検索クエリの画像](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="041db-115">クエリについて説明し、検索するテーブルを指定する</span><span class="sxs-lookup"><span data-stu-id="041db-115">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="041db-116">クエリの先頭に短いコメントが追加されました。その目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="041db-116">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="041db-117">これは、後でクエリを保存して組織内の他のユーザーと共有する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="041db-117">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="041db-118">通常、クエリ自体はテーブル名から始まり、続いてパイプ (`|`) で始まる一連の要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="041db-118">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="041db-119">この例では、まず、2つのテーブル`DeviceProcessEvents`のユニオンを作成`DeviceNetworkEvents`し、を、必要に応じてパイプライン処理された要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="041db-119">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="041db-120">時間の範囲を設定する</span><span class="sxs-lookup"><span data-stu-id="041db-120">Set the time range</span></span>
<span data-ttu-id="041db-121">最初のパイプライン処理された要素は、前の7日間を対象範囲とする時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="041db-121">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="041db-122">時間範囲をできる限り狭くすることで、クエリが適切に実行され、管理可能な結果が返され、タイムアウトが回避されます。</span><span class="sxs-lookup"><span data-stu-id="041db-122">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="041db-123">特定のプロセスを確認する</span><span class="sxs-lookup"><span data-stu-id="041db-123">Check specific processes</span></span>
<span data-ttu-id="041db-124">時間範囲の直後には、PowerShell アプリケーションを表すプロセスファイル名の検索が続きます。</span><span class="sxs-lookup"><span data-stu-id="041db-124">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="041db-125">特定のコマンド文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="041db-125">Search for specific command strings</span></span>
<span data-ttu-id="041db-126">その後、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンドラインの文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="041db-126">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="041db-127">結果の列と長さをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="041db-127">Customize result columns and length</span></span> 
<span data-ttu-id="041db-128">クエリによって、検索するデータが明確に識別されるようになったので、結果の見た目を定義する要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="041db-128">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="041db-129">`project`特定の列を返し`top` 、結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="041db-129">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="041db-130">これらの演算子を使用すると、結果が適切に書式設定されており、処理がかなり簡単になります。</span><span class="sxs-lookup"><span data-stu-id="041db-130">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="041db-131">[**クエリの実行**] をクリックして結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="041db-131">Click **Run query** to see the results.</span></span> <span data-ttu-id="041db-132">クエリエディターの右上にある展開アイコンを選択して、お探しのクエリと結果にフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="041db-132">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![高度な検索クエリエディターの展開コントロールのイメージ](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="041db-134">クエリ結果をグラフとして表示し、フィルターをすばやく調整することができます。</span><span class="sxs-lookup"><span data-stu-id="041db-134">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="041db-135">ガイダンスについては、「[クエリ結果の使用方法](advanced-hunting-query-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041db-135">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="041db-136">高度な捜索のための一般的なクエリ演算子を学習する</span><span class="sxs-lookup"><span data-stu-id="041db-136">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="041db-137">最初のクエリを実行し、そのコンポーネントの一般的な概念を理解したので、少しだけ遡って基本的なことを学習しましょう。</span><span class="sxs-lookup"><span data-stu-id="041db-137">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="041db-138">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="041db-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="041db-139">演算子</span><span class="sxs-lookup"><span data-stu-id="041db-139">Operator</span></span> | <span data-ttu-id="041db-140">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="041db-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="041db-141">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="041db-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="041db-142">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="041db-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="041db-143">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="041db-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="041db-144">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="041db-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="041db-145">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="041db-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="041db-146">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="041db-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="041db-147">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="041db-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="041db-148">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="041db-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="041db-149">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="041db-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="041db-150">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="041db-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="041db-151">これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="041db-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="041db-152">データ型とクエリ構文の意味を理解する</span><span class="sxs-lookup"><span data-stu-id="041db-152">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="041db-153">高度な捜索テーブルのデータは、通常、次のデータ型に分類されます。</span><span class="sxs-lookup"><span data-stu-id="041db-153">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="041db-154">データ型</span><span class="sxs-lookup"><span data-stu-id="041db-154">Data type</span></span> | <span data-ttu-id="041db-155">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="041db-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="041db-156">通常、イベントのタイムスタンプを表すデータおよび時間の情報</span><span class="sxs-lookup"><span data-stu-id="041db-156">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="041db-157">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="041db-157">Character string</span></span> |
| `bool` | <span data-ttu-id="041db-158">True または False</span><span class="sxs-lookup"><span data-stu-id="041db-158">True or false</span></span> |
| `int` | <span data-ttu-id="041db-159">32 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="041db-159">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="041db-160">64 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="041db-160">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="041db-161">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="041db-161">Use sample queries</span></span>

<span data-ttu-id="041db-162">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="041db-162">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="041db-163">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="041db-163">Try running these queries and making small modifications to them.</span></span>

![高度な捜索ウィンドウの画像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="041db-165">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="041db-165">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="041db-166">ページ左側の共有クエリまたは GitHub クエリ リポジトリを探します。</span><span class="sxs-lookup"><span data-stu-id="041db-166">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="041db-167">クエリ言語のドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="041db-167">Access query language documentation</span></span>

<span data-ttu-id="041db-168">Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/kusto/query/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041db-168">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="041db-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="041db-169">Related topics</span></span>
- [<span data-ttu-id="041db-170">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="041db-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="041db-171">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="041db-171">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="041db-172">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="041db-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="041db-173">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="041db-173">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="041db-174">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="041db-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="041db-175">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="041db-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
