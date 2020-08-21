---
title: EOP がフィッシングを防止するために送信元アドレスを検証する方法
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
description: 管理者は、Exchange Online Protection (EOP) によって承諾または拒否された電子メール アドレスの種類とフィッシング対策に役立つ Outlook.com の種類について学習することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827423"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP がフィッシングを防止するために送信元アドレスを検証する方法

フィッシング攻撃は、すべてのメール組織に対して常に脅威を引き出す可能性があります。 スプーフィング [された (偽の) 送信者](anti-spoofing-protection.md)のメール アドレスに加えて、攻撃者は、インターネット標準に反する差出人アドレスの値をよく使用します。 この種類のフィッシングを防止するために、このトピックで説明したように、Exchange Online Protection (EOP) および Outlook.com では、受信メッセージに RFC に準拠した送信者アドレスを含めるように要求しています。 この強制は、2017 年 11 月に有効になりました。

**注**:

- このトピックで説明されているとおり、差出先アドレスの形式が正しい組織からメールを定期的に受信する場合は、最新のセキュリティ基準に準拠するように組織の電子メール サーバーを更新するようにします。

- 関連する送信者フィールド (代理人として送信する、メール送信リストによって使用される) は、これらの要件の影響を受けません。 詳細については、次のブログ投稿を参照してください。メールの「送信者」を参照する[場合はどうやっても何を意味しますか?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)

## <a name="an-overview-of-email-message-standards"></a>電子メール メッセージ標準の概要

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でのメッセージの送信と配信に必要な情報が含まれます。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは [RFC 5321 で](https://tools.ietf.org/html/rfc5321)説明され、メッセージ ヘッダーは [RFC 5322 で表されます](https://tools.ietf.org/html/rfc5322)。 実際のメッセージ エンベロープはメッセージ送信プロセスによって生成されるもので、実際にはメッセージの一部ではないため、受信者が実際のメッセージ エンベロープを認識することはない。

- アドレス `5321.MailFrom` **(MAIL FROM** アドレス、P1 送信者、またはエンベロープの差出人とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール アドレスです。 通常、この電子メール アドレスはメッセージ ヘッダー **の Return-Path** ヘッダー フィールドに記録されます (ただし、差出人は異なる **Return-Path メール アドレスを指定** することができます)。

- From アドレスまたは P2 送信者とも呼ばれる) は From ヘッダー フィールドのメール アドレスで、メール クライアントに表示される差出人 `5322.From` のメール アドレスです。 **From** From アドレスは、このトピックの要件の中で重点的に説明します。

From アドレスは、複数の RFC の詳細で定義されます (RFC 5322 セクション 3.2.3、3.4、3.4.1、RFC [3696](https://tools.ietf.org/html/rfc3696)など)。 アドレス指定に関するバリエーションは数多く、有効または無効と見なされるものがあります。 簡単にするために、次の形式と定義をお勧めします。

`From: "Display Name" <EmailAddress>`

- **表示名**: メール アドレスの所有者を説明するオプションの語句。

  - 表示名は、表示されているように常に二重引用符 (") で囲むことをお勧めします。 表示名にコンマが含まれる場合_must_、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。
  - From アドレスに表示名が含まれている場合は、示すように、EmailAddress の値を角かっこ (< >) で囲む必要があります。
  - 表示名と電子メール アドレスの間にスペースを挿入するのを強くお勧めします。

- **EmailAddress**: メール アドレスに次の形式が使用されます `local-part@domain` 。

  - **local-part**: そのアドレスに関連付けられているメールボックスを識別する文字列。 この値はドメイン内で一意です。 多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。
  - **domain:** 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。

  EmailAddress 値に関するその他の考慮事項を次に示します。

  - 電子メール アドレスは 1 つだけです。
  - 角かっこはスペースで区切ないことをお勧めします。
  - メール アドレスの後に追加のテキストを含めないでください。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有効な、無効な送信元アドレスの例

次の送信元メール アドレスが有効です。

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` 角かっこと電子メール アドレスの間にスペースがあるため、推奨しません。

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (表示名が二重引用符で囲されていないため推奨されません)。

次の [送信元のメール アドレスが無効です]

- **[いいえ]**: 一部の自動メッセージに From アドレスが含まれていない。 Microsoft 365 または Outlook.com が From アドレスのないメッセージを受信すると、メッセージを配信可能にするために、サービスは次の既定の From: アドレスを追加しました。

  `From: <>`

  この時点で、送信元アドレスが空白のメッセージを受け入れながらしなけれなけれなけれなけれなけ開始されました。

- `From: Microsoft 365 sender@contoso.com` (表示名が存在しますが、電子メール アドレスは角かっこで囲む表は囲じません)。

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト。

- `From: Sender, Example <sender.example@contoso.com>` 表示名にカンマが含まれますが、二重引用符で囲んではいません。

- `From: "Microsoft 365 <sender@contoso.com>"` 値全体が二重引用符で囲まれます。

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名が存在しますが、電子メール アドレスは角かっこで囲む表は囲じません)。

- `From: Microsoft 365<sender@contoso.com>` 表示名と左角かっこの間にスペースは必要ありません。

- `From: "Microsoft 365"<sender@contoso.com>` 二重引用符と左角かっこの間にスペースを空けません。

## <a name="suppress-auto-replies-to-your-custom-domain"></a>カスタム ドメインへの自動返信を抑制する

この値を使用して `From: <>` 自動応答を表示しない。 代わりに、カスタム ドメインに対して NULL MX レコードを設定する必要があります。 自動応答 (およびすべての返信) は、応答サーバーがメッセージを送信できる公開済みアドレスがないため、当然に抑制されます。

- メールを受信しないメール ドメインを選む。 たとえば、プライマリ ドメインがプライマリ ドメインであるcontoso.com場合に、ユーザーのドメインnoreply.contoso.com。

- このドメインの null の MX レコードは、1 つの期間で構成されます。

たとえば、次のようにします。

```text
noreply.contoso.com IN MX .
```

MX レコードの設定の詳細については、「任意の [DNS ホスティング プロバイダーで Microsoft 365 用の DNS レコードを作成する」を参照してください](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

Null MX の公開の詳細については [、RFC 7505 をご覧ください](https://tools.ietf.org/html/rfc7505)。

## <a name="override-from-address-enforcement"></a>From アドレスの適用を上書きする

受信メールの差出人アドレスの要件をバイパスするには [、Microsoft 365](create-safe-sender-lists-in-office-365.md)で安全な送信者のリストを作成する方法に規されている IP 許可一覧 (接続フィルター) またはメール フロー ルール (別名: トランスポート ルール) を使用できます。

Microsoft 365 から送信される送信メールの From アドレスの要件を上書きしてはいけない。 また、サポートOutlook.com上書きが許可されない場合があります。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Microsoft 365 のサイバーキルを防止および保護するその他の方法

フィッシング、スパム、データ侵害、その他の脅威から組織を強度に強度化する方法の詳細については、 [上位 10 の方法によるビジネス向け Microsoft 365 プランをセキュリティで保護する方法をご覧ください](../../admin/security-and-compliance/secure-your-business-data.md)。
