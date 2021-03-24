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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064395"
---
# <a name="advanced-hunting-query-best-practices"></a>高度な検索クエリのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>クエリのパフォーマンスを最適化する

これらの推奨事項を適用して、結果をより速く取得し、複雑なクエリの実行中にタイムアウトを回避します。

- 新しいクエリを試行するときは、結果セットが大きくなり過ぎないよう、常に `limit` を使用します。 `count` を使用して結果セットのサイズを最初に判断することもできます。
- 最初に時間フィルターを使用します。 クエリを 7 日に制限するのが理想です。
- 時間フィルターの適用直後に、ほとんどのデータがクエリの開始時に除外されるようなフィルターを適用します。
- 完全なトークンを検索する場合の演算子として、`contains` ではなく `has` を使用します。
- すべての列に対して全文検索を実行するのではなく、特定の列を検索します。
- テーブルを結合するときは、最初は行数が少ないテーブルを指定します。
- `project` は、結合したテーブルの必要な列に対してのみ使用します。

>[!TIP]
>クエリのパフォーマンスを向上させる方法の詳細については、「[Kusto クエリのベスト プラクティス](https://docs.microsoft.com/azure/kusto/query/best-practices)」を参照してください。

## <a name="query-tips-and-pitfalls"></a>クエリのヒントと落とし穴

### <a name="queries-with-process-ids"></a>プロセス ID を使用するクエリ

Windows では、プロセス ID (PID) はリサイクルされ、新しいプロセス用に再利用されます。 そのため、それ単体では特定のプロセスの一意の識別子として機能しません。 特定のデバイス上のプロセスの一意の識別子を取得するには、プロセスの作成時間と共にプロセス ID を使用します。 プロセスに関するデータを結合または集計する場合は、デバイス識別子 (または) 、プロセス ID (または)、およびプロセス作成時間 (または) の列を `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` 含 `ProcessCreationTime` める `InitiatingProcessCreationTime` 必要があります。

次のクエリ例では、ファイル共有のスキャンを行っている可能性がある、ポート 445 (SMB) 経由で 10 個を超える IP アドレスにアクセスしているプロセスを見つけます。

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
- 大文字と小文字を区別しない一致を使用します。 たとえば、 `=~` 、 、 `in~` の代 `contains` わりに 、 `==` を使用 `in` します。 `contains_cs`
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

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出の概要](overview-custom-detections.md)
