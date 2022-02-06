---
title: 疑わしいメール転送アクティビティのアラート の評価
description: 不審なメール転送アクティビティのアラート の評価を行い、アラートを確認し、推奨されるアクションを実行して攻撃を修復し、ネットワークを保護します。
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
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>疑わしいメール転送アクティビティのアラート の評価

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威のアクターは、ユーザーの受信トレイ内のメールの読み取り、外部受信者へのメールの転送、フィッシング メールの送信など、いくつかの悪意のある目的で侵害されたユーザー アカウントを使用できます。 対象となるユーザーは、自分のメールが転送されているのに気づいていない可能性があります。 これは、ユーザー アカウントが侵害された場合に攻撃者が使用する非常に一般的な方法です。

電子メールは、転送ルールを使用して手動または自動的に転送できます。 自動転送は、受信トレイ ルール、トランスポート ルール (ETR)、SMTP 転送Exchange複数の方法で実装できます。 手動転送ではユーザーからの直接操作が必要ですが、自動転送された電子メールのすべてが認識されない場合があります。 このMicrosoft 365、ユーザーが悪意のある可能性のある電子メール アドレスに電子メールを自動転送すると、アラートが発生します。

このプレイブックは、不審なメール転送アクティビティアラートを調査し、それらを True Positive (TP) または False Positive (FP) として迅速に評価するのに役立ちます。 その後、TP アラートに対して推奨されるアクションを実行して、攻撃を修復できます。

Microsoft Defender for Office 365および Microsoft Defender for Cloud Apps のアラート の評価の概要については、概要記事を[参照してください](alert-grading-playbooks.md)。

このプレイブックを使用した結果は次のとおりです。

- 自動転送された電子メールに関連付けられているアラートは、悪意のある (TP) アクティビティまたは良性 (FP) アクティビティとして識別されています。

  悪意のある場合は、影響を受 [けるメールボックスの](../office-365-security/external-email-forwarding.md) 電子メールの自動転送を停止しました。

- 電子メールが悪意のある電子メール アドレスに転送されている場合は、必要なアクションを実行しました。

## <a name="email-forwarding-rules"></a>メール転送ルール

メール転送ルールを使用すると、ユーザーは、ユーザーのメールボックスに送信された電子メール メッセージを組織の内部または外部の別のユーザーのメールボックスに転送するルールを作成できます。 一部の電子メール ユーザー(特に複数のメールボックスを持つユーザー)は、雇用主の電子メールをプライベートメール アカウントに移動する転送ルールを構成します。 電子メール転送は便利な機能ですが、情報の開示が発生する可能性があるため、セキュリティリスクを引き起す可能性があります。 攻撃者は、この情報を使用して組織またはパートナーを攻撃する可能性があります。

### <a name="suspicious-email-forwarding-activity"></a>疑わしいメール転送アクティビティ

攻撃者は、侵害されたユーザー メールボックス内の受信メールを非表示にし、悪意のあるアクティビティをユーザーから隠す電子メール ルールを設定する可能性があります。 また、侵害されたユーザー メールボックスにルールを設定して、メールを削除したり、RSS フォルダーなどの目立たない別のフォルダーにメールを移動したり、メールを外部アカウントに転送したりすることもできます。  

一部のルールでは、すべてのメールを別のフォルダーに移動して"読み取り" としてマークする場合があります。一部のルールでは、電子メール メッセージまたは件名に特定のキーワードが含まれるメールのみを移動する場合があります。 たとえば、受信トレイ ルールを設定して、"請求書"、"フィッシング"、"返信しない"、"疑わしいメール"、"スパム" など、キーワードを検索し、外部メール アカウントに移動します。 攻撃者は、侵害されたユーザー メールボックスを使用してスパム、フィッシングメール、マルウェアを配布する場合もあります。
 
Microsoft Defender for Office 365疑わしいメール転送ルールを検出して通知することができ、ソースで非表示のルールを見つけて削除できます。

詳細については、次のブログ投稿を参照してください。

