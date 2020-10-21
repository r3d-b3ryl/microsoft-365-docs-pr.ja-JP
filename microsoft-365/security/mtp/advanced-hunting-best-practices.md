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
ms.openlocfilehash: 29e5eb64445c6c5c45b8e1fd1633c030b5f32b86
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649669"
---
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

これらの推奨事項を適用して、結果を迅速に取得し、複雑なクエリの実行中にタイムアウトを回避します。 クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。

## <a name="understand-cpu-resource-quotas"></a>CPU リソースの制限について
各テナントは、そのサイズに応じて、高度な検索クエリの実行に割り当てられた CPU リソースの設定済み容量にアクセスできます。 さまざまなサービス制限の詳細については、 [「高度な検索クォータと使用状況パラメーターについて](advanced-hunting-limits.md)」を参照してください。

複数のクエリを定期的に実行する必要がある場合は、使用量を追跡し、この記事の最適化のガイダンスを適用して、クォータまたは使用状況のパラメーターの超過による影響を最小限に抑えます。

## <a name="general-optimization-tips"></a>一般的な最適化のヒント

- **新しいクエリのサイズ**変更-クエリが大きな結果セットを返すことが疑われる場合は、まず [count 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)を使用して評価します。 大きな結果セットを使用しないように [制限](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) またはシノニムを使用し `take` ます。
- **事前にフィルターを適用**する-タイムフィルターとその他のフィルターを適用してデータセットを縮小します。特に、変換関数と解析関数 ( [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction)、 [replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)、 [trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)、 [toupper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)、または [parse_json () など)](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)を使用する前に行います。 次の例では、フィルター演算子を使用してレコード数を減らした後、解析関数 [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) を使用しています。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- 拍の数が**含まれている**-単語内のサブ文字列を不必要に検索しないようにするには、ではなく演算子を使用し `has` `contains` ます。 [文字列演算子について](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **[特定の列を検索**する]: すべての列で全文検索を実行するのではなく、特定の列を参照します。 すべての `*` 列のチェックには使用しないでください。
- **大文字**と小文字を区別します。大文字と小文字を区別する検索はより具体的で、一般的にパフォーマンスが高くなります。 大文字と小文字が区別された [文字列演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)の名前 ( `has_cs` および `contains_cs` は通常、で終わる) `_cs` 。 また、ではなく、大文字と小文字を区別する等値演算子を使用することもでき `==` `=~` ます。
- **Parse (抽出しない**): 可能であれば、 [parse 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) または [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)のような解析関数を使用します。 `matches regex`文字列演算子または[extract () 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)を使用しないでください。両方で正規表現を使用します。 より複雑なシナリオのために正規表現の使用を予約します。 [解析関数の詳細を参照してください。](#parse-strings)
- [**テーブルに式**を適用しない]: テーブルの列にフィルターを適用する場合は、集計列に対してフィルターを適用しません。
- **3 文字の用語はありません**。3文字以下の用語を使用して、比較またはフィルターを適用しないでください。 これらの用語はインデックス付けされず、一致するリソースが必要になります。
- **選択的**に表示する: 必要な列だけを射影して、結果をわかりやすくします。 [Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)または同様の操作を実行する前に特定の列を予測することも、パフォーマンスの向上に貢献します。

## <a name="optimize-the-join-operator"></a>演算子を最適化する `join`
[Join 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator)は、指定した列の値を一致させることによって、2つのテーブルの行を結合します。 この演算子を使用するクエリを最適化するには、以下のヒントを適用します。

- **左側に小さなテーブル** `join` 。演算子は join ステートメントの左側にあるテーブルのレコードを右側のレコードに一致させる。 小さい方のテーブルを左側に配置することで、一致する必要があるレコードが少なくなるため、クエリを高速化できます。 

    次の表では、左側の表を、 `DeviceLogonEvents` アカウント sid で結合する前に3つの特定のデバイスのみカバーするように減らして `IdentityLogonEvents` います。
 
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

- **内部結合のフレーバーを使用**します。既定の [結合フレーバー](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) または [innerunique-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) join は、左側のテーブルの行を返す前に、結合キーを使用して、右のテーブルと一致する行を返します。 左側のテーブルにキーに同じ値を持つ複数の行がある場合 `join` 、これらの行は、一意の値ごとに単一のランダムな行を残すように deduplicated されます。

    この既定の動作により、役に立つ洞察を提供できる左側の表から重要な情報が残らないことがあります。 たとえば、次のクエリは、同じ添付ファイルが複数のメールメッセージを使用して送信された場合でも、特定の添付ファイルを含む1つの電子メールのみを表示します。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    この制限に対処するには、 [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)左側の表のすべての `kind=inner` 行を右に一致する値で表示するように指定して、内部結合のフレーバーを適用します。
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **時間枠からレコードを結合**する: セキュリティイベントを調査する際に、アナリストは、同じ期間に発生する関連イベントを検索します。 同じ方法を使用する場合は、 `join` 確認するレコードの数を減らして、パフォーマンスを向上させることもできます。
    
    次のクエリは、悪意のあるファイルを受信してから30分以内にログオンイベントをチェックします。

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
- **両方の側に時間フィルターを適用**します。特定のタイムウィンドウを調査していない場合でも、左と右の両方のテーブルで時間フィルターを適用すると、確認してパフォーマンスを向上させるためのレコード数を減らすことができ `join` ます。 次のクエリは両方のテーブルに適用され、 `Timestamp > ago(1h)` 過去1時間のレコードのみが結合されるようにします。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **ヒントを使用してパフォーマンスを向上**させる: `join` リソース集中型の操作を実行するときに負荷を分散するようにバックエンドに指示するには、オペレーターとのヒントを使用します。 [結合ヒントの詳細情報](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    たとえば、次のクエリのように、長いカーディナリティを持つキーを使用してテーブルを結合する場合は、 **[シャッフルヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** によってクエリパフォーマンスが向上し `AccountObjectId` ます。

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[ブロードキャストヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** は、左テーブルが小さい (最大10万レコード)、右テーブルが非常に大きい場合に役立ちます。 たとえば、次のクエリは、テーブルにリンクが含まれる _すべて_ のメッセージに特定の件名を持つ少数の電子メールに参加しようとしてい `EmailUrlInfo` ます。

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>演算子を最適化する `summarize`
[集約演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator)は、テーブルの内容を集約します。 この演算子を使用するクエリを最適化するには、以下のヒントを適用します。

- **Distinct 値を検索**する一般的に、を使用し `summarize` て、繰り返し可能な個別の値を検索します。 繰り返し値を持たない列を集計するために使用する必要はありません。

    1つの電子メールは複数のイベントの一部にすることができますが、次の例では、個々の電子メールのネットワークメッセージ ID には常に固有の送信者アドレスが含まれるため、を使用するのは効率的では _ありません_ `summarize` 。
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`演算子は簡単に置き換えることができ、同じ結果になる可能性があるので、リソースの使用 `project` 量が少なくなります。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    次の例は、 `summarize` 同じ受信者アドレスに電子メールを送信する送信者アドレスの複数の異なるインスタンスが存在する可能性があるため、より効率的に使用できます。 このような組み合わせは区別が少なく、重複している可能性があります。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **クエリをシャッフル**する- `summarize` 繰り返しの値を持つ列で使用するのに適していますが、同じ列に _基数_ または大量の一意の値が含まれている場合もあります。 演算子と同様に、 `join` 処理の負荷を分散するために、を使用して [シャッフルヒント](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) を適用し、 `summarize` カーディナリティを使用して列を操作するときにパフォーマンスを向上させることもできます。

    次のクエリは、 `summarize` 個別の受信者の電子メールアドレスをカウントするために使用します。これは、大規模な組織では数十万数の組織で実行できます。 パフォーマンスを向上させるために、次の組み込みが組み込まれてい `hint.shufflekey` ます。

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>クエリシナリオ

### <a name="identify-unique-processes-with-process-ids"></a>プロセス Id を使用して一意のプロセスを識別する
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

### <a name="query-command-lines"></a>クエリコマンドライン
タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。 たとえば、攻撃者は、ファイル拡張子を使用せず、環境変数を使用することも、引用符を使用しても、パスを含まないイメージファイルを参照できます。 また、パラメーターの順序を変更したり、複数の引用符とスペースを追加したりすることもできます。

コマンドラインを中心とした永続的なクエリを作成するには、以下の手順を適用します。

- コマンドライン自体にフィルターを適用するのではなく、ファイル名のフィールドに一致することによって、既知のプロセス ( *net.exe* 、 *psexec.exe*など) を特定します。
- [Parse_command_line () 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)を使用してコマンドラインセクションを解析する 
- コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。 代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。
- 大文字と小文字を区別しない一致を使用します。 たとえば、、、、、、、を使用し `=~` `in~` `contains` `==` `in` `contains_cs` ます。
- コマンドラインによる難読化の手法を緩和するには、引用符を削除し、スペースでコンマを置換し、複数の連続するスペースを1つのスペースで置換することを検討します。 他の方法を必要とする複雑な難読化手法が他にもありますが、これらの調整は一般的な方法に対処するのに役立ちます。

次の例は、ファイアウォールサービス "MpsSvc" を停止するためにファイル *net.exe* を検索するクエリを作成するさまざまな方法を示しています。

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

### <a name="ingest-data-from-external-sources"></a>外部ソースからのデータの取り込み
長いリストまたは大きなテーブルをクエリに組み込むには、 [externaldata 演算子](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) を使用して、指定された URI からデータを取り込みます。 TXT、CSV、JSON、または [その他の形式](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)のファイルからデータを取得できます。 次の例では、MalwareBazaar (abuse.ch) によって提供されるマルウェア SHA 256 ハッシュの拡張リストを使用して、電子メールの添付ファイルを確認する方法を示します。

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
解析または変換が必要な文字列を効率的に処理するために使用できるさまざまな関数があります。 

| String | 関数 | 使用例 |
|--|--|--|
| コマンドライン | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | コマンドとすべての引数を抽出します。 | 
| Paths | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | ファイルまたはフォルダーのパスのセクションを抽出します。 |
| バージョン番号 | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct は、セクションごとに最大4つのセクションと最大8文字のバージョン番号を指定します。 解析されたデータを使用して、バージョンの年齢を比較します。 |
| IPv4 アドレス | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 アドレスを長い整数に変換します。 IPv4 アドレスを変換せずに比較するには、 [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)を使用します。 |
| IPv6 アドレス | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 または IPv6 アドレスを正規の IPv6 表記に変換します。 IPv6 アドレスを比較するには、 [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)を使用します。 |

サポートされているすべての解析関数の詳細については、「 [Kusto string 関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)」を参照してください。 

## <a name="related-topics"></a>関連項目
- [Kusto クエリ言語ドキュメント](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [クォータと使用法のパラメーター](advanced-hunting-limits.md)
- [詳細な検索エラーを処理する](advanced-hunting-errors.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
