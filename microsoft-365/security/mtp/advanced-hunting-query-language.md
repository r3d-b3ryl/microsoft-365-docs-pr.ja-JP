---
title: Microsoft 365 Defender の高度な検索クエリ言語について
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、language、advanced、first query、テレメトリ、イベント、テレメトリ、カスタム検出、スキーマ、kusto、operators、データ型、powershell ダウンロード、クエリの例
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
ms.openlocfilehash: bb3caff642e752cb6d3941b697820fbad69ae23c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841978"
---
# <a name="learn-the-advanced-hunting-query-language"></a>高度な捜索のクエリ言語について学習する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な捜索は、[Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。 Kusto 演算子およびステートメントを使用して、特定の [スキーマ](advanced-hunting-schema-tables.md)で情報を検索するクエリを作成できます。 これらの概念をよりよく理解するために、最初のクエリを実行します。

## <a name="try-your-first-query"></a>最初のクエリを試してみる

Microsoft 365 セキュリティセンターで、「検索 **」に移動** して最初のクエリを実行します。 次の例を使用してください。

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

**[高度な検索でこのクエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>クエリについて説明し、検索するテーブルを指定する
クエリの先頭に短いコメントが追加されました。その目的について説明します。 このコメントは、後でクエリを保存して組織内の他のユーザーと共有する場合に役に立ちます。 

```kusto
// Finds PowerShell execution events that could involve a download
```

通常、クエリ自体はテーブル名から始まり、パイプ () で始まる複数の要素が続き `|` ます。 この例では、まず、2つのテーブルのユニオンを作成し、  `DeviceProcessEvents` `DeviceNetworkEvents` を、必要に応じてパイプライン処理された要素を追加します。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>時間の範囲を設定する
最初のパイプライン処理された要素は、前の7日間を対象範囲とする時間フィルターです。 時間範囲を制限すると、クエリが適切に実行されるようになり、管理可能な結果を返すことができます。タイムアウトすることはありません。

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>特定のプロセスを確認する
時間範囲の直後には、PowerShell アプリケーションを表すプロセスファイル名の検索が続きます。

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>特定のコマンド文字列を検索する
その後、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンドラインの文字列を検索します。

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

### <a name="customize-result-columns-and-length"></a>結果の列と長さをカスタマイズする 
検索するデータをクエリが明確に識別できるようになったので、結果の外観を定義できます。 `project` 特定の列を返し、 `top` 結果の数を制限します。 これらの演算子を使用すると、結果が適切に書式設定されており、処理がかなり簡単になります。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

[ **クエリの実行** ] を選択して結果を表示します。 クエリエディターの右上にある展開アイコンを使用して、探しているクエリと結果にフォーカスを移動します。 

![高度な検索クエリエディターの展開コントロールのイメージ](../../media/advanced-hunting-expand.png)

>[!TIP]
>クエリ結果をグラフとして表示し、フィルターをすばやく調整することができます。 ガイダンスについては、「[クエリ結果の使用方法](advanced-hunting-query-results.md)」を参照してください。

## <a name="learn-common-query-operators"></a>一般的なクエリ演算子について説明します。

最初のクエリを実行し、そのコンポーネントの概要を把握していること。 少し時間をずらして、いくつかの基本事項について説明します。 高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。

| 演算子 | 説明および使用法 |
|--|--|
| `where` | 述語に適合する行のサブセットにテーブルをフィルター処理します。 |
| `summarize` | 入力テーブルの内容を集約したテーブルを作成します。 |
| `join` | 各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。 |
| `count` | 入力レコード セットのレコード数を返します。 |
| `top` | 指定された列によって並べ替えられた最初の N レコードを返します。 |
| `limit` | 指定された行数まで返します。 |
| `project` | 新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。 |
| `extend` | 計算列を作成し、結果セットに追加します。 |
| `makeset` |  Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。 |
| `find` | テーブルのセットで述語と一致する行を検索します。 |

これらの演算子の実際の例を見るには、高度な捜索の [ **はじめに** ] セクションから実行します。

## <a name="understand-data-types"></a>データ型について理解する

高度な検索では、次の一般的な種類を含む Kusto データ型をサポートしています。

| データ型 | 説明とクエリの意味 |
|--|--|
| `datetime` | 通常、イベントのタイムスタンプを表すデータおよび時刻情報。 [サポートされている datetime 形式を参照する](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | 一重引用符 ( `'` ) または二重引用符 () で囲んだ utf-8 の文字列 `"` 。 [文字列の詳細を参照する](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | このデータ型 `true` は、またはの `false` 状態をサポートします。 [サポートされているリテラルおよび演算子を参照する](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32ビット整数  |
| `long` | 64ビット整数 |

これらのデータ型の詳細については、「 [Kusto スカラーデータ型](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)」を参照してください。

## <a name="get-help-as-you-write-queries"></a>クエリを記述するときにヘルプを参照する
次の機能を利用して、クエリをより速く記述します。
- **Autosuggest** : クエリを作成すると、高度な検索によって IntelliSense から候補が表示されます。 
- **スキーマツリー** -テーブルとその列のリストを含むスキーマ表現は、作業領域の横に表示されます。 詳細については、アイテムにカーソルを合わせてください。 アイテムをダブルクリックして、クエリ エディターに挿入します。
- **[スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : テーブルと列の説明、およびサポートされるイベントの種類 ( `ActionType` 値) とサンプルクエリを含むポータル内のリファレンス

## <a name="work-with-multiple-queries-in-the-editor"></a>エディターで複数のクエリを操作する
クエリエディターを使用して、複数のクエリを試すことができます。 複数のクエリを使用するには

- 各クエリは空の行で区切ります。
- クエリの任意の部分にカーソルを置き、クエリを実行する前に選択します。 これは、選択したクエリのみを実行します。 別のクエリを実行するには、必要に応じてカーソルを移動して、[ **クエリの実行** ] を選択します。

![複数のクエリを使用したクエリエディターのイメージ](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>サンプル クエリを使用する

[ **はじめに** ] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。 これらのクエリを実行して、少し変更してみてください。

![高度な捜索ウィンドウの画像](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。 ページまたは [GitHub クエリリポジトリ](https://aka.ms/hunting-queries)の左側にある共有クエリを調べます。

## <a name="access-query-language-documentation"></a>クエリ言語のドキュメントにアクセスする

Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](https://docs.microsoft.com/azure/kusto/query/)」を参照してください。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
