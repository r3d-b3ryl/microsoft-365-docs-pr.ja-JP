---
title: 高度なハンティング スキーマの IdentityDirectoryEvents テーブル
description: 高度なハンティング スキーマの IdentityDirectoryEvents テーブルのドメイン コントローラーイベントと Active Directory イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、IdentityDirectoryEvents、ドメイン コントローラー、Active Directory、Azure ATP、ID
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501125"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `IdentityDirectoryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Active Directory を実行しているオンプレミスのドメイン コントローラー (AD) が含AD。 次の表は、パスワードの変更、パスワードの有効期限、ユーザー プリンシパル名 (UPN) の変更など、さまざまな ID 関連のイベントをキャプチャします。 また、タスクのスケジュール設定や PowerShell アクティビティなど、ドメイン コントローラー上のシステム イベントもキャプチャします。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `TargetAccountUpn` | 文字列 | 記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN) |
| `TargetAccountDisplayName` | 文字列 | 記録されたアクションが適用されたアカウントの表示名 |
| `TargetDeviceName` | 文字列 | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `DestinationDeviceName` | 文字列 | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | 文字列 | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | 文字列 | アクティビティの宛先ポート |
| `Protocol` | 文字列 | 通信中に使用されるプロトコル |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `AccountUpn` | 文字列 | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | 文字列 | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | 文字列 | Azure Active Directory のアカウントの一意識別子 |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | 文字列 | 通信中にデバイスに割り当てられた IP アドレス |
| `Port` | 文字列 | 通信中に使用される TCP ポート |
| `Location` | 文字列 | イベントに関連付けられている都市、国、その他の地理的な場所 |
| `ISP` | 文字列 | IP アドレスに関連付けられたインターネット サービス プロバイダー |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
