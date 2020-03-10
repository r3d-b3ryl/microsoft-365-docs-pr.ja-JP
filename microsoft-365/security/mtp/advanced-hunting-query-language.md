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
ms.openlocfilehash: 7f2cf7f62060774343354467d27b76456f6581fc
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2020
ms.locfileid: "42567033"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="98331-104">高度な捜索のクエリ言語について学習する</span><span class="sxs-lookup"><span data-stu-id="98331-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="98331-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="98331-105">**Applies to:**</span></span>
- <span data-ttu-id="98331-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="98331-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="98331-107">高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="98331-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="98331-108">Kusto 構文および演算子を使用して、高度な捜索用に特別に構造化された[スキーマ](advanced-hunting-schema-tables.md)内の情報を検索するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="98331-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="98331-109">これらの概念をよりよく理解するために、最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="98331-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="98331-110">最初のクエリを試してみる</span><span class="sxs-lookup"><span data-stu-id="98331-110">Try your first query</span></span>

<span data-ttu-id="98331-111">Microsoft 365 セキュリティセンターで、「検索 **」に移動**して最初のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="98331-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="98331-112">次の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="98331-112">Use the following example:</span></span>

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

<span data-ttu-id="98331-113">これは、高度な捜索でどのように見えるかを示します。</span><span class="sxs-lookup"><span data-stu-id="98331-113">This is how it will look like in advanced hunting.</span></span>

![Microsoft Threat Protection の高度な検索クエリの画像](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="98331-115">クエリの先頭に短いコメントが追加されました。その目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="98331-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="98331-116">これは、後でクエリを保存して組織内の他のユーザーと共有する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="98331-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="98331-117">通常、クエリ自体はテーブル名から始まり、続いてパイプ (`|`) で始まる一連の要素が続きます。</span><span class="sxs-lookup"><span data-stu-id="98331-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="98331-118">この例では、まず、2つのテーブル`DeviceProcessEvents`のユニオンを作成`DeviceNetworkEvents`し、を、必要に応じてパイプライン処理された要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="98331-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="98331-119">最初のパイプライン処理された要素は、前の7日間を対象範囲とする時間フィルターです。</span><span class="sxs-lookup"><span data-stu-id="98331-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="98331-120">時間範囲をできる限り狭くすることで、クエリが適切に実行され、管理可能な結果が返され、タイムアウトが回避されます。</span><span class="sxs-lookup"><span data-stu-id="98331-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="98331-121">時間範囲の直後には、PowerShell アプリケーションを表すプロセスファイル名の検索が続きます。</span><span class="sxs-lookup"><span data-stu-id="98331-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="98331-122">その後、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンドラインの文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="98331-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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
<span data-ttu-id="98331-123">クエリによって、検索するデータが明確に識別されるようになったので、結果の見た目を定義する要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="98331-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="98331-124">`project`特定の列を`top`返し、結果の数を制限して、結果が適切に書式設定され、大幅に処理しやすいことを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98331-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="98331-125">[**クエリの実行**] をクリックして結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="98331-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="98331-126">クエリエディターの右上にある展開アイコンを選択して、お探しのクエリと結果にフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="98331-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![高度な検索クエリエディターの展開コントロールのイメージ](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="98331-128">高度な捜索のための一般的なクエリ演算子を学習する</span><span class="sxs-lookup"><span data-stu-id="98331-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="98331-129">最初のクエリを実行し、そのコンポーネントの一般的な概念を理解したので、少しだけ遡って基本的なことを学習しましょう。</span><span class="sxs-lookup"><span data-stu-id="98331-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="98331-130">高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="98331-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="98331-131">演算子</span><span class="sxs-lookup"><span data-stu-id="98331-131">Operator</span></span> | <span data-ttu-id="98331-132">説明および使用法</span><span class="sxs-lookup"><span data-stu-id="98331-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="98331-133">述語に適合する行のサブセットにテーブルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="98331-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="98331-134">入力テーブルの内容を集約したテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="98331-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="98331-135">各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="98331-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="98331-136">入力レコード セットのレコード数を返します。</span><span class="sxs-lookup"><span data-stu-id="98331-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="98331-137">指定された列によって並べ替えられた最初の N レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="98331-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="98331-138">指定された行数まで返します。</span><span class="sxs-lookup"><span data-stu-id="98331-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="98331-139">新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。</span><span class="sxs-lookup"><span data-stu-id="98331-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="98331-140">計算列を作成し、結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="98331-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="98331-141">Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。</span><span class="sxs-lookup"><span data-stu-id="98331-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="98331-142">テーブルのセットで述語と一致する行を検索します。</span><span class="sxs-lookup"><span data-stu-id="98331-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="98331-143">これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。</span><span class="sxs-lookup"><span data-stu-id="98331-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="98331-144">データ型とクエリ構文の意味を理解する</span><span class="sxs-lookup"><span data-stu-id="98331-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="98331-145">高度な捜索テーブルのデータは、通常、次のデータ型に分類されます。</span><span class="sxs-lookup"><span data-stu-id="98331-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="98331-146">データ型</span><span class="sxs-lookup"><span data-stu-id="98331-146">Data type</span></span> | <span data-ttu-id="98331-147">説明とクエリの意味</span><span class="sxs-lookup"><span data-stu-id="98331-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="98331-148">通常、イベントのタイムスタンプを表すデータおよび時間の情報</span><span class="sxs-lookup"><span data-stu-id="98331-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="98331-149">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="98331-149">Character string</span></span> |
| `bool` | <span data-ttu-id="98331-150">True または False</span><span class="sxs-lookup"><span data-stu-id="98331-150">True or false</span></span> |
| `int` | <span data-ttu-id="98331-151">32 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="98331-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="98331-152">64 ビットの数値</span><span class="sxs-lookup"><span data-stu-id="98331-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="98331-153">サンプル クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="98331-153">Use sample queries</span></span>

<span data-ttu-id="98331-154">[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。</span><span class="sxs-lookup"><span data-stu-id="98331-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="98331-155">これらのクエリを実行して、少し変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="98331-155">Try running these queries and making small modifications to them.</span></span>

![高度な捜索ウィンドウの画像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="98331-157">基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="98331-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="98331-158">ページ左側の共有クエリまたは GitHub クエリ リポジトリを探します。</span><span class="sxs-lookup"><span data-stu-id="98331-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="98331-159">クエリ言語のドキュメントにアクセスする</span><span class="sxs-lookup"><span data-stu-id="98331-159">Access query language documentation</span></span>

<span data-ttu-id="98331-160">Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/kusto/query/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98331-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="98331-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="98331-161">Related topics</span></span>
- [<span data-ttu-id="98331-162">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="98331-162">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98331-163">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="98331-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="98331-164">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="98331-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="98331-165">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="98331-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="98331-166">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="98331-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
