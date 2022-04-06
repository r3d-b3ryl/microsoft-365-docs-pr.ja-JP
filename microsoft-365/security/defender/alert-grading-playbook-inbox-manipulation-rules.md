---
title: 疑わしい受信トレイ操作ルールのアラート の採点
description: 疑わしい受信トレイ操作ルールのアラート の採点。アラートを確認し、攻撃を修復してネットワークを保護するための推奨されるアクションを実行します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: e663d02037633599b9dffc19e1ebbd174aa279e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663184"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>疑わしい受信トレイ操作ルールのアラート の採点

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威アクターは、侵害されたユーザー アカウントを、ユーザーの受信トレイでメールを読み取る、外部アカウントに電子メールを転送する受信トレイ ルールの作成、トレースの削除、フィッシング メールの送信など、多くの悪意のある目的で使用できます。 悪意のある受信トレイ ルールは、ビジネス メール侵害 (BEC) やフィッシング キャンペーンの間に一般的であり、それらを一貫して監視することが重要です。

このプレイブックは、攻撃者によって構成された疑わしい受信トレイ操作ルールに関連するすべてのインシデントを調査し、攻撃を修復し、ネットワークを保護するために推奨されるアクションを実行するのに役立ちます。 このプレイブックは、セキュリティ オペレーション センター (SOC) アナリストや、アラートの確認、調査、および採点を行う IT 管理者を含むセキュリティ チーム向けです。 アラートを True Positive (TP) または False Positive (TP) として迅速に評価し、TP アラートに対して推奨されるアクションを実行して攻撃を修復できます。

このプレイブックを使用した結果は次のとおりです。

- 受信トレイ操作ルールに関連付けられているアラートを、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別しました。

  悪意のある場合は、悪意のある受信トレイ操作ルールを削除しました。

- メールが悪意のあるメール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="inbox-manipulation-rules"></a>受信トレイ操作ルール

受信トレイルールは、定義済みの条件に基づいて電子メール メッセージを自動的に管理するように設定されます。 たとえば、受信トレイ ルールを作成して、マネージャーから別のフォルダーにすべてのメッセージを移動したり、受信したメッセージを別のメール アドレスに転送したりできます。

### <a name="malicious-inbox-manipulation-rules"></a>悪意のある受信トレイ操作ルール

攻撃者は、侵害されたユーザー メールボックス内の受信メールを非表示にして、悪意のあるアクティビティをユーザーから隠すために電子メール ルールを設定する可能性があります。 また、侵害されたユーザー メールボックスにルールを設定して、メールを削除したり、メールを別の目立たないフォルダー (RSS など) に移動したり、外部アカウントにメールを転送したりすることもできます。 一部のルールでは、すべてのメールを別のフォルダーに移動して "読み取り" としてマークすることがありますが、一部のルールでは、電子メール メッセージまたは件名に特定のキーワードを含むメールのみが移動される場合があります。

たとえば、受信トレイルールは、"invoice"、"フィッシング"、"返信しない"、"疑わしいメール"、または "スパム" などのキーワードを検索し、外部メール アカウントに移動するように設定できます。 攻撃者は、侵害されたユーザー メールボックスを使用して、スパム、フィッシングメール、またはマルウェアを配布する可能性もあります。

## <a name="workflow"></a>ワークフロー

疑わしい受信トレイ操作ルールアクティビティを識別するワークフローを次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="受信トレイ操作ルールのアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::

## <a name="investigation-steps"></a>調査手順

このセクションには、インシデントに対応し、組織をさらなる攻撃から保護するための推奨される手順を実行するための詳細なステップ バイ ステップ ガイダンスが含まれています。

### <a name="1-review-the-alerts"></a>1. アラートを確認する

アラート キュー内の受信トレイ操作ルールアラートの例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="受信トレイ操作ルールの例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

悪意のある受信トレイ操作ルールによってトリガーされたアラートの詳細の例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="悪意のある受信トレイ操作ルールによってトリガーされたアラートの詳細" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::

### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. 受信トレイ操作ルールのパラメーターを調査する

次のルール パラメーターまたは条件に従って、ルールが疑わしいと見なされるかどうかを判断します。

