---
title: 高度な検索スキーマの EmailEvents テーブル
description: 高度なハンティング スキーマの EmailEvents テーブルで、Microsoft 365メールに関連付けられているイベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, EmailEvents, ネットワーク メッセージ ID, 送信者, 受信者, 添付ファイル ID, 添付ファイル名, マルウェアの判定, フィッシング判定, 添付ファイル数, リンク数, URL カウント
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
ms.openlocfilehash: b34ac5538a2c38261f7da0a0cd3a75452660ef6e
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128807"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Microsoft Defender for Office 365

`EmailEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Office 365での電子メールの処理に関連するイベントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

> [!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType`値) の詳細については、Defender for Cloudで使用できる組み込みのスキーマ参照を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `NetworkMessageId` | `string` | Microsoft 365によって生成された電子メールの一意の識別子 |
| `InternetMessageId` | `string` | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `SenderMailFromAddress` | `string` | MAIL FROM ヘッダーの送信者メール アドレス (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromAddress` | `string` | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderDisplayName` | `string` | アドレス帳に表示される送信者の名前(通常は、特定の名前または名、ミドル イニシャル、姓または姓の組み合わせ) |
| `SenderObjectId` | `string` |Azure ADの送信者のアカウントの一意の識別子 |
| `SenderMailFromDomain` | `string` | MAIL FROM ヘッダーの送信者ドメイン (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromDomain` | `string` | 受信者のメール クライアントで受信者に表示される、MAIL FROM ヘッダーの送信者ドメイン |
| `SenderIPv4` | `string` | 検出された、最後にメッセージをリレーしたメール サーバーの IPv4 アドレス |
| `SenderIPv6` | `string` | 検出された、最後にメッセージをリレーしたメール サーバーの IPv6 アドレス |
| `RecipientEmailAddress` | `string` | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `RecipientObjectId` | `string` | Azure ADの電子メール受信者の一意の識別子 |
| `Subject` | `string` | メールの件名 |
| `EmailClusterId` | `string` | コンテンツのヒューリスティック分析に基づいてまとめられた、似通ったメールのグループの識別子 |
| `EmailDirection` | `string` | ネットワークに対するメールの方向: Inbound、Outbound、Intra-org |
| `DeliveryAction` | `string` | メールの配信アクション: Delivered、Junked、Blocked、または Replaced |
| `DeliveryLocation` | `string` | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `ThreatTypes` | `string` | メールにマルウェア、フィッシング、またはその他の脅威が含まれているかどうかに関する電子メール フィルター スタックからの判定 |
| `ThreatNames` | `string` |マルウェアまたはその他の脅威の検出名が見つかりました |
| `DetectionMethods` | `string` | 電子メールで見つかったマルウェア、フィッシング、またはその他の脅威を検出するために使用される方法 |
| `ConfidenceLevel` | `string` | スパムまたはフィッシングの判定の信頼レベルの一覧。 スパムの場合、この列にはスパム信頼レベル (SCL) が表示され、メールがスキップされた (-1)、スパムではない (0,1)、中程度の信頼度 (5,6)、または信頼度の高いスパムであることが検出されたかどうかを示します (9)。 フィッシングの場合、この列には信頼レベルが "高" か "低" かが表示されます。 |
| `EmailAction` | `string` | フィルターの判定、ポリシー、ユーザー アクションに基づいてメールに対して実行される最終的なアクション: メッセージを迷惑メール フォルダーに移動、X-ヘッダーの追加、件名の変更、メッセージのリダイレクト、メッセージの削除、検疫フォルダーへの配信、アクションなし、Bcc メッセージ |
| `EmailActionPolicy` | `string` | 適用されたアクション ポリシー: 高信頼度のスパム対策、スパム対策、バルク メール スパム対策、フィッシング スパム対策、ドメイン偽装フィッシング対策、ユーザー偽装フィッシング対策、スプーフィング フィッシング対策、グラフ偽装フィッシング対策、マルウェア対策、安全な添付ファイル、Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | `string` | メールに対する最終アクションを決定したポリシーの一意の識別子 |
| `AttachmentCount` | `int` | メール内の添付ファイル数 |
| `UrlCount` | `int` | メールに埋め込まれている URL の数 |
| `EmailLanguage` | `string` | 検出されたメールのコンテンツの言語 |
| `Connectors` | `string` | 組織のメール フローとメールのルーティング方法を定義するカスタム手順 |
| `OrgLevelAction` | `string` | 組織レベルで定義されたポリシーへの一致に応答して電子メールに対して実行されるアクション |
| `OrgLevelPolicy` | `string` | 電子メールに対して実行されたアクションをトリガーした組織ポリシー |
| `UserLevelAction` | `string` | 受信者によって定義されたメールボックス ポリシーへの一致に応答して電子メールに対して実行されるアクション |
| `UserLevelPolicy` | `string` | 電子メールで実行されたアクションをトリガーしたエンド ユーザー メールボックス ポリシー |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列とタイムスタンプ列と組み合わせて使用する必要があります。 |
| `AuthenticationDetails` | `string` | DMARC、DKIM、SPF などの電子メール認証プロトコルまたは複数の認証の種類 (CompAuth) の組み合わせによる合格または不合格の判定の一覧 |

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
