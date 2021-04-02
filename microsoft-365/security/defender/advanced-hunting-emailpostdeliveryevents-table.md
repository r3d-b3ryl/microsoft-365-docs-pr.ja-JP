---
title: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブル
description: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブルで Microsoft 365 メールで実行される配信後のアクションについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、EmailPostDeliveryEvents、ネットワーク メッセージ ID、送信者、添付ファイル ID、添付ファイル名、マルウェアの評決、フィッシングの評決、添付ファイル数、リンクカウント、URL カウント
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
ms.openlocfilehash: c6612127f43e650dee18bdc9390fc26b0a693f69
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498887"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `EmailPostDeliveryEvents` な検索スキーマ [の表](advanced-hunting-overview.md) には、Microsoft 365 によって処理された電子メール メッセージに対して実行される配信後のアクションに関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

個々の電子メール メッセージに関する詳細を取得するには、、 [`EmailEvents`](advanced-hunting-emailevents-table.md) 、および [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) テーブルを使用 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) することもできます。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | 文字列 | Microsoft 365 によって生成された電子メールの一意の識別子 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `Action` | string | エンティティに対して実行されるアクション |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類: 手動修復、フィッシング ZAP、マルウェア ZAP |
| `ActionTrigger` | 文字列 | 管理者 (手動または保留中の自動アクションの承認を通じて) または ZAP や動的配信などの特別なメカニズムによってアクションがトリガーされたかどうかを示します。 |
| `ActionResult` | 文字列 | アクションの結果 |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |

## <a name="supported-event-types"></a>サポートされているイベントの種類
次の表は、次の値でイベントを `ActionType` キャプチャします。

- **手動修復** – 管理者は、ユーザー メールボックスに配信された後、電子メール メッセージに対して手動でアクションを実行しました。 これには、脅威エクスプローラーを通 [じて手動](../office-365-security/threat-explorer.md) で実行されるアクションや、自動調査と応答 [(AIR) アクションの承認が含まれます](m365d-autoir-actions.md)。
- **フィッシング ZAP** – 配信後にフィッシング メールに対してゼロ時間自動削除 [(ZAP)](../office-365-security/zero-hour-auto-purge.md) がアクションを実行しました。
- **マルウェア ZAP** – 配信後にマルウェアを含む電子メール メッセージが検出された場合、ゼロ時間自動削除 (ZAP) がアクションを実行しました。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
