---
title: Microsoft 365 Defenderで高度なハンティング クエリ言語を学習する
description: 最初の脅威の捜索クエリを作成し、一般的な演算子と高度な捜索クエリ言語の他の側面について学習する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, 言語, 学習, 最初のクエリ, テレメトリ, イベント, テレメトリ, カスタム検出, スキーマ, kusto, 演算子, データ型, powershell ダウンロード, クエリの例
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c650e639d1a4629ed25bcc3a7f3a8c28df4b8e8
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603486"
---
# <a name="learn-the-advanced-hunting-query-language"></a>高度な捜索のクエリ言語について学習する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft 365 Defender
- Microsoft Defender for Endpoint

高度な捜索は、[Kusto クエリ言語](/azure/kusto/query/)に基づいています。 Kusto 演算子とステートメントを使用して、特殊化されたスキーマ内の情報を検索するクエリを作成 [できます](advanced-hunting-schema-tables.md)。 

この短いビデオでは、便利な Kusto クエリ言語の基本について説明します。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRwfJ]
 
これらの概念をよりよく理解するために、最初のクエリを実行します。

## <a name="try-your-first-query"></a>最初のクエリを試してみる

Microsoft 365 Defender ポータルで **、Hunting** に移動して最初のクエリを実行します。 次の例を使用してください。 

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

