---
title: EOP がフィッシングを防止するために From アドレスを検証する方法
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
description: 管理者は、Exchange Online Protection (EOP) および Outlook.com で受け入れまたは拒否される電子メール アドレスの種類について説明し、フィッシングを防止できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 412b6eb7045051c21a88c8b4b2ba5e80a06832dd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199431"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP がフィッシングを防止するために From アドレスを検証する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

フィッシング攻撃は、メール組織にとって絶え間ない脅威です。 攻撃者は、ス [プーフィングされた (偽造された)](anti-spoofing-protection.md)送信者の電子メール アドレスの使用に加えて、インターネット標準に違反する差出人アドレスの値を使用する場合が多い。 この種類のフィッシングを防止するために、Exchange Online Protection (EOP) と Outlook.com では、この記事で説明するように RFC 準拠の From アドレスを含める受信メッセージが必要になります。 この適用は 2017 年 11 月に有効になっています。

**注意**:

- この記事の説明に従って、不正な形式のアドレスを持つ組織から定期的にメールを受信する場合は、これらの組織に最新のセキュリティ標準に準拠するように電子メール サーバーを更新するようお勧めします。

- 関連する [送信者] フィールド ([Send on Behalf and mailing lists] で使用) は、これらの要件の影響を受け取らない。 詳細については、次のブログ投稿を参照してください。 電子メールの ['sender'](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)を参照する場合の意味は?

## <a name="an-overview-of-email-message-standards"></a>電子メール メッセージ標準の概要

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは [RFC 5321](https://tools.ietf.org/html/rfc5321)で説明され、メッセージ ヘッダーは [RFC 5322 で説明されています](https://tools.ietf.org/html/rfc5322)。 受信者は、メッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、実際のメッセージ エンベロープは表示されません。

- アドレス (MAIL FROM アドレス、P1 送信者、封筒送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。  この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。

- (From アドレスまたは P2 送信者とも呼ばれる) は、[差出人] ヘッダー フィールドの電子メール アドレスであり、電子メール クライアントに表示される送信者の電子メール アドレス `5322.From` です。  From アドレスは、この記事の要件の焦点です。

From アドレスは、複数の RFC (たとえば、RFC 5322 セクション 3.2.3、3.4、および 3.4.1、 [および RFC 3696)](https://tools.ietf.org/html/rfc3696)で詳細に定義されます。 アドレス指定には多くのバリエーションがあります。また、有効または無効と見なされるものがあります。 シンプルに保つために、次の形式と定義をお勧めします。

`From: "Display Name" <EmailAddress>`

- **[表示名**]: 電子メール アドレスの所有者を表すオプションの語句です。

  - 表示名は、常に二重引用符 (") で囲んで表示することをお勧めします。 表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。 
  - From アドレスに表示名が含まれる場合、EmailAddress 値は、図のように角かっこ (< >) で囲む必要があります。
  - 表示名と電子メール アドレスの間にスペースを挿入強く推奨します。

- **EmailAddress**: 電子メール アドレスは、次の形式を使用します `local-part@domain` 。

  - **local-part**: アドレスに関連付けられたメールボックスを識別する文字列。 この値は、ドメイン内で一意です。 多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。
  - **domain**: 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。

  EmailAddress 値に関する追加の考慮事項を次に示します。

  - メール アドレスは 1 つのみです。
  - 角かっこはスペースで区切らすることをお勧めします。
  - 電子メール アドレスの後に追加のテキストを含めない。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有効で無効な From アドレスの例

次の From 電子メール アドレスが有効です。

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (角かっこと電子メール アドレスの間にスペースが含まれているため、お勧めしません)。

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (表示名は二重引用符で囲まないので、お勧めしません。

次の From 電子メール アドレスが無効です。

- **No From address**: 一部の自動メッセージには From アドレスが含まれます。 過去に、Microsoft 365 または Outlook.com が From アドレスなしでメッセージを受信した場合、サービスは次の既定の From: アドレスを追加してメッセージを配信可能にしました。

  `From: <>`

  これで、From アドレスが空白のメッセージは受け入れなくなりました。

- `From: Microsoft 365 sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト。

- `From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれますが、二重引用符で囲む必要はありません)。

- `From: "Microsoft 365 <sender@contoso.com>"` (値全体が誤って二重引用符で囲まれます)。

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。

- `From: Microsoft 365<sender@contoso.com>` (表示名と左かっこの間にスペースはありません。

- `From: "Microsoft 365"<sender@contoso.com>` (閉じる二重引用符と左かっこの間にスペースはありません。

## <a name="suppress-auto-replies-to-your-custom-domain"></a>カスタム ドメインへの自動返信を抑制する

値を使用して自動 `From: <>` 返信を抑制することはできません。 代わりに、カスタム ドメインの NULL MX レコードを設定する必要があります。 応答側サーバーがメッセージを送信できる公開アドレスが存在しないので、自動返信 (およびすべての返信) は自然に抑制されます。

- メールを受信できないメール ドメインを選択します。 たとえば、プライマリ ドメインが使用されている場合 contoso.com を選択 noreply.contoso.com。

- このドメインの NULL MX レコードは、1 つの期間で構成されます。

次に例を示します。

```text
noreply.contoso.com IN MX .
```

MX レコードの設定の詳細については、「任意の DNS ホスティング プロバイダーで DNS レコードを作成する」[を](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)参照Microsoft 365。

NULL MX の発行の詳細については [、「RFC 7505」を参照してください](https://tools.ietf.org/html/rfc7505)。

## <a name="override-from-address-enforcement"></a>Override From address enforcement

受信メールの差出人アドレス要件をバイパスするには、「Microsoft 365 で差出人セーフ リストを作成する」の説明に従って、IP 許可一覧 (接続フィルター) またはメール フロー ルール (トランスポート ルールとも呼ばれる)[を使用できます](create-safe-sender-lists-in-office-365.md)。

メールから送信する送信メールの From アドレス要件を上書きMicrosoft 365。 さらに、Outlook.com は、サポートを通じても、いかなる種類のオーバーライドも許可しない。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>サイバー犯罪を防止し、保護するその他のMicrosoft 365

フィッシング、スパム、データ侵害、その他の脅威に対して組織を強化する方法の詳細については、「ビジネス プランのセキュリティで保護するためのトップ[10](../../admin/security-and-compliance/secure-your-business-data.md)Microsoft 365方法」を参照してください。