- キーワード

   攻撃者は、特定の単語を含む電子メールにのみ操作ルールを適用する可能性があります。 これらのキーワードは、"BodyContainsWords"、"SubjectContainsWords"、"SubjectOrBodyContainsWords" などの特定の属性の下にあります。

   キーワードによるフィルター処理がある場合は、そのキーワードが疑わしいと思われるかどうかを確認します (一般的なシナリオは、"フィッシング"、"スパム"、"返信しない" など、攻撃者のアクティビティに関連するメールをフィルター処理することです)。

   フィルターがまったくない場合は、疑わしい場合もあります。

- コピー先フォルダー

   セキュリティ検出を回避するために、攻撃者は電子メールを目立たないフォルダーに移動し、電子メールを読み取り ("RSS" フォルダーなど) としてマークする可能性があります。 攻撃者が "MoveToFolder" アクションと "MarkAsRead" アクションを適用する場合は、ターゲット フォルダーがルール内のキーワードに何らかの関係があるかどうかを確認して、疑わしいと思われるかどうかを判断します。

- すべてを削除する

   一部の攻撃者は、すべての受信メールを削除してアクティビティを非表示にします。 ほとんどの場合、キーワードでフィルター処理せずに "すべての受信メールを削除する" ルールは、悪意のあるアクティビティの指標です。

関連するイベント ログの "すべての受信メールを削除する" ルール構成 (RawEventData.Parameters で確認) の例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="すべての受信電子メールルールの削除の構成の例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::

### <a name="3-investigate-the-ip-address"></a>3. IP アドレスを調査する

ルール作成の関連イベントを実行した IP アドレスの属性を確認します。

- テナント内の同じ IP から発生したその他の疑わしいクラウド アクティビティを検索します。 たとえば、疑わしいアクティビティは、ログイン試行が複数回失敗した可能性があります。
- このユーザーにとって ISP は一般的で妥当ですか?
- このユーザーにとって、場所は一般的で妥当ですか?

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. ルールを作成する前に、ユーザーによる疑わしいアクティビティを調査する

ルールが作成される前にすべてのユーザー アクティビティを確認し、侵害のインジケーターを確認し、疑わしいと思われるユーザー アクションを調査できます。

たとえば、失敗したログインが複数発生した場合は、次の項目を調べます。

- ログイン アクティビティ

   ルールの作成前にログイン アクティビティが疑わしくないことを検証します。 (共通の場所/ISP/ユーザー エージェント)。

- アラート

   ルールを作成する前に、ユーザーがアラートを受信したかどうかを確認します。 これは、ユーザー アカウントが侵害されている可能性があることを示している可能性があります。 たとえば、不可能な旅行アラート、頻度の低い国、複数の失敗したログインなど)。

- インシデント

   アラートがインシデントを示す他のアラートに関連付けられているかどうかを確認します。 その場合は、インシデントに他の正のアラートが含まれているかどうかを確認します。

## <a name="advanced-hunting-queries"></a>高度なハンティング クエリ

[高度なハンティング](advanced-hunting-overview.md) は、ネットワーク内のイベントを調べて脅威インジケーターを見つけ出すクエリベースの脅威検出ツールです。

このクエリを使用して、特定の時間枠内のすべての新しい受信トレイ ルール イベントを検索します。

```kusto
let start_date = now(-10h);
let end_date = now();
let user_id = ""; // enter here the user id
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where AccountObjectId == user_id
| where Application == @"Microsoft Exchange Online"
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
```

*RuleConfig* 列には、新しい受信トレイルールの構成が提供されます。

このクエリを使用して、ユーザーの履歴を調べて、ISP がユーザーに共通かどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

このクエリを使用して、ユーザーの履歴を調べて、国がユーザーに共通かどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

このクエリを使用して、ユーザーの履歴を調べて、ユーザー エージェントがユーザーに共通かどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

## <a name="recommended-actions"></a>推奨処理

1. 悪意のある受信トレイルールを無効にします。
2. ユーザー アカウントの資格情報をリセットします。 また、Azure Active Directory (Azure AD) Identity Protection からセキュリティシグナルを取得するMicrosoft Defender for Cloud Appsでユーザー アカウントが侵害されているかどうかを確認することもできます。
3. 影響を受けたユーザー アカウントによって実行される他の悪意のあるアクティビティを検索します。
4. 他の侵害されたユーザー アカウントを見つけるために、同じ IP または同じ ISP から発信されたテナント内の他の不審なアクティビティ (ISP が一般的でない場合) を確認します。

## <a name="see-also"></a>関連項目

- [アラートの採点の概要](alert-grading-playbooks.md)
- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)
- [アラートの調査](investigate-alerts.md)
