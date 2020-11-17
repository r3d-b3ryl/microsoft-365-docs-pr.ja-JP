---
title: 高度な検索スキーマの CloudAppEvents テーブル
description: 高度な検索スキーマの CloudAppEvents テーブルにあるクラウドアプリおよびサービスからのイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、CloudAppEvents、Cloud App Security、MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087772"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

現在プレビューで利用可能ですが、 `CloudAppEvents` [高度な](advanced-hunting-overview.md) 検索スキーマの表には、さまざまなクラウドアプリおよびサービスのアクティビティに関する情報、特に Microsoft Teams と Exchange Online が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

この表を拡張して、Microsoft Cloud App Security によって監視されるアクティビティを増やします。 最終的に、この表には [Appfileevents](advanced-hunting-appfileevents-table.md) テーブルに現在格納されているファイルアクティビティが含まれます。 Microsoft は、この表へのデータの移動に関する追加のガイダンスを提供します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `ApplicationId` | string | アプリケーションの一意識別子 |
| `AccountObjectId` | string | Azure Active Directory のアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `IsAdminOperation` | string | アクティビティが管理者によって実行されたかどうかを示します。 |
| `DeviceType` | string | 目的と機能に基づいたデバイスの種類 ("ネットワークデバイス"、"ワークステーション"、"サーバー"、"モバイル"、"ゲームコンソール"、"プリンター" など) | 
| `OSPlatform` | string | デバイス上で実行されているオペレーティングシステムのプラットフォーム。 この列は、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティングシステムを示しています。 |
| `IPAddress` | string | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `IsAnonymousProxy` | string | IP アドレスが既知の匿名プロキシに属するかどうかを示します |
| `CountryCode` | string | クライアント IP アドレスが geolocated する国を示す2文字のコード |
| `City` | string | クライアント IP アドレスが geolocated する市区町村 |
| `Isp` | string | IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP) |
| `UserAgent` | string | Web ブラウザーまたは他のクライアントアプリケーションからのユーザーエージェント情報 |
| `ActivityType` | string | イベントをトリガーしたアクティビティの種類 |
| `ActivityObjects` | string | 記録されたアクティビティに関係したオブジェクト (ファイルまたはフォルダーなど) のリスト |
| `ObjectName` | string | 記録されたアクションが適用されたオブジェクトの名前 |
| `ObjectType` | string | 記録された操作が適用されたオブジェクトの種類 (ファイルやフォルダーなど) |
| `ObjectId` | string | 記録されたアクションが適用されたオブジェクトの一意識別子 |
| `ReportId` | string | イベントの一意識別子 |
| `RawEventData` | string | JSON 形式でのソースアプリケーションまたはサービスからの生イベント情報 |
| `AdditionalFields` | string | エンティティまたはイベントに関するその他の情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
