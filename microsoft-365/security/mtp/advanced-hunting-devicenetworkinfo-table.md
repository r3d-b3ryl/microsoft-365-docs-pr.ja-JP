---
title: 高度な検索スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machinenetworkinfo、DeviceNetworkInfo、device、machine、mac、ip、adapter、dns、dhcp、gateway、tunnel
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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197075"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection



`DeviceNetworkInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、ネットワークアダプター、IP アドレスと MAC アドレス、および接続されたネットワークまたはドメインなど、マシンのネットワーク構成に関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | コンピューターの一意識別子 |
| `DeviceName` | 文字列 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 |
| `NetworkAdapterName` | 文字列 | ネットワークアダプターの名前 |
| `MacAddress` | 文字列 | ネットワークアダプターの MAC アドレス |
| `NetworkAdapterType` | 文字列 | ネットワークアダプターの種類。 可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)を参照してください。 |
| `NetworkAdapterStatus` | 文字列 | ネットワークアダプターの動作状態。 可能な値については、[この列挙型](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)を参照してください。 |
| `TunnelType` | 文字列 | トンネリングプロトコル (6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) にインターフェイスが使用されている場合 |
| `ConnectedNetworks` | 文字列 | アダプターが接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベートまたはドメイン)、説明、およびインターネットにパブリックに接続されているかどうかを示すフラグが含まれています。 |
| `DnsAddresses` | 文字列 | JSON 配列形式の DNS サーバーアドレス |
| `IPv4Dhcp` | 文字列 | DHCP サーバーの IPv4 アドレス |
| `IPv6Dhcp` | 文字列 | DHCP サーバーの IPv6 アドレス |
| `DefaultGateways` | 文字列 | JSON 配列形式の既定のゲートウェイアドレス |
| `IPAddresses` | 文字列 | アダプターに割り当てられたすべての IP アドレスと、それぞれのサブネットプレフィックスと IP アドレス空間 (パブリック、プライベート、リンクローカルなど) を含む JSON 配列。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
