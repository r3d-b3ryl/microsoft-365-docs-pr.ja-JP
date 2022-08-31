---
title: DMARC を使用してメールを検証する、セットアップ手順
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/10/2021
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Domain-based Message Authentication, Reporting, and Conformance (DMARC) を構成して、組織から送信されたメッセージを検証する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7723105d4617937b85a29911122a0e43e2076350
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470277"
---
# <a name="use-dmarc-to-validate-email"></a>DMARC を使用してメールを検証する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) は、Sender Policy Framework (SPF) および DomainKeys Identified Mail (DKIM) と併用することで、メールの送信者を認証できるようになります。

DMARC は、お客様のドメインから送信されたメッセージを、送信先のメール システムが信頼できるようにするものです。 SPF および DKIM と共に DMARC を使用すると、組織ではメールのスプーフィングやフィッシングに対抗する保護を強化できます。 DMARC は、電子メールを受信するシステムが、ドメインからの SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。

> [!TIP]
> Microsoft 365 用の DMARC レポートを提供しているサードパーティ ベンダーを確認するには、「[Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog)」(Microsoft インテリジェント セキュリティ アソシエーション) カタログを参照してください。

> [!TIP]
> **ステップ バイ ステップ ガイドをご覧ください。** 急いで管理者向けの構成 1-2-3s とビジラなし。 *[Microsoft Online Email ルーティング アドレス (MOERA) とパークされたドメインの DMARC レポートを有効にする](step-by-step-guides/how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains.md)* 手順については、こちらのページを参照してください。

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>SPF と DMARC が連携して Microsoft 365 の電子メールを保護するしくみ

 電子メール メッセージには、発信者、送信者、またはアドレスが含まれていることがあります。これらのアドレスは、さまざまな目的に使用できます。たとえば、次のアドレスについて考えてみましょう。

- **「Mail From」アドレス**: 送信者を識別し、メッセージの配信に問題が発生した場合に、配信不能通知などの通知の返送先を伝達します。 *メールの差出人のアドレス* は、メール メッセージの封筒部分に表示され、メール アプリケーションでは表示されません。*5321.MailFrom アドレス* または *逆方向パス アドレス* とも呼ばれます。

- **「From」アドレス**: From アドレスとして、ユーザーの電子メール アプリケーションに表示されるアドレス。 *差出人アドレスにより*、電子メールの作成者を識別します。 つまり、メッセージを書いた個人またはシステムのメールボックスになります。 *差出人アドレス* は、*5322.From アドレス* ともいいます。

SPF は、特定のドメインに対する認証済みの送信側 IP アドレスのリストに DNS TXT レコードを使用します。 通常、SPF チェックは 5321.MailFrom アドレスに対してのみ実行されます。 SPF を単独で使用する場合、5322.From アドレスは認証されないため、ユーザーが SPF チェックに合格したが、送信者アドレスから 5322 というスプーフィングされたメッセージを受け取るシナリオが可能になります。 たとえば、次のような SMTP トランスクリプトを考えてみます。

