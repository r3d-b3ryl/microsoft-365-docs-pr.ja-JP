---
title: EOP が From アドレスを検証してフィッシングを防ぐ方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理者は、フィッシングを防ぐために、Exchange Online Protection (EOP) とOutlook.com によって受け入れられるか拒否される電子メール アドレスの種類について学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 92b7072e3127da71f423648c83fc94c17bed7caa
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131066"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP が From アドレスを検証してフィッシングを防ぐ方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

フィッシング攻撃は、すべての電子メール組織に対する絶え間ない脅威です。 攻撃者は [、スプーフィングされた (偽造された) 送信者の電子メール アドレス](anti-spoofing-protection.md)を使用するだけでなく、インターネット標準に違反する差出人アドレスの値を使用することがよくあります。 この種のフィッシングを防ぐために、Exchange Online Protection (EOP) と Outlook.com では、この記事で説明されているように、RFC 準拠の From アドレスを含めるために受信メッセージが必要になりました。 この適用は 2017 年 11 月に有効になりました。

**注意**:

- この記事で説明されているように、不正な形式の From アドレスを持つ組織から定期的に電子メールを受信する場合は、最新のセキュリティ標準に準拠するように電子メール サーバーを更新することをお勧めします。

- 関連する送信者フィールド (代理送信とメーリング リストで使用) は、これらの要件の影響を受けられません。 詳細については、次のブログ投稿を参照してください。 [電子メールの "送信者" を参照する場合の意味は何ですか](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)?

## <a name="an-overview-of-email-message-standards"></a>電子メール メッセージ標準の概要

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でのメッセージの送信と配信に必要な情報が含まれています。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは [RFC 5321](https://tools.ietf.org/html/rfc5321) で説明されており、メッセージ ヘッダーは [RFC 5322](https://tools.ietf.org/html/rfc5322) で説明されています。 メッセージ エンベロープはメッセージ送信プロセスによって生成されるもので、実際にはメッセージの一部ではないため、受信者がメッセージ エンベロープを目にすることはありません。

- `5321.MailFrom`アドレス (**MAIL FROM** アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれます) は、メッセージの SMTP 送信で使用されるメール アドレスです。 このメール アドレスは通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者は別の **Return-Path** メール アドレスを指定できます)。

- `5322.From` (差出人アドレスまたは P2 送信者とも呼ばれます) は、[**差出人** ヘッダー] フィールドのメール アドレスであり、メール クライアントに表示される送信者のメール アドレスです。 差出人アドレスは、この記事の要件の焦点です。

From アドレスは、複数の RFC (RFC 5322 セクション 3.2.3、3.4、3.4.1、 [RFC 3696](https://tools.ietf.org/html/rfc3696) など) で詳細に定義されています。 アドレス指定と、有効または無効と見なされるものには多くのバリエーションがあります。 シンプルにするために、次の形式と定義をお勧めします。

`From: "Display Name" <EmailAddress>`

- **表示名**: 電子メール アドレスの所有者を表す省略可能な語句。

  - 表示名は、常に二重引用符 (") で囲んで表示することをお勧めします。 表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む _必要があります_ 。
  - 差出人アドレスに表示名が含まれている場合、EmailAddress の値は、次のように山かっこ (< >) で囲む必要があります。
  - 表示名とメール アドレスの間にスペースを挿入することを強くお勧めします。

- **EmailAddress**: 電子メール アドレスは次の形式 `local-part@domain`を使用します。

  - **local-part**: アドレスに関連付けられているメールボックスを識別する文字列。 この値はドメイン内で一意です。 多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。
  - **domain**: 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。

  EmailAddress 値の追加の考慮事項を次に示します。

  - 1 つのメール アドレスのみ。
  - 山かっこをスペースで区切らないことをお勧めします。
  - メール アドレスの後に追加のテキストを含めないでください。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>From アドレスの有効なアドレスと無効なアドレスの例

次の From 電子メール アドレスが有効です。

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (山かっことメール アドレスの間にスペースがあるため、お勧めしません)。

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (表示名は二重引用符で囲まれていないためお勧めしません。

次の From 電子メール アドレスは無効です。

- **差出人アドレスなし**: 一部の自動メッセージには差出人アドレスが含まれていません。 以前は、Microsoft 365またはOutlook.com が差出人アドレスのないメッセージを受信したときに、サービスは既定の From: address を追加して、メッセージを配信可能にしました。

  `From: <>`

  これで、差出人アドレスが空白のメッセージは受け入れられなくなりました。

- `From: Microsoft 365 sender@contoso.com` (表示名は存在しますが、メール アドレスは山かっこで囲まれていません)。

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト。

- `From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれていますが、二重引用符で囲まれていません)。

- `From: "Microsoft 365 <sender@contoso.com>"` (値全体が正しく二重引用符で囲まれていない)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は存在しますが、メール アドレスは山かっこで囲まれていません)。

- `From: Microsoft 365<sender@contoso.com>` (表示名と左山かっこの間にスペースはありません。

- `From: "Microsoft 365"<sender@contoso.com>` (終わりの二重引用符と左山かっこの間にスペースはありません。

## <a name="suppress-auto-replies-to-your-custom-domain"></a>カスタム ドメインへの自動応答を抑制する

この値 `From: <>` を使用して自動応答を抑制することはできません。 代わりに、カスタム ドメインの NULL MX レコードを設定する必要があります。 自動応答 (およびすべての応答) は、応答サーバーがメッセージを送信できる公開アドレスがないため、自然に抑制されます。

- メールを受信できないメール ドメインを選択します。 たとえば、プライマリ ドメインが contoso.com されている場合は、noreply.contoso.com を選択できます。

- このドメインの NULL MX レコードは、1 つの期間で構成されます。

例:

```text
noreply.contoso.com IN MX .
```

MX レコードの設定の詳細については、「[Microsoft 365用の任意の DNS ホスティング プロバイダーで DNS レコードを作成する」を](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)参照してください。

NULL MX の発行の詳細については、 [RFC 7505](https://tools.ietf.org/html/rfc7505) を参照してください。

## <a name="override-from-address-enforcement"></a>アドレスの適用からオーバーライドする

受信メールの差出人アドレス要件をバイパスするには、「Microsoft 365での[差出人セーフ](create-safe-sender-lists-in-office-365.md) リストの作成」の説明に従って、IP 許可一覧 (接続フィルター処理) またはメール フロー ルール (トランスポート ルールとも呼ばれます) を使用できます。

Microsoft 365から送信する送信メールの差出人アドレス要件をオーバーライドすることはできません。 また、Outlook.com では、サポートを通じても、いかなる種類のオーバーライドも許可されません。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Microsoft 365のサイバー犯罪を防止および保護するその他の方法

フィッシング、スパム、データ侵害、その他の脅威から組織を強化する方法の詳細については、「[ビジネス プランのMicrosoft 365をセキュリティで保護する上位 10 の方法](../../admin/security-and-compliance/secure-your-business-data.md)」を参照してください。
