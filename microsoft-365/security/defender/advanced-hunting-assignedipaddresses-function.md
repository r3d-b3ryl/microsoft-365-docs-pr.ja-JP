---
title: アプリケーションの高度な検索で AssignedIPAddresses() Microsoft 365 Defender
description: AssignedIPAddresses() 関数を使用してデバイスに割り当てられた最新の IP アドレスを取得する方法について学習する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
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
ms.openlocfilehash: d3ebd301d6c79bf5286d9293e04e4073b99d1e35
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211973"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な `AssignedIPAddresses()` 検索クエリの [関数を](advanced-hunting-overview.md) 使用して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。 タイムスタンプ引数を指定すると、指定した時刻に最新の IP アドレスが取得されます。 

この関数は、次の列を持つテーブルを返します。

| 列 | データ型 | 説明 |
|------------|-------------|-------------|
| `Timestamp` | 日付型 | IP アドレスを使用してデバイスが観察された最新の時刻 |
| `IPAddress` | string | デバイスで使用される IP アドレス |
| `IPType` | string | IP アドレスがパブリック アドレスかプライベート アドレスかを示します。 |
| `NetworkAdapterType` | int | IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。 使用できる値については、この列挙 [を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれる |

## <a name="syntax"></a>構文

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引数

- **x**— `DeviceId` または `DeviceName` デバイスを識別する値
- **y**— 特定の時刻から最新の割り当てられた IP アドレスを取得するように関数に指示する `Timestamp` (datetime) 値。 指定しない場合、関数は最新の IP アドレスを返します。

## <a name="examples"></a>例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>24 時間前にデバイスで使用される IP アドレスの一覧を取得する

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>デバイスで使用される IP アドレスを取得し、デバイスと通信するデバイスを検索する
このクエリでは、この関数を使用して、デバイス ( ) の割り当てられた IP アドレスを、特定の日付 ( ) のオンまたは前 `AssignedIPAddresses()` `example-device-name` に取得します `example-date` 。 次に、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)