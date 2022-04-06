---
title: 高度なハンティング スキーマの CloudAppEvents テーブル
description: 高度なハンティング スキーマの CloudAppEvents テーブルで、クラウド アプリとサービスからのイベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, CloudAppEvents, Defender for Cloud Apps
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 77b4ebd42a8c105340d6d965380aa42b64ae6734
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664966"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

`CloudAppEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Cloud Appsの対象となるさまざまなクラウド アプリとサービスのアクティビティに関する情報が含まれています。 完全な一覧については、 [対象となるアプリとサービス](#apps-and-services-covered)に移動します。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

> [!IMPORTANT]
> この表には、テーブルで使用できる情報が `AppFileEvents` 含まれています。 2021 年 3 月 7 日以降、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを使用する `CloudAppEvents` 必要があります。 <br><br>テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブルを `AppFileEvents` 使用 `CloudAppEvents` するように編集してください。 影響を受けるクエリの変換に関する詳細なガイダンスについては、[高度なハンティングを使用したクラウド アプリアクティビティ全体のハントMicrosoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)参照してください。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類 |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `ApplicationId` | `string` | アプリケーションの一意の識別子 |
| `AccountObjectId` | `string` | Azure Active Directoryのアカウントの一意識別子 |
| `AccountId` | `string` | Microsoft Defender for Cloud Appsによって検出されたアカウントの識別子。 ID、ユーザー プリンシパル名、またはその他の識別子をAzure Active Directoryできます。 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の開始、姓または姓の組み合わせ。 |
| `IsAdminOperation` | `string` | アクティビティが管理者によって実行されたかどうかを示します |
| `DeviceType` | `string` | 目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"サーバー"、"モバイル"、"ゲーム コンソール"、"プリンター" など) |
| `OSPlatform` | `string` | デバイスで実行されているオペレーティング システムのプラットフォーム。 この列は、Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `IPAddress` | `string` | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `IsAnonymousProxy` | `string` | IP アドレスが既知の匿名プロキシに属しているかどうかを示します |
| `CountryCode` | `string` | クライアント IP アドレスが地理的に割り当てられた国を示す 2 文字のコード |
| `City` | `string` | クライアント IP アドレスが地理的に割り当てられた市区町村 |
| `Isp` | `string` | IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `UserAgent` | `string` | Web ブラウザーまたはその他のクライアント アプリケーションからのユーザー エージェント情報 |
| `ActivityType` | `string` | イベントをトリガーしたアクティビティの種類 |
| `ActivityObjects` | `dynamic` | 記録されたアクティビティに関連したオブジェクト (ファイルやフォルダーなど) の一覧 |
| `ObjectName` | `string` | 記録されたアクションが適用されたオブジェクトの名前 |
| `ObjectType` | `string` | 記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど) |
| `ObjectId` | `string` | 記録されたアクションが適用されたオブジェクトの一意の識別子 |
| `ReportId` | `string` | イベントの一意識別子 |
| `RawEventData` | `string` | ソース アプリケーションまたはサービスからの生のイベント情報 (JSON 形式) |
| `AdditionalFields` | `dynamic` | エンティティまたはイベントに関する追加情報 |
| `AccountType` | `string` | 標準、システム、管理者、DcAdmin、システム、アプリケーションなどの一般的なロールとアクセス レベルを示すユーザー アカウントの種類 |
| `IsExternalUser` | `boolean` | ネットワーク内のユーザーが組織のドメインに属していないかどうかを示します |
| `IsImpersonated` | `boolean` | アクティビティが別のユーザー (偽装された) ユーザーに対して実行されたかどうかを示します。 |
| `IPTags` | `dynamic` | 特定の IP アドレスと IP アドレス範囲に適用される顧客定義の情報 |
| `IPCategory` | `string` | IP アドレスに関する追加情報 |
| `UserAgentTags` | `dynamic` | ユーザー エージェント フィールドのタグのMicrosoft Defender for Cloud Appsによって提供される詳細情報。 ネイティブ クライアント、古いブラウザー、古いオペレーティング システム、Robot のいずれかの値を使用できます。 |

## <a name="apps-and-services-covered"></a>対象となるアプリとサービス

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- OneDrive for Business
- Power Automate
- Power BI
- SharePoint Online
- Skype for Business
- Office 365
- Yammer

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
