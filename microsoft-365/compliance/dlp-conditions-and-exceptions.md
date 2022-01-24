---
title: DLP ポリシーの条件、例外、およびアクション
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: ''
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: dlp ポリシーの条件と例外について学ぶ
ms.openlocfilehash: a0354fe6392d739fa1b616e92625b7507cca823f
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172261"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP ポリシーの条件、例外、およびアクション

DLP ポリシーの条件と例外は、ポリシーが適用される機密性の高いアイテムを識別します。 アクションは、例外が満たされた状態の結果として何が起こるかを定義します。

- 条件は、含めるものについて定義します。
- 例外は、除外する対象を定義します。
- アクションは、条件または例外が満たされた結果として何が起こるかを定義します。

ほとんどの条件と例外には、1 つ以上の値をサポートする 1 つのプロパティがあります。 たとえば、DLP ポリシーが電子メールに適用されている場合Exchange送信者は、メッセージの送信者を必要とします。 プロパティが 2 つある条件もあります。 たとえば、**メッセージ ヘッダーにこれらの単語のいずれかが含まれる** という条件には、ヘッダーを指定するプロパティ 1 つと、ヘッダー フィールド内で検索するテキストを指定する 2 つめのプロパティが必要です。 一部の条件や例外には、プロパティが含めではありません。 たとえば、添付ファイル **はパスワードで保護された** 状態で、パスワードで保護されたメッセージ内の添付ファイルを検索します。

アクションには通常、追加のプロパティが必要になります。 たとえば、DLP ポリシー ルールがメッセージをリダイレクトする場合は、メッセージのリダイレクト先を指定する必要があります。
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP ポリシーの条件と例外

次のセクションの表では、DLP で使用できる条件と例外について説明します。

