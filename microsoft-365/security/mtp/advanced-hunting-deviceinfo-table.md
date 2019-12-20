---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルにある OS、コンピューター名、およびその他のマシン情報について説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の探し、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machineinfo、DeviceInfo、device、machine、OS、プラットフォーム、ユーザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1141447de9b7ac714fb200dab56c4c2e8d75a05d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809355"
---
# <a name="deviceinfo"></a>DeviceInfo

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceInfo` [高度な](advanced-hunting-overview.md)検索スキーマの表には、OS のバージョン、アクティブなユーザー、コンピューター名など、組織内のコンピューターに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | コンピューターの一意識別子 |
| `DeviceName` | 文字列型 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | 文字列型 | コンピューター上で実行されているエンドポイントエージェントまたはセンサーのバージョン |
| `PublicIP` | 文字列型 | Microsoft Defender ATP サービスに接続するために利用コンピューターによって使用されるパブリック IP アドレス。 これは、マシン自体、NAT デバイス、またはプロキシの IP アドレスである場合があります。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティングシステムを示します。 |
| `OSBuild` | 文字列型 | コンピューター上で実行されているオペレーティングシステムのビルドバージョン |
| `IsAzureADJoined` | ブール型 | コンピューターが Azure Active Directory に参加しているかどうかを示すブール値のインジケーター |
| `LoggedOnUsers` | 文字列型 | JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧 |
| `RegistryDeviceTag` | 文字列型 | レジストリに追加されたコンピュータータグ |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `MachineGroup` | string | コンピューターのコンピューターグループ。 このグループは、役割ベースのアクセス制御によって、コンピューターへのアクセスを決定するために使用されます。 |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)