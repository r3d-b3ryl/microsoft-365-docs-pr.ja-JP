---
title: 疑わしい受信トレイ転送ルールのアラート の採点
description: 疑わしい受信トレイ転送ルールのアラート の採点。アラートを確認し、攻撃を修復してネットワークを保護するための推奨されるアクションを実行します。
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
ms.openlocfilehash: dca305b88e6e8db25e0a798c4361086bd7cb1e8b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666022"
---
# <a name="alert-grading-for-suspicious-inbox-forwarding-rules"></a>疑わしい受信トレイ転送ルールのアラート の採点

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威アクターは、侵害されたユーザー アカウントを、ユーザーの受信トレイでメールを読み取る、外部アカウントに電子メールを転送する受信トレイ ルールの作成、フィッシング メールの送信など、悪意のある目的で使用できます。 悪意のある受信トレイ ルールは、ビジネス メール侵害 (BEC) やフィッシング キャンペーンの間に広く一般的であり、それらを一貫して監視することが重要です。

このプレイブックは、疑わしい受信トレイ転送ルールのアラートを調査し、それらを True Positive (TP) または False Positive (TP) として迅速に評価するのに役立ちます。 その後、TP アラートに対して推奨されるアクションを実行して、攻撃を修復できます。

Microsoft Defender for Office 365とMicrosoft Defender for Cloud Appsのアラートの評価の概要については、[概要記事](alert-grading-playbooks.md)を参照してください。

このプレイブックを使用した結果は次のとおりです。

- 受信トレイ転送ルールに関連付けられているアラートを、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別しました。

  悪意のある場合は、悪意のある受信トレイ転送ルールを削除しました。

- メールが悪意のあるメール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="inbox-forwarding-rules"></a>受信トレイの転送ルール

定義済みの条件に基づいて電子メール メッセージを自動的に管理するように受信トレイ ルールを構成します。 たとえば、受信トレイ ルールを作成して、マネージャーから別のフォルダーにすべてのメッセージを移動したり、受信したメッセージを別のメール アドレスに転送したりできます。

### <a name="suspicious-inbox-forwarding-rules"></a>疑わしい受信トレイ転送ルール

攻撃者は、多くの場合、ユーザーのメールボックスにアクセスした後、機密データを外部の電子メール アドレスに流出させ、悪意のある目的で使用できる受信トレイ ルールを作成します。

悪意のある受信トレイ ルールにより、流出プロセスが自動化されます。 特定のルールでは、ルールの条件に一致するターゲット ユーザーの受信トレイ内のすべての電子メールが攻撃者のメールボックスに転送されます。 たとえば、攻撃者は財務に関連する機密データを収集することが望まれます。 受信トレイルールを作成して、件名またはメッセージ本文のキーワード ("finance" や "invoice" など) を含むすべてのメールを自分のメールボックスに転送します。

受信トレイルールのメンテナンスはユーザーが行う一般的なタスクであるため、疑わしい受信トレイ転送ルールを検出することは非常に困難な場合があります。 そのため、アラートを監視することが重要です。

## <a name="workflow"></a>ワークフロー

疑わしいメール転送ルールを識別するワークフローを次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png" alt-text="受信トレイ転送ルールのアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png":::

## <a name="investigation-steps"></a>調査手順

このセクションには、インシデントに対応し、組織をさらなる攻撃から保護するための推奨される手順を実行するための詳細なステップ バイ ステップ ガイダンスが含まれています。

### <a name="review-generated-alerts"></a>生成されたアラートを確認する

アラート キュー内の受信トレイ転送ルールアラートの例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png" alt-text="アラート キュー内の通知の例" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png":::

悪意のある受信トレイ転送ルールによってトリガーされたアラートの詳細の例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png" alt-text="悪意のある受信トレイ転送ルールによってトリガーされたアラートの詳細" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png":::

### <a name="investigate-rule-parameters"></a>ルール パラメーターを調査する

このステージの目的は、ルールが特定の条件によって疑わしいと見えるかどうかを判断することです。

転送ルールの受信者:

