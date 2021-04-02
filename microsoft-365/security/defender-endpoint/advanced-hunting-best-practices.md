---
title: 高度な検索のクエリのベスト プラクティス
description: 高度な検索を使用する場合に、迅速かつ効率的で、エラーのない脅威検索クエリを作成する方法について説明します。
keywords: 高度な狩猟、脅威狩り、サイバー脅威の狩猟、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、回避タイムアウト、コマンド ライン、プロセス ID
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499255"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="840e5-104">高度な検索クエリのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="840e5-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="840e5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="840e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="840e5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="840e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="840e5-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="840e5-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="840e5-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="840e5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="840e5-109">クエリのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="840e5-109">Optimize query performance</span></span>

<span data-ttu-id="840e5-110">これらの推奨事項を適用して、結果をより速く取得し、複雑なクエリの実行中にタイムアウトを回避します。</span><span class="sxs-lookup"><span data-stu-id="840e5-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="840e5-111">新しいクエリを試行するときは、結果セットが大きくなり過ぎないよう、常に `limit` を使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="840e5-112">`count` を使用して結果セットのサイズを最初に判断することもできます。</span><span class="sxs-lookup"><span data-stu-id="840e5-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="840e5-113">最初に時間フィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-113">Use time filters first.</span></span> <span data-ttu-id="840e5-114">クエリを 7 日に制限するのが理想です。</span><span class="sxs-lookup"><span data-stu-id="840e5-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="840e5-115">時間フィルターの適用直後に、ほとんどのデータがクエリの開始時に除外されるようなフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="840e5-116">完全なトークンを検索する場合の演算子として、`contains` ではなく `has` を使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="840e5-117">すべての列に対して全文検索を実行するのではなく、特定の列を検索します。</span><span class="sxs-lookup"><span data-stu-id="840e5-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="840e5-118">テーブルを結合するときは、最初は行数が少ないテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="840e5-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="840e5-119">`project` は、結合したテーブルの必要な列に対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="840e5-120">クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="840e5-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="840e5-121">クエリのヒントと落とし穴</span><span class="sxs-lookup"><span data-stu-id="840e5-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="840e5-122">プロセス ID を使用するクエリ</span><span class="sxs-lookup"><span data-stu-id="840e5-122">Queries with process IDs</span></span>

<span data-ttu-id="840e5-123">Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。</span><span class="sxs-lookup"><span data-stu-id="840e5-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="840e5-124">そのため、それ単体では特定のプロセスの一意の識別子として機能しません。</span><span class="sxs-lookup"><span data-stu-id="840e5-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="840e5-125">特定のデバイス上のプロセスの一意の識別子を取得するには、プロセスの作成時間と共にプロセス ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="840e5-126">プロセスに関するデータを結合または集計する場合は、デバイス識別子 (または) 、プロセス ID (または)、およびプロセス作成時間 (または) の列を `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` 含 `ProcessCreationTime` める `InitiatingProcessCreationTime` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="840e5-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="840e5-127">次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="840e5-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="840e5-128">このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="840e5-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="840e5-129">コマンド ラインを使用したクエリ</span><span class="sxs-lookup"><span data-stu-id="840e5-129">Queries with command lines</span></span>

<span data-ttu-id="840e5-130">さまざまなコマンド ラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="840e5-130">Command lines can vary.</span></span> <span data-ttu-id="840e5-131">該当する場合は、ファイル名をフィルター処理し、あいまい一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="840e5-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="840e5-132">タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。</span><span class="sxs-lookup"><span data-stu-id="840e5-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="840e5-133">たとえば、攻撃者が画像ファイルを参照する際に、パスを使用する場合、パスを使用しない場合、ファイル拡張子を使用しない場合、環境変数を使用する場合、または引用符を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="840e5-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="840e5-134">また、攻撃者はパラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="840e5-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="840e5-135">コマンドラインを使用してより強力なクエリを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="840e5-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="840e5-136">コマンド ライン フィールドを使用してフィルター処理をするのではなく、filename フィールドを一致させることにより既知のプロセス (*net.exe* または *psexec.exe*) を特定します。</span><span class="sxs-lookup"><span data-stu-id="840e5-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="840e5-137">コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。</span><span class="sxs-lookup"><span data-stu-id="840e5-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="840e5-138">代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="840e5-139">大文字と小文字を区別しない一致を使用します。</span><span class="sxs-lookup"><span data-stu-id="840e5-139">Use case insensitive matches.</span></span> <span data-ttu-id="840e5-140">たとえば、 `=~` 、 、 `in~` の代 `contains` わりに 、 `==` を使用 `in` します。 `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="840e5-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="840e5-141">DOS コマンドラインの難読化手法に対処するには、引用符を削除し、コンマをスペースで置き換え、連続する複数のスペースをスペース 1 つで置き換えることを検討します。</span><span class="sxs-lookup"><span data-stu-id="840e5-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="840e5-142">他の方法を使用しないと対処することが難しいより複雑な DOS 難読化手法がありますが、上記の対処法は、最も一般的な手法に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="840e5-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="840e5-143">以下の例では、Windows Defender ファイアウォール サービスを停止させる *net.exe* というファイルを検索するクエリを作成するためのさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="840e5-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> <span data-ttu-id="840e5-144">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="840e5-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="840e5-145">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="840e5-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="840e5-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="840e5-146">Related topics</span></span>

- [<span data-ttu-id="840e5-147">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="840e5-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="840e5-148">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="840e5-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="840e5-149">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="840e5-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="840e5-150">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="840e5-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="840e5-151">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="840e5-151">Custom detections overview</span></span>](overview-custom-detections.md)
