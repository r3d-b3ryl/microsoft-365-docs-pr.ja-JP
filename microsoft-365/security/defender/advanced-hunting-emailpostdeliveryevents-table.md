---
title: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブル
description: 高度なハンティング スキーマの EmailPostDeliveryEvents テーブルで、Microsoft 365 メールで実行された配信後のアクションについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, EmailPostDeliveryEvents, ネットワーク メッセージ ID, 送信者, 受信者, 添付ファイル ID, 添付ファイル名, マルウェアの判定, フィッシング判定, 添付ファイル数, リンク数, URL カウント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 9b33c3cbb976431f87f2e23f12a0743d0b28726e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480108"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Office 365

`EmailPostDeliveryEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft 365 によって処理された電子メール メッセージに対して実行された配信後のアクションに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType` 値) の詳細については、Defender for Cloud で使用できる組み込みのスキーマ参照を使用します。

個々の電子メール メッセージの詳細を取得するには、テーブル、および[`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md)テーブル[`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md)を使用[`EmailEvents`](advanced-hunting-emailevents-table.md)することもできます。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `NetworkMessageId` | `string` | Microsoft 365 によって生成された電子メールの一意の識別子 |
| `InternetMessageId` | `string` | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `Action` | `string` | エンティティに対して実行されるアクション |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類: 手動修復、フィッシング ZAP、マルウェア ZAP |
| `ActionTrigger` | `string` | アクションが管理者によって (手動で、または保留中の自動化されたアクションの承認によって) トリガーされたか、または ZAP や動的配信などの特別なメカニズムによってトリガーされたかどうかを示します。 |
| `ActionResult` | `string` | アクションの結果 |
| `RecipientEmailAddress` | `string` | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `DeliveryLocation` | `string` | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列とタイムスタンプ列と組み合わせて使用する必要があります。 |
| `ThreatTypes` | `string` | メールにマルウェア、フィッシング、またはその他の脅威が含まれているかどうかに関する電子メール フィルター スタックからの判定 |
| `DetectionMethods` | `string` | 電子メールで見つかったマルウェア、フィッシング、またはその他の脅威を検出するために使用される方法 |

## <a name="supported-event-types"></a>サポートされているイベントの種類
次の表は、次 `ActionType` の値を持つイベントをキャプチャします。

- **手動修復** – 管理者は、ユーザー メールボックスに配信された後、電子メール メッセージに対して手動でアクションを実行しました。 これには、 [脅威エクスプローラー](../office-365-security/threat-explorer.md) を介して手動で実行されたアクションや [、自動調査と応答 (AIR) アクション](m365d-autoir-actions.md)の承認が含まれます。
- **フィッシング ZAP** – [ゼロ時間の自動消去 (ZAP)](../office-365-security/zero-hour-auto-purge.md) は、配信後にフィッシング メールに対してアクションを実行しました。
- **マルウェア ZAP** – 0 時間の自動消去 (ZAP) は、配信後にマルウェアを含む電子メール メッセージに対してアクションを実行しました。

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
