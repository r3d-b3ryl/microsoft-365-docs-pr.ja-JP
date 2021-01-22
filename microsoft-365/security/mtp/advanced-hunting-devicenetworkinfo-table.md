---
title: 高度な検索スキーマの DeviceNetworkInfo テーブル
description: 高度な検索スキーマの DeviceNetworkInfo テーブルのネットワーク構成情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、machinenetworkinfo、DeviceNetworkInfo、デバイス、コンピューター、mac、ip、アダプター、dns、dhcp、ゲートウェイ、トンネル
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931208"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `DeviceNetworkInfo` な検索スキーマ[](advanced-hunting-overview.md)の表には、ネットワーク アダプター、IP アドレスと MAC アドレス、接続されたネットワークまたはドメインなど、コンピューターのネットワーク構成に関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `NetworkAdapterName` | string | ネットワーク アダプターの名前 |
| `MacAddress` | string | ネットワーク アダプターの MAC アドレス |
| `NetworkAdapterType` | string | ネットワーク アダプターの種類。 使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | ネットワーク アダプターの動作状態。 使用できる値については、この列挙を [参照してください。](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | トンネリング プロトコル (この目的でインターフェイスを使用する場合(6to4、Teredo、ISATAP、PPTP、SSTP、SSH など) |
| `ConnectedNetworks` | string | アダプターが接続されているネットワーク。 各 JSON 配列には、ネットワーク名、カテゴリ (パブリック、プライベート、またはドメイン)、説明、およびそれがインターネットに一般に接続されていることを示すフラグが含まれる |
| `DnsAddresses` | string | JSON 配列形式の DNS サーバー アドレス |
| `IPv4Dhcp` | string | DHCP サーバーの IPv4 アドレス |
| `IPv6Dhcp` | string | DHCP サーバーの IPv6 アドレス |
| `DefaultGateways` | string | JSON 配列形式の既定のゲートウェイ アドレス |
| `IPAddresses` | string | アダプターに割り当てられているすべての IP アドレスと、それぞれのサブネット プレフィックスと IP アドレス スペース (パブリック、プライベート、リンク ローカルなど) を含む JSON 配列 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
