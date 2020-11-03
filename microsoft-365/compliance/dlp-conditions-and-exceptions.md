---
title: DLP ポリシーの条件と例外 (プレビュー)
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
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841473"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>DLP ポリシーの条件と例外 (プレビュー)

DLP ポリシー内の条件と例外は、ポリシーが適用される機密アイテムを識別します。 条件では、除外する対象と例外を定義します。 すべての条件に対応する例外があり、まったく同じ構文を使用します。

 ほとんどの条件と例外には、1つ以上の値をサポートする1つのプロパティがあります。 たとえば、DLP ポリシーが Exchange メールに適用されている場合、 **送信者** の条件にはメッセージの送信者が必要です。 プロパティが 2 つある条件もあります。 たとえば、 **メッセージ ヘッダーにこれらの単語のいずれかが含まれる** という条件には、ヘッダーを指定するプロパティ 1 つと、ヘッダー フィールド内で検索するテキストを指定する 2 つめのプロパティが必要です。 一部の条件または例外にはプロパティがありません。 たとえば、 **添付ファイルはパスワード** で保護された状態で、パスワードで保護されたメッセージ内の添付ファイルを検索するだけです。

## <a name="conditions-and-exceptions-for-dlp-policies"></a>DLP ポリシーの条件と例外

次のセクションの表では、DLP で使用可能な条件と例外について説明します。

- [[Senders (送信者)](#senders)]
- [受信者](#recipients)
- [メッセージの件名または本文](#message-subject-or-body)
- [添付ファイル](#attachments)
- [メッセージ ヘッダー](#message-headers)
- [メッセージのプロパティ](#message-properties)

## <a name="senders"></a>送信者


|**DLP の条件または例外**  |**Microsoft 365 PowerShell の条件/例外パラメーター** |**プロパティの種類**  |**説明**|
|---------|---------|---------|---------|
|送信者が |条件: *From* <br/> 例外: *ExceptIfFrom*      |住所 |     組織内の指定されたメールボックス、メールユーザー、メール連絡先、または Microsoft 365 グループによって送信されるメッセージ。|
|送信者の IP アドレスが     |条件: *senderipranges 特定*<br/> 例外: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | 送信者の IP アドレスが、指定した IP アドレスと一致するか、指定した IP アドレスの範囲内にあるメッセージです。       |
|送信者のアドレスに単語が含まれている   | 条件: *Fromaddressん words* <br/> 例外: *ExceptIfFromAddressContainsWords*        |   Words      |   送信者のメール アドレスに指定の単語が含まれているメッセージです。|
| 送信者のアドレスがパターンに一致する    | 条件: *FromAddressMatchesPatterns* <br/> 例外: *ExceptFromAddressMatchesPatterns*       |      模様   |  送信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。  |
|送信者のドメインが  |  条件: *SenderDomainIs* <br/> 例外: *ExceptIfSenderDomainIs*       |ネーム         |     送信者のメール アドレスのドメインが指定された値と一致するメッセージです。 指定したドメイン (たとえば、ドメインの任意のサブドメイン) を *含む* 送信者ドメインを検索する必要がある場合は、次の構文を使用して、 **送信者アドレス一致** ( *FromAddressMatchesPatterns* ) 条件を使用し、ドメインを指定します。 ' \. domain \. com $ '。    |

## <a name="recipients"></a>受信者

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター** |    **プロパティの種類** | **説明**|
|---------|---------|---------|---------|
|受信者が|  条件: *により、に* なります。 <br/> 例外: *ExceptIfSentTo* | 住所 | 受信者の 1 人が組織内の指定されたメールボックス、メール ユーザー、メール連絡先であるメッセージです。 受信者はメッセージの **To** 、 **Cc** 、 **Bcc** のフィールドにいることが可能です。|
|受信者ドメインが|   条件: *受信者 Domainis* <br/> 例外: *ExceptIfRecipientDomainIs* |   ネーム |    送信者のメール アドレスのドメインが指定された値と一致するメッセージです。|
|受信者のアドレスに単語が含まれている|  条件: *受信者アドレス、単語* <br/> 例外: *ExceptIfRecipientAddressContainsWords*|    Words|  受信者のメール アドレスに指定の単語が含まれているメッセージです。 <br/>**注** : この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|受信者のアドレスの一致パターン| 条件: *RecipientAddressMatchesPatterns* <br/> 例外: *ExceptIfRecipientAddressMatchesPatterns*|   模様    |受信者のメール アドレスに、特定の正規表現と一致するテキスト パターンが含まれているメッセージです。 <br/> **注** : この条件が、受信プロキシ アドレスに送信されるメッセージについて考慮していない点に注意してください。受信者のプライマリ メール アドレスに送信されるメッセージのみを照合します。|
|のメンバーに送信| 条件: *トポロジ* <br/> 例外: *ExceptIfSentToMemberOf*|  住所|  指定された配布グループ、メールが有効なセキュリティグループ、または Microsoft 365 グループのメンバーである受信者が含まれているメッセージ。 グループはメッセージの **To** 、 **Cc** 、または **Bcc** フィールドにあることが可能です。|

## <a name="message-subject-or-body"></a>メッセージの件名または本文

|**DLP の条件または例外** | **Microsoft 365 PowerShell の条件/例外パラメーター** |**プロパティの種類**| **説明**|
|---------|---------|---------|---------|
|件名に単語または語句が含まれている| 条件: *Subjectcontainswords* <br/> 例外: *ExceptIf Subjectの単語*| Words   |Subject フィールドに特定の単語を持つメッセージです。|
|サブジェクトが一致するパターン|条件: *SubjectMatchesPatterns* <br/> 例外: *ExceptIf SubjectMatchesPatterns*|模様   |件名フィールドに、指定された正規表現と一致するテキストパターンが含まれているメッセージ。|
|コンテンツが含まれている|  条件: *ContentContainsSensitiveInformation* <br/> 例外 *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  データ損失防止 (DLP) ポリシーで定義されているような機密情報を含むメッセージまたはドキュメント。|


## <a name="attachments"></a>Attachments

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

## <a name="message-headers"></a>メッセージ  ヘッダー

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター**| **プロパティの種類**|  **説明**|
|---------|---------|---------|---------|
|ヘッダーに単語または語句が含まれている|条件: *headerん words* <br/> 例外: *ExceptIfHeaderContainsWords*|  ハッシュテーブル  |指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した単語が含まれています。|
|ヘッダーのパターン一致|   条件: *HeaderMatchesPatterns* <br/> 例外: *ExceptIfHeaderMatchesPatterns*|    ハッシュテーブル  |指定したヘッダー フィールドを含むメッセージであり、そのヘッダー フィールドの値には指定した正規表現が含まれています。|

## <a name="message-properties"></a>メッセージのプロパティ

|**DLP の条件または例外**| **Microsoft 365 PowerShell の条件/例外パラメーター**| **プロパティの種類**   |**説明**|
|---------|---------|---------|---------|
|メッセージサイズの超過|条件: *メッセージ* のメッセージ <br/> 例外: *ExceptIfMessageSizeOver*| Size    |合計サイズ (メッセージ プラス添付ファイル) が指定値以上のメッセージです。 <br/>**注** :メールボックスのメッセージ サイズの制限は、メール フロー ルールの前に評価されます。この条件を含むルールがメッセージを処理する前に、メールボックスに対して大きすぎるメッセージが拒否されます。|

