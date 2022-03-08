---
title: 不審な受信トレイ転送ルールのアラート の評価
description: 不審な受信トレイ転送ルールに関するアラート の評価を行い、アラートを確認し、推奨されるアクションを実行して攻撃を修復し、ネットワークを保護します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
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
ms.openlocfilehash: 08178a1672e3bdd5b124138f698b42be8181373a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325503"
---
# <a name="alert-grading-for-suspicious-inbox-forwarding-rules"></a>不審な受信トレイ転送ルールのアラート の評価

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威のアクターは、ユーザーの受信トレイでメールを読み取る、メールを外部アカウントに転送するための受信トレイ ルールの作成、フィッシング メールの送信など、いくつかの悪意のある目的で、侵害されたユーザー アカウントを使用できます。 悪意のある受信トレイ ルールは、ビジネス メール侵害 (BEC) やフィッシング キャンペーンの間に広く一般的であり、それらを一貫して監視することが重要です。

このプレイブックは、不審な受信トレイ転送ルールに関するアラートを調査し、それらを True Positive (TP) または False Positive (TP) として迅速に評価するのに役立ちます。 その後、TP アラートに対して推奨されるアクションを実行して、攻撃を修復できます。 

Microsoft Defender for Office 365および Microsoft Defender for Cloud Apps のアラート の評価の概要については、概要記事を[参照してください](alert-grading-playbooks.md)。

このプレイブックを使用した結果は次のとおりです。

- 受信トレイ転送ルールに関連付けられているアラートは、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別されています。

  悪意のある場合は、悪意のある受信トレイ転送ルールを削除しました。

- 電子メールが悪意のある電子メール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="inbox-forwarding-rules"></a>受信トレイ転送ルール

受信トレイ ルールを構成して、定義済みの条件に基づいて電子メール メッセージを自動的に管理します。 たとえば、受信トレイ ルールを作成して、すべてのメッセージをマネージャーから別のフォルダーに移動したり、受信したメッセージを別のメール アドレスに転送することができます。

### <a name="suspicious-inbox-forwarding-rules"></a>疑わしい受信トレイ転送ルール

ユーザーのメールボックスにアクセスした後、攻撃者はしばしば受信トレイ ルールを作成し、機密データを外部の電子メール アドレスに引き出し、悪意のある目的で使用することができます。 

悪意のある受信トレイ ルールは、exfiltration プロセスを自動化します。 特定のルールでは、ルール条件に一致するターゲット ユーザーの受信トレイ内のすべての電子メールが攻撃者のメールボックスに転送されます。 たとえば、攻撃者が財務に関連する機密データを収集する場合があります。 受信トレイ ルールを作成して、件名やメッセージ本文の 'finance' や 'invoice' などのキーワードを含むすべてのメールをメールボックスに転送します。

不審な受信トレイ転送ルールは、受信トレイ ルールのメンテナンスがユーザーによって行われる一般的なタスクなので、検出が非常に困難な場合があります。 したがって、アラートを監視することが重要です。 

## <a name="workflow"></a>ワークフロー

疑わしいメール転送ルールを識別するワークフローを次に示します。
 
:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png" alt-text="受信トレイ転送ルールのアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png":::

## <a name="investigation-steps"></a>調査手順

このセクションには、インシデントに対応し、組織をさらなる攻撃から保護するための推奨手順を実行するための詳細な手順が含まれます。

### <a name="review-generated-alerts"></a>生成されたアラートを確認する

アラート キュー内の受信トレイ転送ルールアラートの例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png" alt-text="アラート キュー内の通知の例" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png":::

悪意のある受信トレイ転送ルールによってトリガーされたアラートの詳細の例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png" alt-text="悪意のある受信トレイ転送ルールによってトリガーされたアラートの詳細" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png":::

### <a name="investigate-rule-parameters"></a>ルール パラメーターの調査 

この段階の目的は、ルールが特定の条件によって疑わしいと見えるかどうかを判断します。

