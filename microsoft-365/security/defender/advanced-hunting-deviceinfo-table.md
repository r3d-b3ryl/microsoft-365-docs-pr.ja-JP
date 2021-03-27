---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、machineinfo、DeviceInfo、デバイス、コンピューター、OS、プラットフォーム、ユーザー
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d56710f4933a8971230c78d7b3570f14b9bda335
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382627"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | コンピューターの一意識別子 |
| `DeviceName` | 文字列 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | 文字列 | コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | 文字列 | オンボード コンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 これは、コンピューター自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `OSPlatform` | 文字列 | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSBuild` | 文字列 | コンピューターで実行されているオペレーティング システムのバージョンをビルドする |
| `IsAzureADJoined` | boolean | コンピューターが Azure Active Directory に参加するかどうかを示すブール値インジケーター |
| `AadObjectId` | 文字列 | Azure のデバイスの一意の識別子AD |
| `LoggedOnUsers` | 文字列 | JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧 |
| `RegistryDeviceTag` | 文字列 | レジストリを介して追加されたコンピューター タグ |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `MachineGroup` | string | コンピューターのコンピューター グループ。 このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
|`AdditionalFields` | 文字列 | JSON 配列形式のイベントに関する追加情報 |

この表は、定期的なレポートまたはデバイスからの信号であるハートビートに基づくデバイス `DeviceInfo` 情報を提供します。 15 分ごとに、デバイスは頻繁に変更される属性を含む部分的なハートビートを送信します `LoggedOnUsers` 。 1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。

次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
