---
title: Microsoft 365 Defender で高度な検索クエリ結果を操作する
description: Microsoft 365 Defender で高度な検索によって返されるクエリ結果の大部分を作成する
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection、視覚エフェクト、グラフ、フィルター、ドリルダウン
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
ms.openlocfilehash: de26989b9092b783a45d27ad2a529720d21169f8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844130"
---
# <a name="work-with-advanced-hunting-query-results"></a>高度な検索クエリの結果を操作する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な](advanced-hunting-overview.md)検索クエリを作成して非常に正確な情報を返すことができますが、クエリ結果を使用して、特定のアクティビティとインジケーターをより詳細に把握し、調査することもできます。 クエリ結果に対して次の操作を行うことができます。

- 結果を表またはグラフとして表示する
- テーブルとグラフをエクスポートする
- 詳細なエンティティ情報へのドリルダウン
- 結果から直接、またはフィルターを適用してクエリを微調整する

## <a name="view-query-results-as-a-table-or-chart"></a>クエリ結果を表またはグラフとして表示する
既定では、高度な検索では、クエリ結果が表形式データとして表示されます。 同じデータをグラフとして表示することもできます。 高度な検索では、次のビューがサポートされます。

| ビューの種類 | 説明 |
| -- | -- |
| **Table** | クエリの結果を表形式で表示します。 |
| **縦棒グラフ** | X 軸に一連の一意のアイテムを垂直バーとしてレンダリングし、高さが別のフィールドの数値を表すようにします。 |
| **積み上げ縦棒グラフ** | X 軸上の一連の一意のアイテムを、1つまたは複数の他のフィールドからの数値で表される垂直な積み上げ縦棒グラフで描画します。 |
| **円グラフ** | 一意のアイテムを表す、断面パイをレンダリングします。 各円グラフのサイズは、別のフィールドの数値を表します。 |
| **ドーナツグラフ** | 一意の項目を表す各弧をレンダリングします。 各弧の長さは、別のフィールドの数値を表します。 |
| **折れ線グラフ** | 一連の固有のアイテムの数値をプロットし、プロットされた値を接続します。 |
| **散布図** | 一連の固有のアイテムの数値をプロットします。 |
| **面グラフ** | 一連の固有のアイテムの数値をプロットし、プロットされた値の下にセクションを塗りつぶします。 |

### <a name="construct-queries-for-effective-charts"></a>効果的なグラフのクエリを作成する
グラフを表示する場合、高度な検索では、目的の列と集計する数値を自動的に識別します。 意味のあるグラフを取得するには、表示する特定の値を返すようにクエリを作成します。 いくつかのサンプルクエリと結果のグラフを次に示します。

#### <a name="alerts-by-severity"></a>重要度別のアラート
演算子を使用して、 `summarize` グラフにする値の数値の個数を取得します。 次のクエリは、オペレーターを使用し `summarize` てアラートの数を重要度別に取得します。

```kusto
AlertInfo
| summarize Total = count() by Severity
```
結果を表示するときに、縦棒グラフにそれぞれの重要度の値が個別の列として表示されます。

![重要度別のアラートの列グラフクエリ結果として表示されている高度な検索クエリ結果の画像 ](../../media/advanced-hunting-column-chart.jpg)
 *列のグラフとして表示され* ます。

#### <a name="alert-severity-by-operating-system"></a>オペレーティングシステムによるアラートの重要度
また、演算子を使用して、 `summarize` 複数のフィールドからのグラフ値の結果を準備することもできます。 たとえば、オペレーティングシステム (OS) 間でアラートの重大度がどのように分散されているかを理解する必要があるかもしれません。 

次のクエリでは、演算子を使用して `join` テーブルから OS 情報を取得し、を使用して `DeviceInfo` `summarize` と列の両方の値をカウントし `OSPlatform` `Severity` ます。

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
これらの結果は、積み上げ縦棒グラフを使用するのが最適です。

![拡張 ](../../media/advanced-hunting-stacked-chart.jpg)
 *グラフとして表示される OS と重要度によって* 、高度な検索クエリ結果が積み上げグラフクエリ結果として表示される画像

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>上位10人の送信者ドメインでのフィッシング電子メール
限定されていない値のリストを処理する場合は、演算子を使用して、 `Top` インスタンスが最も多い値のみをグラフ化できます。 たとえば、最もフィッシング詐欺メールで上位10個の送信者ドメインを取得するには、次のクエリを使用します。

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
[円グラフ] ビューを使用して、上位ドメイン間の分散を効果的に表示します。

![](../../media/advanced-hunting-pie-chart.jpg)
*上位の送信者ドメイン間でのフィッシング電子メールの配布を示す* 円グラフとして表示される高度な検索クエリ結果の画像

#### <a name="file-activities-over-time"></a>時間の経過に伴うファイルアクティビティ
`summarize`関数で演算子を使用 `bin()` すると、特定のインジケーターに関係するイベントを時間の経過とともに確認できます。 次のクエリは、ファイルに関連するイベントを `invoice.doc` 30 分間隔でカウントし、そのファイルに関連するアクティビティのスパイクを示します。

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
下の行は、次のようなアクティビティを伴う期間を明確に強調してい `invoice.doc` ます。 

![](../../media/advanced-hunting-line-chart.jpg)
*時間の経過に伴うファイルに関連するイベントの数を示す* 折れ線グラフの折れ線グラフとして表示される高度な検索クエリ結果の画像


## <a name="export-tables-and-charts"></a>テーブルとグラフをエクスポートする
クエリを実行した後、[ **エクスポート** ] を選択して結果をローカルファイルに保存します。 選択したビューによって、結果のエクスポート方法が決まります。

- **テーブルビュー** -クエリ結果は、Microsoft Excel ブックとして表形式でエクスポートされます。
- **任意のグラフ** -クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。

## <a name="drill-down-from-query-results"></a>クエリ結果からドリルダウンする
クエリ結果のレコードをすばやく検査するには、対応する行を選択して [ **レコードの検査** ] パネルを開きます。 パネルには、選択したレコードに基づいて次の情報が表示されます。

- **アセット** : レコードに含まれているメインアセット (メールボックス、デバイス、ユーザー) の要約されたビューで、リスクや露出レベルなどの利用可能な情報で拡充されています。
- **プロセスツリー** —プロセス情報を含むレコードに対して生成され、使用可能なコンテキスト情報を使用して拡充されます。一般に、クエリが多くの列を返すと、より豊富なプロセスツリーになることがあります。
- **すべての詳細** : レコード内の列のすべての値  

![レコードを検査するためのパネルがある、選択されたレコードのイメージ](../../media/mtp-ah/inspect-record.png)

コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果内の特定のエンティティに関する詳細情報を表示するには、エンティティ識別子を選択してそのエンティティの詳細なプロファイルページを開きます。

## <a name="tweak-your-queries-from-the-results"></a>結果からクエリを絞り込む
結果セットの値を右クリックすると、クエリがすばやく強化されます。 次のようなオプションを使用できます。

- 選択した値 (`==`) を明示的に検索する
- 選択した値をクエリ (`!=`) から除外する 
- クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する 

![高度な検索結果セットの画像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>クエリ結果をフィルター処理する
右に表示されるフィルターは、結果セットの要約を提供します。 各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。

含めるまたは除外する値のまたはボタンを選択し、[クエリの実行] を選択して、クエリの絞り込みを行い `+` `-` ます。 **Run query**

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
