---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度なハンティング スキーマの AppFileEvents テーブルで、クラウド アプリとサービスに関連付けられているファイル関連のイベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、AppFileEvents、Cloud App Security、MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b8b3b34e1b8535772d19f8ddd9f52c5c0a89292b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499347"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `AppFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Cloud App Security によって監視されるクラウド アプリおよびサービスにおけるファイル関連のアクティビティに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!WARNING]
>このテーブルは近日廃止されます。 2021 年 3 月 7 日現在、テーブル `AppFileEvents` はレコードをログに記録しなくなりました。 クラウド サービスのファイル関連のアクティビティを検索するユーザーは、その日付以降に、 [代わりに CloudAppEvents](advanced-hunting-cloudappevents-table.md) テーブルを使用する必要があります。 <br><br>テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。 影響を受けるクエリの変換に関する詳細なガイダンスについては [、「Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)Advanced hunting を使用したクラウド アプリアクティビティ全体のハント」を参照してください。


高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `PreviousFileName` | 文字列 | アクションの結果として名前が変更されたファイルの元の名前 |
| `PreviousFolderPath` | 文字列 | 記録されたアクションが適用される前のファイルを含む元のフォルダー |
| `Protocol` | 文字列 | 使用されるネットワーク プロトコル |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `AccountSid` | 文字列 | アカウントのセキュリティ識別子 (SID) |
| `AccountUpn` | 文字列 | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountObjectId` | 文字列 | Azure アカウントのアカウントの一意AD |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | 文字列 | デバイスの種類 | 
| `OSPlatform` | 文字列 | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | 文字列 | 通信中に使用される TCP ポート  |
| `DestinationDeviceName` | 文字列 | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | 文字列 | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | 文字列 | 関連するネットワーク通信の宛先ポート |
| `Location` | 文字列 | イベントに関連付けられている都市、国、その他の地理的な場所 |
| `Isp` | 文字列 | エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関する追加情報 |

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
