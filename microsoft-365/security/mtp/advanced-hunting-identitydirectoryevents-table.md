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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4a698bc0d6a7c1ebadec44357b932e9b56dc0a3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196847"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`IdentityDirectoryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表に、ACTIVE Directory (AD) を実行しているオンプレミスのドメインコントローラーに関連するイベントが含まれています。 このテーブルは、パスワードの変更、パスワードの有効期限、ユーザープリンシパル名 (UPN) の変更など、さまざまな id 関連イベントをキャプチャします。 また、タスクのスケジューリングや PowerShell アクティビティなど、ドメインコントローラーのシステムイベントもキャプチャします。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `TargetAccountUpn` | 文字列 | 記録されたアクションが適用されたアカウントのユーザープリンシパル名 (UPN) |
| `TargetAccountDisplayName` | 文字列 | 記録済みのアクションが適用されたアカウントの名前を表示します。 |
| `TargetDeviceName` | 文字列 | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `DestinationDeviceName` | 文字列 | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | 文字列 | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | 文字列 | アクティビティの宛先ポート |
| `Protocol` | 文字列 | 通信中に使用されるプロトコル |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `AccountUpn` | 文字列 | アカウントのユーザープリンシパル名 (UPN) |
| `AccountSid` | 文字列 | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | 文字列 | Azure AD でのアカウントの一意識別子 |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `IPAddress` | 文字列 | 通信中にデバイスに割り当てられた IP アドレス |
| `Port` | 文字列 | 通信中に使用される TCP ポート |
| `Location` | 文字列 | イベントに関連付けられている市区町村、国、またはその他の地理的な場所 |
| `ISP` | 文字列 | IP アドレスに関連付けられているインターネットサービスプロバイダー |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関するその他の情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
