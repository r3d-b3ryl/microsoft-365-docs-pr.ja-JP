---
title: DMARC を使用してメールを検証する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: Domain-based Message Authentication, Reporting, and Conformance (DMARC) を構成して、組織から送信されたメッセージを検証する方法について説明します。
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016323"
---
# <a name="use-dmarc-to-validate-email"></a>DMARC を使用してメールを検証する

Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) は、Sender Policy Framework (SPF) および DomainKeys Identified Mail (DKIM) と併用することで、メールの送信者を認証できるようになり、送信先の電子メール システムはドメインから送信されたメッセージを信頼するようになります。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。

> [!TIP]
> Microsoft 365 用の DMARC レポートを提供しているサードパーティ ベンダーを確認するには、「[Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog)」(Microsoft インテリジェント セキュリティ アソシエーション) カタログを参照してください。

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>SPF と DMARC が連携して Microsoft 365 の電子メールを保護するしくみ

 電子メール メッセージには、発信者、送信者、またはアドレスが含まれていることがあります。 これらのアドレスは、さまざまな目的に使用できます。 たとえば、次のアドレスについて考えてみましょう。

- **「Mail From」アドレス**: 送信者を識別し、メッセージの配信に問題が発生した場合に、配信不能通知などの通知の返送先を指定します。 これは電子メール メッセージのエンベロープ部分に表示されます。通常、ユーザーの電子メール アプリケーションには表示されません。 これは、5321.MailFrom アドレスまたはリバース パス アドレスとも呼ばれます。

- **「From」アドレス**: From アドレスとして、ユーザーの電子メール アプリケーションに表示されるアドレス。 このアドレスにより、電子メールの作成者を識別します。 つまり、メッセージを書いた個人またはシステムのメールボックスになります。 これは、 5322.From アドレスとも呼ばれます。

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

このトランスクリプトでは、送信者のアドレスは次にようになります。

- Mail From アドレス (5321.MailFrom): phish@phishing.contoso.com

