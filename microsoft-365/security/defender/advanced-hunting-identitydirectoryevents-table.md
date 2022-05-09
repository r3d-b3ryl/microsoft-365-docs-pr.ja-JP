---
title: 高度なハンティング スキーマの IdentityDirectoryEvents テーブル
description: 高度なハンティング スキーマの IdentityDirectoryEvents テーブルで、ドメイン コントローラーと Active Directory イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, IdentityDirectoryEvents, ドメイン コントローラー, Active Directory, Microsoft Defender for Identity, ID
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
ms.openlocfilehash: b7d880e0865ebeaf09e40fc543abba37566d2081
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531812"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityDirectoryEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Active Directory (AD) を実行しているオンプレミス ドメイン コントローラーに関連するイベントが含まれています。 この表では、パスワードの変更、パスワードの有効期限、ユーザー プリンシパル名 (UPN) の変更など、さまざまな ID 関連イベントをキャプチャします。 また、タスクのスケジュール設定や PowerShell アクティビティなど、ドメイン コントローラー上のシステム イベントもキャプチャします。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType`値) の詳細については、Defender for Cloudで使用できる組み込みのスキーマ参照を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `TargetAccountUpn` | `string` | 記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN) |
| `TargetAccountDisplayName` | `string` | 記録されたアクションが適用されたアカウントの表示名 |
| `TargetDeviceName` | `string` | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `DestinationDeviceName` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | `string` | アクティビティの宛先ポート |
| `Protocol` | `string` | 通信中に使用されるプロトコル |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | `string` | Azure Active Directoryのアカウントの一意識別子 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の開始、姓または姓の組み合わせ。 |
| `DeviceName` | `string` | デバイスの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | `string` | 通信中にデバイスに割り当てられた IP アドレス |
| `Port` | `string` | 通信中に使用される TCP ポート |
| `Location` | `string` | イベントに関連付けられている都市、国、またはその他の地理的な場所 |
| `ISP` | `string` | IP アドレスに関連付けられているインターネット サービス プロバイダー |
| `ReportId` | `long` | イベントの一意識別子 |
| `AdditionalFields` | `string` | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