- [ビジネスメールの侵害](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [ビジネスメール侵害の舞台裏:ドメイン間の脅威データを使用して大規模な BEC キャンペーンを中断する](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)


## <a name="alert-details"></a>アラートの詳細

[不審なメール転送アクティビティ] アラートを確認するには、[通知] ページ **を開** き、[アクティビティ一覧 **] セクションを表示** します。 次に例を示します。
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="アラートに関連するアクティビティの一覧" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

[ **アクティビティ] を**  選択して、そのアクティビティの詳細をサイドバーに表示します。 次に例を示します。
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="アクティビティの詳細" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

[ **理由]** フィールドには、このアラートに関連する次の情報が含まれます。

- 転送の種類 (FT) は、次のいずれかの方法です。

    -  Exchange トランスポート ルール (ETR): トランスポート ルールを使用Exchange転送 

    -  SMTP: メールボックス転送を使用して転送する

    -  InboxRule: 受信トレイ ルールを使用して転送される

- メッセージ トレース ID (MTI): これは、このアラートをトリガーした転送された電子メールの識別子 (NetworkMessageId) です。 NetworkMessageId は、組織内の電子メールの一意の識別子です。
- フォスター (F): このメールを転送したユーザー。
- 不審な受信者一覧 (SRL): この電子メールで疑わしいと見なされる受信者の一覧。
- 受信者一覧 (RL): この電子メール内のすべての受信者の一覧。

## <a name="investigation-workflow"></a>調査ワークフロー

このアラートの調査中に、次の情報を確認する必要があります。

- ユーザー アカウントとそのメールボックスが侵害されていますか?
- アクティビティは悪意がありますか?

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>ユーザー アカウントとそのメールボックスが侵害されていますか?

送信者の過去の動作と最近のアクティビティを見て、ユーザーのアカウントが侵害されたと見なされるかどうかを判断できる必要があります。 ユーザーのページから発生したアラートの詳細は、ポータルのMicrosoft 365 Defenderできます。 

また、影響を受けるメールボックスに対して次の追加アクティビティを分析できます。

- 脅威エクスプローラーを使用して電子メール関連の脅威を理解する

    - 送信者から送信された最近送信されたメールの数が、フィッシング、スパム、マルウェアとして検出された数を確認します。

    - 送信されたメールの中に機密情報が含まれているメールの数を確認します。 

- ポータルで危険なサインイン動作をMicrosoft Azureします。
- ユーザーのデバイス上の悪意のあるアクティビティを確認します。

### <a name="are-the-activities-malicious"></a>アクティビティは悪意がありますか?

メール転送アクティビティを調査します。 たとえば、メールの種類、このメールの受信者、またはメールの転送方法を確認します。 

詳細については、次の資料を参照してください。

- [自動転送されたメッセージのインサイト](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [新しいユーザーがメールを転送していますのインサイト](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [侵害された電子メール アカウントへの対応](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [Outlook の誤検出と検出漏れを報告する](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

疑わしいメール転送アクティビティを識別するワークフローを次に示します。

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="メール転送のアラート調査ワークフロー" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

脅威エクスプローラーを使用して、または高度な検索クエリを使用して、電子メール転送アラートを調査できます。このポータルの機能の可用性にMicrosoft 365 Defenderできます。 必要に応じて、プロセス全体またはプロセスの一部に従います。

## <a name="using-threat-explorer"></a>脅威エクスプローラーの使用

Threat Explorer は、電子メール関連の脅威に対する対話的な調査エクスペリエンスを提供し、このアクティビティが疑わしいかどうかを判断します。 アラート情報から次のインジケーターを使用できます。

- SRL/RL: (疑わしい) 受信者一覧 (SRL) を使用して、次の詳細を確認します。
 
    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="受信者の一覧の例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

    - Who受信者にメールを転送した場合

    - これらの受信者に転送されたメールの数。

    - これらの受信者に送信される電子メールの頻度
 

- MTI: メッセージ トレース ID/ネットワーク メッセージ ID を使用して、次の詳細を確認します。

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="ネットワーク メッセージ ID の例" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

    - このメールに使用できるその他の詳細は何ですか? たとえば、件名、戻り値のパス、タイムスタンプなどです。

    - このメールの配信元は何ですか? 類似のメールはありますか?

    - このメールには URL が含まれているか。 URL は機密データを指していますか?

    - 電子メールに添付ファイルが含まれているか。 添付ファイルに機密情報が含まれているか。

    - メールに対して実行されたアクションは何ですか? 削除されたか、読み取り済みとしてマークされたか、または別のフォルダーに移動されましたか?

    - このメールに関連付けられている脅威はありますか? このメールはキャンペーンの一部ですか?

これらの質問に対する回答に基づいて、電子メールが悪意のあるか良性かを判断できる必要があります。

## <a name="advanced-hunting-queries"></a>高度な検索クエリ

高度な [ハンティング クエリ](advanced-hunting-overview.md) を使用して、アラートに関連する情報を収集し、アクティビティが疑わしいかどうかを判断するには、次の表にアクセスできます。

- EmailEvents - メール フローに関連する情報が含まれる。

- EmailUrlInfo - メール内の URL に関連する情報が含まれる。

- CloudAppEvents -ユーザー アクティビティの監査ログが含まれます。

- IdentityLogonEvents - すべてのユーザーのログイン情報が含まれる。

>[!Note]
>特定のパラメーターは、組織またはネットワークに固有です。 各クエリの指示に従って、これらの特定のパラメーターを入力します。
>

このクエリを実行して、他のユーザーがこれらの受信者 (SRL/RL) にメールを転送したユーザーを確認します。

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

このクエリを実行して、これらの受信者に転送される電子メールの頻度を確認します。

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress, bin(Timestamp, 1d)
```

このクエリを実行して、メールに URL が含まれているか確認します。
 
```kusto
let mti='{MTI}'; //Replace {MTI} with MTI from alert
EmailUrlInfo
| where NetworkMessageId == mti
```

このクエリを実行して、メールに添付ファイルが含まれているか確認します。

   ```kusto
   let mti='{MTI}'; //Replace {MTI} with MTI from alert
   EmailAttachmentInfo
   | where NetworkMessageId == mti
   ```

このクエリを実行して、Forwarder (送信者) が新しいルールを作成したのか確認します。

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

このクエリを実行して、このユーザーから異常なログイン イベントが発生した場合に確認します。 たとえば、不明な AP、新しいアプリケーション、一般的でない国、複数の LogonFailed イベントなどです。

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>転送ルールの調査

また、ルールの種類 (アラートの FT 値) に基づいて、Exchange管理センターを使用して不審な転送ルールを検索することもできます。

- ETR 

  Exchangeトランスポート ルールは、[ルール] セクションに **一覧表示** されます。 すべてのルールが期待通りである必要があります。

- SMTP

  送信者のメールボックスを選択すると、メールボックス転送ルールを **\>\>確認できます メール フローの設定を管理する メール転送の編集\>**。

- InboxRule

  受信トレイ ルールは、電子メール クライアントで構成されます。 [Get-InboxRule](/powershell/module/exchange/get-inboxrule) PowerShell コマンドレットを使用して、ユーザーが作成した受信トレイ ルールを一覧表示できます。

### <a name="additional-investigation"></a>追加の調査

これまでに検出された証拠と共に、新しい転送ルールが作成されるかどうかを判断できます。 ルールに関連付けられている IP アドレスを調査します。 異常な IP アドレスではなく、ユーザーが実行する通常のアクティビティと一致している必要があります。

## <a name="recommended-actions"></a>推奨処理

関連付けられたアクティビティによってこのアラートが True Positive に設定されたと判断したら、アラートを分類し、修復のために次のアクションを実行します。

1. 受信トレイ転送ルールを無効にして削除します。
2. InboxRule 転送タイプの場合は、ユーザーのアカウント資格情報をリセットします。
3. SMTP または ETR 転送の種類については、アラートを作成したユーザー アカウントのアクティビティを調査します。

    - その他の疑わしい管理アクティビティを調査します。

    - ユーザー アカウントの資格情報をリセットします。

4. 影響を受け取ったアカウント、IP アドレス、疑わしい送信者から発生したその他のアクティビティを確認します。

## <a name="see-also"></a>関連項目

- [アラート の評価の概要](alert-grading-playbooks.md)
- [疑わしい受信トレイ転送ルール](alert-grading-playbook-inbox-forwarding-rules.md)
- [疑わしい受信トレイ操作ルール](alert-grading-playbook-inbox-manipulation-rules.md)
- [アラートの調査](investigate-alerts.md)
