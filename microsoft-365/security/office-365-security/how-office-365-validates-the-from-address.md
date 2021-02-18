---
title: EOP がフィッシング詐欺を防ぐために From アドレスを検証する方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) によって受け付けまたは拒否される電子メール アドレスの種類と、フィッシングOutlook.comに役立つ情報を確認できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ced200c2e521533c1dec8a9d0917add7ca058f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287821"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP がフィッシング詐欺を防ぐために From アドレスを検証する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

フィッシング攻撃は、すべての電子メール組織にとって絶え間ない脅威です。 攻撃者は、 [スプーフィングされた (偽造された)](anti-spoofing-protection.md)送信者の電子メール アドレスを使用する以外に、インターネット標準に違反する差出人アドレスの値を頻繁に使用します。 この種のフィッシングを防止するために、Exchange Online Protection (EOP) と Outlook.com では、この記事で説明するように、RFC 準拠の差出人アドレスを含める受信メッセージが必要になります。 この実施は、2017 年 11 月に有効になっています。

**注**:

- この記事で説明したように、From アドレスの形式が正しい組織からメールを定期的に受信する場合は、最新のセキュリティ標準に準拠するように電子メール サーバーを更新するよう組織に勧めします。

- 関連する Sender フィールド ([代理送信] および [郵送リスト] で使用) は、これらの要件の影響を受け取らない。 詳細については、次のブログ投稿を参照してください。メールの「送信者」を参照した場合の[意味は何ですか。](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)

## <a name="an-overview-of-email-message-standards"></a>電子メール メッセージの標準の概要

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれます。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは [RFC 5321](https://tools.ietf.org/html/rfc5321)で記述され、メッセージ ヘッダーは [RFC 5322 で記述されています](https://tools.ietf.org/html/rfc5322)。 実際のメッセージ エンベロープはメッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、受信者には表示されません。

- アドレス (MAIL FROM アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。  この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。

- The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients. From アドレスは、この記事の要件の焦点です。

From アドレスは、いくつかの RFC (RFC 5322 セクション 3.2.3、3.4、3.4.1、RFC [3696](https://tools.ietf.org/html/rfc3696)など) で詳細に定義されます。 アドレス指定には多くのバリエーションが存在し、有効または無効と見なされるものがあります。 シンプルに保つために、次の形式と定義をお勧めします。

`From: "Display Name" <EmailAddress>`

- **表示名**: 電子メール アドレスの所有者を説明するオプションの語句。

  - 次に示すように、表示名は常に二重引用符 (") で囲む必要があります。 表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。 
  - From アドレスに表示名が含まれる場合は、次に示すように EmailAddress 値を角かっこ (< >) で囲む必要があります。
  - 表示名と電子メール アドレスの間にスペースを挿入強く推奨します。

- **EmailAddress**: 電子メール アドレスは次の形式を使用します `local-part@domain` 。

  - **local-part**: アドレスに関連付けられているメールボックスを識別する文字列。 この値はドメイン内で一意です。 多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。
  - **domain**: 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。

  EmailAddress 値に関する追加の考慮事項を次に示します。

  - 1 つのメール アドレスのみ。
  - 角かっこはスペースで区切らはお勧めしません。
  - メール アドレスの後にテキストを追加しない。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有効な From アドレスと無効な From アドレスの例

次の From 電子メール アドレスが有効です。

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (角かっこと電子メール アドレスの間にスペースが含まれているため、お勧めしません。

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (表示名は二重引用符で囲んでいないので、お勧めしません。

次の From 電子メール アドレスは無効です。

- **[From アドレスなし**]: 一部の自動メッセージには From アドレスが含まれます。 Microsoft 365 または Outlook.com が From アドレスのないメッセージを受信した場合、サービスは次の既定の From: アドレスを追加してメッセージを配信可能にしました。

  `From: <>`

  これで、空の From アドレスを持つメッセージは受け付けなくなりました。

- `From: Microsoft 365 sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト)。

- `From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれますが、二重引用符で囲む必要はありません)。

- `From: "Microsoft 365 <sender@contoso.com>"` (値全体が誤って二重引用符で囲まれている。

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。

- `From: Microsoft 365<sender@contoso.com>` (表示名と左の角かっこの間にはスペースはありません。

- `From: "Microsoft 365"<sender@contoso.com>` (終了二重引用符と左の角かっこの間にはスペースはありません。

## <a name="suppress-auto-replies-to-your-custom-domain"></a>カスタム ドメインへの自動返信を抑制する

この値を使用して `From: <>` 自動応答を抑制することはできません。 代わりに、カスタム ドメインの NULL MX レコードを設定する必要があります。 自動応答 (およびすべての返信) は、応答側サーバーがメッセージを送信できる発行済みアドレスが存在しないので、自然に抑制されます。

- メールを受信できないメール ドメインを選択します。 たとえば、プライマリ ドメインがcontoso.com場合は、次のnoreply.contoso.com。

- このドメインの NULL MX レコードは、1 つのピリオドで構成されます。

例:

```text
noreply.contoso.com IN MX .
```

MX レコードの設定の詳細については [、「Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)の任意の DNS ホスティング プロバイダーで DNS レコードを作成する」を参照してください。

NULL MX の公開の詳細については [、RFC 7505 を参照](https://tools.ietf.org/html/rfc7505)してください。

## <a name="override-from-address-enforcement"></a>アドレスの適用による上書き

受信メールの差出人アドレスの要件を回避するには [、「Microsoft 365](create-safe-sender-lists-in-office-365.md)で差出人セーフ リストを作成する」の説明に従って、IP 許可一覧 (接続フィルター) またはメール フロー ルール (トランスポート ルールとも呼ばれる) を使用できます。

Microsoft 365 から送信する送信メールの From アドレス要件を上書きできない。 また、サポートOutlook.com、どのような種類のオーバーライドも許可されていません。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Microsoft 365 でのサイバー犯罪を防止して保護するその他の方法

フィッシング、スパム、データ侵害、その他の脅威に対して組織を強化する方法の詳細については、「ビジネス プラン向け [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)をセキュリティで保護するトップ 10 の方法」を参照してください。
