---
title: Go Hunt を使用してエンティティに関する関連情報を取得する
description: 高度な検索を使用してエンティティまたはイベントに関する関連情報をすばやく照会するために、移動ハント ツールを使用する方法について学習します。
keywords: 高度な捜索、インシデント、ピボット、エンティティ、移動ハント、関連イベント、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
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
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929507"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Go Hunt を使用してエンティティまたはイベント情報をすばやく検索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Go *Hunt アクションを使用* すると、強力なクエリ ベースの高度なハンティング機能を使用して、イベントやさまざまなエンティティの種類をすばやく [調査](advanced-hunting-overview.md) できます。 このアクションは、高度な検索クエリを自動的に実行して、選択したイベントまたはエンティティに関する関連情報を検索します。

Go *Hunt* アクションは、イベントまたはエンティティの詳細が表示されるたびに、セキュリティ センターのさまざまなセクションで使用できます。 たとえば、次のセクションの *go ハント* を使用できます。

- インシデント ページ [では、](investigate-incidents.md#incident-overview)ユーザー、デバイス、およびインシデントに関連付けられている他の多くのエンティティに関する詳細を確認できます。 エンティティを選択すると、追加情報と、そのエンティティに対して実行できるさまざまなアクションが表示されます。 次の例では、メールボックスが選択され、メールボックスに関する詳細と、メールボックスに関する詳細を検索するオプションが表示されます。

    ![移動ハント オプションを使用したメールボックスの詳細を示す画像](../../media/mtp-ah/go-hunt-email.png)

- インシデント ページでは、[エビデンス] タブの下にあるエンティティの一覧にアクセスすることもできます。これらのエンティティの 1 つを選択すると、そのエンティティに関する情報をすばやく検索できます。

    ![[エビデンス] タブの [Go Hunt] オプションを使用して選択したファイルを示す画像](../../media/mtp-ah/go-hunt-evidence-file.png)


- デバイスのタイムラインを表示する場合は、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示できます。 イベントを選択すると、高度な検索で他の関連するイベントを探すオプションが表示されます。

    ![Go Hunt オプションを使用したイベントの詳細を示す画像](../../media/mtp-ah/go-hunt-event.png)

関連する **イベントの検索****またはハント** を選択すると、エンティティまたはイベントが選択されたかどうかに応じて、異なるクエリが渡されます。

## <a name="query-for-entity-information"></a>エンティティ情報のクエリ
ユーザー、 *デバイス、その* 他の種類のエンティティに関する情報を検索するために移動ハントを使用する場合、クエリは関連するすべてのスキーマ テーブルで、そのエンティティに関連するすべてのイベントをチェックします。 結果を管理可能な状態に保つために、クエリの対象範囲は、エンティティを含み、インシデントに関連付けられた過去 30 日間の最初のアクティビティと同じ時間です。

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
### <a name="supported-entity-types"></a>サポートされるエンティティの種類
次のエンティティ *の種類を選択* した後で、移動ハントを使用できます。

- ファイル
- メール
- メール クラスター
- メールボックス
- ユーザー
- デバイス
- IP アドレス
- URL

## <a name="query-for-event-information"></a>イベント情報のクエリ
タイムライン イベント *に関する* 情報を検索するために移動ハントを使用する場合、クエリは、選択したイベントの時刻に関連するすべてのスキーマ テーブルで他のイベントをチェックします。 たとえば、次のクエリは、同じデバイスで同じ期間に発生したさまざまなスキーマ テーブルのイベントを一覧表示します。

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
クエリ言語に関する知識 [がある](advanced-hunting-query-language.md)場合は、クエリを好みに合わせて調整できます。 たとえば、この行を調整して、タイム ウィンドウのサイズを決定できます。

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

より関連性の高い結果を得るクエリを変更する以外に、次の方法も実行できます。
- [結果をグラフとして表示する](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [カスタム検出ルールを作成する](custom-detection-rules.md)

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出ルール](custom-detection-rules.md)
