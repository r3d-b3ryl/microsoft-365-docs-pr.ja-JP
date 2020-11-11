---
title: DLP ポリシー条件、例外、およびアクション (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: dlp ポリシーの条件と例外について説明します。
ms.openlocfilehash: a371c564cc314c457e1d9afe667115c244e0185d
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993345"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>DLP ポリシー条件、例外、およびアクション (プレビュー)

DLP ポリシー内の条件と例外は、ポリシーが適用される機密アイテムを識別します。 アクションは、例外の条件が満たされた結果として行われる処理を定義します。

- 条件に含める内容を定義する
- 例外は除外するものを定義します。
- アクションによって、条件または満たされた例外の結果として行われる処理が定義されます。
 
ほとんどの条件と例外には、1つ以上の値をサポートする1つのプロパティがあります。 たとえば、DLP ポリシーが Exchange メールに適用されている場合、 **送信者** の条件にはメッセージの送信者が必要です。 プロパティが 2 つある条件もあります。 たとえば、 **メッセージ ヘッダーにこれらの単語のいずれかが含まれる** という条件には、ヘッダーを指定するプロパティ 1 つと、ヘッダー フィールド内で検索するテキストを指定する 2 つめのプロパティが必要です。 一部の条件または例外にはプロパティがありません。 たとえば、 **添付ファイルはパスワード** で保護された状態で、パスワードで保護されたメッセージ内の添付ファイルを検索するだけです。

アクションには通常、追加のプロパティが必要になります。 たとえば、DLP ポリシールールがメッセージをリダイレクトする場合、メッセージのリダイレクト先を指定する必要があります。 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP ポリシーの条件と例外

次のセクションの表では、DLP で使用可能な条件と例外について説明します。

- [[Senders (送信者)](#senders)]
- [受信者](#recipients)
- [メッセージの件名または本文](#message-subject-or-body)
- [添付ファイル](#attachments)
- [メッセージ ヘッダー](#message-headers)
- [メッセージのプロパティ](#message-properties)

### <a name="senders"></a>送信者


|**DLP の条件または例外**  |**Microsoft 365 PowerShell の条件/例外パラメーター** |**プロパティの種類**  |**説明**|
|---------|---------|---------|---------|
|送信者が |条件: *From* <br/> 例外: *ExceptIfFrom*      |住所 |     組織内の指定されたメールボックス、メールユーザー、メール連絡先、または Microsoft 365 グループによって送信されるメッセージ。|
|送信者の IP アドレスが     |条件: *senderipranges 特定*<br/> 例外: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | 送信者の IP アドレスが、指定した IP アドレスと一致するか、指定した IP アドレスの範囲内にあるメッセージです。       |
|送信者のアドレスに単語が含まれている   | 条件: *Fromaddressん words* <br/> 例外: *ExceptIfFromAddressContainsWords*        |   Words      |   送信者のメール アドレスに指定の単語が含まれているメッセージです。|
| 送信者のアドレスがパターンに一致する    | 条件: *FromAddressMatchesPatterns* <br/> 例外: *ExceptFromAddressMatchesPatterns*       |      模様   |  送信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。  |
|送信者のドメインが  |  条件: *SenderDomainIs* <br/> 例外: *ExceptIfSenderDomainIs*       |ネーム         |     送信者のメール アドレスのドメインが指定された値と一致するメッセージです。 指定したドメイン (たとえば、ドメインの任意のサブドメイン) を *含む* 送信者ドメインを検索する必要がある場合は、次の構文を使用して、 **送信者アドレス一致** ( *FromAddressMatchesPatterns* ) 条件を使用し、ドメインを指定します。 ' \. domain \. com $ '。    |

### <a name="recipients"></a>Recipients

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター** |    **プロパティの種類** | **説明**|
|---------|---------|---------|---------|
|受信者が|  条件: *により、に* なります。 <br/> 例外: *ExceptIfSentTo* | 住所 | 受信者の 1 人が組織内の指定されたメールボックス、メール ユーザー、メール連絡先であるメッセージです。 受信者はメッセージの **To** 、 **Cc** 、 **Bcc** のフィールドにいることが可能です。|
|受信者ドメインが|   条件: *受信者 Domainis* <br/> 例外: *ExceptIfRecipientDomainIs* |   ネーム |    送信者のメール アドレスのドメインが指定された値と一致するメッセージです。|
|受信者のアドレスに単語が含まれている|  条件: *受信者アドレス、単語* <br/> 例外: *ExceptIfRecipientAddressContainsWords*|    Words|  受信者のメール アドレスに指定の単語が含まれているメッセージです。 <br/>**注** : この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|受信者のアドレスの一致パターン| 条件: *RecipientAddressMatchesPatterns* <br/> 例外: *ExceptIfRecipientAddressMatchesPatterns*|   模様    |受信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。 <br/> **注** : この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|のメンバーに送信| 条件: *トポロジ* <br/> 例外: *ExceptIfSentToMemberOf*|  住所|  指定された配布グループ、メールが有効なセキュリティグループ、または Microsoft 365 グループのメンバーである受信者が含まれているメッセージ。 グループはメッセージの **To** 、 **Cc** 、または **Bcc** フィールドにあることが可能です。|

### <a name="message-subject-or-body"></a>メッセージの件名または本文

|**DLP の条件または例外** | **Microsoft 365 PowerShell の条件/例外パラメーター** |**プロパティの種類**| **説明**|
|---------|---------|---------|---------|
|件名に単語または語句が含まれている| 条件: *Subjectcontainswords* <br/> 例外: *ExceptIf Subjectの単語*| Words   |Subject フィールドに特定の単語を持つメッセージです。|
|サブジェクトが一致するパターン|条件: *SubjectMatchesPatterns* <br/> 例外: *ExceptIf SubjectMatchesPatterns*|模様   |件名フィールドに、指定された正規表現と一致するテキストパターンが含まれているメッセージ。|
|コンテンツが含まれている|  条件: *ContentContainsSensitiveInformation* <br/> 例外 *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  データ損失防止 (DLP) ポリシーで定義されているような機密情報を含むメッセージまたはドキュメント。|


### <a name="attachments"></a>Attachments

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター**| **プロパティの種類**   |**説明**|
|---------|---------|---------|---------|
|添付ファイルがパスワードで保護されている|条件: *DocumentIsPasswordProtected* <br/> 例外: *ExceptIfDocumentIsPasswordProtected*|none| 添付ファイルがパスワードで保護された (ゆえにスキャンすることができない) メッセージです。 パスワード検出は、Office ドキュメントおよび .zip ファイルにのみ有効です。|
|添付ファイルのファイル拡張子は|条件: *ContentExtensionMatchesWords* <br/> 例外: *ExceptIfContentExtensionMatchesWords*|  Words   |添付ファイルの拡張子が、以下の指定の単語と一致するメッセージです。|
|任意の電子メール添付ファイルのコンテンツをスキャンできませんでした|条件: *DocumentIsUnsupported* <br/>例外: *ExceptIf DocumentIsUnsupported*|   該当なし|    添付ファイルが Exchange Online によってネイティブに認識されないメッセージ。|
|すべての電子メール添付ファイルのコンテンツのスキャンが完了しなかった|   条件: *Processinglimitexceeded* <br/> 例外: *ExceptIfProcessingLimitExceeded*|    該当なし |ルール エンジンが添付ファイルのスキャンを完了できなかったメッセージです。内容が完全にスキャンできなかったメッセージを認識し、処理するために協力して作用するルールを作成するために、この条件を使用できます。|
|ドキュメント名に単語が含まれている|条件: *DocumentNameMatchesWords* <br/> 例外: *ExceptIfDocumentNameMatchesWords* |Words  |添付ファイルのファイル名が、指定したいずれかの単語と一致するメッセージ。|
|ドキュメント名がパターンに一致する|条件: *DocumentNameMatchesPatterns* <br/> 例外: *ExceptIfDocumentNameMatchesPatterns*|    模様    |添付ファイル名に特定の正規表現と一致するテキスト パターンが含まれているメッセージです。|
|文書のプロパティが|条件: *Contentpropertyの単語* <br/> 例外: *ExceptIfContentPropertyContainsWords* |Words| 添付ファイルの拡張子が、指定した単語のいずれかと一致するメッセージまたはドキュメント。|
|ドキュメントサイズが等しいか、より大きい| 条件: *Documentsizeover* <br/> 例外: *ExceptIfDocumentSizeOver*|    Size    |任意の添付ファイルが指定値以上のメッセージです。|

### <a name="message-headers"></a>メッセージ  ヘッダー

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター**| **プロパティの種類**|  **説明**|
|---------|---------|---------|---------|
|ヘッダーに単語または語句が含まれている|条件: *headerん words* <br/> 例外: *ExceptIfHeaderContainsWords*|  ハッシュテーブル  |指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した単語が含まれています。|
|ヘッダーのパターン一致|   条件: *HeaderMatchesPatterns* <br/> 例外: *ExceptIfHeaderMatchesPatterns*|    ハッシュテーブル  |指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した正規表現が含まれています。|

### <a name="message-properties"></a>メッセージのプロパティ

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター**| **プロパティの種類**   |**説明**|
|---------|---------|---------|---------|
|メッセージサイズの超過|条件: *メッセージ* のメッセージ <br/> 例外: *ExceptIfMessageSizeOver*| Size    |合計サイズ (メッセージ プラス添付ファイル) が指定値以上のメッセージです。 <br/>**注** :メールボックスのメッセージ サイズの制限は、メール フロー ルールの前に評価されます。この条件を含むルールがメッセージを処理する前に、メールボックスに対して大きすぎるメッセージが拒否されます。|

## <a name="actions-for-dlp-policies"></a>DLP ポリシーのアクション

次の表では、DLP で使用できる Exchange Online メールフロールールの処理について説明します。


|**DLP でのアクション**|**Microsoft 365 PowerShell のアクションパラメーター**|**プロパティの種類**|**説明**|
|---------|---------|---------|---------|
|ヘッダーの設定|SetHeader|最初のプロパティ: *ヘッダー名* </br> 2番目のプロパティ: *ヘッダー値*|SetHeader パラメーターは、メッセージヘッダー内のヘッダーフィールドと値を追加または変更する DLP ルールのアクションを指定します。 このパラメーターには、構文 "ヘッドホン Ername: HeaderValue" を使用します。 複数のヘッダー名と値のペアをコンマで区切って指定できます。|
|ヘッダーの削除| RemoveHeader| 最初のプロパティ: *MessageHeaderField*</br> 2 番目のプロパティ: *String*|  RemoveHeader パラメーターは、メッセージヘッダーからヘッダーフィールドを削除する DLP ルールのアクションを指定します。 このパラメーターでは、構文として "ヘッドホン Ername" または "-Ername: HeaderValue" を使用します。複数のヘッダー名またはヘッダー名と値のペアをコンマで区切って指定できます。|
|メッセージを特定のユーザーにリダイレクトする|*RedirectMessageTo*|住所| 特定の受信者にメッセージをリダイレクトします。元の受信者にメッセージを配信せず、送信者や元の受信者に通知を送信しません。|
|承認のためにメッセージを送信者の上司に転送する| 中|最初のプロパティ: *ModerateMessageByManager*</br> 2番目のプロパティ: *Boolean*|中パラメーターは、モデレーターに電子メールメッセージを送信する DLP ルールのアクションを指定します。 このパラメーターは、次の構文を使用します。 @ {ModerateMessageByManager = <$true \| $false>;|
|承認のためにメッセージを特定の承認者に転送する| 中|最初のプロパティ: *ModerateMessageByUser*</br>2 番目のプロパティ: *Addresses*|中パラメーターは、モデレーターに電子メールメッセージを送信する DLP ルールのアクションを指定します。 このパラメーターは、次の構文を使用します。 @ {ModerateMessageByUser = @ ("emailaddress1", "emailaddress2",... "emailaddressN")}|
|受信者の追加|AddRecipients|最初のプロパティ: *Field*</br>2 番目のプロパティ: *Addresses*| メッセージの [宛先/Cc/Bcc] フィールドに1人または複数の受信者を追加します。 このパラメーターでは、次の構文を使用します。 @ {<AddToRecipients \| \| BlindCopyTo emailaddress = ""}|
|送信者の上司を受信者として追加する|AddRecipients | 最初のプロパティ: *Addedmanageraction*</br>2番目のプロパティ: *Field* | 送信者の上司を指定の受信者タイプ ( To 、 Cc 、 Bcc ) としてメッセージに追加したり、送信者や受信者に通知することなくメッセージを送信者の上司にリダイレクトします。 このアクションは、送信者の Manager 属性が Active Directory で定義されている場合のみ有効です。 このパラメーターでは、次の構文を使用します。 @ {AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|

