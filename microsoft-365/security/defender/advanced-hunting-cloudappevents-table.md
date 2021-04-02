---
title: 高度なハンティング スキーマの CloudAppEvents テーブル
description: 高度なハンティング スキーマの CloudAppEvents テーブルで、クラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、CloudAppEvents、CloudAppEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498673"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `CloudAppEvents` な検索スキーマ[](advanced-hunting-overview.md)の表には、Microsoft Cloud App Security (特に Dropbox、Exchange Online、OneDrive、Microsoft Teams、SharePoint) でカバーされるさまざまなクラウド アプリとサービスのアクティビティに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!IMPORTANT]
>この表には、表で使用できる情報が含 `AppFileEvents` まれています。 2021 年 3 月 7 日から、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを `CloudAppEvents` 使用する必要があります。 <br><br>テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。 影響を受けるクエリの変換に関する詳細なガイダンスについては [、「Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)Advanced hunting を使用したクラウド アプリアクティビティ全体のハント」を参照してください。


高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `ApplicationId` | 文字列 | アプリケーションの一意の識別子 |
| `AccountObjectId` | 文字列 | Azure Active Directory のアカウントの一意識別子 |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `IsAdminOperation` | 文字列 | アクティビティが管理者によって実行されたかどうかを示します。 |
| `DeviceType` | 文字列 | 目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"Server"、"Mobile"、"Gaming console"、"Printer" など) | 
| `OSPlatform` | 文字列 | デバイスで実行されているオペレーティング システムのプラットフォーム。 この列は、同じファミリ内のバリエーション (Windows 10 や Windows 7 など) を含む特定のオペレーティング システムを示します。 |
| `IPAddress` | 文字列 | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `IsAnonymousProxy` | 文字列 | IP アドレスが既知の匿名プロキシに属するかどうかを示します。 |
| `CountryCode` | 文字列 | クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード |
| `City` | 文字列 | クライアント IP アドレスが地理的に位置付けされている都市 |
| `Isp` | 文字列 | IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `UserAgent` | 文字列 | Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報 |
| `ActivityType` | 文字列 | イベントをトリガーしたアクティビティの種類 |
| `ActivityObjects` | 文字列 | 記録されたアクティビティに含まれるファイルやフォルダーなどのオブジェクトの一覧 |
| `ObjectName` | 文字列 | 記録されたアクションが適用されたオブジェクトの名前 |
| `ObjectType` | 文字列 | 記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど) |
| `ObjectId` | 文字列 | 記録されたアクションが適用されたオブジェクトの一意の識別子 |
| `ReportId` | 文字列 | イベントの一意識別子 |
| `RawEventData` | 文字列 | JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関する追加情報 |


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
