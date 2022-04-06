---
title: 高度な捜索スキーマの EmailAttachmentInfo テーブル
description: 高度な捜索スキーマの EmailAttachmentInfo テーブルでのメール添付ファイルの情報について学習する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, EmailAttachmentInfo, ネットワーク メッセージ ID, 送信者, 受信者, 添付ファイル ID, 添付ファイル名, マルウェアの判定
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
ms.openlocfilehash: e787f79b5af90f45dd2823f53402830c7fc287db
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664042"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

`EmailAttachmentInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Office 365によって処理された電子メールの添付ファイルに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `NetworkMessageId` | `string` | Microsoft 365によって生成された電子メールの一意の識別子 |
| `SenderFromAddress` | `string` | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderDisplayName` | `string` | アドレス帳に表示される送信者の名前(通常は、特定の名前または名、ミドル イニシャル、姓または姓の組み合わせ) |
| `SenderObjectId` | `string` | Azure ADの送信者のアカウントの一意の識別子 |
| `RecipientEmailAddress` | `string` | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `RecipientObjectId` | `string` | Azure ADの電子メール受信者の一意の識別子 |
| `FileName` | `string` | 記録されたアクションが適用されたファイルの名前 |
| `FileType` | `string` | ファイル拡張子の種類 |
| `SHA256` | `string` | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `ThreatTypes` | `string` | メールにマルウェア、フィッシング、またはその他の脅威が含まれているかどうかに関する電子メール フィルター スタックからの判定 |
| `ThreatNames` | `string` | マルウェアまたはその他の脅威の検出名が見つかりました |
| `DetectionMethods` | `string` | 電子メールで見つかったマルウェア、フィッシング、またはその他の脅威を検出するために使用される方法 |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列とタイムスタンプ列と組み合わせて使用する必要があります。 |
| `FileSize` | `string` | ファイルのサイズ (バイト単位) |

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
