---
title: Go hunt を使用してエンティティに関する関連情報を取得する
description: Go hunt ツールを使用して、高度なハンティングを使用してエンティティまたはイベントに関する関連情報をすばやく照会する方法について説明します。
keywords: 高度な捜索, インシデント, ピボット, エンティティ, go hunt, 関連イベント, 脅威の捜索, サイバー脅威の捜索, 検索, クエリ, テレメトリ, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 7c1e4153afb7f279b5d31cce29a86f42bdc93832
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483390"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Go hunt を使用してエンティティまたはイベント情報をすばやく検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

*Go hunt* アクションを使用すると、強力なクエリ ベースの [高度なハンティング](advanced-hunting-overview.md)機能を使用して、イベントやさまざまなエンティティの種類をすばやく調査できます。 このアクションは、選択したイベントまたはエンティティに関する関連情報を検索するために、高度なハンティング クエリを自動的に実行します。

*Go hunt* アクションは、Defender for Cloud のさまざまなセクションで使用できます。 このアクションは、イベントまたはエンティティの詳細が表示されたら表示できます。 たとえば、次のセクションの *go hunt* オプションを使用できます。

- [インシデント ページ](investigate-incidents.md#summary)では、インシデントに関連付けられているユーザー、デバイス、およびその他の多くのエンティティに関する詳細を確認できます。 エンティティを選択すると、追加情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。 次の例では、メールボックスが選択され、メールボックスに関する詳細と、メールボックスの詳細を検索するオプションが表示されます。

    :::image type="content" source="../../media/go-hunt-1-incident.png" alt-text="Microsoft 365 Defender ポータルの [Go hunt] オプションが表示された [メールボックス] ページ" lightbox="../../media/go-hunt-1-incident.png":::

- インシデント ページでは、[ **証拠** ] タブでエンティティの一覧にアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく検索できます。

    :::image type="content" source="../../media/go-hunt-2-entity.png" alt-text="ポータルの [インシデント] ページの証拠の [Go hunt] オプションMicrosoft 365 Defender" lightbox="../../media/go-hunt-2-entity.png":::


- デバイスのタイムラインを表示するときに、タイムラインでイベントを選択すると、そのイベントに関する追加情報を表示できます。 イベントが選択されると、高度なハンティングで他の関連イベントを探すオプションが表示されます。

    :::image type="content" source="../../media/go-hunt-3-event.png" alt-text="ポータルの [タイムライン] タブにあるイベントのページの [関連イベントのハント] オプションMicrosoft 365 Defender" lightbox="../../media/go-hunt-3-event.png":::

**関連イベントに対して** **Go hunt** または Hunt を選択すると、エンティティとイベントのどちらを選択したかに応じて、さまざまなクエリが渡されます。

## <a name="query-for-entity-information"></a>エンティティ情報のクエリ
*Go hunt* を使用して、ユーザー、デバイス、またはその他の種類のエンティティに関する情報を照会できます。クエリは、関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックして情報を返します。 結果を管理しやすい状態に保つため、クエリは次のとおりです。
- は、エンティティを含む過去 30 日間の最も早いアクティビティとほぼ同じ期間にスコープされます。
- インシデントに関連付けられている。

デバイスの Go ハント クエリの例を次に示します。

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
次のいずれかのエンティティの種類を選択した後で *、go hunt* オプションを使用できます。

- Files
- メール
- Email クラスター
- メールボックス
- ユーザー
- デバイス
- IP アドレス
- URL

## <a name="query-for-event-information"></a>イベント情報のクエリ
*Go hunt* を使用してタイムライン イベントに関する情報を照会する場合、クエリは、選択したイベントの前後の他のイベントについて、関連するすべてのスキーマ テーブルをチェックします。 たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。

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
[クエリ言語](advanced-hunting-query-language.md)に関する知識があれば、クエリを好みに合わせて調整できます。 たとえば、タイム ウィンドウのサイズを決定する次の行を調整できます。

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

クエリを変更して、より関連性の高い結果を得るだけでなく、次の操作も行うことができます。
- [結果をグラフとして表示する](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [カスタム検出ルールを作成する](custom-detection-rules.md)

>[!NOTE]
>この記事の一部のテーブルは、Microsoft Defender for Endpointでは使用できない場合があります。 [Microsoft 365 Defenderを有効にして](m365d-enable.md)、より多くのデータ ソースを使用して脅威を検出します。 高度なハンティング クエリをMicrosoft Defender for Endpointから移行するの手順に従って、[高度なハンティング ワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defender](advanced-hunting-migrate-from-mde.md)に移動できます。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出ルール](custom-detection-rules.md)