転送ルールの受信者:

- 宛先メール アドレスが同じユーザーが所有する追加のメールボックスではない (ユーザーが個人用メールボックス間で電子メールを自己転送する場合を避ける) ことを検証します。 
- 宛先の電子メール アドレスが、会社に属する内部アドレスまたはサブドメインではないか検証します。

フィルター:
 
- 受信トレイ ルールにメールの件名または本文の特定のキーワードを検索するフィルターが含まれている場合は、提供されたキーワード (財務、資格情報、ネットワークなど) が悪意のあるアクティビティに関連しているように見えるかどうかを確認します。 これらのフィルターは、次の属性 (イベント RawEventData 列に表示されます): "BodyContainsWords"、"SubjectContainsWords" または "SubjectOrBodyContainsWords" の下に表示されます。
- 攻撃者がメールにフィルターを設定しない場合、受信トレイ ルールによってすべてのメールボックス アイテムが攻撃者のメールボックスに転送される場合、この動作も疑わしい場合があります。 

### <a name="investigate-ip-address"></a>IP アドレスの調査

ルール作成の関連イベントを実行した IP アドレスに関連する属性を確認します。

1. テナント内の同じ IP から発生した他の疑わしいクラウド アクティビティを検索します。 たとえば、疑わしいアクティビティは、複数の失敗したログイン試行である可能性があります。 
2. ISP は一般的で、このユーザーに対して妥当ですか?
3. このユーザーの場所は一般的で妥当ですか?

### <a name="investigate-any-suspicious-activity-with-the-user-inbox-before-creating-rules"></a>ルールを作成する前に、ユーザーの受信トレイで疑わしいアクティビティを調査する

ルールを作成する前に、すべてのユーザー アクティビティを確認し、侵害の指標を確認し、疑わしいと思われるユーザーアクションを調査できます。 たとえば、複数の失敗したサインイン。  

- サインイン: 

  ルール作成イベントの前のサインイン アクティビティが疑わしからなく (共通の場所、ISP、ユーザー エージェントなど) 検証します。 

- その他のアラートまたはインシデント 

   - ルールの作成前に、ユーザーに対して他のアラートがトリガーされた。 その場合は、ユーザーが侵害された可能性があります。 

   - アラートが他のアラートと関連付いてインシデントを示している場合、インシデントには他の正の正のアラートが含まれているか。 

## <a name="advanced-hunting-queries"></a>高度な検索クエリ

[Advanced Hunting](advanced-hunting-overview.md) は、ネットワーク内のイベントを検査し、脅威インジケーターを見つけ出すクエリ ベースの脅威検出ツールです。 

このクエリを実行して、特定のタイム ウィンドウですべての新しい受信トレイ ルール イベントを検索します。  

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

*RuleConfig* には、ルール構成が含まれる。

このクエリを実行して、ユーザーの履歴を確認して、ISP がユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 30d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP 
```

このクエリを実行して、ユーザーの履歴を確認して、国がユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 30d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

このクエリを実行して、ユーザーの履歴を確認して、ユーザーエージェントがユーザーに共通であるかどうかを確認します。

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

1. 悪意のある受信トレイ ルールを無効にします。 
2. ユーザーのアカウント資格情報をリセットします。 また、ユーザー アカウントが Microsoft Defender for Cloud Apps で侵害されたのか確認することもできます。これは、Azure Active Directory (Azure AD) Id Protection からセキュリティ信号を取得します。
3. 影響を受け取ったユーザーが実行した他の悪意のあるアクティビティを検索します。
4. 同じ IP または同じ ISP (ISP が一般的でない場合) から発生したテナント内の他の疑わしいアクティビティを確認して、他の侵害されたユーザーを検索します。

## <a name="see-also"></a>関連項目

- [アラート の評価の概要](alert-grading-playbooks.md)
- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [アラートの調査](investigate-alerts.md)
