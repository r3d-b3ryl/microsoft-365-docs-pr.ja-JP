---
title: 不審な受信トレイ操作ルールのアラート の評価
description: 不審な受信トレイ操作ルールに関する警告の評価を行い、アラートを確認し、推奨されるアクションを実行して攻撃を修復し、ネットワークを保護します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: e1bfb37ebf88ffd67a7fcfaddde46141583fb717
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524095"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>不審な受信トレイ操作ルールのアラート の評価

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威アクターは、ユーザーの受信トレイでメールを読み取る、外部アカウントにメールを転送するための受信トレイ ルールの作成、トレースの削除、フィッシング メールの送信など、多くの悪意のある目的で侵害されたユーザー アカウントを使用できます。 悪意のある受信トレイ ルールは、ビジネス メール侵害 (BEC) やフィッシング キャンペーンの間に一般的であり、一貫して監視することが重要です。 

このプレイブックは、攻撃者によって構成された不審な受信トレイ操作ルールに関連するインシデントを調査し、攻撃を修復してネットワークを保護するために推奨されるアクションを実行するのに役立ちます。 このプレイブックは、セキュリティ 運用センター (SOC) アナリストや、アラートを確認、調査、および評価する IT 管理者を含むセキュリティ チーム向けです。 アラートを True Positive (TP) または False Positive (TP) として迅速に評価し、攻撃を修復するために TP アラートに対して推奨されるアクションを実行できます。 

このプレイブックを使用した結果は次のとおりです。

- 受信トレイ操作ルールに関連付けられているアラートは、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別されています。

  悪意のある場合は、悪意のある受信トレイ操作ルールを削除しました。

- 電子メールが悪意のある電子メール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="inbox-manipulation-rules"></a>受信トレイの操作ルール

受信トレイ ルールは、定義済みの条件に基づいて電子メール メッセージを自動的に管理するために設定されます。 たとえば、受信トレイ ルールを作成して、すべてのメッセージをマネージャーから別のフォルダーに移動したり、受信したメッセージを別のメール アドレスに転送することができます。

### <a name="malicious-inbox-manipulation-rules"></a>悪意のある受信トレイ操作ルール

攻撃者は、侵害されたユーザー メールボックス内の受信メールを非表示にし、悪意のあるアクティビティをユーザーから隠す電子メール ルールを設定する可能性があります。 また、侵害されたユーザー メールボックスのルールを設定して、メールを削除したり、メールを別の目立たないフォルダー (RSS など) に移動したり、メールを外部アカウントに転送したりすることもできます。 一部のルールでは、すべてのメールを別のフォルダーに移動して"読み取り" としてマークする場合があります。一部のルールでは、電子メール メッセージまたは件名に特定のキーワードが含まれるメールのみを移動する場合があります。 

たとえば、受信トレイ ルールを設定して、"請求書"、"フィッシング"、"返信しない"、"疑わしいメール"、"スパム" など、キーワードを検索し、外部メール アカウントに移動します。 攻撃者は、侵害されたユーザー メールボックスを使用してスパム、フィッシングメール、マルウェアを配布する場合もあります。 

## <a name="workflow"></a>ワークフロー

不審な受信トレイ操作ルールのアクティビティを特定するワークフローを次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="受信トレイ操作ルールのアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::


## <a name="investigation-steps"></a>調査手順

このセクションには、インシデントに対応し、組織をさらなる攻撃から保護するための推奨手順を実行するための詳細な手順が含まれます。

### <a name="1-review-the-alerts"></a>1. アラートを確認する

アラート キュー内の受信トレイ操作ルールアラートの例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="受信トレイ操作ルールの例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

悪意のある受信トレイ操作ルールによってトリガーされたアラートの詳細の例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="悪意のある受信トレイ操作ルールによってトリガーされたアラートの詳細" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::


### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. 受信トレイ操作ルールのパラメーターを調査する 

次のルール パラメーターまたは条件に従って、ルールが疑わしいと見えるかどうかを判断します。

- キーワード

   攻撃者は、特定の単語を含む電子メールにのみ操作ルールを適用する可能性があります。 これらのキーワードは、"BodyContainsWords"、"SubjectContainsWords"、"SubjectOrBodyContainsWords" などの特定の属性の下に表示されます。 

   キーワードによるフィルター処理がある場合は、キーワードが疑わしいと思われるかどうかを確認します (一般的なシナリオは、"フィッシング"、"スパム"、"返信しない" など、攻撃者のアクティビティに関連するメールをフィルター処理するシナリオです)。

   フィルターが全くない場合は、疑わしい場合もあります。

