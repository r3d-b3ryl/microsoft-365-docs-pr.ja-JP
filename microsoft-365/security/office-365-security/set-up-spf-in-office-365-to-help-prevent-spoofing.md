---
title: SPF を設定して、スプーフィングを防止する
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 で Sender Policy Framework (SPF) をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5677d8840226551d31e8f846f8763bcee85c19acd79535939d1688083b5e176
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53810188"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>SPF を設定して、スプーフィングを防止する

- [前提条件](#prerequisites)
- [SPF TXT レコードを作成または更新する](#create-or-update-your-spf-txt-record)
- [サブドメインの処理方法](#how-to-handle-subdomains)
- [SPF のトラブルシューティング](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

この記事では、Office 365 で Sender Policy Framework (SPF) のメール認証をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。

SPF は、カスタム ドメイン(実際の送信元) から来た送信メールを *検証* するのに役立ちます。  これは、全体的に推奨している SPF、 [DKIM](use-dkim-to-validate-outbound-email.md)、[DMARC](use-dmarc-to-validate-email.md) 認証において電子メール認証方法を設定する最初の手順です。

- [前提条件](#prerequisites)
- [SPF TXT レコードを作成または更新する](#create-or-update-your-spf-txt-record)
  - [サブドメインの処理方法](#how-to-handle-subdomains)
- [SPF メール認証で実際に行う操作](#what-does-spf-email-authentication-actually-do)
  - [SPF のトラブルシューティング](#troubleshooting-spf)
- [SPF の詳細情報](#more-information-about-spf)

## <a name="prerequisites"></a>前提条件

> [!IMPORTANT]
> **中小企業のビジネス** または IP アドレスまたは DNS の構成に慣れていない場合は、インターネット ドメイン レジストラーに電話してください (例: GoDaddy、Bluehost、web.com)。また、*SPF のDNS 構成* (および他のメール認証方法) に関してお尋ねください。 <p> **カスタム URL** を使用していない場合 (Office 365 に使用されている URL が **onmicrosoft.com** で終わっている場合) は、Office 365 サービスで SPF が既に設定されています。

では、始めましょう。

Office 365 の SPF TXT レコードは、カスタム ドメインまたはサブドメインの外部の DNS で作成されます。 レコードを作成するには、いくつかの情報が必要です。 次の情報を収集します。

- カスタム ドメインの SPF TXT レコード (存在する場合)。 手順に関しては、「[Office 365 の DNS レコードの作成に必要な情報を収集する](../../admin/get-help-with-domains/information-for-dns-records.md)」をご覧ください。

- メッセージング サーバーに移動して、(すべてのオンプレミス メッセージング サーバーからの必要な) 外部 IP アドレスを発見します。 たとえば、**131.107.2.200** などです。

- SPF TXT レコードに含める必要があるサードパーティ製のすべてのドメインに使用するドメイン名。一部のバルク メール プロバイダーは、顧客用のサブドメインを設定しています。たとえば、会社 MailChimp に **servers.mcsv.net** を設定するなどです。

- SPF TXT レコードで使う強制ルールを決定します。 **-all** ルールが推奨されます。 その他の構文オプションについて詳しくは、「[Office 365 用の SPF TXT レコードの構文](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)」をご覧ください。

> [!IMPORTANT]
> カスタム ドメインを使用するには、Office 365 では、Sender Policy Framework (SPF) TXT レコードを DNS レコードに追加してスプーフィングを防止する必要があります。

## <a name="create-or-update-your-spf-txt-record"></a>SPF TXT レコードを作成または更新する

1. 以下の表の SFP 構文について、十分に理解しておいてください。

   ****

   |要素|もし今使っているとしたら...|お客様に共通のことでは?|追加対象|
   |---|---|---|---|
   |1|いずれかの電子メール システム (必須)|共通。この値で始まるすべての SPF レコード|`v=spf1`|
   |2|Exchange Online|共通|`include:spf.protection.outlook.com`|
   |3|Exchange Online 専用のみ|共通ではない|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4|Office 365 Germany、Microsoft Cloud Germany のみ|共通ではない|`include:spf.protection.outlook.de`|
   |5|サード パーティ製の電子メール システム|共通ではない|`include:<domain_name>` <p> \<domain_name\> は、他社製の電子メール システムのドメインです。|
   |6|オンプレミスの電子メール システム。たとえば、Exchange Online Protection と別のメール システム|共通ではない|各追加メール システムで次のいずれかを使用します。 <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> と \<domain_name\> は、ドメインの代理としてメールを送信する他のメールシステムの IP アドレスとドメインです。|
   |7|いずれかの電子メール システム (必須)|共通。この値で終わるすべての SPF レコード|`<enforcement rule>` <p> これは、いくつかの値のどれか 1 つかもしれません。 値 `-all` をお勧めします。|
   |

2. まだ行っていない場合は、表の構文を使用して SPF TXT レコードを作成します。

   たとえば、Office 365 で完全にホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、2 行目、7 行目が含まれます。

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **上記は、SPF TXT レコード の最も一般的な例です**。 このレコードは、Microsoft データセンターが米国、ヨーロッパ (ドイツを含む)、または他の場所にあっても、ほぼすべてのユーザーに対して機能します。

   ただし、Microsoft Cloud Germany の一部である Office 365 Germany を購入している場合は、2 行目ではなく 4 行目から include ステートメントを使用してください。たとえば、Office 365 Germany で全体がホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、4 行目、7 行目が含まれます。

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Office 365 で既に展開し、カスタム ドメインの SPF TXT レコードをセットアップしている状態で Office 365 Germany に移行する場合は、SPF TXT レコードを更新する必要があります。 これを行うには、`include:spf.protection.outlook.com` を`include:spf.protection.outlook.de`に変更します。

3. SPF TXT レコードを構成した後、DNS でレコードを更新する必要があります。 **ドメインに配置できる SPF TXT レコードは 1 つのみです**。 SPF TXT レコードが存在する場合、新しいレコードを追加するのではなく、既存のレコードを更新しなければなりません。 「[Office 365 の DNS レコードを作成する](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」に移動し、DNS ホストのリンクをクリックします。

4. SPF TXT レコードをテストします。

## <a name="how-to-handle-subdomains"></a>サブドメインの処理方法とは?

*サブドメインは、上位ドメインの SPF レコードを継承しないので、サブドメインごとに、別々のレコードを作成する必要がある* ことに注意してください。

存在しないサブドメインからのメールを、攻撃者が送信することを防ぐために、すべてのドメインとサブドメインに対して追加のワイルドカード SPF レコード (`*.`) が必要です。 例:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>SPF のトラブルシューティング

SPF TXT レコードで問題が発生している場合「[トラブルシューティング:Office 365 における SPF のベスト プラクティス](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)」をお読みください。

## <a name="what-does-spf-email-authentication-actually-do"></a>SPF メール認証では、実際に何が行われますか?

SPF は、ユーザーの代わりにメールを送信できるメール サーバを識別します。 SPF は基本的に、DKIM、DMARC、および Office 365 でサポートされているその他のテクノロジーとともにスプーフィングとフィッシングを防止します。 SPF は、カスタム ドメインの代わりにメールを送信できるメール サーバを識別するために DNS によって使用される TXT レコードとして追加されます。 受信者のメール システムは、SPF TXT レコードを参照して、カスタム ドメインからのメッセージが許可されたメッセージ サーバから送信されたかどうかを判断します。

たとえば、カスタム ドメイン contoso.com が Office 365 を使用しているとします。ユーザーのドメインの正当なメール サーバーとして Office 365 メッセージング サーバーを一覧表示する SPF TXT レコードを追加します。受信メッセージング サーバーが joe@contoso.com からのメッセージを取得すると、サーバーによって contoso.com の SPF TXT レコードが検索され、適切なメッセージであるかどうかが検出されます。受信サーバーで、SPF レコードに一覧表示されている Office 365 メッセージング サーバー以外のサーバーからメッセージを取得していることが検出された場合、受信メール サーバーはそのメッセージを迷惑メールとして拒否できます。

また、カスタム ドメインに SPF TXT レコードが含まれていないと、一部の受信サーバーはメッセージを完全に拒否することがあります。これは、受信サーバーが、承認されたメッセージング サーバーからのメッセージであることを検証できないためです。

既に Office 365 のメールを設定している場合、SPF TXT レコードとして Microsoft のメッセージング サーバーが DNS に含まれています。ただし、場合によっては DNS で SPF TXT レコードを更新する必要があります。たとえば、次のような場合です。

- 以前は、SharePoint Online を使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。この作業を行う必要はなくなりました。この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。参照の制限数である 10 に達し、"参照制限を超えました"、"ホップが多すぎます" などのメッセージを示すエラーが表示される場合は、SPF TXT レコードを更新します。

- Office 365 とオンプレミスの Exchange を使用したハイブリッド環境の場合。

- DKIM と DMARC をセットアップする場合 (推奨)。

## <a name="more-information-about-spf"></a>SPF の詳細情報

サポートされている SPF 構文、スプーフィング、トラブルシューティング、Office 365 が SPF をサポートする方法の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。

## <a name="next-steps-dkim-and-dmarc"></a>次の手順: DKIM と DMARC

 SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング方法があります。それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Office 365 用に構成する必要があります。

[DKIM](use-dkim-to-validate-outbound-email.md) メール認証の目標は、メールの内容が改ざんされていないと証明することです。

[DMARC](use-dmarc-to-validate-email.md) メール認証の目標は、SPF と DKIM の情報が From アドレスと確実に一致していることを確認することです。

 サポートされている SPF 構文の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。

*このドキュメントに関してフィードバックがある場合は、[フィードバック] の下にある [このページ] を選択してください。*