- [[Senders (送信者)](#senders)]
- [受信者](#recipients)
- [メッセージの件名または本文](#message-subject-or-body)
- [添付ファイル](#attachments)
- [メッセージ ヘッダー](#message-headers)
- [メッセージのプロパティ](#message-properties)

### <a name="senders"></a>送信者

送信者アドレスを条件または例外として使用する場合、値が検索される実際のフィールドは、使用するルールの種類によって異なります。 DLP ベースのルールでは、エンベロープ アドレスが送信者アドレスとして使用されます。 たとえばExchangeのトランスポート ルールでは、ヘッダー アドレスが送信者アドレスとして使用されます。

<!--
> [!NOTE]
> Starting January 20, 2022, the default sender address location will be moved to the Header address along with the availability of the -SenderAddressLocation parameter to configure desired behavior at a DLP rule level.

![image](https://user-images.githubusercontent.com/53205984/145942298-6b435ba6-d146-44fe-a1c5-58babeaf8d7a.png)

At the tenant level, you can configure a sender address location to be used across all rules, unless overridden by a single rule. To revert tenant DLP policy configuration to evaluate the sender address from the Envelope across all rules, you can run the following command:

```PowerShell
Set-PolicyConfig –SenderAddressLocation Envelope
```

To configure the sender address location at a DLP rule level, the parameter is _SenderAddressLocation_. The available values are:

- **Header**: Only examine senders in the message headers (for example, the **From**, **Sender**, or **Reply-To** fields). This is the default value.

- **Envelope**: Only examine senders from the message envelope (the **MAIL FROM** value that was used in the SMTP transmission, which is typically stored in the **Return-Path** field).

- **Header or envelope** (`HeaderOrEnvelope`) Examine senders in the message header and the message envelope.
<br>
-->
|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|送信者が|condition: *From* <br/> 例外: *ExceptIfFrom*|住所|指定されたメールボックス、メール ユーザー、メール連絡先、または組織内のMicrosoft 365によって送信されるメッセージ。|
|送信者が次のメンバーの場合 |_FromMemberOf_ <br/> _ExceptIfFromMemberOf_|住所|指定した配布グループ、メールが有効なセキュリティ グループ、またはグループのメンバーによって送信Microsoft 365メッセージ。|
|送信者の IP アドレスが|condition: *SenderIPRanges*<br/> 例外: *ExceptIfSenderIPRanges*|IPAddressRanges|送信者の IP アドレスが、指定した IP アドレスと一致するか、指定した IP アドレスの範囲内にあるメッセージです。|
|送信者アドレスに単語が含まれている|condition: *FromAddressContainsWords* <br/> 例外: *ExceptIfFromAddressContainsWords*|Words|送信者のメール アドレスに指定の単語が含まれているメッセージです。|
|送信者のアドレスがパターンと一致している|condition: *FromAddressMatchesPatterns* <br/> 例外: *ExceptFromAddressMatchesPatterns*|パターン|送信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。|
|送信者のドメインが次の場合|condition: *SenderDomainIs* <br/> 例外: *ExceptIfSenderDomainIs*|DomainName|送信者のメール アドレスのドメインが指定された値と一致するメッセージです。 指定したドメイン (ドメインのサブドメインなど) を含む送信者ドメインを検索する必要がある場合は、送信者アドレス一致 **(***FromAddressMatchesPatterns*) 条件を使用し、次の構文を使用してドメインを指定します。 \. \.|
|送信者スコープ|condition: *FromScope* <br/> 例外: *ExceptIfFromScope*|UserScopeFrom|内部または外部の送信者によって送信されるメッセージ。|
|送信者の指定のプロパティが次の単語のいずれかを含む|condition: *SenderADAttributeContainsWords* <br/> 例外: *ExceptIfSenderADAttributeContainsWords*|First プロパティ: `ADAttribute` <p> 2 番目のプロパティ: `Words`|送信者の指定した Active Directory 属性に、指定された単語が含まれているメッセージ。|
|送信者の指定のプロパティが次のテキスト パターンと一致する|condition: *SenderADAttributeMatchesPatterns* <br/> 例外: *ExceptIfSenderADAttributeMatchesPatterns*|First プロパティ: `ADAttribute` <p> 2 番目のプロパティ: `Patterns`|送信者の指定した Active Directory 属性に、指定した正規表現に一致するテキスト パターンが含まれるメッセージ。|
|

### <a name="recipients"></a>受信者

<br>

****

|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|受信者が|condition: *SentTo* <br/> 例外: *ExceptIfSentTo*|住所|受信者の 1 人が組織内の指定されたメールボックス、メール ユーザー、メール連絡先であるメッセージです。受信者はメッセージの **To**、**Cc**、**Bcc** のフィールドにいることが可能です。|
|受信者ドメインが|condition: *RecipientDomainIs* <br/> 例外: *ExceptIfRecipientDomainIs*|DomainName|受信者の電子メール アドレスのドメインが指定した値と一致するメッセージ。|
|受信者のアドレスに単語が含まれている|condition: *AnyOfRecipientAddressContainsWords* <br/> 例外: *ExceptIfAnyOfRecipientAddressContainsWords*|Words|受信者のメール アドレスに指定の単語が含まれているメッセージです。 <br/>**注**: この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|受信者のアドレスがパターンと一致している|condition: *AnyOfRecipientAddressMatchesPatterns* <br/> 例外: *ExceptIfAnyOfRecipientAddressMatchesPatterns*|パターン|受信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。 <br/> **注**: この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|のメンバーに送信されます。|condition: *SentToMemberOf* <br/> 例外: *ExceptIfSentToMemberOf*|住所|指定した配布グループ、メールが有効なセキュリティ グループ、またはグループのメンバーである受信者をMicrosoft 365メッセージ。 グループはメッセージの **To**、**Cc**、または **Bcc** フィールドにあることが可能です。|
|受信者の指定のプロパティが次の単語のいずれかを含む |_RecipientADAttributeContainsWords_ <br/> _ExceptIfRecipientADAttributeContainsWords_|First プロパティ: `ADAttribute` <p> 2 番目のプロパティ: `Words`|受信者の指定した Active Directory 属性に、指定された単語が含まれているメッセージ。 <p> **Country** 属性には、2 文字の国コードの値 (たとえば、ドイツの DE) が必要であることに注意してください。|
|受信者の指定のプロパティが次のテキスト パターンと一致する |_RecipientADAttributeMatchesPatterns_ <br/> _ExceptIfRecipientADAttributeMatchesPatterns_|First プロパティ: `ADAttribute` <p> 2 番目のプロパティ: `Patterns`|受信者の指定した Active Directory 属性に、指定した正規表現に一致するテキスト パターンが含まれるメッセージ。|
|

### <a name="message-subject-or-body"></a>メッセージの件名または本文

<br>

****

|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|件名には、単語または語句が含まれている|condition: *SubjectContainsWords* <br/> 例外: *ExceptIf SubjectContainsWords*|Words|Subject フィールドに特定の単語を持つメッセージです。|
|件名がパターンと一致している|condition: *SubjectMatchesPatterns* <br/> 例外: *ExceptIf SubjectMatchesPatterns*|パターン|Subject フィールドに、指定された正規表現に一致するテキスト パターンが含まれるメッセージ。|
|コンテンツが含まれている|condition: *ContentContainsSensitiveInformation* <br/> 例外 *ExceptIfContentContainsSensitiveInformation*|SensitiveInformationTypes|データ損失防止 (DLP) ポリシーで定義された機密情報を含むメッセージまたはドキュメント。|
|件名または本文の一致パターン|condition: *SubjectOrBodyMatchesPatterns* <br/> 例外: *ExceptIfSubjectOrBodyMatchesPatterns*|パターン|件名フィールドまたはメッセージ本文に、指定した正規表現に一致するテキスト パターンが含まれるメッセージ。|
|件名または本文に単語が含まれている|condition: *SubjectOrBodyContainsWords* <br/> 例外: *ExceptIfSubjectOrBodyContainsWords*|Words|件名フィールドまたはメッセージ本文に指定された単語があるメッセージ|
|

### <a name="attachments"></a>Attachments

<br>

****

|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|添付ファイルがパスワードで保護されている|condition: *DocumentIsPasswordProtected* <br/> 例外: *ExceptIfDocumentIsPasswordProtected*|none|添付ファイルがパスワードで保護された (ゆえにスキャンすることができない) メッセージです。 パスワードの検出は、Office、.zip.7z ファイルでのみ機能します。|
|添付ファイルのファイル拡張子は、|condition: *ContentExtensionMatchesWords* <br/> 例外: *ExceptIfContentExtensionMatchesWords*|Words|添付ファイルの拡張子が、以下の指定の単語と一致するメッセージです。|
|メール添付ファイルのコンテンツをスキャンできない|condition: *DocumentIsUnsupported* <br/>例外: *ExceptIf DocumentIsUnsupported*|該当なし|添付ファイルがユーザーによってネイティブに認識されないExchange Online。|
|メール添付ファイルのコンテンツがスキャンを完了しなかった|condition: *ProcessingLimitExceeded* <br/> 例外: *ExceptIfProcessingLimitExceeded*|該当なし|ルール エンジンが添付ファイルのスキャンを完了できなかったメッセージです。内容が完全にスキャンできなかったメッセージを認識し、処理するために協力して作用するルールを作成するために、この条件を使用できます。|
|ドキュメント名に単語が含まれている|condition: *DocumentNameMatchesWords* <br/> 例外: *ExceptIfDocumentNameMatchesWords*|Words|添付ファイルのファイル名が指定した単語と一致するメッセージ。|
|ドキュメント名がパターンと一致する|condition: *DocumentNameMatchesPatterns* <br/> 例外: *ExceptIfDocumentNameMatchesPatterns*|パターン|添付ファイル名に特定の正規表現と一致するテキスト パターンが含まれているメッセージです。|
|文書のプロパティが|condition: *ContentPropertyContainsWords* <br/> 例外: *ExceptIfContentPropertyContainsWords*|Words|添付ファイルのファイル拡張子が指定された単語と一致するメッセージまたはドキュメント。|
|ドキュメント のサイズが等しいか、またはより大きい|condition: *DocumentSizeOver* <br/> 例外: *ExceptIfDocumentSizeOver*|Size|任意の添付ファイルが指定値以上のメッセージです。|
|添付ファイルのコンテンツには、これらの単語が含まれます|condition: *DocumentContainsWords* <br/> 例外: *ExceptIfDocumentContainsWords*|`Words`|添付ファイルに指定された単語が含まれているメッセージです。|
|添付ファイルのコンテンツがこれらのテキスト パターンと一致する|condition: *DocumentMatchesPatterns* <br/> 例外: *ExceptIfDocumentMatchesPatterns*|`Patterns`|添付ファイルに特定の正規表現と一致するテキスト パターンが含まれているメッセージです。|
|

### <a name="message-headers"></a>メッセージ  ヘッダー

<br>

****

|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|ヘッダーには、単語または語句が含まれています|condition: *HeaderContainsWords* <br/> 例外: *ExceptIfHeaderContainsWords*|ハッシュ テーブル|指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した単語が含まれています。|
|ヘッダーがパターンと一致している|condition: *HeaderMatchesPatterns* <br/> 例外: *ExceptIfHeaderMatchesPatterns*|ハッシュ テーブル|指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した正規表現が含まれています。|

### <a name="message-properties"></a>メッセージのプロパティ

<br>

****

|DLP の条件または例外|PowerShell の condition/exception パラメーター Microsoft 365|プロパティの種類|description|
|---|---|---|---|
|重要度の高い|condition: *WithImportance* <br/> 例外: *ExceptIfWithImportance*|Importance|指定された重要度レベルでマークされたメッセージ。|
|コンテンツ文字セットに単語が含まれている|condition: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*|CharacterSets|指定した文字セット名のいずれかを含むメッセージです。|
|送信者の上書きを持つ|condition: *HasSenderOverride* <br/> 例外: *ExceptIfHasSenderOverride*|該当なし|送信者がデータ損失防止 (DLP) ポリシーを上書きすることを選択したメッセージです。 DLP ポリシーの詳細については、「データ損失 [防止について」を参照してください。](./dlp-learn-about-dlp.md)|
|メッセージの種類が一致する|condition: *MessageTypeMatches* <br/> 例外: *ExceptIfMessageTypeMatches*|MessageType|指定の種類のメッセージです。|
|メッセージ サイズが次の値以上の場合|condition: *MessageSizeOver* <br/> 例外: *ExceptIfMessageSizeOver*|`Size`|合計サイズ (メッセージ プラス添付ファイル) が指定値以上のメッセージです。 **注**:メールボックスのメッセージ サイズの制限は、メール フロー ルールの前に評価されます。 この条件を含むルールがメッセージを処理する前に、メールボックスに対して大きすぎるメッセージが拒否されます。|
|

## <a name="actions-for-dlp-policies"></a>DLP ポリシーのアクション

次の表に、DLP で使用できるアクションについて説明します。

<br>

****

|DLP のアクション|PowerShell のアクション Microsoft 365パラメーター|プロパティの種類|description|
|---|---|---|---|
|ヘッダーの設定|SetHeader|First プロパティ: *ヘッダー名* </br> 2 番目のプロパティ: *ヘッダー値*|SetHeader パラメーターは、メッセージ ヘッダーのヘッダー フィールドと値を追加または変更する DLP ルールのアクションを指定します。 このパラメーターは、構文 "HeaderName:HeaderValue" を使用します。 複数のヘッダー名と値のペアをコンマで区切って指定できます|
|ヘッダーの削除|RemoveHeader|最初のプロパティ: *MessageHeaderField*</br> 2 番目のプロパティ: *String*|RemoveHeader パラメーターは、メッセージ ヘッダーからヘッダー フィールドを削除する DLP ルールのアクションを指定します。 このパラメーターは、構文 "HeaderName" または "HeaderName:HeaderValue" を使用します。複数のヘッダー名またはヘッダー名と値のペアをコンマで区切って指定できます。|
|メッセージを特定のユーザーにリダイレクトする|*RedirectMessageTo*|住所|特定の受信者にメッセージをリダイレクトします。元の受信者にメッセージを配信せず、送信者や元の受信者に通知を送信しません。|
|承認のためにメッセージを送信者のマネージャーに転送する|中|First プロパティ: *ModerateMessageByManager*</br> 2 番目のプロパティ: *ブール型 (Boolean)*|Moderate パラメーターは、電子メール メッセージをモデレーターに送信する DLP ルールのアクションを指定します。 このパラメーターでは、@{ModerateMessageByManager = \| <$true$false>。|
|承認のメッセージを特定の承認者に転送する|中|First プロパティ: *ModerateMessageByUser*</br>2 番目のプロパティ: *Addresses*|Moderate パラメーターは、電子メール メッセージをモデレーターに送信する DLP ルールのアクションを指定します。 このパラメーターでは、@{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")} という構文を使用します。|
|受信者の追加|AddRecipients|First プロパティ: *Field*</br>2 番目のプロパティ: *Addresses*|メッセージの [宛先/Cc/Bcc] フィールドに 1 つ以上の受信者を追加します。 このパラメーターでは、@{<AddToRecipients \| CopyTo \| BlindCopy> To = "emailaddress"} という構文を使用します。|
|送信者のマネージャーを受信者として追加する|AddRecipients|First プロパティ: *AddedManagerAction*</br>2 番目のプロパティ: *Field*|送信者の上司を指定の受信者タイプ (To、Cc、Bcc) としてメッセージに追加したり、送信者や受信者に通知することなくメッセージを送信者の上司にリダイレクトします。 このアクションは、送信者の Manager 属性が Active Directory で定義されている場合のみ有効です。 このパラメーターは、@{AddManagerAsRecipientType = "<\| Cc \| Bcc>"} という構文を使用します。|
件名の先頭に付く|PrependSubject|文字列|メッセージの Subject フィールドの冒頭に指定のテキストを追加します。元の件名のテキストを区別するために、指定されたテキストの最後の文字としてスペースまたはコロン (:) を使用してください。  </br>件名に既にテキストが含まれているメッセージ (返信など) に同じ文字列が追加されるのを防ぐには、"件名に単語が含まれている" (ExceptIfSubjectContainsWords) 例外をルールに追加します。|
|HTML 免責事項の適用|ApplyHtmlDisclaimer|First プロパティ: *Text*</br>2 番目のプロパティ: *場所*</br>3 番目のプロパティ: *フォールバック アクション*|指定した HTML 免責事項をメッセージの必要な場所に適用します。</br>このパラメーターでは、@{ Text = " という構文を使用します。Location = <Append \| Prepend>。FallbackAction = <Wrap \| Ignore \| Reject> }|
|権限Office 365 Message Encryption保護を削除する|RemoveRMSTemplate|該当なし|電子メールOffice 365された暗号化を削除します。|
|ホストされた検疫にメッセージを配信する |_Quarantine_|該当なし| このアクションは現在パブリック プレビュー **中です**。 このフェーズでは、DLP ポリシーによって検疫された電子メールに、ポリシーの種類が ExchangeTransportRule として表示されます。</br> EOP の検疫にメッセージを配信します。 詳細については [、「EOP の検疫済み電子メール メッセージ」を参照してください](/microsoft-365/security/office-365-security/quarantine-email-messages)。|
|

<!--|Modify Subject|ModifySubject|PswsHashTable | Remove text from the subject line that matches a specific pattern and replace it with different text. See the example below. You can: </br>- **Replace** all matches in the subject with the replacement text </br>- **Append** to remove all matches in the subject and inserts the replacement text at the end of the subject. </br>- **Prepend** to remove all matches and inserts the replacement text at the beginning of the subject. See ModifySubject parameter in, /powershell/module/exchange/new-dlpcompliancerule|-->

