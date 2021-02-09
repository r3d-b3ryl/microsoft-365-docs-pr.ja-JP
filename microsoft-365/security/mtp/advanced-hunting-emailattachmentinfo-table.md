---
title: 高度な捜索スキーマの EmailAttachmentInfo テーブル
description: 高度な捜索スキーマの EmailAttachmentInfo テーブルでのメール添付ファイルの情報について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、EmailAttachmentInfo、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの検証
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
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145021"
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
| `NetworkMessageId` | 文字列型 | Microsoft 365 によって生成される電子メールの一意識別子 |
| `SenderFromAddress` | 文字列型 | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderDisplayName` | 文字列型 | アドレス帳に表示される送信者の名前。通常は、名、ミドル ネームのイニシャル、姓または姓の組み合わせ |
| `SenderObjectId` | 文字列型 | Azure AD の送信者のアカウントの一意の識別子 |
| `RecipientEmailAddress` | 文字列型 | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `RecipientObjectId` | 文字列型 | Azure AD の電子メール受信者の一意の識別子 |
| `FileName` | 文字列型 | 記録されたアクションが適用されたファイルの名前 |
| `FileType` | 文字列型 | ファイル拡張子の種類 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MalwareFilterVerdict` | 文字列型 | メールにマルウェアが含まれているかどうかに関する、メールのフィルター処理スタックの判定 (マルウェア、マルウェア以外) |
| `MalwareDetectionMethod` | string | 電子メール内のマルウェアを検出するために使用する方法: マルウェア対策エンジン、ファイル評価、安全な添付ファイル |
| `ThreatTypes` | string | 電子メールにマルウェア、フィッシング、その他の脅威が含まれているかどうかに関する、電子メール フィルター スタックからの判断 |
| `ThreatNames` | string | マルウェアまたは他の脅威が検出された検出名 |
| `DetectionMethods` | string | 電子メールで検出されたマルウェア、フィッシング、その他の脅威を検出するために使用される方法 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
