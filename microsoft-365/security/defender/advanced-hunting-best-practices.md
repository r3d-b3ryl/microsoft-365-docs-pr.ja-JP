---
title: 高度な検索クエリのベスト プラクティス (Microsoft 365 Defender
description: 高度な検索を使用して、高速、効率的、エラーフリーの脅威ハンティング クエリを作成する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ、kusto、回避タイムアウト、コマンド ライン、プロセス ID、最適化、ベスト プラクティス、解析、参加、要約
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 20a9206574565b2a02e1dcf57545e7b40619beec212daf29d6d2cc571e08dffb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53867753"
---
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

これらの推奨事項を適用して、結果をより速く取得し、複雑なクエリの実行中にタイムアウトを回避します。 クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](/azure/kusto/query/best-practices)」を参照してください。

## <a name="understand-cpu-resource-quotas"></a>CPU リソースクォータの理解
そのサイズに応じて、各テナントは、高度な検索クエリを実行するために割り当てられた一定の CPU リソースにアクセスできます。 さまざまなサービス制限の詳細については、「高度な検索クォータと使用状況パラメーター」 [を参照してください](advanced-hunting-limits.md)。

複数のクエリを定期的に実行しているお客様は、使用量を追跡し、この記事の最適化ガイダンスを適用して、クォータまたは使用パラメーターの超過による中断を最小限に抑える必要があります。

## <a name="general-optimization-tips"></a>一般的な最適化のヒント