- 移動先フォルダー

   セキュリティ検出を回避するために、攻撃者は電子メールを目立たないフォルダーに移動し、電子メールを読み取り (たとえば"RSS" フォルダー) としてマークする可能性があります。 攻撃者が "MoveToFolder" アクションと "MarkAsRead" アクションを適用する場合は、対象フォルダーがルール内のキーワードに何らかの形で関連付けされているかどうかを確認して、疑わしいと思われるかどうかを判断します。 

- すべて削除する

   一部の攻撃者は、すべての受信メールを削除してアクティビティを非表示にします。 主に、キーワードでフィルターを適用せずに"すべての受信メールを削除する" というルールは、悪意のあるアクティビティの指標です。 
 
関連するイベント ログの "すべての受信メールを削除する" ルール構成の例を次に示します (RawEventData.Parameters を参照)。 

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="すべての受信メールの削除ルール構成の例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::


### <a name="3-investigate-the-ip-address"></a>3. IP アドレスを調査する

ルール作成の関連イベントを実行した IP アドレスの属性を確認します。

- テナント内の同じ IP から発生した他の疑わしいクラウド アクティビティを検索します。 たとえば、疑わしいアクティビティは複数の失敗したログイン試行である可能性があります。 
- ISP は一般的で、このユーザーに対して妥当ですか?
- このユーザーの場所は一般的で妥当ですか?

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. ルールを作成する前に、ユーザーが疑わしいアクティビティを調査する

ルールが作成される前に、すべてのユーザー アクティビティを確認し、侵害の指標を確認し、疑わしいと思われるユーザーアクションを調査できます。 

たとえば、複数の失敗したログインの場合は、次の内容を確認します。 

- ログイン アクティビティ 

   ルールの作成前のログイン アクティビティが疑わしいではないか検証します。 (共通の場所 / ISP / ユーザー エージェント)。 

- アラート

   ルールを作成する前に、ユーザーが通知を受け取ったかどうかを確認します。 これは、ユーザー アカウントが侵害されている可能性を示している可能性があります。 たとえば、不可能な旅行アラート、まれな国、複数の失敗したログインなど)。

- インシデント

   アラートがインシデントを示す他のアラートに関連付けられているかどうかを確認します。 その場合は、インシデントに他の正のアラートが含まれているかどうかを確認します。

## <a name="advanced-hunting-queries"></a>高度な検索クエリ

[Advanced Hunting](advanced-hunting-overview.md) はクエリベースの脅威検出ツールで、ネットワーク内のイベントを検査して脅威インジケーターを特定できます。 

このクエリを使用して、特定のタイム ウィンドウですべての新しい受信トレイ ルール イベントを検索します。  

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

[ *RuleConfig]* 列には、新しい受信トレイ ルールの構成が表示されます。

このクエリを使用して、ユーザーの履歴を確認して、ISP がユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP 
```

このクエリを使用して、ユーザーの履歴を確認して、国がユーザーに共通であるかどうかを確認します。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

このクエリを使用して、ユーザーの履歴を確認して、ユーザー エージェントがユーザーに共通であるかどうかを確認します。

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

1. 悪意のある受信トレイ ルールを無効にします。
2. ユーザー アカウントの資格情報をリセットします。 また、Microsoft Defender for Cloud Apps でユーザー アカウントが侵害されたのか確認することもできます。これは、Azure Active Directory (Azure AD) ID Protection からセキュリティ信号を取得します。
3. 影響を受け取ったユーザー アカウントによって実行される他の悪意のあるアクティビティを検索します。
4. 同じ IP または同じ ISP (ISP が一般的でない場合) から発生したテナント内の他の疑わしいアクティビティを確認して、他の侵害されたユーザー アカウントを検索します。

## <a name="see-also"></a>関連項目

- [アラート の評価の概要](alert-grading-playbooks.md)
- [疑わしいメール転送アクティビティ](alert-grading-playbook-email-forwarding.md)
- [疑わしい受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)
- [アラートの調査](investigate-alerts.md)
