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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: メール フロー ルール (トランスポート ルール) は、組織を通して通受信するメッセージを識別し、アクションを実行するために使用できます。
ms.openlocfilehash: ed17ac62009f5e766772095985441fad2367edf4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827703"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>スタンドアロン EOP のメール フロー ルール (トランスポート ルール)

Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、組織を通じたメッセージを識別してアクションを実行することができます。

このトピックでは、メール フロー ルールの構成要素とその動作について説明します。

メール フロー ルールを作成、コピー、管理する手順については、「Exchange [Online でメール フロー ルールの管理」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。 ルールごとに、ルールを適用、ルールをテスト、ルールをテストして送信者に通知するという、いずれかのオプションを選択できます。 テスト オプションの詳細については、Exchange Online の [ [メール フロー ルールのテスト](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) ] および [[ポリシー ヒント] を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)。

メール フロー ルールに一致したメッセージに関する概要と詳細のレポートについては、「 [メール保護レポートを使用してマルウェア、スパム、ルールの検出に関するデータを表示する」を参照してください](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)。

メール フロー ルールを使用して特定のメッセージング ポリシーを実装するには、次のトピックを参照してください。

- [Exchange Online でメール フロー ルールを使用してメッセージの添付ファイルを検検する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Office 365 Enterprise で暗号化を設定する](../../compliance/set-up-encryption.md)

- [Exchange Online の組織全体のメッセージの免責事項、署名、フッター、ヘッダー](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [EOP で受信拒否リストを作成する](create-block-sender-lists-in-office-365.md)

- [Exchange Online Protection でファイルの添付のブロックを通じてマルウェアの脅威を削減する](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [電子メール メッセージの暗号化または暗号化解除ルールの定義 (Office 365)](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

次のビデオでは、スタンドアロン EOP でのメール フロー ルールの設定方法を示しています。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>メール フロー ルールの構成要素

メール フロー ルールは条件、例外、アクション、プロパティからできています。

- **条件**: アクションを適用するメッセージを特定します。 一部の条件は、メッセージ ヘッダー フィールド (例、宛先、差出人、または CC フィールド) を確認します。 その他の条件はメッセージ プロパティ (例、メッセージの件名、本文、添付ファイル、メッセージ サイズ、またはメッセージ分類) を確認します。 ほとんどの条件は、比較演算子 (例、次と一致する、次と一致しない、または次が含まれる) と一致する値を指定する必要があります。 条件または例外が 1 つもない場合、ルールはすべてのメッセージに適用されます。

スタンドアロン EOP でのメール フロー ルール条件の詳細については、Exchange Online 内のメール フロー ルールの条件と [例外 (述語) を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

- **例外**: アクションが適用されるべきメッセージを任意で特定します。 条件で使用可能なメッセージ識別子と同じものが、例外でも使用可能です。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメッセージにルール アクションが適用されないようにします。

- **アクション**: ルールの条件に一致し、どの例外でも一致しないメッセージに対して行う操作を指定します。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメール メッセージにアクションが適用されないようにします。

スタンドアロン EOP で使用可能なメール フロー ルール操作の詳細については、「Exchange Online 内の [メール フロー ルールのアクション」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。

- **プロパティ**: その他のルールの設定で、条件、例外、またはアクションではないものを指定します。 たとえば、いつルールを適用するか、ルールを強制するか、あるいはテストするかどうか、およびルールを有効化する期間などです。

  詳細に関しては、このトピックの「[メール フロー ルールのプロパティ](#mail-flow-rule-properties)」セクションを参照してください。

### <a name="multiple-conditions-exceptions-and-actions"></a>複数の条件、例外、アクション

Use a transport rule so messages can bypass Clutter

****

|コンポーネント|ロジック|コメント|
|---|---|---|
|コメント|および|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、特定のテキストを含んでいるメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。EAC においては、ルールは簡単にコピーできます。|
|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、コンテンツがパターンと一致するメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。ルールは簡単にコピーできます。|または|条件によっては、複数の値を指定できる場合もあります。メッセージは指定された値の任意の 1 つ (すべてではない) に一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、 **[件名に次のいずれかの語が含まれている場合]** という条件が「 Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に値が少なくとも 1 つは含まれているので、この条件は満たされています。  |
|条件によっては、複数の値を指定できる場合もあります。1 つの条件に複数の値を入力できる場合、メッセージはその条件で指定された値のいずれかに一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、トランスポート ルールの [件名に次のいずれかの語が含まれている場合] という条件が「Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に条件の値が少なくとも 1 つは含まれているので、この条件は満たされています。|または|メッセージがいずれか 1 つの例外に一致すると、アクションはメッセージに適用されません。メッセージがすべての例外に一致する必要はありません。|
|メッセージがいずれかの例外に一致すると、アクションは実行されません。メッセージが、すべての例外に一致する必要はありません。|および|ルールの条件に一致するメッセージには、ルールに指定されるすべてのアクションが実行されます。たとえば、 **[メッセージの件名の先頭に付加する]** というアクションと、 **[受信者を BCC ボックスに追加する]** というアクションが選択されている場合、両方のアクションがメッセージに適用されます。  <br/><br/> ルールの条件に一致するメッセージには、そのルールで指定されたすべてのアクションが実行されます。たとえば、[メッセージの件名の先頭に付加する] というアクションと、[受信者を BCC ボックスに追加する] というアクションが選択されている場合、両方のアクションがメッセージに適用されます。メッセージには、メッセージの件名の先頭に指定の文字列が追加され、指定された受信者が BCC 受信者として追加されます。<br/><br/> ルールにアクションを設定して、そのルールが適用されたときに、メッセージにそれ以降のルールの適用されないようにすることもできます。|
|

### <a name="mail-flow-rule-properties"></a>メール フロー ルールのプロパティ

次の表で、メール フロー ルールで使用可能なルールのプロパティについて説明します。

****

|EAC におけるプロパティ名|PowerShell におけるパラメーター名|説明|
|---|---|---|
|**[優先度]**|_Priority_|メッセージにルールを適用する順番を示します。優先度の既定値はルールの作成時期に基づいています (古いルールのほうが新しいルールより優先度が高く、優先度の高いルールが優先度の低いルールよりも先に処理されます)。   <br/><br/> EAC 内でのルールの優先度は、ルール一覧内でそのルールを上下に移動させることで変更します。 PowerShell では、優先度番号を設定します (0 が最高優先度)。 <br/><br/> たとえば、クレジット カード番号が含まれるメッセージを拒否するルールと、承認を必要とする別のルールがある場合、拒否のルールを最初に適用して、他のルールの適用を停止する必要があります。  |
|**[モード]**|_Mode_|ルールにすぐにメッセージの処理を開始させるか、あるいはメッセージの配信に影響を与えずにルールをテストするかどうかを指定することができます (データ紛失防止、DLP ポリシー ヒントの有無を問わず)。 <br/><br/> ポリシー ヒントは、メッセージを作成しているユーザーにそれがポリシー違反の可能性があることを通知する短いメモを、Outlook または Web 上の Outlook で提示します。詳細については、「 **Policy Tips** 」を参照してください。  <br/><br/> モードの詳細については、「 **Test a mail flow rule** 」を参照してください。|
|**次の日付でこのルールを有効にする** <br/><br/> **次の日付に、このルールを無効にする**|_ActivationDate_ <br/> _ExpiryDate_|ルールが有効化される日付の範囲を指定します。|
|選択されているかどうかに関わらず、チェック ボックスを **オン** にします。|新しいルール_Enabled_**:New-TransportRule コマンドレットで有効なパラメーター** 。 <br/><br/> 既存のルール: **Enable-TransportRule** または **Disable-TransportRule** コマンドレットを使用します。 <br/><br/> 値はルールの **State** プロパティに表示されます。|無効なルールを作成して、それをテストする準備ができたときに有効にすることができます。または、設定を保持するために削除することなくルールを無効にすることができます|
|**[ルール処理が完了しない場合メッセージを優先する]**|_RuleErrorAction_|ルール処理が完了しない場合にメッセージをどのように扱うかを指定することができます。既定値ではルールは無視されますが、処理のためにメッセージを再送信することを選択できます。|
|**メッセージの送信者アドレスを一致**|_SenderAddressLocation_|ルールが送信者のメール アドレスを確認する例外や条件を使用する場合、メッセージ ヘッダー、メッセージのエンベロープ、またはその両方の値を検索できます。|
|**[ルールの処理を中止する]**|_SenderAddressLocation_|これはルールのアクションですが、EAC でのプロパティのように見えます。ルールがメッセージを処理した後に、追加のルールが適用されないように選択できます。|
|**コメント**|_Comments_|ルールに関する説明的なコメントを入力することができます。|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>メッセージへのメール フロー ルールの適用方法

組織を通過するすべてのメッセージが、組織内の有効にされているメール フロー ルールについて評価されます。 ルールは、EAC の [メール フロー ルール] ページ**でリストされている**順に、または PowerShell の対応 \> **Rules**_する優先度パラメーター値_に基づいて処理されます。

各ルールでは、そのルールが一致した場合に、以降のルールの処理を停止するオプションを選択できます。この設定は、メッセージが複数のメール フロー ルールの条件に一致する場合に重要です (メッセージにどのルールを適用しますか?すべてですか?1 つだけですか?)。

### <a name="differences-in-processing-based-on-message-type"></a>メッセージの種類による処理の違い

組織を通過するメッセージにはいくつかの種類があります。次の表に、メール フロー ルールで処理できるメッセージの種類を示します。

****

|組織を通過するメッセージにはいくつかの種類があります。次の表に、トランスポート ルールで処理できるメッセージの種類を示します。|メッセージの種類|
|---|---|
|**通常の**メッセージ:単一のリッチ テキスト形式 (RTF)、HTML、プレーン テキストのメッセージ本文あるいはメッセージ本文のマルチパートまたは代替セットが含まれるメッセージ。|はい|
|**Office 365 Message Encryption:** Office 365 の Office 365 Message Encryption によって Office暗号化されたメッセージ。 詳細については、「[Office 365 での暗号化](https://docs.microsoft.com/microsoft-365/compliance/encryption)」をご覧ください。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <br/><br/> 暗号化されたメッセージのコンテンツをルールで検査または変更するには、トランスポート復号化が有効になっていることを確認する必要があります (必須または省略可能。既定値は省略可能です)。 詳細については、「外部メールボックス と [365 で電子メール メッセージを暗号化または暗号化解除するルールの定義Officeを参照してください](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。|
|**S/MIME 暗号化されたメッセージ**|ルールは、エンベロープ ヘッダーにのみアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <br/><br/> メッセージ コンテンツの検査を必要とする条件を使用したルール、またはメッセージのコンテンツを変更するアクションを処理することはできません。|
|**RMS で保護されたメッセージ**: メールボックス (組織Active Directory Rights Management サービス RMS) AD または Azure Rights Management (RMS) ポリシーが適用されたメッセージ。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <br/><br/> RMS で保護されたメッセージのコンテンツをルールで検査または変更する場合、トランスポート復号化が有効になっていることを確認する必要があります (必須または省略可能。既定値は省略可能)。|
|**クリア署名された**メッセージ: 署名されているが暗号化はされていないメッセージ。|はい|
|**UM メッセージ**: ボイス メール、フックス、不在着信通知などのユニファイド メッセージング サービスによって作成または処理されたメッセージ、および Microsoft Outlook Voice Access を使用して転送されたメッセージ。|はい|
|**匿名メッセージ**: 匿名の送信者によって送信されるメッセージ|はい|
|**開か**れます: 送信者による開開確認要求を読み取るための応答として生成されたレポート。 開開示レポートには、メッセージ クラスまたは `IPM.Note*.MdnRead` のメッセージ クラスがあります `IPM.Note*.MdnNotRead` 。|はい|
|

## <a name="what-else-should-i-know"></a>その他の注意事項

- ルール **の** **Version プロパティまたは RuleVersion** プロパティの値は Exchange Online Protection では重要ではありません。

- メール フロー ルールを作成または変更した後に、新規または更新されたルールがメッセージに適用されるまで、最大で 30 分かかります。

## <a name="for-more-information"></a>詳細情報

[Exchange Online でメール フロー ルールを使用してメッセージの添付ファイルを検検する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Office 365 での電子メールの暗号化](../../compliance/email-encryption.md)

[ジャーナル、トランスポート、受信トレイのルール上の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
