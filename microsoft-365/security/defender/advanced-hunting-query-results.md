---
title: 高度なハンティング クエリの結果をMicrosoft 365 Defenderで操作する
description: Microsoft 365 Defenderの高度な捜索によって返されるクエリ結果を最大限に活用する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto, 視覚化, グラフ, フィルター, ドリルダウン
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
ms.openlocfilehash: cb17e2a3624471031eb4f72199705d6b8fe06979
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092869"
---
# <a name="work-with-advanced-hunting-query-results"></a>高度なハンティング クエリの結果を操作する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な捜索](advanced-hunting-overview.md)クエリを作成して正確な情報を返すこともできますが、クエリ結果を操作して、さらに詳しい分析情報を得て、特定のアクティビティとインジケーターを調査することもできます。 クエリ結果に対して次のアクションを実行できます。

- 結果をテーブルまたはグラフとして表示する
- テーブルとグラフをエクスポートする
- 詳細なエンティティ情報にドリルダウンする
- 結果から直接クエリを調整する

## <a name="view-query-results-as-a-table-or-chart"></a>クエリ結果をテーブルまたはグラフとして表示する

既定では、高度な検索では、クエリ結果が表形式のデータとして表示されます。 グラフと同じデータを表示することもできます。 高度なハンティングでは、次のビューがサポートされます。

| ビューの種類 | 説明 |
|--|--|
| **表** | クエリ結果を表形式で表示します |
| **縦棒グラフ** | 高さが別のフィールドの数値を表す垂直バーとして、X 軸上の一連の一意の項目をレンダリングします |
| **円グラフ** | 一意の項目を表すセクション円グラフをレンダリングします。 各円のサイズは、別のフィールドの数値を表します。 |
| **折れ線グラフ** | 一連の一意の項目の数値をプロットし、プロットされた値を接続します |
| **散布図** | 一連の一意の項目の数値をプロットする |
| **面グラフ** | 一連の一意の項目の数値をプロットし、プロットされた値の下のセクションに入力します。 |
| **積み上げ面グラフ** | 一連の一意の項目の数値をプロットし、プロットされた値の下に塗りつぶされたセクションを積み重ねる  |
| **タイム チャート** | 線形時間スケールでカウントして値をプロットする |

### <a name="construct-queries-for-effective-charts"></a>効果的なグラフのクエリを作成する

グラフを表示する場合、高度な捜索では、対象の列と集計する数値が自動的に識別されます。 わかりやすいグラフを取得するには、視覚化して表示する特定の値を返すクエリを作成します。 いくつかのサンプル クエリと結果のグラフを次に示します。

#### <a name="alerts-by-severity"></a>重大度別のアラート

演算子を `summarize` 使用して、グラフ化する値の数値カウントを取得します。 次のクエリでは、演算子を `summarize` 使用して重大度別のアラートの数を取得します。

```kusto
AlertInfo
| summarize Total = count() by Severity
```

結果を表示する場合、縦棒グラフには各重大度の値が個別の列として表示されます。

:::image type="content" source="../../media/advanced-hunting-column-chart-new.png" alt-text="Microsoft 365 Defender ポータルに高度なハンティング結果を表示するグラフの例" lightbox="../../media/advanced-hunting-column-chart-new.png":::
*縦棒グラフとして表示される重大度別のアラートのクエリ結果*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>上位 10 の送信者ドメインにわたるフィッシングメール

有限でない値の一覧を処理する場合は、演算子を `Top` 使用して、最も多くのインスタンスを持つ値のみをグラフ化できます。 たとえば、フィッシングメールが最も多い上位 10 の送信者ドメインを取得するには、次のクエリを使用します。

```kusto
EmailEvents
| where ThreatTypes has "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```

円グラフ ビューを使用して、上位ドメイン間の分布を効果的に表示します。

:::image type="content" source="../../media/advanced-hunting-pie-chart-new.png" alt-text="高度なハンティング結果をMicrosoft 365 Defender ポータルに表示する円グラフ" lightbox="../../media/advanced-hunting-pie-chart-new.png":::
*上位の送信者ドメイン間でのフィッシングメールの分布を示す円グラフ*

#### <a name="file-activities-over-time"></a>時間の経過に伴うファイル アクティビティ
`summarize`この関数で演算子を`bin()`使用すると、時間の経過と共に特定のインジケーターに関連するイベントを確認できます。 次のクエリでは、30 分間隔でファイル `invoice.doc` に関連するイベントがカウントされ、そのファイルに関連するアクティビティの急増が表示されます。

```kusto
CloudAppEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```

次の折れ線グラフでは、次のアクティビティが含まれる `invoice.doc`期間が明確に示されています。

:::image type="content" source="../../media/line-chart-a.png" alt-text="Microsoft 365 Defender ポータルに高度なハンティング結果を表示する折れ線グラフ" lightbox="../../media/line-chart-a.png":::
*時間の経過に伴うファイルに関連するイベントの数を示す折れ線グラフ*

## <a name="export-tables-and-charts"></a>テーブルとグラフをエクスポートする

クエリを実行した後、 **エクスポート** を選択して結果をローカル ファイルに保存します。 選択したビューによって、結果のエクスポート方法が決まります。

- **テーブル ビュー** - クエリ結果は、Microsoft Excel ブックとして表形式でエクスポートされます
- **任意のグラフ** - クエリ結果は、レンダリングされたグラフの JPEG イメージとしてエクスポートされます

## <a name="drill-down-from-query-results"></a>クエリ結果からのドリルダウン

クエリ結果のレコードをすばやく調べるには、対応する行を選択して [レコードの **検査** ] パネルを開きます。 パネルには、選択したレコードに基づいて次の情報が表示されます。

- **資産** - レコードに含まれる主要な資産 (メールボックス、デバイス、およびユーザー) の概要ビュー。リスクレベルや露出レベルなどの利用可能な情報で強化されています
- **すべての詳細** - レコード内の列のすべての値

:::image type="content" source="../../media/results-inspect-record.png" alt-text="Microsoft 365 Defender ポータルでレコードを調べるパネルを含む選択したレコード" lightbox="../../media/results-inspect-record.png":::

コンピューター、ファイル、ユーザー、IP アドレス、URL など、クエリ結果内の特定のエンティティの詳細を表示するには、エンティティ識別子を選択して、そのエンティティの詳細なプロファイル ページを開きます。

## <a name="tweak-your-queries-from-the-results"></a>結果からクエリを絞り込む

[ **レコードの検査** ] パネルで、任意の列の右側にある 3 つのドットを選択します。 次のようなオプションを使用できます。

- 選択した値 (`==`) を明示的に検索する
- 選択した値をクエリ (`!=`) から除外する 
- 、、など`contains``starts with`、クエリに値を追加するためのより高度な演算子を取得します。`ends with`

:::image type="content" source="../../media/work-with-query-tweak-query.png" alt-text="Microsoft 365 Defender ポータルの [レコードの検査] ページの [アクションの種類] ウィンドウ" lightbox="../../media/work-with-query-tweak-query.png":::

> [!NOTE]
> この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](custom-detections-overview.md)