- **新しいクエリのサイズを設定** する —クエリが大きな結果セットを返す疑いがある場合は、count 演算子を使用して最初に評価 [します](/azure/data-explorer/kusto/query/countoperator)。 大 [きな結果セット](/azure/data-explorer/kusto/query/limitoperator) を回避するには、limit `take` または類義語を使用します。
- **フィルター** を早期に適用する —時間フィルターや他のフィルターを適用して、特に [substring()](/azure/data-explorer/kusto/query/substringfunction) [、replace() 、trim()](/azure/data-explorer/kusto/query/replacefunction) [、toupper()、](/azure/data-explorer/kusto/query/toupperfunction)[または parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction)などの変換および解析関数を使用する前に、データ セットを削減します。 [](/azure/data-explorer/kusto/query/trimfunction) 次の例では、フィルター処理演算子がレコード数を減らした後に解析関数 [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) が使用されます。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has beats contains**—単語内の部分文字列を不必要に検索しないようにするには、 の代わりに `has` 演算子を使用します `contains` 。 [文字列演算子の詳細](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **特定の列を検索** する -すべての列でフル テキスト検索を実行するのではなく、特定の列を検索します。 すべての列を `*` チェックするために使用する必要があります。
- **速度に対して大文字と** 小文字を区別する —大文字と小文字を区別する検索は、より具体的で、一般的にはパフォーマンスが高い検索です。 大文字と小文字を区別する [文字列演算子](/azure/data-explorer/kusto/query/datatypes-string-operators)(およびなど) `has_cs` の名前 `contains_cs` は、通常はで終わり `_cs` です。 代わりに大文字と小文字を区別する等号演算子 `==` を使用することもできます `=~` 。
- **解析、抽出しない**—可能な場合は、parse [演算子](/azure/data-explorer/kusto/query/parseoperator) または [parse_json() のような解析関数を使用します](/azure/data-explorer/kusto/query/parsejsonfunction)。 文字列演算子 `matches regex` または [extract() 関数は避け、](/azure/data-explorer/kusto/query/extractfunction)どちらも正規表現を使用します。 より複雑なシナリオでは、正規表現の使用を予約します。 [解析関数の詳細](#parse-strings)
- **式ではなくテーブルをフィルター** 処理する -テーブル列でフィルター処理できる場合は、計算列でフィルター処理を行う必要があります。
- **3 文字の用語はありません**。用語を 3 文字以下で比較またはフィルター処理しないようにします。 これらの用語はインデックス付けされていないので、一致する場合は、より多くのリソースが必要になります。
- **Project選択 —** 必要な列のみを投影することで、結果を理解しやすくなります。 結合または類似の操作を実行[](/azure/data-explorer/kusto/query/joinoperator)する前に特定の列を投影すると、パフォーマンスが向上します。

## <a name="optimize-the-join-operator"></a>演算子を最適化 `join` する
結合 [演算子は、](/azure/data-explorer/kusto/query/joinoperator) 指定した列の値と一致して、2 つのテーブルの行を結合します。 この演算子を使用するクエリを最適化するには、次のヒントを適用します。

- **左側の小さいテーブル**—演算子は、結合ステートメントの左側にあるテーブル内のレコードを右側の `join` レコードに一致します。 左側の小さいテーブルを使用すると、一致する必要があるレコードが少なく、クエリが高速化されます。

    次の表では、左側の表を 3 つの特定のデバイスのみをカバーするために減らしてから、アカウント `DeviceLogonEvents` `IdentityLogonEvents` の SID で参加します。

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

- **内部結合フレーバー** を使用します。既定の [](/azure/data-explorer/kusto/query/joinoperator#join-flavors)結合フレーバーまたは [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor)重複排除行は、右の表に一致するごとに行を返す前に、結合キーによって左テーブルの行を重複排除します。 左のテーブルにキーの同じ値を持つ複数の行がある場合、それらの行は重複排除され、一意の値ごとに 1 つのランダムな行 `join` を残します。

    この既定の動作では、有用な分析情報を提供できる重要な情報を左側の表から取り残す可能性があります。 たとえば、次のクエリでは、同じ添付ファイルが複数の電子メール メッセージを使用して送信された場合でも、特定の添付ファイルを含む 1 つのメールだけが表示されます。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    この制限に対処するために、左側の[](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)表のすべての行を右に一致する値で表示するために、内部結合 `kind=inner` フレーバーを適用します。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- **タイム ウィンドウからレコードに参加する**- セキュリティ イベントを調査するときに、アナリストは同じ期間に発生する関連イベントを探します。 同じ方法を使用する場合も、チェックするレコードの数を減らすことでパフォーマンス `join` が向上します。

    以下のクエリは、悪意のあるファイルを受信して 30 分以内にログオン イベントをチェックします。

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **両側にタイム** フィルターを適用する :特定のタイム ウィンドウを調査していない場合でも、左右のテーブルにタイム フィルターを適用すると、パフォーマンスを確認して向上させるレコードの数を減らします `join` 。 以下のクエリは両方 `Timestamp > ago(1h)` のテーブルに適用されます。このクエリは過去 1 時間のレコードのみを結合します。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- **パフォーマンスにヒントを使用する**— リソースを大量に消費する操作を実行するときに、バックエンドに負荷を分散するように指示するヒントをオペレーター `join` と一緒に使用します。 [参加ヒントの詳細](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    たとえば、シャッ **[](/azure/data-explorer/kusto/query/shufflequery)** フル ヒントは、カーディナリティが高いキー (一意の値が多いキー) を使用してテーブルを結合するときにクエリのパフォーマンスを向上させるのに役立ちます。たとえば、次のクエリでは次のようになります `AccountObjectId` 。

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    ブロードキャスト **[ヒントは、](/azure/data-explorer/kusto/query/broadcastjoin)** 左の表が小さい (最大 100,000 レコード)、右側のテーブルが非常に大きい場合に役立ちます。 たとえば、次のクエリは、特定の件名を持ついくつかの電子メールに、テーブル内のリンクを含むすべてのメッセージを参加させ `EmailUrlInfo` ようとしています。

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a>演算子を最適化 `summarize` する
集計 [演算子は](/azure/data-explorer/kusto/query/summarizeoperator) 、テーブルの内容を集計します。 この演算子を使用するクエリを最適化するには、次のヒントを適用します。

- **個別の値を検索** する —一般に、反復 `summarize` 可能な個別の値を検索するために使用します。 繰り返し値のない列を集計するために使用する必要が生じ得ない場合があります。

    1 つの電子メールは複数のイベントに含めることができますが、個々の電子メールのネットワーク メッセージ ID には常に一意の送信者アドレスが含むため、次の例は効率的に `summarize` 使用されません。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    演算子を簡単に置き換え、リソースを少なくしながら、潜在的に同じ `summarize` `project` 結果を得ることができます。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    次の例は、同じ受信者アドレスに電子メールを送信する送信者アドレスのインスタンスが複数ある可能性があるため、より効率的 `summarize` に使用できます。 このような組み合わせは区別が少なく、重複する可能性があります。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- **クエリをシャッフル** する —繰り返し値を持つ列で最も使われる一方で、同じ列に高いカーディナリティや多数の一意の値を `summarize` 持つ場合があります。  また、操作者と同様に、シャッフル ヒントを適用して処理負荷を分散し、カーディナリティが高い列で操作する場合のパフォーマンスを向上させる `join` [](/azure/data-explorer/kusto/query/shufflequery) `summarize` 可能性があります。

    以下のクエリは、大規模な組織で数十万人の組織で実行できる、個別の受信者の電子メール アドレス `summarize` をカウントするために使用します。 パフォーマンスを向上させるために、次の機能が組み込されています `hint.shufflekey` 。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>クエリシナリオ

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
タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。 たとえば、攻撃者は、パスのないイメージ ファイル、ファイル拡張子のないイメージ ファイル、環境変数を使用する、または引用符で囲まれたイメージ ファイルを参照する可能性があります。 また、攻撃者はパラメーターの順序を変更したり、複数の引用符とスペースを追加したりする可能性があります。

コマンド ラインに対してより永続的なクエリを作成するには、次のプラクティスを適用します。

- コマンド ライン自体でフィルター処理 *するのではなく、ファイル名フィールドnet.exe* またはpsexec.exe *など、* 既知のプロセスを識別します。
- parse_command_line() 関数を使用してコマンド [ライン セクションを解析する](/azure/data-explorer/kusto/query/parse-command-line)
- コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。 代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。
- 大文字と小文字を区別しない一致を使用します。 たとえば、 `=~` 、 、 、 `in~` の代 `contains` わりに 、 、 と `==` `in` を使用します `contains_cs` 。
- コマンド ライン難読化の手法を軽減するには、引用符を削除し、コンマをスペースに置き換え、複数の連続するスペースを 1 つのスペースに置き換える方法を検討してください。 他のアプローチを必要とする複雑な難読化手法がありますが、これらの調整は一般的な方法に対処するのに役立ちます。

次の例は、ファイアウォール サービス "MpsSvc" を停止するために、net.exeを検索するクエリを作成するさまざまな方法を示しています。

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
長いリストまたは大きなテーブルをクエリに組み込むには [、externaldata 演算子](/azure/data-explorer/kusto/query/externaldata-operator) を使用して、指定した URI からデータを取り込む必要があります。 TXT、CSV、JSON、または他の形式のファイルからデータ [を取得できます](/azure/data-explorer/ingestion-supported-formats)。 次の例は、MalwareBazaar (abuse.ch) が提供するマルウェア SHA-256 ハッシュの広範なリストを使用して、電子メールの添付ファイルを確認する方法を示しています。

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo
| where Timestamp > ago(1d)
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>文字列の解析
解析または変換が必要な文字列を効率的に処理するために使用できるさまざまな関数があります。

| String | 職務 | 使用例 |
|--|--|--|
| コマンド ライン | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | コマンドとすべての引数を抽出します。 |
| Paths | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | ファイルパスまたはフォルダー パスのセクションを抽出します。 |
| バージョン番号 | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | セクションごとに最大 4 つのセクションと最大 8 文字のバージョン番号を分解します。 解析されたデータを使用してバージョンの年齢を比較します。 |
| IPv4 アドレス | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 アドレスを長整数に変換します。 IPv4 アドレスを変換せずに比較するには [、ipv4_compare() を使用します](/azure/data-explorer/kusto/query/ipv4-comparefunction)。 |
| IPv6 アドレス | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 または IPv6 アドレスを標準の IPv6 表記に変換します。 IPv6 アドレスを比較するには [、ipv6_compare() を使用します](/azure/data-explorer/kusto/query/ipv6-comparefunction)。 |

サポートされている解析関数の詳細については [、「Kusto 文字列関数」を参照してください](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)。

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。 [複数のデータ Microsoft 365 Defender](m365d-enable.md)を使用して脅威を検出するには、このオプションをオンにしてください。 高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動するには、「Advanced Hunting [queries](advanced-hunting-migrate-from-mde.md)を Microsoft Defender for Endpoint から移行する」の手順に従います。

## <a name="related-topics"></a>関連トピック
- [Kusto クエリ言語のドキュメント](/azure/data-explorer/kusto/query/)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)