- From アドレス (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>DMARC TXT レコードとは

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Microsoft の DMARC TXT レコードは、次のような内容になります。

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft は、DMARC レポートをサード パーティの [Agari](https://agari.com) に送信します。 Agari では、DMARC レポートを収集して分析します。 Microsoft 365 用の DMARC レポートを提供している他のサードパーティ ベンダーを確認するには、[MISA カタログ](https://www.microsoft.com/misapartnercatalog)を参照してください。

## <a name="implement-dmarc-for-inbound-mail"></a>受信メール用に DMARC を実装する

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>Microsoft 365 からの送信メール用に DMARC を実装する

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [手順 1:ドメインに対する有効なメールのソースを特定する](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [手順 2: ドメイン用に SPF をセットアップする](#step-2-set-up-spf-for-your-domain)

- [手順 3: カスタム ドメイン用に DKIM をセットアップする](#step-3-set-up-dkim-for-your-custom-domain)

- [手順 4: ドメイン用の DMARC TXT レコードを作成する](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>手順 1:ドメインに対する有効なメールのソースを特定する

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- どの IP アドレスにドメインからメッセージを送信するか。

- 自分の代わりにサード パーティから送信されるメールについて、5321.MailFrom ドメインと 5322.From ドメインが一致しているか。

### <a name="step-2-set-up-spf-for-your-domain"></a>手順 2: ドメイン用に SPF をセットアップする

すべての有効な送信者の一覧が用意できると、「[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」手順を実行できるようになります。

たとえば、contoso.com が Exchange Online からメールを送信するとします。このとき、オンプレミスの Exchange サーバーの IP アドレスが 192.168.0.1、Web アプリケーションの IP アドレスが 192.168.100.100 だと仮定すると、SPF TXT テキストレコードは次のようになります。

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

ベスト プラクティスとして、SPF TXT レコードでは、サード パーティの送信者についても考慮に入れておく必要があります。

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>手順 3: カスタム ドメイン用に DKIM をセットアップする

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

サード パーティの送信者がドメインを偽装できるように DKIM をセットアップする方法を含め、ドメインの DKIM をセットアップする手順については、「[DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>手順 4: ドメイン用の DMARC TXT レコードを作成する

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

各部分の意味は次のとおりです。

- *domain* は、保護対象にするドメインです。 既定では、このレコードは、ドメインとすべてのサブドメインからのメールを保護します。 たとえば、\_dmarc.contoso.com を指定すると、DMARC は、このドメインとすべてのサブドメイン (housewares.contoso.com や plumbing.contoso.com など) からのメールを保護します。

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* は、このルールがメールの 100% に使用される必要があることを示します。

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

どのオプションを使用するかについては、「[Microsoft 365 で DMARC を実装する際のベスト プラクティス](#best-practices-for-implementing-dmarc-in-microsoft-365)」の概念をよく理解してください。

例:

- ポリシーをなし (none) に設定する

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- ポリシーを検疫 (quarantine) に設定する

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- ポリシーを拒否 (reject) に設定する

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Microsoft 365 で DMARC を実装する際のベスト プラクティス

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. DMARC の実装による影響を監視する

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. DMARC に失敗したメールの検疫を外部のメール システムに要求する

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. DMARC に失敗したメッセージを受け取らないように外部システムに要求する

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Microsoft 365 が DMARC に失敗した送信メールを処理する方法

メッセージが Microsoft 365 から送信され、DMARC に失敗し、ポリシーを p=quarantine または p=reject に設定していると、メッセージは「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」によってルーティングされます。 送信メールの上書きはありません。

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Microsoft 365 が DMARC に失敗した受信メールを処理する方法

送信側サーバーの DMARC ポリシーが `p=reject` の場合、EOP はメッセージを拒否するのではなく、スプーフィングとしてのマークを付けます。 つまり、受信メールの場合、Microsoft 365 は `p=reject` と `p=quarantine` を同様に扱うということです。 管理者は、[フィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)内のスプーフィングとして分類されたメッセージに対するアクションを定義できます。

このように Microsoft 365 が構成されている理由は、一部の正当なメールが DMARC に失敗することがあるためです。 たとえば、メッセージがメーリング リストに送信されてから、リストのすべての参加者にメッセージが中継される場合、DMARC に失敗することがあります。 こうしたメッセージを Microsoft 365 が拒否すると、受信者は正当なメールを失うことになり、そのメールを取得する手段がなくなります。 その代わりに、このようなメッセージは DMARC に失敗するようにしておき、スパムのマークを付けて拒否しないようにします。 必要であれば、ユーザーは自分の受信トレイから、次の方法でメッセージを取得できます。

- ユーザーが、自分のメール クライアントを使用して、個別に安全な送信者を追加します。

- 管理者は、[スプーフィング インテリジェンス](learn-about-spoof-intelligence.md) レポートを更新して、スプーフィングを許可できます。

- 管理者が、該当する送信者のメッセージを許可するすべてのユーザーに向けて Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。

詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Microsoft 365 でオーセンティケーテッド レシーブド チェーン (ARC) を活用する方法

Microsoft 365 でホストされているすべてのメール ボックスでは、向上したメッセージの配信率と強化されたスプーフィング対策保護と共に、ARC の利点が得られます。 ARC では、元のサーバーから受信者のメールボックスへと電子メールがルーティングされると、すべての関与する仲介役、つまりホップからの電子メール認証の結果が保持されます。 ARC 以前、転送ルールまたは自動署名などの電子メール ルーティングの仲介役によって実行される変更は、受信者のメールボックスで電子メールが受信される時間によって DMARC の失敗を引き起こす場合があります。 ARC を使用すると、認証の結果の暗号化保存により、Microsoft 365 では電子メールの送信者の真正性を検証することができます。

Microsoft が ARC Sealer の場合、現在、Microsoft 365 では ARC を使用して認証の結果を検証します。しかし、将来的にはサードパーティの ARC Sealer のサポートを追加する予定です。

## <a name="troubleshooting-your-dmarc-implementation"></a>DMARC 実装のトラブルシューティング

ドメインの MX レコードを構成したときに、最初のエントリを EOP 以外にすると、DMARC の失敗はドメインに強制されなくなります。

お客様の場合でも、ドメインのプライマリ MX レコードが EOP を指していないと、DMARC による利点は得られなくなります。 たとえば、MX レコードがオンプレミスのメール サーバーを指していて、コネクタを使用することで EOP にメールをルーティングしていると、DMARC は機能しなくなります。 このシナリオでは、受信側ドメインは認証済みドメインのいずれかになりますが、EOP はプライマリ MX ではありません。 たとえば、contoso.com がそれ自体の MX をポイントしていて、セカンダリ MX レコードとして EOP を使用しているとすると、contoso.com の MX レコードは次のようになります。

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

すべて、またはほとんどのメールは、最初にプライマリ MX である mail.contoso.com にルーティングされてから、EOP にルーティングされます。 場合によっては、MX レコードとして EOP をリストすることさえなく、単にメールをルーティングするようにコネクタを接続していることもあります。 EOP は、DMARC 検証を行うための最初のエントリである必要はありません。 検証は、オンプレミスまたは O365 以外のすべてのサーバーが DMARC チェックを行うわけではないため、検証だけを行います。  DMARC TXT レコードを設定するときに顧客のドメイン (サーバーではなく) に対して DMARC を強制できますが、実際に強制するのは受信サーバーだけです。  EOP を受信サーバーとして設定すると、EOP は DMARC 強制を行います。

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC のトラブルシューティング グラフィック、Daniel Mande 提供":::

## <a name="for-more-information"></a>詳細情報

Want more information about DMARC? These resources can help.

- [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)には、Microsoft 365 が DMARC チェックに使用する構文とヘッダー フィールドが含まれています。

- M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group) の「<sup>DMARC TRAINING SERIES</sup>」

- [dmarcian](https://space.dmarcian.com/deployment/) のチェックリストを使用する。

- [DMARC.org](https://dmarc.org) のソースに直接アクセスする。

## <a name="see-also"></a>関連項目

[Microsoft 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法](how-office-365-uses-spf-to-prevent-spoofing.md)

[Microsoft 365 で SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[DKIM を使用して、Microsoft 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)
