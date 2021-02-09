---
title: 高度な検索スキーマの EmailPostDeliveryEvents テーブル
description: 高度な検索スキーマの EmailPostDeliveryEvents テーブルで Microsoft 365 メールに対して実行された配信後のアクションについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、EmailPostDeliveryEvents、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの検証、フィッシングの検証、添付ファイル数、リンク数、URL カウント
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145501"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `EmailPostDeliveryEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft 365 によって処理された電子メール メッセージに対して実行された配信後アクションに関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

個々の電子メール メッセージに関する詳細を取得するには、表 [`EmailEvents`](advanced-hunting-emailevents-table.md) を使用 [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) することもできます。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | string | Microsoft 365 によって生成される電子メールの一意識別子 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `Action` | string | エンティティに対して実行されたアクション |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類: 手動修復、フィッシング ZAP、マルウェア ZAP |
| `ActionTrigger` | string | 管理者 (手動または保留中の自動アクションの承認によって) または ZAP や動的配信などの特別なメカニズムによってアクションがトリガーされたかどうかを示します。 |
| `ActionResult` | string | アクションの結果 |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |

## <a name="supported-event-types"></a>サポートされているイベントの種類
次の表は、次の値を持つイベントをキャプチャ `ActionType` します。

- **手動による修復** - 管理者は、ユーザーメールボックスに配信された後、電子メール メッセージに対して手動でアクションを実行しました。 これには、脅威エクスプローラー [を使用して](../office-365-security/threat-explorer.md) 手動で実行されたアクションや、自動調査および対応 (AIR) アクションの承認 [が含まれます](mtp-autoir-actions.md)。
- **フィッシング ZAP** – [ゼロアワー自動消去 (ZAP)](../office-365-security/zero-hour-auto-purge.md) が配信後にフィッシング メールに対してアクションを実行しました。
- **マルウェア ZAP** – ゼロアワー自動消去 (ZAP) が、配信後にマルウェアを含む電子メール メッセージに対してアクションを実行しました。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
