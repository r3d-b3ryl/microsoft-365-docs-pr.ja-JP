---
title: 高度な検索スキーマの IdentityQueryEvents テーブル
description: 高度なハンティング スキーマの IdentityQueryEvents テーブルの Active Directory クエリ イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、IdentityQueryEvents、Azure AD、Active Directory、Microsoft Defender for Identity、IDENTITY、LDAP クエリ
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0b3c98b629d8984b984af3f3dba25a65ab7671e6
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531329"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `IdentityQueryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対して実行されるクエリに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、Defender for Cloud で使用できる組み込みのスキーマ `ActionType` 参照を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `QueryType` | `string` | QueryGroup、QueryUser、または EnumerateUsers などのクエリの種類 |
| `QueryTarget` | `string` | クエリを実行するユーザー、グループ、デバイス、ドメイン、その他のエンティティ型の名前 |
| `Query` | `string` | クエリの実行に使用される文字列 |
| `Protocol` | `string` | 通信中に使用されるプロトコル |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | `string` | アカウントの一意の識別子は、Azure AD |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `DeviceName` | `string` | エンドポイントの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | `string` | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | `string` | 通信中に使用される TCP ポート |
| `DestinationDeviceName` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | `string` | 関連するネットワーク通信の宛先ポート |
| `TargetDeviceName` | `string` | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountUpn` | `string` | 記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN) |
| `TargetAccountDisplayName` | `string` | 記録されたアクションが適用されたアカウントの表示名 |
| `Location` | `string` | イベントに関連付けられている都市、国、その他の地理的な場所 |
| `ReportId` | `long` | イベントの一意識別子 |
| `AdditionalFields` | `string` | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
