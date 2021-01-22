---
title: Microsoft 365 Defender での高度な検索クエリのベスト プラクティス
description: 高度な検索を使用して高速、効率的、およびエラーが発生する脅威の検索クエリを作成する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ、kusto、タイムアウト回避、コマンド ライン、プロセス ID、最適化、ベスト プラクティス、解析、参加、概要
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
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928476"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="353a8-104">高度な検索クエリのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="353a8-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="353a8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="353a8-105">**Applies to:**</span></span>
- <span data-ttu-id="353a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="353a8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="353a8-107">これらの推奨事項を適用して、結果をより速く取得し、複雑なクエリの実行中にタイムアウトを回避します。</span><span class="sxs-lookup"><span data-stu-id="353a8-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="353a8-108">クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="353a8-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="353a8-109">CPU リソース クォータについて</span><span class="sxs-lookup"><span data-stu-id="353a8-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="353a8-110">各テナントは、そのサイズに応じて、高度なハンティング クエリの実行に割り当てられた一連の CPU リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="353a8-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="353a8-111">さまざまなサービス制限の詳細については、高度な検索クォータと使用 [パラメーターに関するページを参照してください](advanced-hunting-limits.md)。</span><span class="sxs-lookup"><span data-stu-id="353a8-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="353a8-112">複数のクエリを定期的に実行しているお客様は、使用量を追跡し、この記事の最適化ガイダンスを適用して、クォータまたは使用パラメーターの超過による中断を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="353a8-113">一般的な最適化のヒント</span><span class="sxs-lookup"><span data-stu-id="353a8-113">General optimization tips</span></span>

