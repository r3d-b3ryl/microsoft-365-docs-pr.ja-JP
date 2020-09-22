---
title: AssignedIPAddresses () 関数の詳細については、「Microsoft の脅威保護」をお探しください。
description: AssignedIPAddresses () 関数を使用して、デバイスに割り当てられている最新の IP アドレスを取得する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、FileProfile、file profile、function、エンリッチメント
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 685132e3f5c303f21fde3702725a84e24383e679
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198249"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

関数を使用して、 `AssignedIPAddresses()` デバイスに割り当てられている最新の IP アドレスをすばやく取得します。 Timestamp 引数を指定すると、この関数は指定された時刻に最新の IP アドレスを取得します。 

この関数は、次の列を持つテーブルを返します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| `Timestamp` | 日付型 | デバイスが IP アドレスを使用して観測された最新時刻 |
| `IPAddress` | 文字列 | デバイスによって使用される IP アドレス |
| `IPType` | 文字列 | IP アドレスがパブリックまたはプライベートアドレスであるかどうかを示します |
| `NetworkAdapterType` | int | IP アドレスが割り当てられているデバイスによって使用されるネットワークアダプターの種類。 可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)を参照してください。 |
| `ConnectedNetworks` | int | 割り当てられた IP アドレスを持つアダプターがに接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。 |

## <a name="syntax"></a>構文

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>引数

- **x** `DeviceId` または `DeviceName` デバイスを識別する値
- **y**- `Timestamp` (datetime) 値は、指定した時刻から最新の IP アドレスを取得するように関数に指示します。 指定しない場合、関数は最新の IP アドレスを返します。

## <a name="examples"></a>例

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>デバイスによって使用される IP アドレスの一覧を取得する24時間前

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>デバイスによって使用される IP アドレスを取得し、それと通信するデバイスを検出する
このクエリは、関数を使用して、 `AssignedIPAddresses()` デバイス () に割り当てられている IP アドレスを `example-device-name` 特定の日付 () に対して取得 `example-date` します。 その後、IP アドレスを使用して、他のデバイスによって開始されたデバイスへの接続を検索します。 

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
