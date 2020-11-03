---
title: 高度な検索スキーマの [イベント] テーブル
description: 高度な検索スキーマのイベントテーブルのドメインコントローライベントと Active Directory イベントについて説明します。
keywords: 高度な検索、脅威の調査、サイバー脅威の調査、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、identity Directoryevents、domain controller、Active Directory、Azure ATP、id
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
ms.openlocfilehash: 41b429e32122d6cc58a746649c8a0428f0a90b0f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847430"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityDirectoryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表に、ACTIVE Directory (AD) を実行しているオンプレミスのドメインコントローラーに関連するイベントが含まれています。 このテーブルは、パスワードの変更、パスワードの有効期限、ユーザープリンシパル名 (UPN) の変更など、さまざまな id 関連イベントをキャプチャします。 また、タスクのスケジューリングや PowerShell アクティビティなど、ドメインコントローラーのシステムイベントもキャプチャします。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `TargetAccountUpn` | string | 記録されたアクションが適用されたアカウントのユーザープリンシパル名 (UPN) |
| `TargetAccountDisplayName` | string | 記録済みのアクションが適用されたアカウントの名前を表示します。 |
| `TargetDeviceName` | string | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `DestinationDeviceName` | string | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | string | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | string | アクティビティの宛先ポート |
| `Protocol` | string | 通信中に使用されるプロトコル |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountUpn` | string | アカウントのユーザープリンシパル名 (UPN) |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure Active Directory のアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | string | 通信中にデバイスに割り当てられた IP アドレス |
| `Port` | string | 通信中に使用される TCP ポート |
| `Location` | string | イベントに関連付けられている市区町村、国、またはその他の地理的な場所 |
| `ISP` | string | IP アドレスに関連付けられているインターネットサービスプロバイダー |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | string | エンティティまたはイベントに関するその他の情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
