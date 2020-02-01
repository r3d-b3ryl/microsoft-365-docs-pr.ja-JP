---
title: Microsoft Threat Protection の高度な捜索のベスト プラクティス
description: 高度な検索を使用する場合に、迅速かつ効率的で、エラーのない脅威検索クエリを作成する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタムの検出、スキーマ、kusto、タイムアウトの回避、コマンドライン、プロセス id
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
ms.openlocfilehash: b5cd421770469e674e66045ac341d12a2808da09
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602844"
---
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="optimize-query-performance"></a>クエリのパフォーマンスを最適化する
次の推奨事項を適用すると、複雑なクエリを実行する際に結果をすばやく表示し、タイムアウトを回避することができます。
- 新しいクエリを試行するときは、結果セットが大きくなり過ぎないよう、常に `limit` を使用します。 `count` を使用して結果セットのサイズを最初に判断することもできます。
- 最初に時間フィルターを使用します。 クエリを偶数の日数に制限するのが理想です。
- 時間フィルターの適用直後に、ほとんどのデータがクエリの開始時に除外されるようなフィルターを適用します。
- 完全なトークンを検索する場合の演算子として、`contains` ではなく `has` を使用します。
- すべての列に対して全文検索を実行するのではなく、特定の列を検索します。
- テーブルを結合するときは、最初は行数が少ないテーブルを指定します。
- `project` は、結合したテーブルの必要な列に対してのみ使用します。

>[!Tip]
>クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。

## <a name="query-tips-and-pitfalls"></a>クエリのヒントと落とし穴

### <a name="queries-with-process-ids"></a>プロセス ID を使用するクエリ
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

### <a name="queries-with-command-lines"></a>コマンド ラインを使用したクエリ

さまざまなコマンド ラインを使用できます。 該当する場合は、ファイル名をフィルター処理し、あいまい一致を実行します。

タスクを実行するためのコマンド ラインは、さまざまな方法で構築できます。 たとえば、攻撃者が画像ファイルを参照する際に、パスを使用する場合、パスを使用しない場合、ファイル拡張子を使用しない場合、環境変数を使用する場合、または引用符を使用する場合があります。 また、攻撃者はパラメーターの順序を変更したり、複数の引用符やスペースを追加したりすることもできます。

コマンドラインを使用してより強力なクエリを作成するには、次の方法を実行します。

- コマンド ライン フィールドを使用してフィルター処理をするのではなく、filename フィールドを一致させることにより既知のプロセス (*net.exe* または *psexec.exe*) を特定します。
- コマンドライン引数をクエリする際は、関連性のない複数の引数で完全な一致を特定の順序で検索しないようにします。 代わりに、正規表現を使用するか、複数の個別の contains 演算子を使用します。
- 大文字と小文字を区別しない一致を使用します。 たとえば、`==`、`in`、`contains_cs` の代わりに `=~`、`in~`、`contains` を使用します。 
- DOS コマンドラインの難読化手法に対処するには、引用符を削除し、コンマをスペースで置き換え、連続する複数のスペースをスペース 1 つで置き換えることを検討します。 他の方法を使用しないと対処することが難しいより複雑な DOS 難読化手法がありますが、上記の対処法は、最も一般的な手法に対して有効です。

以下の例では、Windows Defender ファイアウォール サービスを停止させる *net.exe* というファイルを検索するクエリを作成するためのさまざまな方法を示します。

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
## <a name="related-topics"></a>関連項目
- [積極的に脅威を検索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使う](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を検索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
