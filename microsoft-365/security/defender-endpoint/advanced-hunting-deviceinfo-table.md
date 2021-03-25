---
title: 高度な検索スキーマの DeviceInfo テーブル
description: 高度な検索スキーマの DeviceInfo テーブルで、OS、コンピューター名、その他のデバイス情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、deviceinfo、deviceinfo、デバイス、OS、プラットフォーム、ユーザー、DeviceInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067067"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度 `DeviceInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、組織内のデバイスに関する情報 (OS バージョン、アクティブ ユーザー、コンピューター名など) が含まれている。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | string | デバイスで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | string | オンボード デバイスが Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 これは、デバイス自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。 |
| `OSArchitecture` | string | デバイスで実行されているオペレーティング システムのアーキテクチャ |
| `OSPlatform` | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSBuild` | string | デバイスで実行されているオペレーティング システムのバージョンをビルドする |
| `IsAzureADJoined` | boolean | デバイスが Azure Active Directory に参加するかどうかを示すブール値インジケーター |
| `LoggedOnUsers` | string | JSON 配列形式のイベント時にデバイスにログオンしているすべてのユーザーの一覧 |
| `RegistryDeviceTag` | string | レジストリを介して追加されたデバイス タグ |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `OSVersion` | string | デバイスで実行されているオペレーティング システムのバージョン |
| `MachineGroup` | string | コンピューターのコンピューター グループ。 このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
