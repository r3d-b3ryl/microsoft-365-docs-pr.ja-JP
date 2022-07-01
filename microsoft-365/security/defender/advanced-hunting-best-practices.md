---
title: Microsoft 365 Defenderの高度なハンティング クエリのベスト プラクティス
description: 高度なハンティングを使用して、高速で効率的でエラーのない脅威ハンティング クエリを構築する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ, kusto, avoid timeout, コマンド ライン, プロセス ID, 最適化, ベスト プラクティス, 解析, 結合, 要約
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c4236edcb2b5ec15b7c66be8f4b74ad0a2bc44c7
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603475"
---
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

これらの推奨事項を適用して、結果を迅速に取得し、複雑なクエリの実行中にタイムアウトを回避します。 クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](/azure/kusto/query/best-practices)」を参照してください。

## <a name="understand-cpu-resource-quotas"></a>CPU リソース クォータを理解する
そのサイズに応じて、各テナントは、高度なハンティング クエリを実行するために割り当てられた一定量の CPU リソースにアクセスできます。 さまざまな使用パラメーターの詳細については、 [高度なハンティング クォータと使用状況パラメーターについて説明します](advanced-hunting-limits.md)。

クエリを実行した後、実行時間とそのリソース使用量 (低、中、高) を確認できます。 高は、クエリの実行に必要なリソースが多く、結果をより効率的に返すように改善できることを示します。

:::image type="content" source="../../media/resource-usage.png" alt-text="Microsoft 365 Defender ポータルの [**結果** ] タブのクエリの詳細" lightbox="../../media/resource-usage.png":::

複数のクエリを定期的に実行しているお客様は、使用量を追跡し、この記事の最適化ガイダンスを適用して、クォータや使用状況パラメーターを超えることによる中断を最小限に抑える必要があります。

