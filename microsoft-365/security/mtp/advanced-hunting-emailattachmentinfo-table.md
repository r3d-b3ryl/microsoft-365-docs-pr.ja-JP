---
title: 高度な捜索スキーマの EmailAttachmentInfo テーブル
description: 高度な捜索スキーマの EmailAttachmentInfo テーブルでのメール添付ファイルの情報について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、EmailAttachmentInfo、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの検証
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c6cab4d813eba79e298d0082072888e3ef1ad1cd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927004"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `EmailAttachmentInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Defender for Office 365 で処理された電子メールの添付ファイルに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AttachmentId` | 文字列型 | 一意のメール添付ファイルの識別子 |
| `NetworkMessageId` | 文字列型 | Microsoft 365 によって生成される電子メールの一意識別子 |
| `SenderFromAddress` | 文字列型 | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `RecipientEmailAddress` | 文字列型 | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `FileName` | 文字列型 | 記録されたアクションが適用されたファイルの名前 |
| `FileType` | 文字列型 | ファイル拡張子の種類 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MalwareFilterVerdict` | 文字列型 | メールにマルウェアが含まれているかどうかに関する、メールのフィルター処理スタックの判定 (マルウェア、マルウェア以外) |
| `MalwareDetectionMethod` | 文字列型 | 電子メール内のマルウェアを検出するために使用する方法: マルウェア対策エンジン、ファイル評価、安全な添付ファイル |
| `SenderDisplayName` | string | アドレス帳に表示される送信者の名前。通常は、名、ミドル ネームのイニシャル、姓または姓の組み合わせ |
| `SenderObjectId` | string | Azure AD での送信者のアカウントの一意の識別子 |
| `ThreatTypes` | string | 電子メールにマルウェア、フィッシング、その他の脅威が含まれているかどうかに関する、電子メール フィルター スタックからの判断 |
| `ThreatNames` | string | マルウェアまたは他の脅威が検出された検出名 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
