---
title: go hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやくクエリするために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な狩猟、インシデント、ピボット、エンティティ、go hunt、関連イベント、脅威ハンティング、サイバー脅威ハンティング、検索、クエリ、テレメトリ、Microsoft 365、Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dba2bacc170163f37e8bf7e8dbb2c4b9b6474d93
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59163686"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>go hunt を使用してエンティティまたはイベント情報をすばやく検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類 [をすばやく調査](advanced-hunting-overview.md) できます。 このアクションでは、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。

go *hunt アクション* は、イベントまたはエンティティの詳細が表示されるたびに、セキュリティ センターのさまざまなセクションで使用できます。 たとえば、次のセクション *から go hunt* を使用できます。

- インシデント ページ [では、](investigate-incidents.md#summary)インシデントに関連付けられているユーザー、デバイス、その他多くのエンティティに関する詳細を確認できます。 エンティティを選択すると、追加の情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。 次の例では、メールボックスが選択され、メールボックスに関する詳細と、メールボックスの詳細を検索するオプションが表示されます。

    ![移動ハント オプションを使用してメールボックスの詳細を示す画像。](../../media/mtp-ah/go-hunt-email.png)

- インシデント ページでは、[証拠] タブの下のエンティティの一覧にアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく検索できます。

    ![[証拠] タブの [移動ハント] オプションを使用して選択したファイルを示す画像。](../../media/mtp-ah/go-hunt-evidence-file.png)


- デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。 イベントを選択すると、高度な検索で他の関連イベントを探すオプションが表示されます。

    ![Go ハント オプションを使用してイベントの詳細を示す画像。](../../media/mtp-ah/go-hunt-event.png)

関連イベント **に対して** [Go hunt] または **[ハント** ] を選択すると、エンティティまたはイベントを選択したかどうかに応じて、さまざまなクエリが渡されます。

## <a name="query-for-entity-information"></a>エンティティ情報のクエリ
ユーザー、 *デバイス、その* 他の種類のエンティティに関する情報を検索するために移動ハントを使用する場合、クエリは関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックします。 結果を管理可能に保つために、クエリの対象範囲は、エンティティを含み、インシデントに関連付けられた過去 30 日間の最も早いアクティビティと同じ期間です。

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
次のエンティティ *の種類を選択* した後で、go hunt を使用できます。

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
>この記事の一部のテーブルは、Microsoft Defender for Endpoint では使用できない場合があります。 [複数のデータ Microsoft 365 Defender](m365d-enable.md)を使用して脅威を検出するには、このオプションをオンにしてください。 高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動するには、「Advanced Hunting [queries](advanced-hunting-migrate-from-mde.md)を Microsoft Defender for Endpoint から移行する」の手順に従います。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出ルール](custom-detection-rules.md)
