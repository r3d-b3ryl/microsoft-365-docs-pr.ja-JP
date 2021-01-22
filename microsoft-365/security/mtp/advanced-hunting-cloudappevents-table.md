---
title: 高度な検索スキーマの CloudAppEvents テーブル
description: 高度な検索スキーマの CloudAppEvents テーブルにあるクラウド アプリとサービスからのイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、CloudAppEvents、Cloud App Security、MCAS
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928455"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

現在プレビューで利用可能な高度な検索スキーマの表には、さまざまなクラウド アプリとサービス、特に Microsoft Teams と Exchange Online のアクティビティに関する情報 `CloudAppEvents` が含されています。 [](advanced-hunting-overview.md) このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

次の表は、Microsoft Cloud App Security によって監視されるその他のアクティビティを含む拡張されます。 最終的に、このテーブルには [、AppFileEvents](advanced-hunting-appfileevents-table.md) テーブルに現在格納されているファイル アクティビティが含まれます。 Microsoft では、この表に移動するデータの数が多い場合に、追加のガイダンスを提供します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `ApplicationId` | string | アプリケーションの一意識別子 |
| `AccountObjectId` | string | Azure Active Directory のアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、ミドル ネームの開始、姓または姓の組み合わせ。 |
| `IsAdminOperation` | string | アクティビティが管理者によって実行されたかどうかを示します |
| `DeviceType` | string | 目的と機能に基づくデバイスの種類 ("ネットワーク デバイス"、"Workstation"、"Server"、"Mobile"、"Gaming console"、"Printer" など) | 
| `OSPlatform` | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 この列は、Windows 10 や Windows 7 など、同じファミリ内のバリエーションなど、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `IsAnonymousProxy` | string | IP アドレスが既知の匿名プロキシに属するかどうかを示します |
| `CountryCode` | string | クライアント IP アドレスが地理的に位置する国を示す 2 文字のコード |
| `City` | string | クライアント IP アドレスが地理的に位置する市区町地 |
| `Isp` | string | IP アドレスに関連付けられているインターネット サービス プロバイダー (ISP) |
| `UserAgent` | string | Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報 |
| `ActivityType` | string | イベントをトリガーしたアクティビティの種類 |
| `ActivityObjects` | string | 記録されたアクティビティに関係したオブジェクト (ファイルやフォルダーなど) のリスト |
| `ObjectName` | string | 記録されたアクションが適用されたオブジェクトの名前 |
| `ObjectType` | string | 記録されたアクションが適用されたオブジェクトの種類 (ファイルやフォルダーなど) |
| `ObjectId` | string | 記録されたアクションが適用されたオブジェクトの一意の識別子 |
| `ReportId` | string | イベントの一意識別子 |
| `RawEventData` | string | JSON 形式のソース アプリケーションまたはサービスからの生のイベント情報 |
| `AdditionalFields` | string | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
