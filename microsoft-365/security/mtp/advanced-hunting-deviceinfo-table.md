---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルにある OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、machineinfo、DeviceInfo、デバイス、コンピューター、OS、プラットフォーム、ユーザー
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
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931280"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `DeviceInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のコンピューターに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | string | コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | string | オンボードしたコンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 コンピューター自体の IP アドレス、NAT デバイス、プロキシなどです。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSBuild` | string | コンピューターで実行されているオペレーティング システムのビルド バージョン |
| `IsAzureADJoined` | ブール値 | コンピューターが Azure Active Directory に参加しているかどうかを示すブールインジケーター |
| `LoggedOnUsers` | string | イベントの時点でコンピューターにログオンしているすべてのユーザーの一覧 (JSON 配列形式) |
| `RegistryDeviceTag` | string | レジストリを介して追加されたコンピューター タグ |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `MachineGroup` | string | コンピューターのコンピューター グループ。 このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
