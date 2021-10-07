---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のコンピューター情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、machineinfo、DeviceInfo、デバイス、コンピューター、OS、プラットフォーム、ユーザー
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2e71699e35339fe6fcf81b9eeaa93e84737e026d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190427"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | string | コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | string | オンボード コンピューターが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 これは、コンピューター自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。 |
| `OSArchitecture` | string | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、特定のオペレーティング システム (同じファミリ内のバリエーション (Windows 11、Windows 10、Windows 7 など) を示します。 |
| `OSBuild` | string | コンピューターで実行されているオペレーティング システムのバージョンをビルドする |
| `IsAzureADJoined` | ブール値 | コンピューターがコンピューターに参加しているかどうかを示すブールAzure Active Directory |
| `AadObjectId` | string | Azure のデバイスの一意の識別子AD |
| `LoggedOnUsers` | string | JSON 配列形式のイベント時にコンピューターにログオンしているすべてのユーザーの一覧 |
| `RegistryDeviceTag` | string | レジストリを介して追加されたコンピューター タグ |
| `OSVersion` | string | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `MachineGroup` | string | コンピューターのコンピューター グループ。 このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `OnboardingStatus` | string | デバイスが現在オンボードされているかどうかを示す Microsoft Defender For Endpoint またはデバイスがサポートされていない場合 |
|`AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |
|`DeviceCategory` | string | 特定のデバイスの種類を次のカテゴリにグループ化する広範な分類: エンドポイント、ネットワーク デバイス、IoT、不明 |
|`DeviceType` | string | 目的と機能に基づくデバイスの種類 (ネットワーク デバイス、ワークステーション、サーバー、モバイル、ゲーム コンソール、プリンターなど) |
|`DeviceSubType` | string | 特定の種類のデバイスの追加修飾子 (たとえば、モバイル デバイスはタブレットまたはスマートフォンなど) |
|`Model` | string | ベンダーまたは製造元の製品のモデル名または番号 |
|`Vendor` | string | 製品ベンダーまたは製造元の名前 |
|`OSDistribution` | string | Linux プラットフォーム用の Ubuntu や RedHat などの OS プラットフォームの配布 |
|`OSVersionInfo` | string | OS バージョンに関する追加情報 (一般的な名前、コード名、バージョン番号など) |
|`MergedDeviceIds` | string | 同じデバイスに割り当てられている以前のデバイス ID |
|`MergedToDeviceId` | string | デバイスに割り当てられた最新のデバイス ID |

この表は、定期的なレポートまたはデバイスからの信号であるハートビートに基づくデバイス `DeviceInfo` 情報を提供します。 15 分ごとに、デバイスは頻繁に変更される属性を含む部分的なハートビートを送信します `LoggedOnUsers` 。 1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。

次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
