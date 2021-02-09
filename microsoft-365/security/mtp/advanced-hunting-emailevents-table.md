---
title: 高度な検索スキーマの EmailEvents テーブル
description: 高度な検索スキーマの EmailEvents テーブルで Microsoft 365 メールに関連付けられているイベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、EmailEvents、ネットワーク メッセージ ID、送信者、受信者、添付ファイル ID、添付ファイル名、マルウェアの検証、フィッシングの検証、添付ファイル数、リンク数、URL カウント
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
ms.openlocfilehash: f39e8f77a53b018fdf9c96981524e12f9aface65
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145045"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

高度 `EmailEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、Microsoft Defender for Office 365 での電子メールの処理に関連するイベントに関する情報が記載されています。 このテーブルの情報を返すクエリを作成するには、この参照を使用できます。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | string | Microsoft 365 によって生成される電子メールの一意識別子 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `SenderMailFromAddress` | string | MAIL FROM ヘッダーの送信者メール アドレス (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromAddress` | string | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderDisplayName` | string | アドレス帳に表示される送信者の名前。通常は、名、ミドル ネームのイニシャル、姓または姓の組み合わせ |
| `SenderObjectId` | string |Azure AD の送信者のアカウントの一意の識別子 |
| `SenderMailFromDomain` | string | MAIL FROM ヘッダーの送信者ドメイン (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromDomain` | string | 受信者のメール クライアントで受信者に表示される、MAIL FROM ヘッダーの送信者ドメイン |
| `SenderIPv4` | string | 検出された、最後にメッセージをリレーしたメール サーバーの IPv4 アドレス |
| `SenderIPv6` | string | 検出された、最後にメッセージをリレーしたメール サーバーの IPv6 アドレス |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `RecipientObjectId` | string | Azure AD の電子メール受信者の一意の識別子 |
| `Subject` | string | メールの件名 |
| `EmailClusterId` | string | コンテンツのヒューリスティック分析に基づいてまとめられた、似通ったメールのグループの識別子 |
| `EmailDirection` | string | ネットワークに対するメールの方向: Inbound、Outbound、Intra-org |
| `DeliveryAction` | string | メールの配信アクション: Delivered、Junked、Blocked、または Replaced |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `PhishFilterVerdict` | string | メールがフィッシングであるかどうかに関する、メール フィルタリング スタックの判定: Phish または Not Phish |
| `PhishDetectionMethod` | string | 電子メールをフィッシングとして検出するために使用される方法: 悪意のある URL 評価、安全なリンク URL の分析、高度なフィッシング フィルター、一般的なフィッシング フィルター、スプーフィング対策: 組織内、スプーフィング対策: 外部ドメイン、ドメイン偽装、ユーザー偽装、ブランド偽装 |
| `MalwareFilterVerdict` | string | メールにマルウェアが含まれているかどうかに関する、メールのフィルター処理スタックの判定 (マルウェア、マルウェア以外) |
| `MalwareDetectionMethod` | string | 電子メール内のマルウェアを検出するために使用する方法: マルウェア対策エンジン、ファイル評価、安全な添付ファイル |
| `ThreatTypes` | string | 電子メールにマルウェア、フィッシング、その他の脅威が含まれているかどうかに関する、電子メール フィルター スタックからの判断 |
| `ThreatNames` | string |マルウェアまたは他の脅威が検出された検出名 |
| `DetectionMethods` | string | 電子メールで検出されたマルウェア、フィッシング、その他の脅威を検出するために使用される方法 |
| `ConfidenceLevel` | string | スパムまたはフィッシングの否認の信頼レベルのリスト。 スパムの場合、この列には、電子メールがスキップされた (-1)、スパムではない (0,1)、中程度の信頼度 (5,6) のスパムである、または高い信頼性を持つスパムである (9) ことを示す、Spam Confidence Level (SCL) が表示されます。 フィッシングの場合、この列には信頼度が "高" か "低" かを表示します。 |
| `EmailAction` | string | フィルターの判定、ポリシー、ユーザー アクションに基づいてメールに対して実行される最終的なアクション: メッセージを迷惑メール フォルダーに移動、X-ヘッダーの追加、件名の変更、メッセージのリダイレクト、メッセージの削除、検疫フォルダーへの配信、アクションなし、Bcc メッセージ |
| `EmailActionPolicy` | string | 適用されたアクション ポリシー: 高信頼度のスパム対策、スパム対策、バルク メール スパム対策、フィッシング スパム対策、ドメイン偽装フィッシング対策、ユーザー偽装フィッシング対策、スプーフィング フィッシング対策、グラフ偽装フィッシング対策、マルウェア対策、安全な添付ファイル、Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | string | メールに対する最終アクションを決定したポリシーの一意の識別子 |
| `AttachmentCount` | int | メール内の添付ファイル数 |
| `UrlCount` | int | メールに埋め込まれている URL の数 |
| `EmailLanguage` | string | 検出されたメールのコンテンツの言語 |
| `Connectors` | string | 組織のメール フローと電子メールのルーティング方法を定義するカスタム手順 |
| `OrgLevelAction` | string | 組織レベルで定義されたポリシーに一致した場合に電子メールに対して実行されるアクション |
| `OrgLevelPolicy` | string | 電子メールに対して実行されたアクションをトリガーした組織ポリシー |
| `UserLevelAction` | string | 受信者によって定義されたメールボックス ポリシーに一致した場合に電子メールに対して実行されるアクション |
| `UserLevelPolicy` | string | 電子メールに対して実行されたアクションをトリガーしたエンド ユーザーメールボックス ポリシー |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |

## <a name="related-topics"></a>関連項目

- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
