---
title: Microsoft Threat Protection で高度な捜索のクエリ言語について学習する
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、検索、クエリ、言語、学習、最初のクエリ、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、演算子、データ型
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ed5dd99d2ac569353ed72ddf67d906dfe21e7cd0
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911307"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="3e10c-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="3e10c-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="3e10c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3e10c-105">**Applies to:**</span></span>
- <span data-ttu-id="3e10c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e10c-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="3e10c-107">高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3e10c-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="3e10c-108">Kusto 構文および演算子を使用して、高度な捜索用に特別に構造化された[スキーマ](advanced-hunting-schema-tables.md)内の情報を検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="3e10c-109">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="3e10c-110">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="3e10c-110">Try your first query</span></span>

<span data-ttu-id="3e10c-111">Microsoft 365 セキュリティ センターで、[**捜索**] に移動して最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-111">in the Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="3e10c-112">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3e10c-112">Use the following example as a guide.</span></span>

```
// Finds PowerShell execution events that could involve a download.
ProcessCreationEvents  
| where EventTime > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project EventTime, ComputerName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by EventTime
```

<span data-ttu-id="3e10c-113">これは、高度な捜索でどのように見えるかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Defender ATP の高度な捜索クエリの画像](../images/advanced-hunting-query-example.png)

<span data-ttu-id="3e10c-115">クエリは、まず、目的を説明する短いコメントから始まります。</span><span class="sxs-lookup"><span data-stu-id="3e10c-115">The query starts with a short comment describing what it is for.</span></span> <span data-ttu-id="3e10c-116">これは、後でクエリを保存し、組織内の他のユーザーと共有することを決定した場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-116">This helps if you later decide to save your query and share it with others in your organization.</span></span>

```
// Finds PowerShell execution events that could involve a download.
ProcessCreationEvents
```

<span data-ttu-id="3e10c-117">通常、クエリ自体はテーブル名から始まり、続いてパイプ (`|`) で始まる一連の要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="3e10c-118">この例では、まずテーブル名 `ProcessCreationEvents` を追加し、必要に応じてパイプ要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-118">In this example, we start by adding  with the table name `ProcessCreationEvents` and add piped elements as needed.</span></span>

<span data-ttu-id="3e10c-119">最初のパイプ要素は、過去 7 日間に限定された時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="3e10c-119">The first piped element is a time filter scoped within the previous seven days.</span></span> <span data-ttu-id="3e10c-120">時間範囲をできる限り狭くすることで、クエリが適切に実行され、管理可能な結果が返され、タイムアウトが回避されます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```
| where EventTime > ago(7d)
```

<span data-ttu-id="3e10c-121">時間範囲の直後に、PowerShell アプリケーションを表すファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-121">The time range is immediately followed by a search for files representing the PowerShell application.</span></span>

```
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

<span data-ttu-id="3e10c-122">その後、クエリは通常、ファイルをダウンロードするために PowerShell で使用されるコマンド ラインを探します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-122">Afterwards, the query looks for command lines that are typically used with PowerShell to download files.</span></span>

```
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

<span data-ttu-id="3e10c-123">クエリによって、検索するデータが明確に識別されるようになったので、結果の見た目を定義する要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="3e10c-124">`project` は特定の列を返し、`top` は結果の数を制限するため、結果が適切に書式設定され、適度に大きく、処理も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="3e10c-124">`project` returns specific columns and `top` limits the number of results, making the results well-formatted and reasonably large and easy to process.</span></span>

```
| project EventTime, ComputerName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by EventTime'
```

<span data-ttu-id="3e10c-125">[**クエリの実行**] をクリックして結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="3e10c-126">画面表示を拡大すると、捜索クエリと結果に集中できます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-126">You can expand the screen view so you can focus on your hunting query and the results.</span></span>

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="3e10c-127">高度な捜索のための一般的なクエリ演算子を学習する</span><span class="sxs-lookup"><span data-stu-id="3e10c-127">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="3e10c-128">最初のクエリを実行し、そのコンポーネントの一般的な概念を理解したので、少しだけ遡って基本的なことを学習しましょう。</span><span class="sxs-lookup"><span data-stu-id="3e10c-128">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="3e10c-129">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e10c-129">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="3e10c-130">演算子</span><span class="sxs-lookup"><span data-stu-id="3e10c-130">Operator</span></span> | <span data-ttu-id="3e10c-131">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="3e10c-131">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="3e10c-132">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-132">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="3e10c-133">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-133">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="3e10c-134">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-134">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="3e10c-135">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-135">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="3e10c-136">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-136">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="3e10c-137">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-137">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="3e10c-138">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-138">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="3e10c-139">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-139">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="3e10c-140">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-140">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="3e10c-141">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-141">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="3e10c-142">これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-142">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="3e10c-143">データ型とクエリ構文の意味を理解する</span><span class="sxs-lookup"><span data-stu-id="3e10c-143">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="3e10c-144">高度な捜索テーブルのデータは、通常、次のデータ型に分類されます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-144">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="3e10c-145">データ型</span><span class="sxs-lookup"><span data-stu-id="3e10c-145">Data type</span></span> | <span data-ttu-id="3e10c-146">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="3e10c-146">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="3e10c-147">通常、イベントのタイムスタンプを表すデータおよび時間の情報</span><span class="sxs-lookup"><span data-stu-id="3e10c-147">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="3e10c-148">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="3e10c-148">Character string</span></span> |
| `bool` | <span data-ttu-id="3e10c-149">True または False</span><span class="sxs-lookup"><span data-stu-id="3e10c-149">True or False</span></span> |
| `int` | <span data-ttu-id="3e10c-150">32 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="3e10c-150">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="3e10c-151">64 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="3e10c-151">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="3e10c-152">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3e10c-152">Use sample queries</span></span>

<span data-ttu-id="3e10c-153">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-153">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="3e10c-154">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="3e10c-154">Try running these queries and making small modifications to them.</span></span>

![高度な捜索ウィンドウの画像](../images/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="3e10c-156">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e10c-156">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="3e10c-157">ページ左側の共有クエリまたは GitHub クエリ リポジトリを探します。</span><span class="sxs-lookup"><span data-stu-id="3e10c-157">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="3e10c-158">クエリ言語のドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="3e10c-158">Access query language documentation</span></span>

<span data-ttu-id="3e10c-159">Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/kusto/query/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e10c-159">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e10c-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e10c-160">Related topics</span></span>
- [<span data-ttu-id="3e10c-161">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="3e10c-161">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3e10c-162">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3e10c-162">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3e10c-163">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="3e10c-163">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3e10c-164">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3e10c-164">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3e10c-165">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="3e10c-165">Apply query best practices</span></span>](advanced-hunting-best-practices.md)