- 宛先の電子メール アドレスが、同じユーザーが所有する追加のメールボックスではないかどうかを検証します (ユーザーが個人用メールボックス間で電子メールを自己転送するケースを回避します)。
- 宛先電子メール アドレスが会社に属する内部アドレスまたはサブドメインでないことを確認します。

フィルター：

- 受信トレイ ルールに、電子メールの件名または本文内の特定のキーワードを検索するフィルターが含まれている場合は、指定されたキーワード (金融、資格情報、ネットワークなど) が悪意のあるアクティビティに関連しているように見えるかどうかを確認します。 これらのフィルターは、次の属性 (イベント RawEventData 列に表示されます): "BodyContainsWords"、"SubjectContainsWords"、または "SubjectOrBodyContainsWords" の下にあります。
- 攻撃者がメールにフィルターを設定しないことを選択し、代わりに受信トレイ ルールですべてのメールボックス アイテムを攻撃者のメールボックスに転送する場合)、この動作も疑わしいものです。

### <a name="investigate-ip-address"></a>IP アドレスを調査する

ルール作成の関連イベントを実行した IP アドレスに関連する属性を確認します。

1. テナント内の同じ IP から発生したその他の疑わしいクラウド アクティビティを検索します。 たとえば、疑わしいアクティビティは、失敗したログイン試行が複数回発生している可能性があります。
2. このユーザーにとって ISP は一般的で妥当ですか?
3. このユーザーにとって、場所は一般的で妥当ですか?

### <a name="investigate-any-suspicious-activity-with-the-user-inbox-before-creating-rules"></a>ルールを作成する前に、ユーザーの受信トレイで疑わしいアクティビティを調査する

ルールを作成する前にすべてのユーザー アクティビティを確認し、侵害のインジケーターを確認し、疑わしいと思われるユーザー アクションを調査できます。 たとえば、複数のサインインに失敗しました。

- サインイン:

  ルール作成イベントの前にサインイン アクティビティが疑わしくないことを検証します (一般的な場所、ISP、ユーザー エージェントなど)。

- その他のアラートまたはインシデント
  - ルールの作成前に、ユーザーに対して他のアラートがトリガーされました。 その場合は、ユーザーが侵害されたことを示している可能性があります。
  - アラートが他のアラートと関連付けてインシデントを示す場合、インシデントには他の正のアラートが含まれていますか?

## <a name="advanced-hunting-queries"></a>高度なハンティング クエリ

[高度なハンティング](advanced-hunting-overview.md) は、ネットワーク内のイベントを調べて脅威インジケーターを見つけ出すクエリベースの脅威検出ツールです。

このクエリを実行して、特定の時間枠内のすべての新しい受信トレイ ルール イベントを検索します。

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

*RuleConfig* にはルール構成が含まれます。

このクエリを実行して、ユーザーの履歴を調べて、ISP がユーザーに共通かどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

このクエリを実行して、ユーザーの履歴を調べて、国がユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

このクエリを実行して、ユーザーの履歴を調べて、ユーザーエージェントがユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

このクエリを実行して、他のユーザーが同じ宛先に転送ルールを作成したかどうかを確認します (他のユーザーも侵害されている可能性があります)。

```kusto
let start_date = now(-10h);
let end_date = now();
let dest_email = ""; // enter here destination email as seen in the alert
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
| where RuleConfig has dest_email
```

## <a name="recommended-actions"></a>推奨処理

1. 悪意のある受信トレイルールを無効にします。
2. ユーザーのアカウント資格情報をリセットします。 また、Azure Active Directory (Azure AD) Identity Protection からセキュリティシグナルを取得するMicrosoft Defender for Cloud Appsでユーザー アカウントが侵害されているかどうかを確認することもできます。
3. 影響を受けたユーザーによって実行された他の悪意のあるアクティビティを検索します。
4. テナント内の他の疑わしいアクティビティが、同じ IP または同じ ISP から発信されたことを確認します (ISP が一般的でない場合)。

## <a name="see-also"></a>関連項目

- [アラートの採点の概要](alert-grading-playbooks.md)
- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [アラートの調査](investigate-alerts.md)
