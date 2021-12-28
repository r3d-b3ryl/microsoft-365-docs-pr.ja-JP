---
title: 高度なハンティング スキーマの CloudAppEvents テーブル
description: 高度なハンティング スキーマの CloudAppEvents テーブルで、クラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、CloudAppEvents、Defender for Cloud Apps
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
ms.openlocfilehash: daed3fb87aab498cdf91247a59e48af685aed010
ms.sourcegitcommit: 27eb93a7d46bcbb9c948a50b0a8481ffd3832ca0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/28/2021
ms.locfileid: "61612538"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `CloudAppEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Defender for Cloud Apps の対象となるさまざまなクラウド アプリおよびサービスのアクティビティに関する情報が含まれています。 完全なリストについては、「対象のアプリ [とサービス」に移動します](#apps-and-services-covered)。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。 

>[!IMPORTANT]
>この表には、表で使用できる情報が含 `AppFileEvents` まれています。 2021 年 3 月 7 日から、この日付以降のクラウド サービスでファイル関連のアクティビティを検索するユーザーは、代わりにテーブルを `CloudAppEvents` 使用する必要があります。 <br><br>テーブルを引き続き使用するクエリとカスタム検出ルールを検索し、テーブル `AppFileEvents` を使用するために編集 `CloudAppEvents` してください。 影響を受けるクエリの変換に関する詳細なガイダンスについては、「高度な検索を使用したクラウド アプリアクティビティ全体のハントMicrosoft 365 Defender[参照してください](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。


高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類 |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `ApplicationId` | `string` | アプリケーションの一意の識別子 |
| `AccountObjectId` | `string` | アカウントの一意の識別子は、Azure Active Directory |
| `AccountId` | `string` | Microsoft Defender for Cloud Apps が見つけたアカウントの識別子。 ID、Azure Active Directoryプリンシパル名、または他の識別子を使用できます。 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `IsAdminOperation` | `string` | アクティビティが管理者によって実行されたかどうかを示します。 |
| `DeviceType` | `string` | 目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"ワークステーション"、"Server"、"Mobile"、"Gaming console"、"Printer" など) | 
| `OSPlatform` | `string` | デバイスで実行されているオペレーティング システムのプラットフォーム。 この列は、同じファミリ内のバリエーション (Windows 11、Windows 10、Windowsなど) を示します。 |
| `IPAddress` | `string` | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `IsAnonymousProxy` | `string` | IP アドレスが既知の匿名プロキシに属するかどうかを示します。 |
| `CountryCode` | `string` | クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード |
| `City` | `string` | クライアント IP アドレスが地理的に位置付けされている都市 |
| `Isp` | `string` | IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `UserAgent` | `string` | Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報 |
| `ActivityType` | `string` | イベントをトリガーしたアクティビティの種類 |
| `ActivityObjects` | `dynamic` | 記録されたアクティビティに含まれるファイルやフォルダーなどのオブジェクトの一覧 |
| `ObjectName` | `string` | 記録されたアクションが適用されたオブジェクトの名前 |
| `ObjectType` | `string` | 記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど) |
| `ObjectId` | `string` | 記録されたアクションが適用されたオブジェクトの一意の識別子 |
| `ReportId` | `string` | イベントの一意識別子 |
| `RawEventData` | `string` | JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報 |
| `AdditionalFields` | `dynamic` | エンティティまたはイベントに関する追加情報 |
| `AccountType` | `string` | ユーザー アカウントの種類(標準、System、Admin、DcAdmin、System、Application など)の一般的な役割とアクセス レベルを示します。 | 
| `IsExternalUser` | `boolean` | ネットワーク内のユーザーが組織のドメインに属していないかどうかを示します。 | 
| `IsImpersonated` | `boolean` | あるユーザーが別の (偽装された) ユーザーに対してアクティビティを実行したかどうかを示します。 | 
| `IPTags` | `dynamic` | 特定の IP アドレスおよび IP アドレス範囲に適用される顧客定義の情報 | 
| `IPCategory` | `string` | IP アドレスに関する追加情報 | 
| `UserAgentTags` | `dynamic` | Microsoft Defender for Cloud Apps がユーザー エージェント フィールドのタグで提供する詳細。 ネイティブ クライアント、古いブラウザー、古いオペレーティング システム、Robot など、任意の値を指定できます。 | 

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
