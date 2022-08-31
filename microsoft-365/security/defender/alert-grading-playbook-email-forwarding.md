---
title: 疑わしいメール転送アクティビティのアラートの採点
description: アラートを確認し、攻撃を修復し、ネットワークを保護するための推奨されるアクションを実行する、疑わしい電子メール転送アクティビティのアラート の採点。
keywords: インシデント、アラート、調査、分析、応答、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 088cb74f16fae1155b86b1bfa6b5c72aae287720
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482100"
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>疑わしいメール転送アクティビティのアラートの採点

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威アクターは、侵害されたユーザー アカウントを、ユーザーの受信トレイのメールの読み取り、外部受信者へのメールの転送、フィッシングメールの送信など、悪意のある目的で使用できます。 対象ユーザーは、自分のメールが転送されていることを認識していない可能性があります。 これは、攻撃者がユーザー アカウントが侵害されたときに使用する非常に一般的な戦術です。

メールは、手動で転送することも、転送ルールを使用して自動的に転送することもできます。 自動転送は、受信トレイ ルール、Exchange トランスポート ルール (ETR)、SMTP 転送など、複数の方法で実装できます。 手動転送ではユーザーからの直接操作が必要ですが、自動転送されたすべてのメールに気づいていない可能性があります。 Microsoft 365 では、ユーザーが悪意のある可能性のある電子メール アドレスに電子メールを自動転送すると、アラートが発生します。

このプレイブックは、疑わしいEmail転送アクティビティ アラートを調査し、それらを真陽性 (TP) または偽陽性 (FP) として迅速に評価するのに役立ちます。 その後、TP アラートに対して推奨されるアクションを実行して、攻撃を修復できます。

Microsoft Defender for Office 365とMicrosoft Defender for Cloud Appsのアラートの評価の概要については、[概要記事](alert-grading-playbooks.md)を参照してください。

このプレイブックを使用した結果は次のとおりです。

- 自動転送された電子メールに関連付けられているアラートを、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別しました。

  悪意のある場合は、影響を受けるメールボックスの [電子メールの自動転送を停止](../office-365-security/external-email-forwarding.md) しました。

- メールが悪意のあるメール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="email-forwarding-rules"></a>Email転送ルール

Email転送ルールを使用すると、ユーザーは、ユーザーのメールボックスに送信された電子メール メッセージを組織内または外部の別のユーザーのメールボックスに転送するルールを作成できます。 一部のメール ユーザー (特に複数のメールボックスを持つユーザー) は、勤務先のメールを自分のプライベートメール アカウントに移動するように転送ルールを構成します。 Email転送は便利な機能ですが、情報が漏えいする可能性があるため、セキュリティ リスクを引き起こす可能性もあります。 攻撃者はこの情報を使用して、組織またはそのパートナーを攻撃する可能性があります。

### <a name="suspicious-email-forwarding-activity"></a>疑わしいメール転送アクティビティ

攻撃者は、侵害されたユーザー メールボックス内の受信メールを非表示にして、悪意のあるアクティビティをユーザーから隠すために電子メール ルールを設定する可能性があります。 また、侵害されたユーザー メールボックスにルールを設定して、メールを削除したり、RSS フォルダーなどの目立たない別のフォルダーにメールを移動したり、外部アカウントに電子メールを転送したりすることもできます。

一部のルールでは、すべてのメールを別のフォルダーに移動して "読み取り" としてマークすることがありますが、一部のルールでは、電子メール メッセージまたは件名に特定のキーワードを含むメールのみが移動される場合があります。 たとえば、受信トレイルールは、"invoice"、"フィッシング"、"返信しない"、"疑わしいメール"、または "スパム" などのキーワードを検索し、外部メール アカウントに移動するように設定できます。 攻撃者は、侵害されたユーザー メールボックスを使用して、スパム、フィッシングメール、またはマルウェアを配布する可能性もあります。

Microsoft Defender for Office 365は、疑わしいメール転送ルールを検出してアラートを送信できるため、ソースで非表示のルールを見つけて削除できます。

詳細については、次のブログ記事を参照してください。

