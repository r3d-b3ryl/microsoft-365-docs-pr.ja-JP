---
title: Microsoft 365 Defender の高度な検索での AssignedIPAddresses() 関数
description: AssignedIPAddresses() 関数を使用して、デバイスに割り当てられた最新の IP アドレスを取得する方法について
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
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
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933020"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な `AssignedIPAddresses()` 検索クエリの [関数を使用](advanced-hunting-overview.md) して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。 timestamp 引数を指定すると、この関数は指定した時刻に最新の IP アドレスを取得します。 

この関数は、次の列を含むテーブルを返します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| `Timestamp` | 日付型 | IP アドレスを使用してデバイスが確認された最新時刻 |
| `IPAddress` | string | デバイスで使用される IP アドレス |
| `IPType` | string | IP アドレスがパブリック アドレスかプライベート アドレスかを示します。 |
| `NetworkAdapterType` | int | IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。 使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | 割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびそれがインターネットに一般に接続されていることを示すフラグが含まれる |

## <a name="syntax"></a>構文

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引数

- **x**— `DeviceId` または `DeviceName` デバイスを識別する値
- **y**— 特定の時刻から割り当てられた最新の IP アドレスを取得するように関数に指示する `Timestamp` (datetime) 値。 指定しない場合、関数は最新の IP アドレスを返します。

## <a name="examples"></a>例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>24 時間前にデバイスで使用された IP アドレスの一覧を取得する

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>デバイスで使用される IP アドレスを取得し、デバイスと通信しているデバイスを検索する
このクエリは、この関数を使用して、特定の日付 ( ) 以前のデバイス ( ) の割り当てられた IP アドレス `AssignedIPAddresses()` `example-device-name` を取得します `example-date` 。 その後、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。 

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
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
