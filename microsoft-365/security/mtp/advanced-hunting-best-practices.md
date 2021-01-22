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
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

これらの推奨事項を適用して、結果をより速く取得し、複雑なクエリの実行中にタイムアウトを回避します。 クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。

## <a name="understand-cpu-resource-quotas"></a>CPU リソース クォータについて
各テナントは、そのサイズに応じて、高度なハンティング クエリの実行に割り当てられた一連の CPU リソースにアクセスできます。 さまざまなサービス制限の詳細については、高度な検索クォータと使用 [パラメーターに関するページを参照してください](advanced-hunting-limits.md)。

複数のクエリを定期的に実行しているお客様は、使用量を追跡し、この記事の最適化ガイダンスを適用して、クォータまたは使用パラメーターの超過による中断を最小限に抑える必要があります。

## <a name="general-optimization-tips"></a>一般的な最適化のヒント

- **新しいクエリのサイズ** を変更する - クエリが大きな結果セットを返す可能性がある場合は、カウント演算子を使用して最初に [評価します](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)。 大 [きな結果セット](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) を回避するには、制限 `take` または類義語を使用します。
- **フィルター** を早期に適用する - 時間フィルターや他のフィルターを適用して、データ セットを減らします。特に、部分 [文字列()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction) [、replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction) [、trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction) [、toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)、または [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)などの変換および解析関数を使用する前に行います。 次の例では、フィルター演算子によってレコード数が減った後に解析関数 [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) が使用されます。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has beats contains**—To avoid searching substrings within words unnecessarly, use the `has` operator instead of `contains` . [文字列演算子の詳細](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **特定の列を検索** する - すべての列でフルテキスト検索を実行するのではなく、特定の列を検索します。 すべての列を `*` チェックするために使用する必要があります。
- **速度に対して大文字と** 小文字が区別されます。大文字と小文字を区別した検索は、より具体的で、一般的にパフォーマンスが高い検索です。 大文字と小文字を区別する [文字列演算子の名前](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)(および `has_cs` 一般に末尾が `contains_cs` `_cs` . 代わりに、大文字と小文字を区別する等号 `==` 演算子を使用することもできます `=~` 。
- **解析、抽出しない**—できる限り、解析演算子または [](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) [parse_json() のような解析関数を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)。 文字列演算子 `matches regex` または [extract() 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)は、どちらも正規表現を使用しないようにします。 より複雑なシナリオでは、正規表現の使用を予約してください。 [関数の解析の詳細](#parse-strings)
- **式ではなくテーブルをフィルター** 処理する - テーブルの列でフィルター処理できる場合は、集計列に対してフィルター処理を行います。
- **3 文字の用語なし**- 3 文字以下の用語を使用して比較またはフィルター処理を行うのを避ける。 これらの用語はインデックス付けされません。一致する場合は、より多くのリソースが必要になります。
- **プロジェクトの選択**— 必要な列のみを投影することで、結果を理解しやすくします。 結合または同様の操作を実行する前に [特定](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) の列を投影すると、パフォーマンスも向上します。

## <a name="optimize-the-join-operator"></a>演算子を最適化 `join` する
結合 [演算子は、指定](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) された列の値を照合して、2 つのテーブルの行を結合します。 これらのヒントを適用して、この演算子を使用するクエリを最適化します。

- **左に小さい** テーブル — 演算子は、結合ステートメントの左側にあるテーブル内のレコードを右側の `join` レコードに一致します。 小さいテーブルを左側に置く場合、一致する必要があるレコードが少なめなので、クエリの速度が上がっています。 

    次の表では、アカウントの SID で参加する前に、3 つの特定のデバイスのみをカバーするために左 `DeviceLogonEvents` の表 `IdentityLogonEvents` を減らします。
 
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

- **内部** 結合の味を使用します。左 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors)のテーブルの既定 [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)の結合方法または内部結合重複データ行は、右のテーブルに一致するごとに行を返す前に結合キーによって結合キーによって重複します。 左の表にキーの同じ値を持つ複数の行がある場合、それらの行は重複排除され、一意の値ごとに 1 つのランダムな行 `join` が残されます。

    この既定の動作では、有用な分析情報を提供できる重要な情報が左側の表から取り残される可能性があります。 たとえば、次のクエリでは、同じ添付ファイルが複数の電子メール メッセージを使用して送信された場合でも、特定の添付ファイルを含む 1 つのメールだけが表示されます。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    この制限に対処するために、左側の[](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)表のすべての行を右に一致する値で表示するために、内部結合機能 `kind=inner` を適用します。
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **タイム ウィンドウからレコード** を参加する - セキュリティ イベントを調査するときに、アナリストは同じ期間に発生する関連イベントを探します。 同じ方法を使用する場合も、チェックするレコードの数を減らすことでパフォーマンス `join` が向上します。
    
    次のクエリは、悪意のあるファイルを受信した 30 分以内にログオン イベントをチェックします。

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
- **両側に** 時間フィルターを適用する - 特定のタイム ウィンドウを調査していない場合でも、左右の両方のテーブルに時間フィルターを適用すると、確認してパフォーマンスを向上させるレコードの数を減らします。 `join` 次のクエリは、過去 1 時間のレコードのみを結合するために、両方の `Timestamp > ago(1h)` テーブルに適用されます。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **パフォーマンスにヒントを使用** する — 演算子と一緒にヒントを使用して、リソースを大量に消費する操作を実行するときに負荷を分散 `join` するようにバックエンドに指示します。 [参加ヒントの詳細](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    たとえば、次の **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** クエリなど、多くの一意の値を持つキーである高いカーディナリティを持つキーを使用してテーブルを結合する場合、シャッフル ヒントを使用すると、クエリのパフォーマンスが向上 `AccountObjectId` します。

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    ブロードキャスト **[ヒントは、](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** 左の表が小さく (最大 100,000 レコード)、右側のテーブルが非常に大きい場合に役立ちます。 たとえば、次のクエリは、特定の件名を持ついくつかの電子メールを、テーブル内のリンクを含むすべてのメッセージに参加 `EmailUrlInfo` させようとしています。

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>演算子を最適化 `summarize` する
集計 [演算子は](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) 、テーブルの内容を集計します。 これらのヒントを適用して、この演算子を使用するクエリを最適化します。

- **異なる値を** 検索する —一般に、繰り返し `summarize` 使用できる個別の値を検索するために使用します。 繰り返し値のない列を集計するために使用する必要が生じ得る。

    1 つの電子メールは複数のイベントに含めることができますが、次の例では、個々の電子メールのネットワーク メッセージ ID に常に一意の送信者アドレスが付くため、効率的に `summarize` 使用することはできません。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    演算子 `summarize` は簡単に置き換えられるので、リソースを少なくしながら同じ結果 `project` が得られる可能性があります。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    次の例は、同じ受信者のアドレスに電子メールを送信する送信者アドレスの複数の異なるインスタンスが考えられます `summarize` 。 このような組み合わせは区別が少なく、重複する可能性があります。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **クエリの** シャッフル — 繰り返し値を持つ列で使用すると最も便利ですが、同じ列に高い基数や多数の一意の値を設定 `summarize` することもできます。  演算子と同様に、シャッフル ヒントを適用して処理負荷を分散し、高い基数で列を操作するときにパフォーマンスを向上させる可能性 `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` があります。

    次のクエリは、大規模な組織の数十万人の中で実行できる、個別の受信者の電子メール アドレス `summarize` をカウントするために使用します。 パフォーマンスを向上させるために、次の機能が組み込されています `hint.shufflekey` 。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>クエリ シナリオ

### <a name="identify-unique-processes-with-process-ids"></a>プロセス ID を使用して一意のプロセスを識別する
Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。 そのため、それ単体では特定のプロセスの一意の識別子として機能しません。

特定のコンピューター上のプロセスの一意の識別子を取得するには、プロセス ID をプロセスの作成日時と共に使用します。 プロセスに関するデータを結合または集計する際は、コンピューターの識別子の列 (`DeviceId` または `DeviceName`)、プロセス ID (`ProcessId` または `InitiatingProcessId`)、およびプロセスの作成日時 (`ProcessCreationTime` または `InitiatingProcessCreationTime`) を含めます。

次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。

クエリ例:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。

### <a name="query-command-lines"></a>クエリコマンド ライン
タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。 たとえば、攻撃者は、パスのない画像ファイル、ファイル拡張子のない画像ファイル、環境変数、引用符を使用して画像ファイルを参照する可能性があります。 攻撃者は、パラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。

コマンド ラインに対してより永続的なクエリを作成するには、次のプラクティスを適用します。

- コマンド ライン自体でフィルター *処理* するのではなく、ファイル名フィールドを照合して既知のプロセス (net.exeやpsexec.exe *など)* を特定します。
- parse_command_line() 関数を使用してコマンド [ライン セクションを解析する](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。 代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。
- 大文字と小文字を区別しない一致を使用します。 たとえば、, `=~` , `in~` , and `contains` の代わりに `==` , `in` とを使用します `contains_cs` 。
- コマンドライン難読化の手法を軽減するには、引用符を削除し、コンマをスペースに置き換え、連続する複数のスペースを 1 つのスペースに置き換える方法を検討してください。 他のアプローチを必要とするより複雑な難読化技術がありますが、これらの調整は一般的な方法に対処するのに役立ちます。

次の例は、ファイアウォール サービス "MpsSvc" を停止するファイルを検索するクエリ *net.exe* を作成するさまざまな方法を示しています。

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

### <a name="ingest-data-from-external-sources"></a>外部ソースからデータを取り込む
長いリストまたは大きなテーブルをクエリに組み込むには [、externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) 演算子を使用して、指定した URI からデータを取り込む必要があります。 TXT、CSV、JSON などの形式のファイルからデータ [を取得できます](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)。 次の例は、MalwareB malwarear (abuse.ch) によって提供されるマルウェア SHA-256 ハッシュの広範なリストを利用して、電子メールの添付ファイルを確認する方法を示しています。

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

### <a name="parse-strings"></a>文字列を解析する
解析または変換を必要とする文字列を効率的に処理するために使用できるさまざまな関数があります。 

| String | 関数 | 使用例 |
|--|--|--|
| コマンド ライン | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | コマンドとすべての引数を抽出します。 | 
| Paths | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | ファイルまたはフォルダーのパスのセクションを抽出します。 |
| バージョン番号 | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | 1 つのセクションに最大 4 つのセクションと最大 8 文字のバージョン番号を展開します。 解析されたデータを使用してバージョンの保存時間を比較します。 |
| IPv4 アドレス | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 アドレスを長整数に変換します。 IPv4 アドレスを変換せずに比較するには [、ipv4_compare() を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)。 |
| IPv6 アドレス | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 または IPv6 アドレスを正規の IPv6 表記に変換します。 IPv6 アドレスを比較するには [、ipv6_compare() を使用します](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

サポートされている解析関数の詳細については [、Kusto 文字列関数を参照してください](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。 

## <a name="related-topics"></a>関連項目
- [Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
