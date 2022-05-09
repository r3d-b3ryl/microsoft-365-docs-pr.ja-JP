---
title: 高度なMicrosoft 365 Defenderのハンティングにおける AssignedIPAddresses() 関数
description: AssignedIPAddresses() 関数を使用して、デバイスに割り当てられた最新の IP アドレスを取得する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, FileProfile, ファイル プロファイル, 関数, エンリッチメント
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b82a079a476ee6ed3d5465b52bca381cd49746b5
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530914"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`AssignedIPAddresses()` [高度なハンティング](advanced-hunting-overview.md) クエリの関数を使用して、デバイスに割り当てられている最新の IP アドレスをすばやく取得します。 timestamp 引数を指定した場合、この関数は指定した時刻に最新の IP アドレスを取得します。 

この関数は、次の列を含むテーブルを返します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| `Timestamp` | `datetime` | IP アドレスを使用してデバイスが観察された最新時刻 |
| `IPAddress` | `string` | デバイスで使用される IP アドレス |
| `IPType` | `string` | IP アドレスがパブリック アドレスかプライベート アドレスかを示します。 |
| `NetworkAdapterType` | `int` | IP アドレスが割り当てられているデバイスで使用されるネットワーク アダプターの種類。 使用可能な値については、 [この列挙体を参照してください。](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | `int` | 割り当てられた IP アドレスを持つアダプターが接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。 |

## <a name="syntax"></a>構文

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引数

- **x**-`DeviceId` または `DeviceName` デバイスを識別する値
- **y**-`Timestamp` 特定の時刻から最新の割り当て IP アドレスを取得するように関数に指示する (datetime) 値。 指定しない場合、関数は最新の IP アドレスを返します。

## <a name="examples"></a>例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>24 時間前にデバイスによって使用された IP アドレスの一覧を取得する

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>デバイスで使用される IP アドレスを取得し、デバイスと通信しているデバイスを見つける
このクエリでは、この関数を `AssignedIPAddresses()` 使用して、特定の日付 () 以前のデバイスに`example-device-name`割り当てられた IP アドレスを`example-date`取得します。 次に、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。 

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