---
title: EOP がフィッシングを防ぐために From アドレスを検証する方法
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
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) および Outlook.com によって承諾または拒否される電子メールアドレスの種類について学び、フィッシングを防ぐことができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196061"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP がフィッシングを防ぐために From アドレスを検証する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


フィッシング攻撃は、電子メール組織にとって常に脅威となります。 [スプーフィング (偽造) された送信者電子メールアドレス](anti-spoofing-protection.md)を使用することに加えて、多くの場合、攻撃者は、インターネット標準に違反した From アドレスの値を使用します。 この種のフィッシングを防ぐために、Exchange Online Protection (EOP) と Outlook.com では、このトピックで説明するように、受信メッセージに RFC 準拠の差出人のアドレスを含めるように要求されています。 この強制は、2017年11月に有効になっています。

**注**:

- このトピックで説明されているように、アドレスが正しくない組織から電子メールを定期的に受信している場合は、最新のセキュリティ標準に準拠するように電子メールサーバーを更新するように組織を促します。

- 関連する Sender フィールド (代理人とメーリングリストで使用) は、これらの要件の影響を受けません。 詳細については、次のブログ投稿を参照してください。 [電子メールの ' sender ' を参照するとどういう](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)ことですか。

## <a name="an-overview-of-email-message-standards"></a>電子メールメッセージの標準の概要

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。 メッセージエンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージエンベロープは [rfc 5321](https://tools.ietf.org/html/rfc5321)で説明されており、メッセージヘッダーについては [rfc 5322](https://tools.ietf.org/html/rfc5322)で説明されています。 メッセージの送信プロセスによって生成されたメッセージエンベロープがメッセージの一部ではないため、受信者に実際のメッセージエンベロープが表示されることはありません。

- `5321.MailFrom`アドレス ( **MAIL FROM** address、P1 sender、または envelope sender とも呼ばれます) は、メッセージの SMTP 送信で使用される電子メールアドレスです。 通常、この電子メールアドレスは、メッセージヘッダーの **リターンパス** ヘッダーフィールドに記録されます (ただし、送信者は別の **リターンパス** 電子メールアドレスを指定することもできます)。

- `5322.From`(From アドレスまたは P2 送信者とも呼ばれる) は、[送信**元**アドレス] フィールドの電子メールアドレスであり、電子メールクライアントに表示される送信者の電子メールアドレスです。 From アドレスは、このトピックに記載されている要件の焦点です。

From アドレスは、いくつかの Rfc (たとえば、RFC 5322 セクション3.2.3、3.4、3.4.1、 [rfc 3696](https://tools.ietf.org/html/rfc3696)) にわたって詳細に定義されています。 アドレス指定には多くのバリエーションがあり、どのような意味があるかは無効です。 簡単にするために、次の形式と定義をお勧めします。

`From: "Display Name" <EmailAddress>`

- [**表示名**: 電子メールアドレスの所有者を説明する省略可能な語句です。

  - 表示名は常に二重引用符 (") で囲むようにすることをお勧めします。 表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む _必要があり_ ます。
  - [差出人] アドレスに表示名を指定する場合は、EmailAddress の値を山かっこ (< >) で囲む必要があります。
  - Microsoft では、表示名と電子メールアドレスの間にスペースを挿入することを強くお勧めします。

- **EmailAddress**: 電子メールアドレスの形式は `local-part@domain` 次のとおりです。

  - **ローカルパート**: アドレスに関連付けられているメールボックスを識別する文字列。 この値は、ドメイン内で一意です。 多くの場合、メールボックスの所有者のユーザー名または GUID が使用されます。
  - **ドメイン**: 電子メールアドレスのローカル部分で識別されたメールボックスをホストする電子メールサーバーの完全修飾ドメイン名 (FQDN)。

  EmailAddress の値に関するその他の考慮事項を次に示します。

  - 電子メールアドレスは1つだけです。
  - 角かっこは、スペースで区切り文字として使用しないことをお勧めします。
  - 電子メールアドレスの後に追加のテキストを含めないでください。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有効な/無効なアドレスの例

以下は、有効な電子メールアドレスです。

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (角かっこと電子メールアドレスの間にスペースがあるため、この方法は推奨されません)。

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (表示名が二重引用符で囲まれていないため、推奨されません)。

次の電子メールアドレスは無効です。

- **From アドレスなし**: 一部の自動メッセージに差出人住所が含まれていません。 以前は、Microsoft 365 または Outlook.com が差出人アドレスを持たないメッセージを受信すると、サービスは次の既定の From: address を追加して、メッセージを配信するようにしました。

  `From: <>`

  これで、空の差出人アドレスを持つメッセージは受け付けられなくなりました。

- `From: Microsoft 365 sender@contoso.com` (表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (電子メールアドレスの後のテキスト)

- `From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれていますが、二重引用符で囲まれていません)。

- `From: "Microsoft 365 <sender@contoso.com>"` (全体の値が誤って二重引用符で囲まれています。)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。

- `From: Microsoft 365<sender@contoso.com>` (表示名と左山かっこの間にスペースはありません)。

- `From: "Microsoft 365"<sender@contoso.com>` (閉じる二重引用符と左山かっこの間にスペースを入れることはできません)。

## <a name="suppress-auto-replies-to-your-custom-domain"></a>カスタムドメインへの自動返信を抑制する

この値を使用して `From: <>` 自動応答を抑制することはできません。 代わりに、カスタムドメインの null MX レコードを設定する必要があります。 応答サーバーがメッセージを送信できる公開アドレスがないため、自動応答 (およびすべての返信) は自然に抑制されます。

- 電子メールを受信できない電子メールドメインを選択します。 たとえば、プライマリドメインが contoso.com の場合は、noreply.contoso.com を選択することができます。

- このドメインの null MX レコードは、1つのピリオドで構成されます。

例:

```text
noreply.contoso.com IN MX .
```

MX レコードのセットアップの詳細については、「 [Microsoft 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)する」を参照してください。

Null MX の公開の詳細については、「 [RFC 7505](https://tools.ietf.org/html/rfc7505)」を参照してください。

## <a name="override-from-address-enforcement"></a>アドレスの強制/無効化

受信電子メールの From アドレス要件をバイパスするには、「 [Microsoft 365 の「差出人セーフリストを作成](create-safe-sender-lists-in-office-365.md)する」の説明に従って、IP 許可一覧 (接続フィルター) またはメールフロールール (トランスポートルールとも呼ばれます) を使用できます。

Microsoft 365 から送信する送信電子メールについては、From アドレスの要件を無効にすることはできません。 さらに、Outlook.com では、サポートによっても、あらゆる種類の上書きを許可しません。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Microsoft 365 で cybercrimes を防止および保護する他の方法

フィッシング、スパム、データ漏洩、およびその他の脅威から組織を強化する方法の詳細については、「 [Microsoft 365 for business プランをセキュリティで保護するための上位10の方法](../../admin/security-and-compliance/secure-your-business-data.md)」を参照してください。
