---
title: Microsoft Threat Protection の高度な検索クエリのベストプラクティス
description: 高度な検索を使用して迅速、効率的、およびエラーのない脅威を探すためのクエリを作成する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、timeout、コマンドライン、プロセス id、最適化、ベストプラクティス、解析、参加、要約
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
ms.openlocfilehash: e3b29a8182e38fa05e5f791478157c978632fb13
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477007"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="b1d3e-104">高度な検索クエリのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="b1d3e-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b1d3e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b1d3e-105">**Applies to:**</span></span>
- <span data-ttu-id="b1d3e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b1d3e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b1d3e-107">これらの推奨事項を適用して、結果を迅速に取得し、複雑なクエリの実行中にタイムアウトを回避します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="b1d3e-108">クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-limits"></a><span data-ttu-id="b1d3e-109">CPU リソースの制限を理解する</span><span class="sxs-lookup"><span data-stu-id="b1d3e-109">Understand CPU resource limits</span></span>
<span data-ttu-id="b1d3e-110">各テナントは、そのサイズに応じて、高度な検索クエリの実行に割り当てられた CPU リソースの設定済み容量にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="b1d3e-111">さまざまなサービス制限の詳細については、 [「アドバンス検索の制限について](advanced-hunting-limits.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-111">For detailed information about various service limits, [read about advanced hunting limits](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="b1d3e-112">複数のクエリを定期的に実行する必要がある場合は、この記事の最適化ガイダンスを使用して、制限を超えたことによる影響を最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding the limits.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="b1d3e-113">一般的な最適化のヒント</span><span class="sxs-lookup"><span data-stu-id="b1d3e-113">General optimization tips</span></span>

- <span data-ttu-id="b1d3e-114">**新しいクエリのサイズ**変更-クエリが大きな結果セットを返すことが疑われる場合は、まず [count 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)を使用して評価します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="b1d3e-115">大きな結果セットを使用しないように [制限](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) またはシノニムを使用し `take` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="b1d3e-116">**事前にフィルターを適用**する-タイムフィルターとその他のフィルターを適用してデータセットを縮小します。特に、変換関数と解析関数 ( [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、 [replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)、または [parse_json () など)](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)を使用する前に行います。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="b1d3e-117">次の例では、フィルター演算子を使用してレコード数を減らした後、解析関数 [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="b1d3e-118">拍の数が**含まれている**-単語内のサブ文字列を不必要に検索しないようにするには、ではなく演算子を使用し `has` `contains` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="b1d3e-119">文字列演算子について</span><span class="sxs-lookup"><span data-stu-id="b1d3e-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="b1d3e-120">**[特定の列を検索**する]: すべての列で全文検索を実行するのではなく、特定の列を参照します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="b1d3e-121">すべての `*` 列のチェックには使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="b1d3e-122">**大文字**と小文字を区別します。大文字と小文字を区別する検索はより具体的で、一般的にパフォーマンスが高くなります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="b1d3e-123">大文字と小文字が区別された [文字列演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)の名前 ( `has_cs` および `contains_cs` は通常、で終わる) `_cs` 。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="b1d3e-124">また、ではなく、大文字と小文字を区別する等値演算子を使用することもでき `==` `=~` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="b1d3e-125">**Parse (抽出しない**): 可能であれば、 [parse 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) または [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)のような解析関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="b1d3e-126">`matches regex`文字列演算子または[extract () 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)を使用しないでください。両方で正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="b1d3e-127">より複雑なシナリオのために正規表現の使用を予約します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="b1d3e-128">解析関数の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="b1d3e-129">[**テーブルに式**を適用しない]: テーブルの列にフィルターを適用する場合は、集計列に対してフィルターを適用しません。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="b1d3e-130">**3 文字の用語はありません**。3文字以下の用語を使用して、比較またはフィルターを適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="b1d3e-131">これらの用語はインデックス付けされず、一致するリソースが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="b1d3e-132">**選択的**に表示する: 必要な列だけを射影して、結果をわかりやすくします。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="b1d3e-133">[Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)または同様の操作を実行する前に特定の列を予測することも、パフォーマンスの向上に貢献します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="b1d3e-134">演算子を最適化する `join`</span><span class="sxs-lookup"><span data-stu-id="b1d3e-134">Optimize the `join` operator</span></span>
<span data-ttu-id="b1d3e-135">[Join 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)は、指定した列の値を一致させることによって、2つのテーブルの行を結合します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="b1d3e-136">この演算子を使用するクエリを最適化するには、以下のヒントを適用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="b1d3e-137">**左側に小さなテーブル** `join` 。演算子は join ステートメントの左側にあるテーブルのレコードを右側のレコードに一致させる。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="b1d3e-138">小さい方のテーブルを左側に配置することで、一致する必要があるレコードが少なくなるため、クエリを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="b1d3e-139">次の表では、左側の表を、 `DeviceLogonEvents` アカウント sid で結合する前に3つの特定のデバイスのみカバーするように減らして `IdentityLogonEvents` います。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="b1d3e-140">**内部結合のフレーバーを使用**します。既定の [結合フレーバー](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) または [innerunique-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) join は、左側のテーブルの行を返す前に、結合キーを使用して、右のテーブルと一致する行を返します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="b1d3e-141">左側のテーブルにキーに同じ値を持つ複数の行がある場合 `join` 、これらの行は、一意の値ごとに単一のランダムな行を残すように deduplicated されます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="b1d3e-142">この既定の動作により、役に立つ洞察を提供できる左側の表から重要な情報が残らないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="b1d3e-143">たとえば、次のクエリは、同じ添付ファイルが複数のメールメッセージを使用して送信された場合でも、特定の添付ファイルを含む1つの電子メールのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="b1d3e-144">この制限に対処するには、 [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)左側の表のすべての `kind=inner` 行を右に一致する値で表示するように指定して、内部結合のフレーバーを適用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="b1d3e-145">**時間枠からレコードを結合**する: セキュリティイベントを調査する際に、アナリストは、同じ期間に発生する関連イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="b1d3e-146">同じ方法を使用する場合は、 `join` 確認するレコードの数を減らして、パフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="b1d3e-147">次のクエリは、悪意のあるファイルを受信してから30分以内にログオンイベントをチェックします。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="b1d3e-148">**両方の側に時間フィルターを適用**します。特定のタイムウィンドウを調査していない場合でも、左と右の両方のテーブルで時間フィルターを適用すると、確認してパフォーマンスを向上させるためのレコード数を減らすことができ `join` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="b1d3e-149">次のクエリは両方のテーブルに適用され、 `Timestamp > ago(1h)` 過去1時間のレコードのみが結合されるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="b1d3e-150">**ヒントを使用してパフォーマンスを向上**させる: `join` リソース集中型の操作を実行するときに負荷を分散するようにバックエンドに指示するには、オペレーターとのヒントを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="b1d3e-151">結合ヒントの詳細情報</span><span class="sxs-lookup"><span data-stu-id="b1d3e-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="b1d3e-152">たとえば、次のクエリのように、長いカーディナリティを持つキーを使用してテーブルを結合する場合は、 **[シャッフルヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** によってクエリパフォーマンスが向上し `AccountObjectId` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="b1d3e-153">**[ブロードキャストヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** は、左テーブルが小さい (最大10万レコード)、右テーブルが非常に大きい場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="b1d3e-154">たとえば、次のクエリは、テーブルにリンクが含まれる _すべて_ のメッセージに特定の件名を持つ少数の電子メールに参加しようとしてい `EmailUrlInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="b1d3e-155">演算子を最適化する `summarize`</span><span class="sxs-lookup"><span data-stu-id="b1d3e-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="b1d3e-156">[集約演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)は、テーブルの内容を集約します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="b1d3e-157">この演算子を使用するクエリを最適化するには、以下のヒントを適用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="b1d3e-158">**Distinct 値を検索**する一般的に、を使用し `summarize` て、繰り返し可能な個別の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="b1d3e-159">繰り返し値を持たない列を集計するために使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="b1d3e-160">1つの電子メールは複数のイベントの一部にすることができますが、次の例では、個々の電子メールのネットワークメッセージ ID には常に固有の送信者アドレスが含まれるため、を使用するのは効率的では _ありません_ `summarize` 。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="b1d3e-161">`summarize`演算子は簡単に置き換えることができ、同じ結果になる可能性があるので、リソースの使用 `project` 量が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="b1d3e-162">次の例は、 `summarize` 同じ受信者アドレスに電子メールを送信する送信者アドレスの複数の異なるインスタンスが存在する可能性があるため、より効率的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="b1d3e-163">このような組み合わせは区別が少なく、重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="b1d3e-164">**クエリをシャッフル**する- `summarize` 繰り返しの値を持つ列で使用するのに適していますが、同じ列に _基数_ または大量の一意の値が含まれている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="b1d3e-165">演算子と同様に、 `join` 処理の負荷を分散するために、を使用して [シャッフルヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) を適用し、 `summarize` カーディナリティを使用して列を操作するときにパフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="b1d3e-166">次のクエリは、 `summarize` 個別の受信者の電子メールアドレスをカウントするために使用します。これは、大規模な組織では数十万数の組織で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="b1d3e-167">パフォーマンスを向上させるために、次の組み込みが組み込まれてい `hint.shufflekey` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="b1d3e-168">クエリシナリオ</span><span class="sxs-lookup"><span data-stu-id="b1d3e-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="b1d3e-169">プロセス Id を使用して一意のプロセスを識別する</span><span class="sxs-lookup"><span data-stu-id="b1d3e-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="b1d3e-170">Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="b1d3e-171">そのため、それ単体では特定のプロセスの一意の識別子として機能しません。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="b1d3e-172">特定のコンピューター上のプロセスの一意の識別子を取得するには、プロセス ID をプロセスの作成日時と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="b1d3e-173">プロセスに関するデータを結合または集計する際は、コンピューターの識別子の列 (`DeviceId` または `DeviceName`)、プロセス ID (`ProcessId` または `InitiatingProcessId`)、およびプロセスの作成日時 (`ProcessCreationTime` または `InitiatingProcessCreationTime`) を含めます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="b1d3e-174">次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="b1d3e-175">クエリ例:</span><span class="sxs-lookup"><span data-stu-id="b1d3e-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="b1d3e-176">このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="b1d3e-177">クエリコマンドライン</span><span class="sxs-lookup"><span data-stu-id="b1d3e-177">Query command lines</span></span>
<span data-ttu-id="b1d3e-178">タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="b1d3e-179">たとえば、攻撃者は、ファイル拡張子を使用せず、環境変数を使用することも、引用符を使用しても、パスを含まないイメージファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="b1d3e-180">また、パラメーターの順序を変更したり、複数の引用符とスペースを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="b1d3e-181">コマンドラインを中心とした永続的なクエリを作成するには、以下の手順を適用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="b1d3e-182">コマンドライン自体にフィルターを適用するのではなく、ファイル名のフィールドに一致することによって、既知のプロセス ( *net.exe* 、 *psexec.exe*など) を特定します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="b1d3e-183">[Parse_command_line () 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)を使用してコマンドラインセクションを解析する</span><span class="sxs-lookup"><span data-stu-id="b1d3e-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="b1d3e-184">コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="b1d3e-185">代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="b1d3e-186">大文字と小文字を区別しない一致を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-186">Use case insensitive matches.</span></span> <span data-ttu-id="b1d3e-187">たとえば、、、、、、、を使用し `=~` `in~` `contains` `==` `in` `contains_cs` ます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="b1d3e-188">コマンドラインによる難読化の手法を緩和するには、引用符を削除し、スペースでコンマを置換し、複数の連続するスペースを1つのスペースで置換することを検討します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="b1d3e-189">他の方法を必要とする複雑な難読化手法が他にもありますが、これらの調整は一般的な方法に対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="b1d3e-190">次の例は、ファイアウォールサービス "MpsSvc" を停止するためにファイル *net.exe* を検索するクエリを作成するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="b1d3e-191">外部ソースからのデータの取り込み</span><span class="sxs-lookup"><span data-stu-id="b1d3e-191">Ingest data from external sources</span></span>
<span data-ttu-id="b1d3e-192">長いリストまたは大きなテーブルをクエリに組み込むには、 [externaldata 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) を使用して、指定された URI からデータを取り込みます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="b1d3e-193">TXT、CSV、JSON、または [その他の形式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)のファイルからデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="b1d3e-194">次の例では、MalwareBazaar (abuse.ch) によって提供されるマルウェア SHA 256 ハッシュの拡張リストを使用して、電子メールの添付ファイルを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="b1d3e-195">文字列を解析する</span><span class="sxs-lookup"><span data-stu-id="b1d3e-195">Parse strings</span></span>
<span data-ttu-id="b1d3e-196">解析または変換が必要な文字列を効率的に処理するために使用できるさまざまな関数があります。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="b1d3e-197">文字列</span><span class="sxs-lookup"><span data-stu-id="b1d3e-197">String</span></span> | <span data-ttu-id="b1d3e-198">関数</span><span class="sxs-lookup"><span data-stu-id="b1d3e-198">Function</span></span> | <span data-ttu-id="b1d3e-199">使用例</span><span class="sxs-lookup"><span data-stu-id="b1d3e-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="b1d3e-200">コマンドライン</span><span class="sxs-lookup"><span data-stu-id="b1d3e-200">Command-lines</span></span> | [<span data-ttu-id="b1d3e-201">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="b1d3e-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="b1d3e-202">コマンドとすべての引数を抽出します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="b1d3e-203">Paths</span><span class="sxs-lookup"><span data-stu-id="b1d3e-203">Paths</span></span> | [<span data-ttu-id="b1d3e-204">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="b1d3e-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="b1d3e-205">ファイルまたはフォルダーのパスのセクションを抽出します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="b1d3e-206">バージョン番号</span><span class="sxs-lookup"><span data-stu-id="b1d3e-206">Version numbers</span></span> | [<span data-ttu-id="b1d3e-207">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="b1d3e-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="b1d3e-208">Deconstruct は、セクションごとに最大4つのセクションと最大8文字のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="b1d3e-209">解析されたデータを使用して、バージョンの年齢を比較します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="b1d3e-210">IPv4 アドレス</span><span class="sxs-lookup"><span data-stu-id="b1d3e-210">IPv4 addresses</span></span> | [<span data-ttu-id="b1d3e-211">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="b1d3e-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="b1d3e-212">IPv4 アドレスを長い整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="b1d3e-213">IPv4 アドレスを変換せずに比較するには、 [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="b1d3e-214">IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="b1d3e-214">IPv6 addresses</span></span> | [<span data-ttu-id="b1d3e-215">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="b1d3e-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="b1d3e-216">IPv4 または IPv6 アドレスを正規の IPv6 表記に変換します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="b1d3e-217">IPv6 アドレスを比較するには、 [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="b1d3e-218">サポートされているすべての解析関数の詳細については、「 [Kusto string 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d3e-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b1d3e-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1d3e-219">Related topics</span></span>
- [<span data-ttu-id="b1d3e-220">Kusto クエリ言語ドキュメント</span><span class="sxs-lookup"><span data-stu-id="b1d3e-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="b1d3e-221">サービスの制限</span><span class="sxs-lookup"><span data-stu-id="b1d3e-221">Service limits</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="b1d3e-222">詳細な検索エラーを処理する</span><span class="sxs-lookup"><span data-stu-id="b1d3e-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b1d3e-223">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="b1d3e-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1d3e-224">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="b1d3e-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
