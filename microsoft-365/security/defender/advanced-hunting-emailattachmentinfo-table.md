---
title: 高度な捜索スキーマの EmailAttachmentInfo テーブル
description: 高度な捜索スキーマの EmailAttachmentInfo テーブルでのメール添付ファイルの情報について学習する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、EmailAttachmentInfo、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの評決
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b38953c5f57b13e7aa13c62da926552c3d45c74b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211934"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `EmailAttachmentInfo` な検索スキーマの[表](advanced-hunting-overview.md)には、Microsoft Defender によって処理された電子メールの添付ファイルに関する情報が含Office 365。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | string | ユーザーが生成する電子メールの一意Microsoft 365 |
| `SenderFromAddress` | string | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderDisplayName` | string | アドレス帳に表示される送信者の名前(通常は、特定の名前または名、ミドル イニシャル、姓または姓の組み合わせ) |
| `SenderObjectId` | string | Azure アカウントの送信者のアカウントの一意AD |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `RecipientObjectId` | string | Azure の電子メール受信者の一意AD |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FileType` | 文字列型 | ファイル拡張子の種類 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `ThreatTypes` | 文字列型 | 電子メールにマルウェア、フィッシング、その他の脅威が含まれているかどうかに関する電子メール フィルター スタックからの評決 |
| `ThreatNames` | string | マルウェアまたは検出された他の脅威の検出名 |
| `DetectionMethods` | string | 電子メールで見つかったマルウェア、フィッシング、その他の脅威を検出するために使用される方法 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `FileSize` | string | ファイルのサイズ (バイト単位) |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
