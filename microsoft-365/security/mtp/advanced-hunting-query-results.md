---
title: Microsoft 365 Defender で高度な検索クエリ結果を処理する
description: Microsoft 365 Defender の高度な検索によって返されるクエリ結果を利用する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection、視覚化、グラフ、フィルター、ドリルダウン
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932324"
---
# <a name="work-with-advanced-hunting-query-results"></a>高度な検索クエリ結果を処理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度な検索クエリを[](advanced-hunting-overview.md)作成して非常に正確な情報を返す一方で、クエリ結果を使用して詳細な洞察を得て、特定のアクティビティとインジケーターを調査することもできます。 クエリ結果に対して次のアクションを実行できます。

- 結果を表またはグラフとして表示する
- 表とグラフをエクスポートする
- 詳細なエンティティ情報へのドリルダウン
- 結果からクエリを直接調整するか、フィルターを適用する

## <a name="view-query-results-as-a-table-or-chart"></a>クエリ結果をテーブルまたはグラフとして表示する
既定では、高度な検索ではクエリ結果が表形式データとして表示されます。 グラフと同じデータを表示することもできます。 高度な検索では、次のビューがサポートされます。

| ビューの種類 | 説明 |
| -- | -- |
| **Table** | クエリ結果を表形式で表示します。 |
| **縦棒グラフ** | x 軸上の一連の一意の項目を、高さが別のフィールドの数値を表す垂直バーとしてレンダリングされます。 |
| **積み上げ棒グラフ** | x 軸上の一連の一意の項目を、高さが 1 つ以上の他のフィールドの数値を表す積み上げ縦棒としてレンダリングされます。 |
| **円グラフ** | 一意の項目を表すパイをレンダリングします。 各円グラフのサイズは、別のフィールドの数値を表します。 |
| **ドーナツ グラフ** | 一意のアイテムを表す円弧をレンダリングします。 各円弧の長さは、別のフィールドの数値を表します。 |
| **折れ線グラフ** | 一連の一意のアイテムの数値をプロットし、プロットされた値を接続します。 |
| **散布図** | 一連の一意のアイテムの数値をプロットします。 |
| **エリア チャート** | 一連の一意のアイテムの数値をプロットし、プロットされた値の下のセクションを塗りつぶしる |

### <a name="construct-queries-for-effective-charts"></a>効果的なグラフのクエリを作成する
グラフをレンダリングする場合、高度な検索では、関心のある列と集計する数値が自動的に識別されます。 意味のあるグラフを取得するには、視覚化する特定の値を返すクエリを作成します。 次に、サンプル クエリと結果のグラフを示します。

#### <a name="alerts-by-severity"></a>重大度別のアラート
演算子を `summarize` 使用して、グラフを作成する値の数値カウントを取得します。 次のクエリでは、演算子 `summarize` を使用して重大度別のアラート数を取得します。

```kusto
AlertInfo
| summarize Total = count() by Severity
```
結果をレンダリングする場合、列グラフには各重要度の値が個別の列として表示されます。

![高度な検索クエリ結果が、重大度別のアラートに対する列グラフクエリ結果として表示された、列 ](../../media/advanced-hunting-column-chart.jpg)
 *グラフとして表示される画像*

#### <a name="alert-severity-by-operating-system"></a>オペレーティング システム別のアラートの重要度
演算子を使用して、 `summarize` 複数のフィールドから値をグラフ化する結果を準備することもできます。 たとえば、警告の重要度がオペレーティング システム (OS) 間でどのように分散されるのかについて理解したい場合があります。 

次のクエリでは、演算子を使用して表から OS 情報を取り込み、列と列の両方の値をカウント `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` します。

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
これらの結果は、積み上げされた棒グラフを使用して視覚化すると最適です。

![OS および重大度別のアラートのクエリ結果を積み上げグラフとして表示する高度な検索クエリ結果 ](../../media/advanced-hunting-stacked-chart.jpg)
 *の画像*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>上位 10 個の送信者ドメインのフィッシングメール
有限ではない値のリストを扱う場合は、演算子を使用して、最も多くのインスタンスを持つ値のみを `Top` グラフ化できます。 たとえば、フィッシングメールが最も多い上位 10 個の送信者ドメインを取得するには、次のクエリを使用します。

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
円グラフ ビューを使用して、上位ドメイン間の分布を効果的に表示します。

![上位送信者ドメイン間でのフィッシング メールの配布を示す円グラフとして表示された高度な検索クエリ結果 ](../../media/advanced-hunting-pie-chart.jpg)
 *の画像*

#### <a name="file-activities-over-time"></a>時間の過ぎたファイル アクティビティ
演算子を `summarize` 関数と一緒に `bin()` 使用すると、特定のインジケーターに関連するイベントを時間のとともにチェックできます。 次のクエリは、ファイルに関連するイベントを 30 分間隔でカウントし、そのファイルに関連するアクティビティのスパイク `invoice.doc` を示します。

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
次の線グラフは、次のアクティビティを含む期間を明確に強調しています `invoice.doc` 。 

![高度な検索クエリの結果が、時間の中でファイルに関係するイベントの数を示す線グラフの線グラフ ](../../media/advanced-hunting-line-chart.jpg)
 *として表示される画像*


## <a name="export-tables-and-charts"></a>表とグラフをエクスポートする
クエリを実行した後、[エクスポート] **を** 選択して結果をローカル ファイルに保存します。 選択したビューによって、結果のエクスポート方法が決なります。

- **テーブル ビュー** - クエリ結果は、Microsoft Excel ブックとして表形式でエクスポートされます。
- **任意の** グラフ — クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます。

## <a name="drill-down-from-query-results"></a>クエリ結果からドリルダウンする
クエリ結果でレコードをすばやく検査するには、対応する行を選択して [レコードの検査] パネル **を開** きます。 パネルは、選択したレコードに基づいて次の情報を提供します。

- **資産** — レコード内の主な資産 (メールボックス、デバイス、ユーザー) の要約ビューで、リスクや露出レベルなどの利用可能な情報が豊富に表示されます。
- **プロセス ツリー** — プロセス情報を持つレコード用に生成され、利用可能なコンテキスト情報を使用して強化されます。一般に、より多くの列を返すクエリを実行すると、より豊富なプロセス ツリーが生成される可能性があります。
- **すべての詳細** - レコード内の列からのすべての値  

![レコードを検査するパネルを含む選択されたレコードの画像](../../media/mtp-ah/inspect-record.png)

コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果の特定のエンティティに関する詳細を表示するには、エンティティ識別子を選択して、そのエンティティの詳細なプロファイル ページを開きます。

## <a name="tweak-your-queries-from-the-results"></a>結果からクエリを絞り込む
結果セットの値を右クリックすると、クエリがすばやく強化されます。 次のようなオプションを使用できます。

- 選択した値 (`==`) を明示的に検索する
- 選択した値をクエリ (`!=`) から除外する 
- クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する 

![高度な検索結果セットの画像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>クエリ結果をフィルター処理する
右に表示されるフィルターは、結果セットの要約を提供します。 各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。

クエリを絞り込むには、含める値または除外する値のボタンを選択し、[クエリの実行] を `+` `-` **選択します**。

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
