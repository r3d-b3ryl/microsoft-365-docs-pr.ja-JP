---
title: 高度な検索スキーマの EmailPostDeliveryEvents テーブル
description: 高度な検索スキーマの EmailPostDeliveryEvents テーブルで Microsoft 365 メールに対して実行された配信後の処理について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、EmailPostDeliveryEvents、network message id、sender、recipient、attachment id、添付ファイル名、マルウェア verdict、フィッシング verdict
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
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198015"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

`EmailPostDeliveryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft 365 によって処理された電子メールメッセージに対して実行された配信後の処理に関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

個々の電子メールメッセージに関する詳細情報を取得するには、、、およびの表を使用することもでき [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) ます。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `EventId` | 文字列 | イベントの一意識別子 |
| `NetworkMessageId` | 文字列 | Microsoft 365 によって生成される電子メールの一意識別子。 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `Action` | string | エンティティに対して実行されたアクション |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類: 手動による修復、フィッシング ZAP、マルウェアの ZAP |
| `ActionTrigger` | 文字列 | アクションが管理者によってトリガーされたかどうか (手動または保留中の自動アクションの承認)、または ZAP または動的配信などの特別なメカニズムによって発生したかどうかを示します。 |
| `ActionResult` | 文字列 | アクションの結果 |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |

## <a name="supported-event-types"></a>サポートされるイベントの種類
このテーブルは、次の値を持つイベントをキャプチャし `ActionType` ます。

- **手動による修復** –管理者は、ユーザーのメールボックスに配信された後に、電子メールメッセージに対して手動でアクションを実行していました。 これには、 [脅威エクスプローラー](../office-365-security/threat-explorer.md) を使用して手動で行う操作や、自動化された [調査と応答 (AIR) アクション](mtp-autoir-actions.md)の承認が含まれます。
- **フィッシング ZAP** – [ゼロ時間自動削除 (ZAP)](../office-365-security/zero-hour-auto-purge.md) は、配信後にフィッシング電子メールに対してアクションを実行しました。
- **マルウェア ZAP** –ゼロ時間自動削除 (ZAP) は、配信後にマルウェアを含む電子メールメッセージに対してアクションを実行しました。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