**[高度な捜索でこのクエリを実行する](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>クエリを記述し、検索するテーブルを指定する

クエリの先頭に短いコメントが追加され、目的を説明しました。 このコメントは、後でクエリを保存し、組織内の他のユーザーと共有することを決定した場合に役立ちます。 

```kusto
// Finds PowerShell execution events that could involve a download
```

通常、クエリ自体はテーブル名で始まり、その後にパイプ (`|`) で始まるいくつかの要素が続きます。 この例では、まず 2 つのテーブルの和集合を作成し`DeviceNetworkEvents`、`DeviceProcessEvents`必要に応じてパイプ要素を追加します。

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```

### <a name="set-the-time-range"></a>時間範囲を設定する

最初のパイプ要素は、前の 7 日間の範囲の時間フィルターです。 時間範囲を制限することで、クエリが適切に実行され、管理可能な結果が返され、タイムアウトが回避されるのに役立ちます。

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>特定のプロセスを確認する

時間範囲の直後に、PowerShell アプリケーションを表すプロセス ファイル名を検索します。

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>特定のコマンド文字列を検索する

その後、クエリは、PowerShell を使用してファイルをダウンロードするために通常使用されるコマンド ライン内の文字列を検索します。

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

クエリによって、検索するデータが明確に識別されるようになったので、結果の見た目を定義できます。 `project` は特定の列を返し `top` 、結果の数を制限します。 これらの演算子は、結果が適切に書式設定され、合理的に大きく、処理が簡単であることを確認するのに役立ちます。

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

[ **クエリの実行** ] を選択して結果を表示します。

>[!TIP]
>クエリ結果をグラフとして表示し、フィルターをすばやく調整できます。 ガイダンスについては、[クエリ結果の操作に関する記事を参照](advanced-hunting-query-results.md)してください



## <a name="learn-common-query-operators"></a>一般的なクエリ演算子について説明します

最初のクエリを実行したばかりで、そのコンポーネントの一般的な考えを持っています。 少しバックトラックし、いくつかの基本を学ぶ時間です。 高度な捜索で使用される Kusto クエリ言語は、次のような一般的な演算子をサポートします。

| 演算子 | 説明および使用法 |
|--|--|
| `where` | 述語に適合する行のサブセットにテーブルをフィルター処理します。 |
| `summarize` | 入力テーブルの内容を集約したテーブルを作成します。 |
| `join` | 各テーブルから指定された列の値を照合して、2 つのテーブルの行を結合し、新しいテーブルを作成します。 方法については、 [KQL の結合テーブル](https://www.youtube.com/watch?v=8qZx7Pp5XgM) をご覧ください。|
| `count` | 入力レコード セットのレコード数を返します。 |
| `top` | 指定された列によって並べ替えられた最初の N レコードを返します。 |
| `limit` | 指定された行数まで返します。 |
| `project` | 新しい計算列を含める、名前を変更する、またはドロップする列を選択し、挿入します。 |
| `extend` | 計算列を作成し、結果セットに追加します。 |
| `makeset` |  Expr がグループ内でとる個別の値のセットの動的 (JSON) 配列を返します。 |
| `find` | テーブルのセットで述語と一致する行を検索します。 |

これらの演算子の実際の例を見るには、高度な捜索の [**はじめに**] セクションから実行します。

## <a name="understand-data-types"></a>データ型を理解する

高度なハンティングでは、次の一般的な型を含む Kusto データ型がサポートされます。

| データ型 | 説明とクエリの意味 |
|--|--|
| `datetime` | 通常、イベントのタイムスタンプを表すデータおよび時間の情報。 [サポートされている datetime 形式を参照する](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | 一重引用符 (`'`) または二重引用符 (`"`) で囲まれた UTF-8 の文字列。 [文字列の詳細を読む](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | このデータ型は `true` または `false` の状態をサポートします。 [サポートされているリテラルと演算子を参照してください](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | 32 ビット整数  |
| `long` | 64 ビット整数 |

これらのデータ型の詳細については、 [Kusto スカラー データ型に関するページを参照してください](/azure/data-explorer/kusto/query/scalar-data-types/)。

## <a name="get-help-as-you-write-queries"></a>クエリを記述するときにヘルプを参照する

次の機能を利用して、クエリをより速く記述します。
- **Autosuggest** —クエリを記述するときに、高度な捜索では IntelliSense からの提案が提供されます。 
- **スキーマ ツリー** - テーブルの一覧とその列を含むスキーマ表現が作業領域の横に表示されます。 詳細については、アイテムにカーソルを合わせてください。 アイテムをダブルクリックして、クエリ エディターに挿入します。
- **[スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - テーブルと列の説明、サポートされているイベントの種類 (`ActionType` 値)、サンプル クエリを含むポータル内参照

## <a name="work-with-multiple-queries-in-the-editor"></a>エディターで複数のクエリを操作する

クエリ エディターを使用して、複数のクエリを試すことができます。 複数のクエリを使用するには:

- 空の行を使用して各クエリを分離します。
- クエリを実行する前に、クエリの任意の部分にカーソルを置いて、そのクエリを選択します。 これにより、選択したクエリのみが実行されます。 別のクエリを実行するには、それに応じてカーソルを移動し、[ **クエリの実行**] を選択します。

:::image type="content" source="../../media/multiple-queries.png" alt-text="Microsoft 365 Defender ポータルの **[新しいクエリ] ページで複数のクエリを実行する例" lightbox="../../media/multiple-queries.png":::

ワークスペースの効率を高めるために、同じハンティング ページで複数のタブを使用することもできます。 [ **新しいクエリ** ] を選択して、新しいクエリのタブを開きます。

:::image type="content" source="../../media/multitab.png" alt-text="Microsoft 365 Defender ポータルで [高度な検索で新規作成] を選択して新しいタブを開く" lightbox="../../media/multitab.png":::

その後、新しいブラウザー タブを開かずに、さまざまなクエリを実行できます。 

:::image type="content" source="../../media/multitab-examples.png" alt-text="Microsoft 365 Defender ポータルの高度なハンティング ページから離れることなく、さまざまなクエリを実行する" lightbox="../../media/multitab-examples.png":::

>[!NOTE] 
> 高度な検索で複数のブラウザー タブを使用すると、保存されていないクエリが失われる可能性があります。 これを防ぐには、ブラウザーの個別のタブではなく、高度なハンティング内でタブ機能を使用します。

## <a name="use-sample-queries"></a>サンプル クエリを使用する

[**はじめに**] セクションでは、一般的に使用されている演算子を使用した簡単なクエリーをいくつか提供します。 これらのクエリを実行して、少し変更してみてください。

:::image type="content" source="../../media/get-started-section.png" alt-text="Microsoft 365 Defender ポータルの **Advanced hunting** ページの **[作業の開始]** セクション" lightbox="../../media/get-started-section.png":::

>[!NOTE]
>基本的なクエリ サンプルとは別に、特定の脅威の捜索シナリオの[共有クエリ](advanced-hunting-shared-queries.md)にアクセスすることもできます。 ページの左側にある共有クエリまたは [GitHub クエリ リポジトリを調べます](https://aka.ms/hunting-queries)。

## <a name="access-query-language-documentation"></a>クエリ言語のドキュメントにアクセスする

Kusto クエリ言語およびサポートされる演算子の詳細については、「[Kusto クエリ言語のドキュメント](/azure/kusto/query/)」を参照してください。

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連トピック

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)