---
title: 高度なハンティング スキーマの IdentityQueryEvents テーブル
description: 高度なハンティング スキーマの IdentityQueryEvents テーブルで Active Directory クエリ イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, IdentityQueryEvents, Azure AD, Active Directory, Microsoft Defender for Identity, ID, LDAP クエリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 84498d0096aa244329020768d3e5f4b53804ea93
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472120"
---
# <a name="identityqueryevents"></a>IdentityQueryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityQueryEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対して実行されるクエリに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType` 値) の詳細については、Defender for Cloud で使用できる組み込みのスキーマ参照を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `QueryType` | `string` | クエリの種類 (QueryGroup、QueryUser、EnumerateUsers など) |
| `QueryTarget` | `string` | クエリ対象のユーザー、グループ、デバイス、ドメイン、またはその他のエンティティの種類の名前 |
| `Query` | `string` | クエリの実行に使用される文字列 |
| `Protocol` | `string` | 通信中に使用されるプロトコル |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | `string` | Azure AD のアカウントの一意識別子 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の開始、姓または姓の組み合わせ。 |
| `DeviceName` | `string` | エンドポイントの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | `string` | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | `string` | 通信中に使用される TCP ポート |
| `DestinationDeviceName` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | `string` | 関連するネットワーク通信の宛先ポート |
| `TargetDeviceName` | `string` | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountUpn` | `string` | 記録されたアクションが適用されたアカウントのユーザー プリンシパル名 (UPN) |
| `TargetAccountDisplayName` | `string` | 記録されたアクションが適用されたアカウントの表示名 |
| `Location` | `string` | イベントに関連付けられている都市、国、またはその他の地理的な場所 |
| `ReportId` | `long` | イベントの一意識別子 |
| `AdditionalFields` | `string` | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
