---
title: EOP のメール フロー ルール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: メール フロー ルール (トランスポート ルール) を使用して、組織を流れるメッセージを識別してアクションを実行できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ff4c723d0c7d8bba2e24ece1b62007f14198e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206270"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>スタンドアロン EOP のメール フロー ルール (トランスポート ルール)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、組織を流れるメッセージを識別して処理できます。

このトピックでは、メール フロー ルールのコンポーネントと、その動作について説明します。

メール フロー ルールを作成、コピー、および管理する手順については、「Exchange Online でメール フロー ルールを管理する」 [を参照してください](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。 ルールごとに、ルールを適用、ルールをテスト、ルールをテストして送信者に通知するという、いずれかのオプションを選択できます。 テスト オプションの詳細については、「Test [mail flow rules and](/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) [Policy Tips in Exchange Online」を参照してください](/exchange/security-and-compliance/data-loss-prevention/policy-tips)。

メール フロー ルールに一致したメッセージに関する概要と詳細レポートについては、「メール保護レポートを使用してマルウェア、スパム、およびルールの検出に関するデータを表示する」を [参照してください](/exchange/monitoring/use-mail-protection-reports)。

メール フロー ルールを使用して特定のメッセージング ポリシーを実装するには、次のトピックを参照してください。

- [メール フロー ルールを使用して Exchange Online でメッセージ添付ファイルを検査する](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Office 365 Enterprise で暗号化を設定する](../../compliance/set-up-encryption.md)

- [Exchange Online での組織全体のメッセージの免責事項、署名、フッター、またはヘッダー](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [EOP でブロック送信者リストを作成する](create-block-sender-lists-in-office-365.md)

- [Exchange Online Protection でファイルの添付のブロックを通じてマルウェアの脅威を削減する](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [365 で電子メール メッセージを暗号化または暗号化解除するOfficeする](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

次のビデオでは、スタンドアロン EOP でメール フロー ルールを設定するデモンストレーションを示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>メール フロー ルールの構成要素

メール フロー ルールは条件、例外、アクション、プロパティからできています。

- **条件**: アクションを適用するメッセージを識別します。 一部の条件は、メッセージ ヘッダー フィールド (例、宛先、差出人、または CC フィールド) を確認します。 その他の条件はメッセージ プロパティ (例、メッセージの件名、本文、添付ファイル、メッセージ サイズ、またはメッセージ分類) を確認します。 ほとんどの条件は、比較演算子 (例、次と一致する、次と一致しない、または次が含まれる) と一致する値を指定する必要があります。 条件または例外が 1 つもない場合、ルールはすべてのメッセージに適用されます。

スタンドアロン EOP のメール フロー ルール条件の詳細については、「Exchange Online のメール フロー ルールの条件と例外 [(述語)」を参照してください](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

- **例外**: 必要に応じて、アクションを適用しないメッセージを識別します。 条件で使用可能なメッセージ識別子と同じものが、例外でも使用可能です。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメッセージにルール アクションが適用されないようにします。

- **Actions**: ルール内の条件に一致し、例外と一致しないメッセージに対して実行する処理を指定します。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメール メッセージにアクションが適用されないようにします。

スタンドアロン EOP で使用可能なメール フロー ルールアクションの詳細については、「Exchange Online のメール [フロー ルールアクション」を参照してください](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **プロパティ**: 条件、例外、またはアクションではない他のルール設定を指定します。 たとえば、いつルールを適用するか、ルールを強制するか、あるいはテストするかどうか、およびルールを有効化する期間などです。

  詳細については、この記事の [「メール フロー ルールのプロパティ」](#mail-flow-rule-properties) セクションを参照してください。

### <a name="multiple-conditions-exceptions-and-actions"></a>複数の条件、例外、アクション

Use a transport rule so messages can bypass Clutter

****

|コンポーネント|ロジック|コメント|
|---|---|---|
|コメント|および|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、特定のテキストを含んでいるメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。EAC においては、ルールは簡単にコピーできます。|
|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、コンテンツがパターンと一致するメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。ルールは簡単にコピーできます。|または|条件によっては、複数の値を指定できる場合もあります。メッセージは指定された値の任意の 1 つ (すべてではない) に一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、 **[件名に次のいずれかの語が含まれている場合]** という条件が「 Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に値が少なくとも 1 つは含まれているので、この条件は満たされています。  |
|条件によっては、複数の値を指定できる場合もあります。1 つの条件に複数の値を入力できる場合、メッセージはその条件で指定された値のいずれかに一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、トランスポート ルールの [件名に次のいずれかの語が含まれている場合] という条件が「Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に条件の値が少なくとも 1 つは含まれているので、この条件は満たされています。|または|メッセージがいずれか 1 つの例外に一致すると、アクションはメッセージに適用されません。メッセージがすべての例外に一致する必要はありません。|
|メッセージがいずれかの例外に一致すると、アクションは実行されません。メッセージが、すべての例外に一致する必要はありません。|および|ルールの条件に一致するメッセージには、ルールに指定されるすべてのアクションが実行されます。たとえば、 **[メッセージの件名の先頭に付加する]** というアクションと、 **[受信者を BCC ボックスに追加する]** というアクションが選択されている場合、両方のアクションがメッセージに適用されます。  <p> ルールの条件に一致するメッセージには、そのルールで指定されたすべてのアクションが実行されます。たとえば、[メッセージの件名の先頭に付加する] というアクションと、[受信者を BCC ボックスに追加する] というアクションが選択されている場合、両方のアクションがメッセージに適用されます。メッセージには、メッセージの件名の先頭に指定の文字列が追加され、指定された受信者が BCC 受信者として追加されます。<p> ルールにアクションを設定して、そのルールが適用されたときに、メッセージにそれ以降のルールの適用されないようにすることもできます。|
|

### <a name="mail-flow-rule-properties"></a>メール フロー ルールのプロパティ

次の表で、メール フロー ルールで使用可能なルールのプロパティについて説明します。

****

|EAC におけるプロパティ名|PowerShell におけるパラメーター名|説明|
|---|---|---|
|**[優先度]**|_Priority_|メッセージにルールを適用する順番を示します。優先度の既定値はルールの作成時期に基づいています (古いルールのほうが新しいルールより優先度が高く、優先度の高いルールが優先度の低いルールよりも先に処理されます)。   <p> EAC 内でのルールの優先度は、ルール一覧内でそのルールを上下に移動させることで変更します。 PowerShell では、優先度番号を設定します (0 が最も優先度が高い)。 <p> たとえば、クレジット カード番号が含まれるメッセージを拒否するルールと、承認を必要とする別のルールがある場合、拒否のルールを最初に適用して、他のルールの適用を停止する必要があります。  |
|**[モード]**|_Mode_|ルールにすぐにメッセージの処理を開始させるか、あるいはメッセージの配信に影響を与えずにルールをテストするかどうかを指定することができます (データ紛失防止、DLP ポリシー ヒントの有無を問わず)。 <p> ポリシー ヒントは、メッセージを作成しているユーザーにそれがポリシー違反の可能性があることを通知する短いメモを、Outlook または Web 上の Outlook で提示します。詳細については、「 **Policy Tips** 」を参照してください。  <p> モードの詳細については、「 **Test a mail flow rule** 」を参照してください。|
|**次の日付でこのルールを有効にする** <p> **次の日付に、このルールを無効にする**|_ActivationDate_ <p> _ExpiryDate_|ルールが有効化される日付の範囲を指定します。|
|選択されているかどうかに関わらず、チェック ボックスを **オン** にします。|新しいルール: **New-TransportRule コマンドレットの Enabled パラメーター** 。  <p> 既存のルール: **Enable-TransportRule** または **Disable-TransportRule** コマンドレットを使用します。 <p> 値はルールの **State** プロパティに表示されます。|無効なルールを作成して、それをテストする準備ができたときに有効にすることができます。または、設定を保持するために削除することなくルールを無効にすることができます|
|**[ルール処理が完了しない場合メッセージを優先する]**|_RuleErrorAction_|ルール処理が完了しない場合にメッセージをどのように扱うかを指定することができます。既定値ではルールは無視されますが、処理のためにメッセージを再送信することを選択できます。|
|**メッセージの送信者アドレスを一致**|_SenderAddressLocation_|ルールが送信者のメール アドレスを確認する例外や条件を使用する場合、メッセージ ヘッダー、メッセージのエンベロープ、またはその両方の値を検索できます。|
|**[ルールの処理を中止する]**|_SenderAddressLocation_|これはルールのアクションですが、EAC でのプロパティのように見えます。ルールがメッセージを処理した後に、追加のルールが適用されないように選択できます。|
|**コメント**|_Comments_|ルールに関する説明的なコメントを入力することができます。|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>メッセージへのメール フロー ルールの適用方法

組織を通過するすべてのメッセージが、組織内の有効にされているメール フロー ルールについて評価されます。 ルールは、EAC の [メールフロー ルール] ページに表示される順序、または PowerShell の対応する Priority パラメーター \> 値に基づいて処理されます。 

各ルールでは、そのルールが一致した場合に、以降のルールの処理を停止するオプションを選択できます。この設定は、メッセージが複数のメール フロー ルールの条件に一致する場合に重要です (メッセージにどのルールを適用しますか?すべてですか?1 つだけですか?)。

### <a name="differences-in-processing-based-on-message-type"></a>メッセージの種類による処理の違い

組織を通過するメッセージにはいくつかの種類があります。次の表に、メール フロー ルールで処理できるメッセージの種類を示します。

****

|組織を通過するメッセージにはいくつかの種類があります。次の表に、トランスポート ルールで処理できるメッセージの種類を示します。|メッセージの種類|
|---|---|
|**通常の** メッセージ : 1 つのリッチ テキスト形式 (RTF)、HTML、またはプレーン テキスト メッセージ本文、またはマルチパートまたは代替メッセージ本文のセットを含むメッセージ。|はい|
|**Office 365 メッセージ** の暗号化: 365 で 365 メッセージOffice暗号化されたメッセージOfficeします。 詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> 暗号化されたメッセージの内容を検査または変更するルールの場合は、トランスポート復号化が有効になっている (必須または省略可能、既定値は省略可能) を確認する必要があります。 詳細については、「Define rules to encrypt or decrypt email messages in Office [365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」 を参照してください。|
|**S/MIME 暗号化されたメッセージ**|ルールは、エンベロープ ヘッダーにのみアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> メッセージ コンテンツの検査を必要とする条件を使用したルール、またはメッセージのコンテンツを変更するアクションを処理することはできません。|
|**RMS で保護されたメッセージ**: RMS (RMS) Active Directory Rights Management サービス (AD RMS) ポリシーが適用されたメッセージ。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> RMS で保護されたメッセージの内容を検査または変更するルールの場合は、トランスポート復号化が有効になっている (必須または省略可能、既定値は省略可能) を確認する必要があります。|
|**クリア署名されたメッセージ**: 署名されているが暗号化されていないメッセージ。|はい|
|**UM メッセージ**: ユニファイド メッセージング サービスによって作成または処理されるメッセージ (ボイス メール、FAX、通話不足通知、Microsoft Outlook Voice Access を使用して作成または転送されたメッセージなど)。|はい|
|**匿名メッセージ**: 匿名送信者によって送信されるメッセージ。|はい|
|**レポートの読** み取り : 送信者による受信要求の読み取りに応じて生成されるレポート。 レポートの読み取りには、 のメッセージ クラス `IPM.Note*.MdnRead` または `IPM.Note*.MdnNotRead` .|はい|
|

## <a name="what-else-should-i-know"></a>その他の注意事項

- Exchange **Online** Protection では、ルールの Version プロパティまたは **RuleVersion** プロパティの値は重要ではありません。

- メール フロー ルールを作成または変更した後に、新規または更新されたルールがメッセージに適用されるまで、最大で 30 分かかります。

## <a name="for-more-information"></a>詳細情報

[メール フロー ルールを使用して Exchange Online でメッセージ添付ファイルを検査する](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Office 365 での電子メールの暗号化](../../compliance/email-encryption.md)

[ジャーナル、トランスポート、受信トレイのルール上の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)