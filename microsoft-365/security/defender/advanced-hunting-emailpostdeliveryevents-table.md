---
title: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブル
description: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブルMicrosoft 365メールで実行される配信後のアクションについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、EmailPostDeliveryEvents、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの評決、フィッシングの評決、添付ファイル数、リンクカウント、URL カウント
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
ms.openlocfilehash: 8fd30ed5f25330a9c835df85a75058a97da2b712
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192581"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `EmailPostDeliveryEvents` な検索スキーマの[表](advanced-hunting-overview.md)には、ユーザーが処理した電子メール メッセージに対して実行される配信後のアクションに関する情報がMicrosoft 365。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

個々の電子メール メッセージに関する詳細を取得するには、、 [`EmailEvents`](advanced-hunting-emailevents-table.md) 、および [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) テーブルを使用 [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) することもできます。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | string | ユーザーが生成する電子メールの一意Microsoft 365 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `Action` | string | エンティティに対して実行されるアクション |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類: 手動修復、フィッシング ZAP、マルウェア ZAP |
| `ActionTrigger` | string | 管理者 (手動または保留中の自動アクションの承認を通じて) または ZAP や動的配信などの特別なメカニズムによってアクションがトリガーされたかどうかを示します。 |
| `ActionResult` | string | アクションの結果 |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `ThreatTypes` | string | 電子メールにマルウェア、フィッシング、その他の脅威が含まれているかどうかに関する電子メール フィルター スタックからの評決 |
| `DetectionMethods` | string | 電子メールで見つかったマルウェア、フィッシング、その他の脅威を検出するために使用される方法 |

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