```console
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
S: Please click the following link to verify that Microsoft has the right information for your account.
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

SPF を構成した場合、受信側サーバーは Mail From アドレス phish@phishing.contoso.com に対してチェックを実行します。 メッセージがドメイン phishing.contoso.com の有効なソースから送信された場合は、SPF チェックをパスします。 電子メール クライアントには差出人アドレスのみが表示されるため、ユーザーには、このメッセージが security@woodgrovebank.com から送信されたように見えます。 SPF だけでは、woodgrovebank.com の有効性は認証されません。

DMARC を使用すると、From アドレスに対するチェックを受信側サーバーも実行するようになります。 前述の例では、woodgrovebank.com の所定の場所に DMARC TXT レコードが存在していれば、From アドレスに対するチェックは失敗します。

## <a name="what-is-a-dmarc-txt-record"></a>DMARC TXT レコードとは

SPF の DNS レコードと同様に、DMARC のレコードは、スプーフィングとフィッシングの防止に役立つ DNS テキスト (TXT) レコードです。DMARC TXT レコードは DNS で発行します。DMARC TXT レコードは、メール作成者の IP アドレスを、送信側ドメインの所有者とされる名前と照合して、メール メッセージの発信元を確認します。 この DMARC TXT レコードにより、承認済みの送信メール サーバーを識別します。送信先メール システムでは、メッセージが承認済みの送信メール サーバーから発信されたことを確認できます。

Microsoft の DMARC TXT レコードは、次のような内容になります。

```console
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.contoso.com; ruf=mailto:d@ruf.contoso.com; fo=1"
```

Microsoft 365 用の DMARC レポートを提供している他のサードパーティ ベンダーについては、[MISA カタログ](https://www.microsoft.com/misapartnercatalog?IntegratedProducts=DMARCReportingforOffice365)を参照してください。

## <a name="set-up-dmarc-for-inbound-mail"></a>受信メール用に DMARC の設定

Microsoft 365 で受信するメールの DMARC を設定するために必要な手順はありません。 それはすべて考慮されています。 DMARC チェックをパスしないメールに対する処理について知る必要がある場合は、「[Microsoft 365 が DMARC に失敗した受信メールを処理する方法](#how-microsoft-365-handles-inbound-email-that-fails-dmarc)」を参照してください。

## <a name="set-up-dmarc-for-outbound-mail-from-microsoft-365"></a>Microsoft 365 からの送信メール用に DMARC を設定する

Microsoft 365 を使用しているもののカスタム ドメインを使用していない場合 (つまり、onmicrosoft.com を使用する場合)、SPF のセットアップは既に完了しており、Microsoft 365 により自動的に送信メールに DKIM 署名が生成されます。この署名の詳細については「[DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。 組織に DMARC を設定するには、onmicrosoft.com ドメインの [[DMARC TXT レコードを作成]](#step-4-form-the-dmarc-txt-record-for-your-domain) し、[Office 365 管理センター](https://admin.microsoft.com) > [設定] > [ドメイン] > [onmicrosoft.com ドメイン] > [レコードの追加] をクリックして DNS に公開する必要があります。

 カスタム ドメインを所有している場合や、Microsoft 365 と合わせてオンプレミスの Exchange サーバーも使用している場合は、送信メール用に手動で DMARC を設定する必要があります。 カスタム ドメイン用に DMARC を設定する手順は次のとおりです。

- [手順 1:ドメインに対する有効なメールのソースを特定する](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [手順 2: ドメイン用に SPF をセットアップする](#step-2-set-up-spf-for-your-domain)

- [手順 3: カスタム ドメイン用に DKIM をセットアップする](#step-3-set-up-dkim-for-your-custom-domain)

- [手順 4: ドメイン用の DMARC TXT レコードを作成する](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>手順 1:ドメインに対する有効なメールのソースを特定する

既に SPF のセットアップが済んでいる場合は、この演習を完了していることになります。 DMARC には、さらにいくつかの考慮事項があります。 ドメインに対するメールのソースを特定するときには、以下の 2 つの問いに答える必要があります。

- どの IP アドレスにドメインからメッセージを送信するか。

- 自分の代わりにサード パーティから送信されるメールについて、5321.MailFrom ドメインと 5322.From ドメインが一致しているか。

### <a name="step-2-set-up-spf-for-your-domain"></a>手順 2: ドメイン用に SPF をセットアップする

すべての有効な送信者の一覧が用意できると、「[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」手順を実行できるようになります。

たとえば、contoso.com が Exchange Online からメールを送信するとします。このとき、オンプレミスの Exchange サーバーの IP アドレスが 192.168.0.1、Web アプリケーションの IP アドレスが 192.168.100.100 だと仮定すると、SPF TXT テキストレコードは次のようになります。

```console
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

ベスト プラクティスとして、SPF TXT レコードでは、サード パーティの送信者についても考慮に入れておく必要があります。

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>手順 3: カスタム ドメイン用に DKIM をセットアップする

SPF のセットアップ後には、DKIM をセットアップする必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 DKIM をセットアップする代わりに、ドメインに対して Microsoft 365 で既定の DKIM 構成の使用を許可すると、DMARC が失敗することがあります。 このエラーは、既定の DKIM 構成が、*5321.MailFrom* アドレスとして *カスタム* ドメインではなく初期設定の *onmicrosoft.com* ドメインを使用するために発生する可能性があります。 これにより、ドメインから送信されたすべてのメールの *5321.MailFrom* アドレスと *5322.From アドレス* との間に不一致が生じることになります。