[KQL クエリの最適化を見て、クエリ](https://www.youtube.com/watch?v=ceYvRuPp5D8)を改善する最も一般的な方法の一部を確認します。  

## <a name="general-optimization-tips"></a>一般的な最適化のヒント

- **新しいクエリのサイズ** を設定する - クエリが大きな結果セットを返すと思われる場合は、最初に [count 演算子](/azure/data-explorer/kusto/query/countoperator)を使用して評価します。 大きな結果セットを回避するには、 [制限](/azure/data-explorer/kusto/query/limitoperator) またはそのシノニム `take` を使用します。
- **フィルターを早期に適用** する - 特に [、部分文字列()](/azure/data-explorer/kusto/query/substringfunction)、 [replace(](/azure/data-explorer/kusto/query/replacefunction))、 [trim()](/azure/data-explorer/kusto/query/trimfunction)、 [toupper()](/azure/data-explorer/kusto/query/toupperfunction)、 [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction)などの変換関数と解析関数を使用する前に、時間フィルターとその他のフィルターを適用してデータ セットを減らします。 次の例では、フィルター処理演算子によってレコードの数が減った後に、解析関数 [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) が使用されます。

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **ビートに含まれるもの** がある - 単語内の部分文字列を不必要に検索しないようにするには、`has``contains`. [文字列演算子について学習する](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **特定の列を検索** する - すべての列でフルテキスト検索を実行するのではなく、特定の列を検索します。 すべての列のチェックには使用 `*` しないでください。
- **速度の大文字と小文字を区別** する - 大文字と小文字を区別する検索は、より具体的で、一般的にはパフォーマンスが高くなります。 大文字と`contains_cs`小文字を区別[する文字列演算子](/azure/data-explorer/kusto/query/datatypes-string-operators)の名前 (たとえば`has_cs`、通常`_cs`は . 大文字と小文字を区別する equals 演算子`==``=~`を使用することもできます。
- **解析、抽出しない** - 可能な限り、 [解析演算子](/azure/data-explorer/kusto/query/parseoperator) または解析関数 ( [parse_json())](/azure/data-explorer/kusto/query/parsejsonfunction) を使用します。 `matches regex`文字列演算子または [extract() 関数は](/azure/data-explorer/kusto/query/extractfunction)避けます。どちらも正規表現を使用します。 より複雑なシナリオでは、正規表現の使用を予約します。 [関数の解析の詳細](#parse-strings)
- **式ではなくテーブルをフィルター** 処理する - テーブル列でフィルター処理できる場合は、計算列でフィルターを適用しないでください。
- **3 文字の用語はありません。3 文字** 以下の用語を使用した比較やフィルター処理は避けてください。 これらの用語にはインデックスが作成されず、一致する場合は、さらに多くのリソースが必要になります。
- **プロジェクトを選択的に** - 必要な列のみを投影することで、結果をわかりやすくします。 [結合](/azure/data-explorer/kusto/query/joinoperator)または同様の操作を実行する前に特定の列を射影すると、パフォーマンスが向上します。



## <a name="optimize-the-join-operator"></a>演算子を最適化する`join`
[結合演算子](/azure/data-explorer/kusto/query/joinoperator)は、指定した列の値を一致させることで、2 つのテーブルの行をマージします。 この演算子を使用するクエリを最適化するには、次のヒントを適用します。

- **左側の小さいテーブル** - 演算子は `join` 、結合ステートメントの左側にあるテーブル内のレコードを右側のレコードと一致します。 左側に小さいテーブルを配置すると、一致する必要があるレコードが少なくなり、クエリが高速化されます。

    次の表では、アカウント SID で参加`IdentityLogonEvents`する前に、左側のテーブル`DeviceLogonEvents`を 3 つの特定のデバイスのみを対象に減らします。

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

- **内部結合フレーバーを使用します**。既定の [結合フレーバー](/azure/data-explorer/kusto/query/joinoperator#join-flavors) または [innerunique 結合](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) では、左テーブルの行を結合キーで重複除去してから、一致する行を右のテーブルに返します。 左側のテーブルにキーの値 `join` が同じ複数の行がある場合、それらの行は重複除去され、一意の値ごとに 1 つのランダム行が残されます。

    この既定の動作では、有用な分析情報を提供できる重要な情報を左側のテーブルから除外できます。 たとえば、次のクエリでは、同じ添付ファイルが複数のメール メッセージを使用して送信された場合でも、特定の添付ファイルを含むメールが 1 つだけ表示されます。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    この制限に対処するために、左側のテーブル内のすべての行を右側に一致する`kind=inner`値で表示するように指定することで、[内部結合](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)のフレーバーを適用します。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- **時間枠からレコードを結合** する - セキュリティ イベントを調査するときに、アナリストは、同じ期間に発生する関連イベントを探します。 また、チェックするレコードの数を減らすことで、同じ方法を使用 `join` するとパフォーマンスが向上します。

    次のクエリは、悪意のあるファイルを受信してから 30 分以内にログオン イベントを確認します。

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
- **両側に時間フィルターを適用** する - 特定の時間枠を調査していない場合でも、左右の両方のテーブルに時間フィルターを適用すると、レコードの数を減らしてパフォーマンスを確認し、向上させることができます `join` 。 次のクエリは、過去 1 時間のレコードのみを結合するように、両方のテーブルに適用されます `Timestamp > ago(1h)` 。

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- **パフォーマンスにヒントを使用** する - リソース集中型操作を `join` 実行するときに、負荷を分散するようにバックエンドに指示するには、オペレーターと共にヒントを使用します。 [結合ヒントの詳細を確認する](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    たとえば、 **[シャッフル ヒント](/azure/data-explorer/kusto/query/shufflequery)** は、カーディナリティの高いキー (一意の値 `AccountObjectId` が多いキー) を使用してテーブルを結合する場合に、クエリのパフォーマンスを向上させるために役立ちます。たとえば、次のクエリでは次のようになります。

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    **[ブロードキャスト ヒント](/azure/data-explorer/kusto/query/broadcastjoin)** は、左側のテーブルが小さく (最大 100,000 レコード)、右側のテーブルが非常に大きい場合に役立ちます。 たとえば、次のクエリでは、テーブル内のリンクを含 _むすべての_ メッセージを含む特定の件名を持ついくつかの電子メールに `EmailUrlInfo` 参加しようとしています。

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a>演算子を最適化する`summarize`
[集計演算子](/azure/data-explorer/kusto/query/summarizeoperator)は、テーブルの内容を集計します。 この演算子を使用するクエリを最適化するには、次のヒントを適用します。

- **個別の値を検索** する - 一般に、反復可能な個別の値を検索するために使用 `summarize` します。 繰り返し値を持たない列を集計するために使用する必要がない場合があります。

    1 つのメールを複数のイベントに含めることができますが、次の例は、個々のメールのネットワーク メッセージ ID には常に一意の`summarize`送信者アドレスが付属しているため、効率的に使用 _することはできません_。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    演算子を `summarize` 簡単に置き換えることができます。リソースの消費量を減らす一方で `project`、同じ結果が得られる可能性があります。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    次の例は、同じ受信者アドレス `summarize` に電子メールを送信する送信者アドレスの複数の異なるインスタンスがあるため、より効率的に使用できます。 このような組み合わせの区別は少なく、重複している可能性があります。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- **クエリをシャッフルする** - 繰り返し値を持つ列で使用するのが最適ですが `summarize` 、同じ列の _カーディナリティが高い_ 場合や、一意の値が多数ある場合もあります。 演算子と同様に`join`、[シャッフル ヒント](/azure/data-explorer/kusto/query/shufflequery)`summarize`を適用して処理負荷を分散し、カーディナリティの高い列で操作する場合のパフォーマンスを向上させることもできます。

    次のクエリは、大規模な組織で数十万で実行できる個別の受信者の電子メール アドレスをカウントするために使用 `summarize` します。 パフォーマンスを向上させるために、次のものが `hint.shufflekey`組み込まれています。

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```



## <a name="query-scenarios"></a>クエリのシナリオ

### <a name="identify-unique-processes-with-process-ids"></a>プロセス ID を使用して一意のプロセスを識別する

Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。 そのため、それ単体では特定のプロセスの一意の識別子として機能しません。

特定のコンピューター上のプロセスの一意の識別子を取得するには、プロセス ID をプロセスの作成日時と共に使用します。 プロセスに関するデータを結合または集計する際は、コンピューターの識別子の列 (`DeviceId` または `DeviceName`)、プロセス ID (`ProcessId` または `InitiatingProcessId`)、およびプロセスの作成日時 (`ProcessCreationTime` または `InitiatingProcessCreationTime`) を含めます。

次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。

クエリ例:

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

このクエリでは `InitiatingProcessId` と `InitiatingProcessCreationTime` の両方を使用して集計が行われるため、同一のプロセス ID を持つ複数のプロセスを混ぜることなく単一のプロセスのみがクエリで検索されます。

### <a name="query-command-lines"></a>コマンド ラインのクエリ
タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。 たとえば、攻撃者は、パスのないイメージ ファイル、ファイル拡張子のないイメージ ファイル、環境変数、引用符を使用して参照する可能性があります。 攻撃者は、パラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。

コマンド ラインに対してより持続性の高いクエリを作成するには、次の方法を適用します。

- コマンド ライン自体でフィルター処理するのではなく、ファイル名フィールドに一致させることで、既知のプロセス ( *net.exe* や *psexec.exe* など) を特定します。
- [parse_command_line() 関数](/azure/data-explorer/kusto/query/parse-command-line)を使用してコマンド ライン セクションを解析する
- コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。 代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。
- 大文字と小文字を区別しない一致を使用します。 たとえば、`=~`、 、 、 `in~``contains` の代わりに`==`使用`in`します`contains_cs`。
- コマンド ラインの難読化手法を軽減するには、引用符を削除し、コンマをスペースに置き換え、複数の連続するスペースを 1 つのスペースに置き換えることを検討してください。 他のアプローチを必要とする複雑な難読化手法もありますが、これらの調整は一般的なアプローチに対処するのに役立ちます。

次の例では、ファイアウォール サービス "MpsSvc" を停止するファイル *net.exe* を検索するクエリを作成するさまざまな方法を示します。

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
長いリストまたは大きなテーブルをクエリに組み込むには、 [外部データ演算子](/azure/data-explorer/kusto/query/externaldata-operator) を使用して、指定した URI からデータを取り込みます。 TXT、CSV、JSON、またはその他の形式のファイルからデータ [を](/azure/data-explorer/ingestion-supported-formats)取得できます。 次の例は、MalwareBazaar (abuse.ch) によって提供されるマルウェア SHA-256 ハッシュの広範な一覧を利用して、電子メールの添付ファイルを確認する方法を示しています。

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

### <a name="parse-strings"></a>文字列を解析する
解析または変換が必要な文字列を効率的に処理するために使用できるさまざまな関数があります。

| String | 職務 | 使用例 |
|--|--|--|
| コマンド ライン | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | コマンドとすべての引数を抽出します。 |
| Paths | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | ファイルまたはフォルダーパスのセクションを抽出します。 |
| バージョン番号 | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | セクションごとに最大 4 つのセクションと最大 8 文字のバージョン番号を分解します。 解析されたデータを使用して、バージョンの有効期間を比較します。 |
| IPv4 アドレス | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | IPv4 アドレスを長整数に変換します。 IPv4 アドレスを変換せずに比較するには、 [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction)を使用します。 |
| IPv6 アドレス | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | IPv4 または IPv6 アドレスを正規の IPv6 表記に変換します。 IPv6 アドレスを比較するには、 [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction)を使用します。 |

サポートされているすべての解析関数の詳細については、 [Kusto 文字列関数に関する](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)ページを参照してください。

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連トピック
- [Kusto クエリ言語のドキュメント](/azure/data-explorer/kusto/query/)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [高度なハンティング エラーを処理する](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)