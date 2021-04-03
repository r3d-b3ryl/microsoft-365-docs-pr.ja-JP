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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500831"
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
| `DeviceId` | 文字列 | サービス内のデバイスの一意の識別子 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `ClientVersion` | 文字列 | デバイスで実行されているエンドポイント エージェントまたはセンサーのバージョン |
| `PublicIP` | 文字列 | オンボード デバイスが Defender for Endpoint サービスに接続するために使用するパブリック IP アドレス。 これは、デバイス自体の IP アドレス、NAT デバイス、またはプロキシである可能性があります。 |
| `OSArchitecture` | 文字列 | デバイスで実行されているオペレーティング システムのアーキテクチャ |
| `OSPlatform` | 文字列 | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `OSBuild` | 文字列 | デバイスで実行されているオペレーティング システムのバージョンをビルドする |
| `IsAzureADJoined` | boolean | デバイスが Azure Active Directory に参加するかどうかを示すブール値インジケーター |
| `LoggedOnUsers` | 文字列 | JSON 配列形式のイベント時にデバイスにログオンしているすべてのユーザーの一覧 |
| `RegistryDeviceTag` | 文字列 | レジストリを介して追加されたデバイス タグ |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `OSVersion` | 文字列 | デバイスで実行されているオペレーティング システムのバージョン |
| `MachineGroup` | 文字列 | コンピューターのコンピューター グループ。 このグループは、役割ベースのアクセス制御によってコンピューターへのアクセスを決定するために使用されます。 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
