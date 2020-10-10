---
title: '[ハント] を使用してエンティティに関する関連情報を取得する'
description: 高度な検索を使用して、エンティティまたはイベントに関する関連情報をすばやくクエリできるようにするために、[ハントの開始] ツールを使用する方法について説明します。
keywords: 高度な検索、インシデント、ピボット、エンティティ、go ハント、関連イベント、脅威の探し、サイバー脅威の検索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e381793caf49318074bcd096e4301cdf49d12e88
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412192"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>ゴーハントを使用してエンティティまたはイベントの情報をすばやく探します。

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

*[ハントハント*] アクションを使用すると、強力なクエリベースの[高度な](advanced-hunting-overview.md)検索機能を使用して、イベントやさまざまなエンティティの種類をすばやく調査できます。 この操作により、選択したイベントまたはエンティティに関する関連情報を検索する高度な検索クエリが自動的に実行されます。

イベントまたはエンティティの詳細が表示されている場合は、セキュリティセンターのさまざまなセクションで [ *ハントの移動* ] アクションを使用できます。 たとえば、 *[ハント* ] を使用するには、次のセクションを参照してください。

- [ [インシデント] ページ](investigate-incidents.md#incident-overview)では、インシデントに関連付けられているユーザー、デバイス、およびその他の多くのエンティティに関する詳細を確認できます。 エンティティを選択すると、その entitity に対して実行できるさまざまなアクションに加えて、追加の情報が得られます。 次の例では、メールボックスが選択されており、メールボックスの詳細と、メールボックスに関する詳細情報を確認するオプションが表示されます。

    ![メールボックスの詳細が表示された状態の [ハント] オプションを含む画像](../../media/mtp-ah/go-hunt-email.png)

- [インシデント] ページでは、[証拠] タブの下にあるエンティティのリストにアクセスすることもできます。これらのエンティティのいずれかを選択すると、そのエンティティに関する情報をすばやく確認するオプションが提供されます。

    ![[証拠] タブの [ハントハント] オプションが選択されたファイルを示す画像](../../media/mtp-ah/go-hunt-evidence-file.png)


- デバイスのタイムラインを表示しているときに、タイムラインでイベントを選択して、そのイベントに関する追加情報を表示することができます。 イベントを選択すると、高度な検索で他の関連イベントを確認するオプションが表示されます。

    ![Go ハントオプションを含むイベントの詳細を示す画像](../../media/mtp-ah/go-hunt-event.png)

エンティティまたはイベントのどちらを選択したかによって、**関連イベントの** **[ハント**の表示] または [ハント] を選択すると、さまざまなクエリが渡されます。

## <a name="query-for-entity-information"></a>エンティティ情報のクエリ
*[ハント*] を使用して、ユーザー、デバイス、またはその他の種類のエンティティに関する情報をクエリに対して実行する場合、クエリはそのエンティティに関連するすべてのイベントについてすべての関連するスキーマテーブルをチェックします。 結果を管理可能な状態に保つために、このクエリは、エンティティに関連し、インシデントに関連付けられている過去30日間の最初のアクティビティと同じ期間に限定されます。

デバイスに対する go ハントクエリの例を次に示します。

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
次のいずれかのエンティティの種類を選択した後、 *[ハント* ] を使用できます。

- Files
- メール
- 電子メールクラスター
- メールボックス
- ユーザー
- デバイス
- IP アドレス
- URL

## <a name="query-for-event-information"></a>イベント情報のクエリ
*[ハント*] を使用して、タイムラインイベントに関する情報をクエリに対して実行すると、選択したイベントの時間の前後にある他のイベントに関する関連するすべてのスキーマテーブルが照会によってチェックされます。 たとえば、次のクエリは、同じデバイス上で同じ期間に発生したさまざまなスキーマテーブルのイベントを一覧表示します。

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
[クエリ言語](advanced-hunting-query-language.md)に関するいくつかの知識があれば、クエリを任意のユーザー設定に変更できます。 たとえば、タイムウィンドウのサイズを決定するこの行を調整できます。

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

クエリを変更して関連性の高い結果を得るだけでなく、次の操作も実行できます。
- [結果をグラフとして表示する](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [カスタム検出ルールを作成する](custom-detection-rules.md)

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [カスタム検出ルール](custom-detection-rules.md)
