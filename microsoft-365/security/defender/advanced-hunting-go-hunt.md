---
title: go hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやくクエリするために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な狩猟、インシデント、ピボット、エンティティ、go hunt、関連イベント、脅威狩り、サイバー脅威狩り、検索、クエリ、テレメトリ、Microsoft 365、Microsoft 365 Defender
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
ms.openlocfilehash: 3d1ec22febe0c0072a4eed2a9b8fece3687762d7
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754283"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>go hunt を使用してエンティティまたはイベント情報をすばやく検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類 [をすばやく調査](advanced-hunting-overview.md) できます。 このアクションでは、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。

Go *Hunt アクション* は、Defender for Cloud のさまざまなセクションで利用できます。 このアクションは、イベントまたはエンティティの詳細が表示された後に表示できます。 たとえば、次のセクションから *go ハント* オプションを使用できます。

- インシデント ページ [では、](investigate-incidents.md#summary)インシデントに関連付けられているユーザー、デバイス、その他多くのエンティティに関する詳細を確認できます。 エンティティを選択すると、追加の情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。 次の例では、メールボックスが選択され、メールボックスの詳細とメールボックスの詳細を検索するオプションが表示されます。

    :::image type="content" source="../../media/go-hunt-1-incident.png" alt-text="[メールボックス] ページと [移動ハント] オプションが含Microsoft 365 Defenderポータル" lightbox="../../media/go-hunt-1-incident.png":::

- インシデント ページでは、[証拠] タブでエンティティの一覧に **アクセス** することもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく検索できます。

    :::image type="content" source="../../media/go-hunt-2-entity.png" alt-text="ポータルの [インシデント] ページの証拠の一部に対する go ハント オプションMicrosoft 365 Defenderします。" lightbox="../../media/go-hunt-2-entity.png":::


- デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。 イベントを選択すると、高度な検索で他の関連イベントを探すオプションが表示されます。

    :::image type="content" source="../../media/go-hunt-3-event.png" alt-text="イベント ポータルの [タイムライン] タブにあるイベントのページの [関連イベントのハント] Microsoft 365 Defenderします。" lightbox="../../media/go-hunt-3-event.png":::

関連イベント **に対して** [Go hunt **] または [ハント** ] を選択すると、エンティティまたはイベントを選択したかどうかに応じて、さまざまなクエリが渡されます。

## <a name="query-for-entity-information"></a>エンティティ情報のクエリ
go hunt を *使用して* 、ユーザー、デバイス、または他の種類のエンティティに関する情報を照会できます。クエリは、関連するすべてのスキーマ テーブルで、そのエンティティが関連するすべてのイベントをチェックして情報を返します。 結果を管理し続けるには、次のクエリを実行します。
- エンティティを含む過去 30 日間の最も早いアクティビティと同じ期間にスコープを設定
- インシデントに関連付けられている。

デバイスの移動ハント クエリの例を次に示します。

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>サポートされているエンティティの種類
次のエンティティの種類 *を選択* した後で、go hunt オプションを使用できます。

- ファイル
- メール
- 電子メール クラスター
- メールボックス
- ユーザー
- デバイス
- IP アドレス
- URL

## <a name="query-for-event-information"></a>イベント情報のクエリ
go *hunt を使用して* タイムライン イベントに関する情報を照会する場合、クエリは、選択したイベントの時刻に関連するすべてのスキーマ テーブルで他のイベントをチェックします。 たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>クエリを調整する
クエリ言語に関する知識 [がある](advanced-hunting-query-language.md)場合は、クエリを好みに合わせて調整できます。 たとえば、タイム ウィンドウのサイズを決定する次の行を調整できます。

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

より関連性の高い結果を得るクエリの変更に加えて、次の処理も実行できます。
- [結果をグラフとして表示する](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [カスタム検出ルールの作成](custom-detection-rules.md)

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。 [複数のデータ Microsoft 365 Defender](m365d-enable.md)を使用して脅威を検出するには、このオプションをオンにしてください。 高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動するには、「[Advanced Hunting queries を Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md) から移行する」の手順に従います。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出ルール](custom-detection-rules.md)
