---
title: 高度なハンティング スキーマの DeviceInfo テーブル
description: 高度なハンティング スキーマの DeviceInfo テーブルで、OS、コンピューター名、およびその他のマシン情報について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, machineinfo, DeviceInfo, デバイス, マシン, OS, プラットフォーム, ユーザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 1808e0fa69f1ea683986b534a88b93e9e4a53af0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482650"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

`DeviceInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、OS バージョン、アクティブ ユーザー、コンピューター名など、組織内のデバイスに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `DeviceId` | `string` | コンピューターの一意識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | `string` | コンピューターで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | `string` | オンボードされたマシンが Microsoft Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 これは、マシン自体、NAT デバイス、またはプロキシの IP アドレスである可能性があります。 |
| `OSArchitecture` | `string` | コンピューターで実行されているオペレーティング システムのアーキテクチャです。 |
| `OSPlatform` | `string` | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSBuild` | `string` | コンピューターで実行されているオペレーティング システムのビルド バージョン |
| `IsAzureADJoined` | `boolean` | マシンが Azure Active Directory に参加しているかどうかを示すブールインジケーター |
| `AadDeviceId` | `string` | Azure AD のデバイスの一意の識別子 |
| `LoggedOnUsers` | `string` | イベント発生時にマシンにログオンしているすべてのユーザーの一覧 (JSON 配列形式) |
| `RegistryDeviceTag` | `string` | レジストリを介して追加されたマシン タグ |
| `OSVersion` | `string` | コンピューターで実行されているオペレーティング システムのバージョンです。 |
| `MachineGroup` | `string` | マシンのマシン グループ。 このグループは、ロールベースのアクセス制御によってマシンへのアクセスを決定するために使用されます |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `OnboardingStatus` | `string` | デバイスが現在オンボードされているか、Microsoft Defender for Endpointされていないか、デバイスがサポートされていないかどうかを示します。 |
|`AdditionalFields` | `string` | JSON 配列形式のイベントに関する追加情報 |
|`DeviceCategory` | `string` | 特定のデバイスの種類を次のカテゴリにグループ化する広範な分類: エンドポイント、ネットワーク デバイス、IoT、不明 |
|`DeviceType` | `string` | ネットワーク デバイス、ワークステーション、サーバー、モバイル、ゲーム コンソール、プリンターなど、目的と機能に基づくデバイスの種類 |
|`DeviceSubType` | `string` | モバイル デバイスは、タブレットやスマートフォンなど、特定の種類のデバイスの追加修飾子です。デバイス検出でこの属性に関する十分な情報が見つかる場合にのみ使用できます |
|`Model` | `string` | ベンダーまたは製造元からの製品のモデル名または番号。デバイス検出でこの属性に関する十分な情報が見つかる場合にのみ使用できます |
|`Vendor` | `string` | デバイス検出でこの属性に関する十分な情報が見つかる場合にのみ使用できる、製品ベンダーまたは製造元の名前 |
|`OSDistribution` | `string` | Ubuntu や RedHat for Linux プラットフォームなどの OS プラットフォームの配布 |
|`OSVersionInfo` | `string` | 一般的な名前、コード名、バージョン番号など、OS バージョンに関する追加情報 |
|`MergedDeviceIds` | `string` | 同じデバイスに割り当てられている以前のデバイス ID |
|`MergedToDeviceId` | `string` | デバイスに割り当てられた最新のデバイス ID |

この表は `DeviceInfo` 、デバイスからの定期的なレポートまたはシグナルであるハートビートに基づくデバイス情報を提供します。 15 分ごとに、デバイスは、頻繁に変化する属性 `LoggedOnUsers`(. 1 日に 1 回、デバイスの属性を含む完全なハートビートが送信されます。

次のサンプル クエリを使用して、デバイスの最新の状態を取得できます。

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