- [ビジネス Email侵害](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [ビジネス メール侵害の背景: クロスドメインの脅威データを使用して大規模な BEC キャンペーンを中断する](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)

## <a name="alert-details"></a>アラートの詳細

不審なEmail転送アクティビティ アラートを確認するには、[**アラート]** ページを開き、[**アクティビティの一覧**] セクションを表示します。 次に例を示します。

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="アラートに関連するアクティビティの一覧" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

[ **アクティビティ]**  を選択すると、サイドバーでそのアクティビティの詳細が表示されます。 次に例を示します。

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="アクティビティの詳細" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

**[理由**] フィールドには、このアラートに関連する次の情報が含まれています。

- 転送の種類 (FT) は、次のいずれかです。
  - Exchange トランスポート ルール (ETR): Exchange トランスポート ルールを使用して転送
  - SMTP: メールボックス転送を使用して転送される
  - InboxRule: 受信トレイルールを使用して転送される

- メッセージ トレース ID (MTI): これは、このアラートをトリガーした転送された電子メールの識別子 (NetworkMessageId) です。 NetworkMessageId は、組織内のメールの一意の識別子です。
- フォワーダー (F): このメールを転送したユーザー。
- 不審な受信者リスト (SRL): この電子メールで疑わしいと見なされた受信者の一覧。
- 受信者リスト (RL): この電子メール内のすべての受信者の一覧。

## <a name="investigation-workflow"></a>調査ワークフロー

このアラートの調査中に、次のことを確認する必要があります。

- ユーザー アカウントとそのメールボックスは侵害されていますか?
- アクティビティは悪意がありますか?

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>ユーザー アカウントとそのメールボックスは侵害されていますか?

送信者の過去の動作と最近のアクティビティを見ることで、ユーザーのアカウントが侵害されたと見なされるかどうかを判断できる必要があります。 ユーザーのページから発生したアラートの詳細は、Microsoft 365 Defender ポータルで確認できます。

影響を受けるメールボックスに対して、次の追加アクティビティを分析することもできます。

- 脅威エクスプローラーを使用して電子メール関連の脅威を理解する
  - 送信者から送信された最近送信されたメールの数がフィッシング、スパム、またはマルウェアとして検出されたことを確認します。
  - 送信された電子メールの数に機密情報が含まれているかどうかを確認します。

- Microsoft Azure portalでの危険なサインイン動作を評価します。
- ユーザーのデバイス上の悪意のあるアクティビティを確認します。

### <a name="are-the-activities-malicious"></a>アクティビティは悪意がありますか?

電子メール転送アクティビティを調査します。 たとえば、電子メールの種類、この電子メールの受信者、または電子メールの転送方法を確認します。

詳細については、次の記事を参照してください。

- [自動転送されたメッセージのインサイト](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [新しいユーザーがメールを転送していますのインサイト](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [侵害された電子メール アカウントへの対応](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [Outlook の誤検出と検出漏れを報告する](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

疑わしいメール転送アクティビティを識別するワークフローを次に示します。

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="電子メール転送のアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

Microsoft 365 Defender ポータルの機能の可用性に基づいて、Threat Explorer または高度なハンティング クエリを使用して、電子メール転送アラートを調査できます。 必要に応じて、プロセス全体またはプロセスの一部に従うことを選択できます。

## <a name="using-threat-explorer"></a>脅威エクスプローラーの使用

脅威エクスプローラーは、電子メール関連の脅威に対する対話型の調査エクスペリエンスを提供し、このアクティビティが疑わしいかどうかを判断します。 アラート情報から次のインジケーターを使用できます。

- SRL/RL: (疑わしい) 受信者リスト (SRL) を使用して、次の詳細を検索します。

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="受信者の一覧の例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

  - 他に誰がこれらの受信者に電子メールを転送しましたか?
  - これらの受信者に転送されたメールの数はどれくらいですか?
  - これらの受信者に電子メールが転送される頻度はどのくらいですか?

- MTI: メッセージ トレース ID/ネットワーク メッセージ ID を使用して、次の詳細を確認します。

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="ネットワーク メッセージ ID の例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

  - このメールで利用できるその他の詳細は何ですか? たとえば、件名、戻り値のパス、タイムスタンプなどです。
  - このメールの配信元は何ですか? 同様のメールはありますか?
  - この電子メールには URL が含まれていますか? URL は機密データを指していますか?
  - メールに添付ファイルは含まれていますか? 添付ファイルには機密情報が含まれていますか?
  - 電子メールに対して実行されたアクションは何ですか? 削除されたか、読み取りとしてマークされているか、別のフォルダーに移動されましたか?
  - このメールに関連付けられている脅威はありますか? このメールはキャンペーンの一部ですか?

これらの質問に対する回答に基づいて、電子メールが悪意があるか、無害であるかを判断できる必要があります。

## <a name="advanced-hunting-queries"></a>高度なハンティング クエリ

[高度なハンティング](advanced-hunting-overview.md) クエリを使用してアラートに関連する情報を収集し、アクティビティが疑わしいかどうかを判断するには、次の表にアクセスできることを確認します。

- EmailEvents - 電子メール フローに関連する情報が含まれています。

- EmailUrlInfo - 電子メールの URL に関連する情報が含まれています。

- CloudAppEvents -ユーザー アクティビティの監査ログが含まれます。

- IdentityLogonEvents - すべてのユーザーのログイン情報が含まれています。

> [!NOTE]
> 特定のパラメーターは、組織またはネットワークに固有です。 各クエリの指示に従って、これらの特定のパラメーターを入力します。

このクエリを実行して、他のユーザーがこれらの受信者 (SRL/RL) に電子メールを転送したかを確認します。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| distinct SenderDisplayName, SenderFromAddress, SenderObjectId
```

このクエリを実行して、これらの受信者に転送されたメールの数を確認します。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress
```

このクエリを実行して、これらの受信者に電子メールが転送される頻度を確認します。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress, bin(Timestamp, 1d)
```

このクエリを実行して、電子メールに URL が含まれているかどうかを確認します。

```kusto
let mti='{MTI}'; //Replace {MTI} with MTI from alert
EmailUrlInfo
| where NetworkMessageId == mti
```

このクエリを実行して、電子メールに添付ファイルが含まれているかどうかを確認します。

   ```kusto
   let mti='{MTI}'; //Replace {MTI} with MTI from alert
   EmailAttachmentInfo
   | where NetworkMessageId == mti
   ```

フォワーダー (送信者) が新しいルールを作成したかどうかを調べるには、このクエリを実行します。

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with display name of Forwarder
let action_types = pack_array(
    "New-InboxRule",
    "UpdateInboxRules",
    "Set-InboxRule",
    "Set-Mailbox",
    "New-TransportRule",
    "Set-TransportRule");
CloudAppEvents
| where AccountDisplayName == sender
| where ActionType in (action_types)
```

このクエリを実行して、このユーザーから異常なログイン イベントが発生したかどうかを確認します。 たとえば、不明な IP、新しいアプリケーション、一般的でない国、複数の LogonFailed イベントなどです。

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder
IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>転送ルールの調査

また、Exchange 管理センターを使用して、ルールの種類 (アラートの FT 値) に基づいて、疑わしい転送ルールを検索することもできます。

- ETR

  Exchange トランスポート ルールは、[ **ルール]** セクションに一覧表示されます。 すべてのルールが想定どおりに動作することを確認します。

- SMTP

  メールボックス転送ルールは、送信者のメールボックス **\> [メール フローの管理] 設定\>Email [転送\>の編集**] を選択して確認できます。

- InboxRule

  受信トレイルールは、電子メール クライアントで構成されます。 [Get-InboxRule](/powershell/module/exchange/get-inboxrule) PowerShell コマンドレットを使用して、ユーザーによって作成された受信トレイルールを一覧表示できます。

### <a name="additional-investigation"></a>追加の調査

これまでに検出された証拠と共に、新しい転送ルールが作成されているかどうかを判断できます。 ルールに関連付けられている IP アドレスを調査します。 異常な IP アドレスではなく、ユーザーが実行する通常のアクティビティと一致していることを確認します。

## <a name="recommended-actions"></a>推奨処理

関連するアクティビティによってこのアラートが True Positive になると判断したら、アラートを分類し、修復のために次のアクションを実行します。

1. 受信トレイ転送ルールを無効にして削除します。
2. InboxRule 転送の種類の場合は、ユーザーのアカウント資格情報をリセットします。
3. SMTP または ETR 転送の種類については、アラートを作成したユーザー アカウントのアクティビティを調査します。

    - その他の疑わしい管理者アクティビティを調査します。

    - ユーザー アカウントの資格情報をリセットします。

4. 影響を受けたアカウント、IP アドレス、疑わしい送信者から発生したその他のアクティビティを確認します。

## <a name="see-also"></a>関連項目

- [アラートの採点の概要](alert-grading-playbooks.md)
- [疑わしい受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [アラートの調査](investigate-alerts.md)