メールを代理で送信するサード パーティの送信者が存在しているときに、そのサード パーティが送信するメールの 5321.MailFrom アドレスと 5322.From アドレスが一致していないと、そのメールに対する DMARC は失敗します。これを回避するには、そのサード パーティの送信者について、具体的にドメインの DKIM をセットアップする必要があります。これにより、このサード パーティのサービスからのメールを Microsoft 365 で認証できるようになります。ただし、そのようにすると、サード パーティが送信したメールを本人が送信したメールであるかのように検証することを他者 (Yahoo、Gmail、Comcast など) にも許可するようになります。これには、顧客がどこにメールボックスを配置していてもドメインとの信頼を構築できるようになるという利点があります。それと同時に、メッセージはドメインの認証チェックをパスしているため、Microsoft 365 は偽装を理由にメッセージをスパムとしてマークしなくなります。

サード パーティの送信者がドメインを偽装できるように DKIM をセットアップする方法を含め、ドメインの DKIM をセットアップする手順については、「[DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>手順 4: ドメイン用の DMARC TXT レコードを作成する

ここでは、Microsoft 365 で最もよく使用される構文オプションを示します。ただし、ここに記載されていない別の構文のオプションもあります。 ドメイン用の DMARC TXT レコードは、次に示す形式で作成します。

```console
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

ここで、

- *domain* は、保護対象にするドメインです。既定では、このレコードは、ドメインとすべてのサブドメインからのメールを保護します。たとえば、\_dmarc.contoso.com を指定すると、DMARC は、このドメインとすべてのサブドメイン (housewares.contoso.com や plumbing.contoso.com など) からのメールを保護します。

- *TTL* は、常に 1 時間に相当する必要があります。TTL に使用される単位は、ドメインのレジストラーに応じて hours (1 時間)、minutes (60 分)、または seconds (3,600 秒) のいずれかになります。

- *pct=100* は、このルールがメールの 100% に使用される必要があることを示します。

- *policy* では、DMARC に失敗した場合に受信側サーバーが従う必要のあるポリシーを指定します。ポリシーは、なし (none)、検疫 (quarantine)、または拒否 (reject) に設定できます。

どのオプションを使用するかについては、「[Microsoft 365 で DMARC を実装する際のベスト プラクティス](#best-practices-for-implementing-dmarc-in-microsoft-365)」の概念をよく理解してください。

例:

- ポリシーをなし (none) に設定する

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- ポリシーを検疫 (quarantine) に設定する

    ```console
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- ポリシーを拒否 (reject) に設定する

    ```console
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

レコードの作成後には、ドメイン レジストラーでレコードを更新する必要があります。

## <a name="dmarc-mail-public-preview-feature"></a>DMARC メール (パブリック プレビュー機能)

> [!CAUTION]
> メールは毎日配信されるわけではありませんし、レポート自体もパブリック プレビュー中に変更される可能性があります。 DMARC 集約レポートのメールは、Consumer アカウント (hotmail.com、outlook.com、live.com アカウントなど) から送信されます。

この DMARC TXT レコードの例では、 `dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"`、サード パーティ企業 Agari によって処理された *rua* アドレスを確認できます。 このアドレスは、分析のための 'フィードバックの集約' を送信するために使用され、レポートを作成するために使用されます。

> [!TIP]
> Microsoft 365 用の DMARC レポートを提供している他のサードパーティ ベンダーを確認するには、[MISA カタログ](https://www.microsoft.com/misapartnercatalog)を参照してください。 DMARC 'rua' アドレスの詳細については、「[IETF.org の 'ドメインベースのメッセージ認証、レポート、適合 (DMARC)'](https://datatracker.ietf.org/doc/html/rfc7489)」を参照してください。

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>Microsoft 365 で DMARC を実装する際のベスト プラクティス

DMARC は、メール フローの他の部分に影響を与えないように段階的に実装できます。ここに示す手順に従ったロール アウト計画を作成して実施してください。ここに示す各手順は、まずサブドメインに実行します。その後で、その他の各サブドメインに対して実行し、最後に組織のトップレベル ドメインに実行してから、次の手順に進みます。

1. DMARC の実装による影響を監視する

    まず、サブドメインまたはドメインに単純な監視モード レコードを使用することから始めます。このレコードでは、そのドメインを使用して確認するメッセージについての統計を送信するように DMARC レシーバーに要求します。 監視モード レコードとは、ポリシーをなし (p=none) に設定したDMARC TXT レコードのことです。 多くの企業は、p=none の DMARC TXT レコードを発行しています。それより制限の厳しいポリシーを発行することで、どれだけのメールが失われるかについて、明確にはわからないためです。

    これは、メッセージング インフラストラクチャに SPF や DKIM を実装する前でも実行できます。 ただし、SPF と DKIM を実装して併用するまでは、DMARC を使用した効果的なメールの検疫や拒否はできません。 SPF と DKIM を導入すると、DMARC によって生成されるレポートには、それらのチェックをパスしなかったメッセージに対してパスしたメッセージの発信元と数が示されます。 それらのチェックの適用対象になる (または適用対象にならない) 正当なトラフィックの量を簡単に確認できます。また、あらゆる問題のトラブルシューティングも簡単になります。 さらに、どれだけの偽装メッセージが送信されているかや、偽装メッセージの送信元についても、次第にわかるようになります。

2. DMARC に失敗したメールの検疫を外部のメール システムに要求する

    すべて、または大部分の正当なトラフィックが SPF と DKIM で保護されるという確信が持てるようになり、DMARC の実装による影響を理解したら、検疫ポリシーを実装してください。 検疫ポリシーとは、ポリシーを検疫 (p=quarantine) に設定した DMARC TXT レコードのことです。 このようにすることで、DMARC レシーバーに対して、DMARC に失敗したドメインからのメッセージを顧客の受信トレイではなく、ローカルのスパム フォルダーと同等のフォルダーに入れるように指示します。

3. DMARC に失敗したメッセージを受け取らないように外部システムに要求する

    最後の手順は、拒否ポリシーの実装です。拒否ポリシーとは、ポリシーを拒否 (p=reject) に設定した DMARC TXT レコードのことです。これにより、DMARC レシーバーに対して、DMARC チェックに失敗したメッセージを受け取らないように指示します。

4. サブドメイン用に DMARC を設定する方法

   DMARC は、ポリシーを DNS の TXT レコードとして公開することで実装され、階層的です (たとえば、contoso.com に公開されたポリシーは、サブドメインに別のポリシーが明示的に定義されていない限り、sub.domain.contonos.com に適用されます)。 これは、より広い範囲をカバーするために、より少ない数の高レベル DMARC レコードを指定できる場合があるため、便利です。 サブドメインがトップ レベル ドメインの DMARC レコードを継承しないようにするには、明示的なサブドメイン DMARC レコードを構成するように注意する必要があります。

   また、`sp=reject` 値を追加することにより、サブドメインがメールを送信してはならないときに DMARC にワイルドカード タイプのポリシーを追加できます。次に例を示します。

   ```text
   _dmarc.contoso.com. TXT "v=DMARC1; p=reject; sp=reject; ruf=mailto:authfail@contoso.com; rua=mailto:aggrep@contoso.com"
   ```

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Microsoft 365 が DMARC に失敗した送信メールを処理する方法

メッセージが Microsoft 365 から送信され、DMARC に失敗し、ポリシーを p=quarantine または p=reject に設定していると、メッセージは「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」によってルーティングされます。 送信メールの上書きはありません。

DMARC 拒否ポリシー (p=reject) を発行すると、どの顧客も Microsoft 365 ではドメインを偽装できなくなります。メッセージは、サービスを通じたメッセージ送信の中継時に、ドメインの SPF または DKIM をパスできないためです。 ただし、DMARC 拒否ポリシーを発行していても、すべてのメールが Microsoft 365 で認証されている場合、前述の説明どおりに受信メールの一部はスパムとしてのマークが付けられます。それ以外のメールは、SPF を発行していない場合に、サービスを通じて送信を中継しようとすると拒否されます。 これは、DMARC TXT レコードの作成時に、ドメインの代理としてメールを送信するサーバーの一部の IP アドレスとアプリを含め忘れている場合などに発生します。

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Microsoft 365 が DMARC に失敗した受信メールを処理する方法

送信側サーバーの DMARC ポリシーが `p=reject` の場合、[Exchange Online Protection](exchange-online-protection-overview.md) (EOP) はメッセージを拒否するのではなく、スプーフィングとしてマークを付けます。 つまり、受信メールの場合、Microsoft 365 は `p=reject` と `p=quarantine` を同様に扱うということです。 管理者は、[フィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)内のスプーフィングとして分類されたメッセージに対するアクションを定義できます。

このように Microsoft 365 が構成されている理由は、一部の正当なメールが DMARC に失敗することがあるためです。 たとえば、メッセージがメーリング リストに送信されてから、リストのすべての参加者にメッセージが中継される場合、DMARC に失敗することがあります。 こうしたメッセージを Microsoft 365 が拒否すると、受信者は正当なメールを失うことになり、そのメールを取得する手段がなくなります。 その代わりに、このようなメッセージは DMARC に失敗するようにしておき、スパムのマークを付けて拒否しないようにします。 必要であれば、ユーザーは自分の受信トレイから、次の方法でメッセージを取得できます。

- ユーザーが、自分のメール クライアントを使用して、個別に安全な送信者を追加します。

- 管理者は、[スプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)や[テナントの許可/ブロック リスト](manage-tenant-allow-block-list.md)を使用して、なりすまし送信者からのメッセージを許可できます。

- 管理者が、該当する送信者のメッセージを許可するすべてのユーザーに向けて Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。

詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Microsoft 365 でオーセンティケーテッド レシーブド チェーン (ARC) を活用する方法

Microsoft 365 でホストされているすべてのメール ボックスでは、向上したメッセージの配信率と強化されたスプーフィング対策保護と共に、ARC の利点が得られます。 ARC では、元のサーバーから受信者のメールボックスへと電子メールがルーティングされると、すべての関与する仲介役、つまりホップからの電子メール認証の結果が保持されます。 ARC 以前、転送ルールまたは自動署名などの電子メール ルーティングの仲介役によって実行される変更は、受信者のメールボックスで電子メールが受信される時間によって DMARC の失敗を引き起こす場合があります。 ARC を使用すると、認証の結果の暗号化保存により、Microsoft 365 では電子メールの送信者の真正性を検証することができます。

Microsoft が ARC Sealer の場合、現在、Microsoft 365 では ARC を使用して認証の結果を検証します。しかし、将来的にはサードパーティの ARC Sealer のサポートを追加する予定です。

## <a name="troubleshooting-your-dmarc-implementation"></a>DMARC 実装のトラブルシューティング

ドメインの MX レコードを構成したときに、最初のエントリを EOP 以外にすると、DMARC の失敗はドメインに強制されなくなります。

お客様の場合でも、ドメインのプライマリ MX レコードが EOP を指していないと、DMARC による利点は得られなくなります。 たとえば、MX レコードがオンプレミスのメール サーバーを指していて、コネクタを使用することで EOP にメールをルーティングしていると、DMARC は機能しなくなります。 このシナリオでは、受信側ドメインは認証済みドメインのいずれかになりますが、EOP はプライマリ MX ではありません。 たとえば、contoso.com がそれ自体の MX をポイントしていて、セカンダリ MX レコードとして EOP を使用しているとすると、contoso.com の MX レコードは次のようになります。

```console
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

すべて、またはほとんどのメールは、最初にプライマリ MX である mail.contoso.com にルーティングされてから、EOP にルーティングされます。 場合によっては、MX レコードとして EOP をリストすることさえなく、単にメールをルーティングするようにコネクタを接続していることもあります。 EOP は、DMARC 検証を行うための最初のエントリである必要はありません。 オンプレミスまたは O365 以外のすべてのサーバーが DMARC チェックを実行することを確認するために、検証だけを行います。  DMARC TXT レコードを設定するときに顧客のドメイン (サーバーではなく) に対して DMARC を強制できますが、実際に強制するのは受信サーバーだけです。  EOP を受信サーバーとして設定すると、EOP は DMARC 強制を行います。

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC のトラブルシューティングのグラフィック" lightbox="../../media/Tp_DMARCTroublehoot.png":::

## <a name="for-more-information"></a>詳細情報

DMARC の詳細情報が必要ですか。以下のリソースが役に立ちます。

- [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)には、Microsoft 365 が DMARC チェックに使用する構文とヘッダー フィールドが含まれています。

- M<sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group) の「[DMARC TRAINING SERIES](https://www.m3aawg.org/activities/training/dmarc-training-series)」。

- [dmarcian](https://space.dmarcian.com/deployment/) のチェックリストを使用する。

- [DMARC.org](https://dmarc.org) のソースに直接アクセスする。

## <a name="see-also"></a>関連項目

[Microsoft 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法](how-office-365-uses-spf-to-prevent-spoofing.md)

[**Microsoft 365 で SPF を設定して、スプーフィングを防止する**](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[**DKIM を使用して、Microsoft 365 のカスタム ドメインから送信される送信電子メールを検証する**](use-dkim-to-validate-outbound-email.md)

[正当なメールフローに信頼された ARC 送信者を使用する](/microsoft-365/security/office-365-security/use-arc-exceptions-to-mark-trusted-arc-senders?view=o365-21vianet&preserve-view=true)