- <span data-ttu-id="353a8-114">**新しいクエリのサイズ** を変更する - クエリが大きな結果セットを返す可能性がある場合は、カウント演算子を使用して最初に [評価します](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。</span><span class="sxs-lookup"><span data-stu-id="353a8-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="353a8-115">大 [きな結果セット](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) を回避するには、制限 `take` または類義語を使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="353a8-116">**フィルター** を早期に適用する - 時間フィルターや他のフィルターを適用して、データ セットを減らします。特に、部分 [文字列()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction) [、replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction) [、trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [、toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)、または [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)などの変換および解析関数を使用する前に行います。</span><span class="sxs-lookup"><span data-stu-id="353a8-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="353a8-117">次の例では、フィルター演算子によってレコード数が減った後に解析関数 [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="353a8-118">**Has beats contains**—To avoid searching substrings within words unnecessarly, use the `has` operator instead of `contains` .</span><span class="sxs-lookup"><span data-stu-id="353a8-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="353a8-119">文字列演算子の詳細</span><span class="sxs-lookup"><span data-stu-id="353a8-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="353a8-120">**特定の列を検索** する - すべての列でフルテキスト検索を実行するのではなく、特定の列を検索します。</span><span class="sxs-lookup"><span data-stu-id="353a8-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="353a8-121">すべての列を `*` チェックするために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="353a8-122">**速度に対して大文字と** 小文字が区別されます。大文字と小文字を区別した検索は、より具体的で、一般的にパフォーマンスが高い検索です。</span><span class="sxs-lookup"><span data-stu-id="353a8-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="353a8-123">大文字と小文字を区別する [文字列演算子の名前](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)(および `has_cs` 一般に末尾が `contains_cs` `_cs` .</span><span class="sxs-lookup"><span data-stu-id="353a8-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="353a8-124">代わりに、大文字と小文字を区別する等号 `==` 演算子を使用することもできます `=~` 。</span><span class="sxs-lookup"><span data-stu-id="353a8-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="353a8-125">**解析、抽出しない**—できる限り、解析演算子または [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) [parse_json() のような解析関数を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)。</span><span class="sxs-lookup"><span data-stu-id="353a8-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="353a8-126">文字列演算子 `matches regex` または [extract() 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)は、どちらも正規表現を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="353a8-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="353a8-127">より複雑なシナリオでは、正規表現の使用を予約してください。</span><span class="sxs-lookup"><span data-stu-id="353a8-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="353a8-128">関数の解析の詳細</span><span class="sxs-lookup"><span data-stu-id="353a8-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="353a8-129">**式ではなくテーブルをフィルター** 処理する - テーブルの列でフィルター処理できる場合は、集計列に対してフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="353a8-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="353a8-130">**3 文字の用語なし**- 3 文字以下の用語を使用して比較またはフィルター処理を行うのを避ける。</span><span class="sxs-lookup"><span data-stu-id="353a8-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="353a8-131">これらの用語はインデックス付けされません。一致する場合は、より多くのリソースが必要になります。</span><span class="sxs-lookup"><span data-stu-id="353a8-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="353a8-132">**プロジェクトの選択**— 必要な列のみを投影することで、結果を理解しやすくします。</span><span class="sxs-lookup"><span data-stu-id="353a8-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="353a8-133">結合または同様の操作を実行する前に [特定](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) の列を投影すると、パフォーマンスも向上します。</span><span class="sxs-lookup"><span data-stu-id="353a8-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="353a8-134">演算子を最適化 `join` する</span><span class="sxs-lookup"><span data-stu-id="353a8-134">Optimize the `join` operator</span></span>
<span data-ttu-id="353a8-135">結合 [演算子は、指定](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) された列の値を照合して、2 つのテーブルの行を結合します。</span><span class="sxs-lookup"><span data-stu-id="353a8-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="353a8-136">これらのヒントを適用して、この演算子を使用するクエリを最適化します。</span><span class="sxs-lookup"><span data-stu-id="353a8-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="353a8-137">**左に小さい** テーブル — 演算子は、結合ステートメントの左側にあるテーブル内のレコードを右側の `join` レコードに一致します。</span><span class="sxs-lookup"><span data-stu-id="353a8-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="353a8-138">小さいテーブルを左側に置く場合、一致する必要があるレコードが少なめなので、クエリの速度が上がっています。</span><span class="sxs-lookup"><span data-stu-id="353a8-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="353a8-139">次の表では、アカウントの SID で参加する前に、3 つの特定のデバイスのみをカバーするために左 `DeviceLogonEvents` の表 `IdentityLogonEvents` を減らします。</span><span class="sxs-lookup"><span data-stu-id="353a8-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- <span data-ttu-id="353a8-140">**内部** 結合の味を使用します。左 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)のテーブルの既定 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)の結合方法または内部結合重複データ行は、右のテーブルに一致するごとに行を返す前に結合キーによって結合キーによって重複します。</span><span class="sxs-lookup"><span data-stu-id="353a8-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="353a8-141">左の表にキーの同じ値を持つ複数の行がある場合、それらの行は重複排除され、一意の値ごとに 1 つのランダムな行 `join` が残されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="353a8-142">この既定の動作では、有用な分析情報を提供できる重要な情報が左側の表から取り残される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="353a8-143">たとえば、次のクエリでは、同じ添付ファイルが複数の電子メール メッセージを使用して送信された場合でも、特定の添付ファイルを含む 1 つのメールだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="353a8-144">この制限に対処するために、左側の[](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)表のすべての行を右に一致する値で表示するために、内部結合機能 `kind=inner` を適用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="353a8-145">**タイム ウィンドウからレコード** を参加する - セキュリティ イベントを調査するときに、アナリストは同じ期間に発生する関連イベントを探します。</span><span class="sxs-lookup"><span data-stu-id="353a8-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="353a8-146">同じ方法を使用する場合も、チェックするレコードの数を減らすことでパフォーマンス `join` が向上します。</span><span class="sxs-lookup"><span data-stu-id="353a8-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="353a8-147">次のクエリは、悪意のあるファイルを受信した 30 分以内にログオン イベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="353a8-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- <span data-ttu-id="353a8-148">**両側に** 時間フィルターを適用する - 特定のタイム ウィンドウを調査していない場合でも、左右の両方のテーブルに時間フィルターを適用すると、確認してパフォーマンスを向上させるレコードの数を減らします。 `join`</span><span class="sxs-lookup"><span data-stu-id="353a8-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="353a8-149">次のクエリは、過去 1 時間のレコードのみを結合するために、両方の `Timestamp > ago(1h)` テーブルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="353a8-150">**パフォーマンスにヒントを使用** する — 演算子と一緒にヒントを使用して、リソースを大量に消費する操作を実行するときに負荷を分散 `join` するようにバックエンドに指示します。</span><span class="sxs-lookup"><span data-stu-id="353a8-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="353a8-151">参加ヒントの詳細</span><span class="sxs-lookup"><span data-stu-id="353a8-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="353a8-152">たとえば、次の **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** クエリなど、多くの一意の値を持つキーである高いカーディナリティを持つキーを使用してテーブルを結合する場合、シャッフル ヒントを使用すると、クエリのパフォーマンスが向上 `AccountObjectId` します。</span><span class="sxs-lookup"><span data-stu-id="353a8-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="353a8-153">ブロードキャスト **[ヒントは、](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 左の表が小さく (最大 100,000 レコード)、右側のテーブルが非常に大きい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="353a8-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="353a8-154">たとえば、次のクエリは、特定の件名を持ついくつかの電子メールを、テーブル内のリンクを含むすべてのメッセージに参加 `EmailUrlInfo` させようとしています。</span><span class="sxs-lookup"><span data-stu-id="353a8-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="353a8-155">演算子を最適化 `summarize` する</span><span class="sxs-lookup"><span data-stu-id="353a8-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="353a8-156">集計 [演算子は](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 、テーブルの内容を集計します。</span><span class="sxs-lookup"><span data-stu-id="353a8-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="353a8-157">これらのヒントを適用して、この演算子を使用するクエリを最適化します。</span><span class="sxs-lookup"><span data-stu-id="353a8-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="353a8-158">**異なる値を** 検索する —一般に、繰り返し `summarize` 使用できる個別の値を検索するために使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="353a8-159">繰り返し値のない列を集計するために使用する必要が生じ得る。</span><span class="sxs-lookup"><span data-stu-id="353a8-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="353a8-160">1 つの電子メールは複数のイベントに含めることができますが、次の例では、個々の電子メールのネットワーク メッセージ ID に常に一意の送信者アドレスが付くため、効率的に `summarize` 使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="353a8-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="353a8-161">演算子 `summarize` は簡単に置き換えられるので、リソースを少なくしながら同じ結果 `project` が得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="353a8-162">次の例は、同じ受信者のアドレスに電子メールを送信する送信者アドレスの複数の異なるインスタンスが考えられます `summarize` 。</span><span class="sxs-lookup"><span data-stu-id="353a8-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="353a8-163">このような組み合わせは区別が少なく、重複する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="353a8-164">**クエリの** シャッフル — 繰り返し値を持つ列で使用すると最も便利ですが、同じ列に高い基数や多数の一意の値を設定 `summarize` することもできます。 </span><span class="sxs-lookup"><span data-stu-id="353a8-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="353a8-165">演算子と同様に、シャッフル ヒントを適用して処理負荷を分散し、高い基数で列を操作するときにパフォーマンスを向上させる可能性 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="353a8-166">次のクエリは、大規模な組織の数十万人の中で実行できる、個別の受信者の電子メール アドレス `summarize` をカウントするために使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="353a8-167">パフォーマンスを向上させるために、次の機能が組み込されています `hint.shufflekey` 。</span><span class="sxs-lookup"><span data-stu-id="353a8-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="353a8-168">クエリ シナリオ</span><span class="sxs-lookup"><span data-stu-id="353a8-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="353a8-169">プロセス ID を使用して一意のプロセスを識別する</span><span class="sxs-lookup"><span data-stu-id="353a8-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="353a8-170">Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="353a8-171">そのため、それ単体では特定のプロセスの一意の識別子として機能しません。</span><span class="sxs-lookup"><span data-stu-id="353a8-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="353a8-172">特定のコンピューター上のプロセスの一意の識別子を取得するには、プロセス ID をプロセスの作成日時と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="353a8-173">プロセスに関するデータを結合または集計する際は、コンピューターの識別子の列 (`DeviceId` または `DeviceName`)、プロセス ID (`ProcessId` または `InitiatingProcessId`)、およびプロセスの作成日時 (`ProcessCreationTime` または `InitiatingProcessCreationTime`) を含めます。</span><span class="sxs-lookup"><span data-stu-id="353a8-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="353a8-174">次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="353a8-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="353a8-175">クエリ例:</span><span class="sxs-lookup"><span data-stu-id="353a8-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="353a8-176">このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="353a8-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="353a8-177">クエリコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="353a8-177">Query command lines</span></span>
<span data-ttu-id="353a8-178">タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。</span><span class="sxs-lookup"><span data-stu-id="353a8-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="353a8-179">たとえば、攻撃者は、パスのない画像ファイル、ファイル拡張子のない画像ファイル、環境変数、引用符を使用して画像ファイルを参照する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="353a8-180">攻撃者は、パラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="353a8-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="353a8-181">コマンド ラインに対してより永続的なクエリを作成するには、次のプラクティスを適用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="353a8-182">コマンド ライン自体でフィルター *処理* するのではなく、ファイル名フィールドを照合して既知のプロセス (net.exeやpsexec.exe *など)* を特定します。</span><span class="sxs-lookup"><span data-stu-id="353a8-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="353a8-183">parse_command_line() 関数を使用してコマンド [ライン セクションを解析する](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="353a8-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="353a8-184">コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。</span><span class="sxs-lookup"><span data-stu-id="353a8-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="353a8-185">代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="353a8-186">大文字と小文字を区別しない一致を使用します。</span><span class="sxs-lookup"><span data-stu-id="353a8-186">Use case insensitive matches.</span></span> <span data-ttu-id="353a8-187">たとえば、, `=~` , `in~` , and `contains` の代わりに `==` , `in` とを使用します `contains_cs` 。</span><span class="sxs-lookup"><span data-stu-id="353a8-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="353a8-188">コマンドライン難読化の手法を軽減するには、引用符を削除し、コンマをスペースに置き換え、連続する複数のスペースを 1 つのスペースに置き換える方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="353a8-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="353a8-189">他のアプローチを必要とするより複雑な難読化技術がありますが、これらの調整は一般的な方法に対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="353a8-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="353a8-190">次の例は、ファイアウォール サービス "MpsSvc" を停止するファイルを検索するクエリ *net.exe* を作成するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="353a8-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="353a8-191">外部ソースからデータを取り込む</span><span class="sxs-lookup"><span data-stu-id="353a8-191">Ingest data from external sources</span></span>
<span data-ttu-id="353a8-192">長いリストまたは大きなテーブルをクエリに組み込むには [、externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 演算子を使用して、指定した URI からデータを取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="353a8-193">TXT、CSV、JSON などの形式のファイルからデータ [を取得できます](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。</span><span class="sxs-lookup"><span data-stu-id="353a8-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="353a8-194">次の例は、MalwareB malwarear (abuse.ch) によって提供されるマルウェア SHA-256 ハッシュの広範なリストを利用して、電子メールの添付ファイルを確認する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="353a8-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a><span data-ttu-id="353a8-195">文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="353a8-195">Parse strings</span></span>
<span data-ttu-id="353a8-196">解析または変換を必要とする文字列を効率的に処理するために使用できるさまざまな関数があります。</span><span class="sxs-lookup"><span data-stu-id="353a8-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="353a8-197">String</span><span class="sxs-lookup"><span data-stu-id="353a8-197">String</span></span> | <span data-ttu-id="353a8-198">関数</span><span class="sxs-lookup"><span data-stu-id="353a8-198">Function</span></span> | <span data-ttu-id="353a8-199">使用例</span><span class="sxs-lookup"><span data-stu-id="353a8-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="353a8-200">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="353a8-200">Command-lines</span></span> | [<span data-ttu-id="353a8-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="353a8-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="353a8-202">コマンドとすべての引数を抽出します。</span><span class="sxs-lookup"><span data-stu-id="353a8-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="353a8-203">Paths</span><span class="sxs-lookup"><span data-stu-id="353a8-203">Paths</span></span> | [<span data-ttu-id="353a8-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="353a8-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="353a8-205">ファイルまたはフォルダーのパスのセクションを抽出します。</span><span class="sxs-lookup"><span data-stu-id="353a8-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="353a8-206">バージョン番号</span><span class="sxs-lookup"><span data-stu-id="353a8-206">Version numbers</span></span> | [<span data-ttu-id="353a8-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="353a8-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="353a8-208">1 つのセクションに最大 4 つのセクションと最大 8 文字のバージョン番号を展開します。</span><span class="sxs-lookup"><span data-stu-id="353a8-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="353a8-209">解析されたデータを使用してバージョンの保存時間を比較します。</span><span class="sxs-lookup"><span data-stu-id="353a8-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="353a8-210">IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="353a8-210">IPv4 addresses</span></span> | [<span data-ttu-id="353a8-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="353a8-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="353a8-212">IPv4 アドレスを長整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="353a8-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="353a8-213">IPv4 アドレスを変換せずに比較するには [、ipv4_compare() を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="353a8-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="353a8-214">IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="353a8-214">IPv6 addresses</span></span> | [<span data-ttu-id="353a8-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="353a8-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="353a8-216">IPv4 または IPv6 アドレスを正規の IPv6 表記に変換します。</span><span class="sxs-lookup"><span data-stu-id="353a8-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="353a8-217">IPv6 アドレスを比較するには [、ipv6_compare() を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。</span><span class="sxs-lookup"><span data-stu-id="353a8-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="353a8-218">サポートされている解析関数の詳細については [、Kusto 文字列関数を参照してください](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。</span><span class="sxs-lookup"><span data-stu-id="353a8-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="353a8-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="353a8-219">Related topics</span></span>
- [<span data-ttu-id="353a8-220">Kusto クエリ言語のドキュメント</span><span class="sxs-lookup"><span data-stu-id="353a8-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="353a8-221">クォータと使用パラメータ</span><span class="sxs-lookup"><span data-stu-id="353a8-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="353a8-222">高度なハンティング エラーの処理</span><span class="sxs-lookup"><span data-stu-id="353a8-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="353a8-223">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="353a8-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="353a8-224">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="353a8-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
