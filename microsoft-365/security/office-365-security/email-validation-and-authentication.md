---
title: Microsoft 365 のメール認証
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 管理者は、スプーフィング、フィッシング、およびスパムを防ぐには、Exchange Online Protection (EOP) がメール認証 (SPF、DKIM、および DMARC) を使用方法を確認できます。
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209501"
---
# <a name="email-authentication-in-eop"></a>EOP のメール認証

メール認証 (メール検証とも呼ばれます) は、スプーフィング (偽造された差出人からのメール メッセージ) を阻止しようとする標準のグループです。 Exchange online のメールボックスを使用している Microsoft 365 の組織、およびExchange Online のメールボックスを使用していないスタンドアローンの Exchange Online Protection (EOP) 組織内で、EOP は受信メールを確認するために次の基準を使用します。

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

メール認証では、差出人 (laura@contoso.com など) からのメール メッセージが正当であり、そのメール ドメイン (contoso.com など) の期待される送信元からのものであることを確認します。

このトピックの残りの部分では、これらのテクノロジのしくみ、EOP がこれらのテクノロジを使用して受信メールをチェックする方法について説明します。

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>メール認証を使用してスプーフィングを防止する

DMARC では、メッセージの**差出人**アドレス (メール クライアントでユーザーに表示される差出人のメール アドレス) を調べて、スプーフィングを防止します。 送信先のメール組織では、メール ドメインが SPF または DKIM にパスしたことも確認できます。これは、ドメインが認証されたため、スプーフィングされていないことを意味します。 

ただし、問題は、メール認証用のDNS 内 SPF、DKIM、および DMARC レコード (総称してメール認証ポリシーと呼ばれます) は完全にオプションであるということです。 そのため、microsoft.com や skype.com などの強力なメール認証ポリシーを公開しているドメインはスプーフィングから保護されますが、公開しているメール認証ポリシーが弱いドメインや認証ポリシーがまったく存在しないドメインはスプーフィングの主な対象になります。

2018 年 3 月の時点で、Fortune 500 の企業のうち強力なメール認証ポリシーを公開しているドメインは 9% のみです。 残りの91% の企業は、攻撃者により、なりすまされている可能性があります。 他のメール フィルタリング メカニズムが組み込まれていない場合、これらのドメインの成りすましの装差出人からのメールがユーザーに配信される可能性があります。

![Fortune 500 企業の DMARC ポリシー](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

Fortune 500 に含まれない中小規模の企業で強力なメール認証ポリシーを公開している割合はさらに少なくなり、北米と西ヨーロッパ以外のメール ドメインでは、それよりも少ない割合になります。

これは重大な問題です。企業はメール認証のしくみを認識していないことがありますが、攻撃者はそのしくみを完全に理解して利用するためです。 フィッシングは大きな問題であり、強力なメール認証ポリシーの導入は限られているため、Microsoft は受信メールをチェックするために*暗黙的なメール認証*を使用しています。

暗示的なメール認証は、通常のメール認証ポリシーに対する多くの拡張機能に基づいて構築されています。 これらの拡張機能には、送信者評価、送信者の履歴、受信者の履歴、行動分析、他の高度な手法が含まれます。 メール認証ポリシーを使用しないドメインから送信されたメッセージは、そのメッセージが正当であることを示す別のシグナルが含まれていないときには、スプーフィングのマークが付けられます。

Microsoft の一般発表については、「[大量のフィッシング詐欺: 第 2 部 - 強化された Microsoft 365 のスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。

## <a name="composite-authentication"></a>複合認証

SPF、DKIM、および DMARC は、いずれも単独で役立つものですが、メッセージに明示的な認証レコードが存在していないときには、認証の状態を十分に伝達しません。 そのため、Microsoft は、複数のシグナルを 1 つの値に結合する_複合認証_ (略称: compauth) と呼ばれる暗黙的なメール認証用のアルゴリズムを開発しました。 メッセージのヘッダーに含まれる **Authentication-Results** ヘッダーに compauth の値がスタンプされます。

> Authentication-Results:<br/>&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\>

これらの値については、「[Authentication-results メッセージ ヘッダー](anti-spam-message-headers.md#authentication-results-message-header)」で説明しています。

メッセージ ヘッダーを調べることによって、管理者またはエンド ユーザーは、Microsoft 365 が送信者がなりすましであることを判断する方法を確認できます。

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>メール認証がスプーフィングの阻止には不十分なことがある理由

受信メッセージがなりすましであるかどうかを判断するためにメール認証のみに依存すると、次の制限が発生します。

- 送信側ドメインに必要な DNS レコードがないか、レコードが正しく構成されていない可能性があります。

- 送信元ドメインに正しく構成された DNS レコードがありますが、そのドメインが差出人アドレスのドメインと一致しません。 SPF と DKIM には、差出人アドレスで使用するドメインは必要はありません。 攻撃者や合法的サービスは、ドメインを登録したり、ドメインの SPF および DKIM を構成したり、差出人アドレスに完全に異なるドメインを使用したりすることができ、そのメッセージは SPF および DKIM にパスします。

複合認証は、メール認証チェックに失敗するメッセージをパスさせることで、これらの制限に対処できます。

> [!NOTE]
> 前述したように、暗黙的なメール認証は複数のシグナルを使用して、メッセージが正当であるかどうかを判断します。 簡単にするために、次の例では、メール認証の結果に焦点を置いています。 他のバックエンド インテリジェンス要因は、メール認証にパスするメッセージをなりすましとして識別したり、メール認証に失敗したメッセージを正当として識別したりする可能性があります。

たとえば、fabrikam.com ドメインには、SPF、DKIM、または DMARC レコードがありません。 fabrikam.com ドメインの送信者からのメッセージは、複合認証に失敗する可能性があります (`compauth` の値と理由に注意してください)。

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

fabrikam.com が DKIM レコードなしで SPF を構成する場合、SPF にパスしたドメインは差出人アドレスのドメインと一致しているため、メッセージは複合認証にパスできます。

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

fabrikam.com が SPF レコードなしで DKIM レコードを構成する場合、パスした DKIM 署名のドメインは差出人アドレスのドメインと一致しているため、メッセージは複合認証にパスできます。

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

SPF または DKIM 署名のドメインが差出人アドレスのドメインと一致しない場合、メッセージは複合認証に失敗する可能性があります。

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>認証されていないメールを送信している正当な送信者のためのソリューション

Microsoft 365 は、認証されていないメールを組織に送信している送信者を追跡しています。 その送信者がサービスによって正当ではないと判断されると、複合認証失敗のマークが付けられます。 この問題を回避するには、このセクションの推奨事項を使用できます。

### <a name="configure-email-authentication-for-domains-you-own"></a>所有しているドメインのメール認証を構成する

この方法は、組織内スプーフィングの解決に使用できます。また、複数のテナントを所有している場合や複数のテナントとやり取りする場合のクロスドメイン スプーフィングの解決にも使用できます。 さらに、Microsoft 365 内の別のユーザー、または別のプロバイダーによりホストされているサード パーティに送信する場合のクロスドメイン スプーフィングを解決する際にも役立ちます。

- ドメインの [SPF レコードを構成します](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

- プライマリ ドメインの [DKIM レコードを構成します](use-dkim-to-validate-outbound-email.md)。

- 正当な送信者を判断するために、ドメインに [DMARC レコードを設定することを検討します](use-dmarc-to-validate-email.md)。

Microsoft は、SPF、DKIM、および DMARC レコードの詳細な実装ガイドラインを提供しません。 ただし、オンラインで利用できる大量の情報があります。 また、組織がメール認証レコードを設定する際の支援を専門としているサード パーティ企業もあります。

#### <a name="you-dont-know-all-sources-for-your-email"></a>メールのすべての送信元がわからない

多くのドメインは、ドメイン内のメッセージのすべてのメール送信元を認識していないため、SPF レコードを公開しません。 自分が知っているすべてのメール送信元を含む SPF レコード (特に会社のトラフィックがある場所にある) を公開することから始めて、次のニュートラル SPF ポリシー (`?all`) を公開します。 以下に例を示します。

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

この例では、会社のインフラストラクチャからのメールはメール認証にパスしますが、不明な送信元からのメールはニュートラルに戻ります。

Microsoft 365 は、会社のインフラストラクチャからの受信メールを認証済みとして扱いますが、識別されていない送信元からのメールは、(Microsoft 365 が暗黙的に認証できるかどうかによって) スプーフィングとしてマークされる可能性があります。 ただし、これは Microsoft 365 によってすべてのメールにスプーフィングのマークが付けられることからの改善に過ぎません。

`?all` の SPF フォールバック ポリシーの使用を開始したら、メッセージのメール送信元を徐々に見つけて含めることができ、より厳しいポリシーを使用して SPF レコードを更新できます。

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>スプーフィング インテリジェンスを使用して、認証されていないメールが許可された送信者を構成する

認証されていないメッセージを組織に送信する送信者を許可するために、[スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)を使用することもできます。

外部ドメインの場合、スプーフィングされたユーザーは差出人アドレスのドメインですが、送信側インフラストラクチャは、送信元 IP アドレス (最大 /24 CIDR 範囲に分割)、または逆引き DNS (PTR) レコードの組織ドメインのいずれかになります。

以下のスクリーンショットでは、送信元 IP は PTR レコード outbound.mail.protection.outlook.com を使用して 131.107.18.4 となる可能性があります。 これは、送信側インフラストラクチャの outlook.com として表示されます。

この送信者に認証されていない電子メールの送信を許可するには、**[いいえ]** を **[はい]** に変更します。

![スプーフィング対策の許可された送信者の設定](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>送信者/受信者ペアの許可エントリを作成する

スパム フィルタリングをバイパスし、フィッシング フィルタリングの一部をバイパスし、特定の送信者のマルウェア フィルタリングをバイパスしない場合は、「[Microsoft 365 で安全な送信者の一覧を作成する](create-safe-sender-lists-in-office-365.md)」をご覧ください。

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>所有していないドメインのメール認証を構成するように送信者に依頼する

スパムとフィッシングの問題があるため、Microsoft は、すべてのメール組織にメール認証をお勧めします。 組織の手動オーバーライドを構成する代わりに、送信側ドメインの管理者にメール認証レコードを構成するように依頼できます。

- 過去にメール認証レコードを公開する必要がなかった場合でも、Microsoft にメールを送信する場合は公開する必要があります。

- SPF を設定してドメインの送信側 IP アドレスを公開します。DKIM (使用可能な場合) を設定してメッセージにデジタル署名します。 また、DMARC レコードの設定も検討する必要があります。

- 一括送信者を使用してメールを送信する場合は、(アドレスが属する場合) 差出人アドレスのドメインが、SPF または DMARC にパスするドメインに一致していることを確認します。

- 次の場所 (使用している場合) が SPF レコードに含まれていることを確認します。
  
  - オンプレミスのメールサーバー。
  - SaaS (サービスとしてのソフトウェア) プロバイダーから送信されたメール。
  - クラウドホスティング サービス (Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services など) から送信されたメール。

- ISP によってホストされている小規模なドメインについては、ISP の指示に従って SPF レコードを構成します。

送信側ドメインで認証することは最初は難しい場合もありますが、そのドメインからの電子メールを迷惑メールとして処理したり拒否したりする電子メール フィルターが時間の経過と共に増え続け、適切に配信されるようにするために適切なレコードを設定することになります。 また、それらを参加させることにより、フィッシング対策を行うことができます。また、メールの送信先の組織や組織内のフィッシング詐欺の可能性を減らすことができます。

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>インフラストラクチャプ ロバイダー (ISP、ESP、クラウド ホスティング サービス) の情報

ドメインのメールをホストする場合、またはメールを送信できるホスティング インフラストラクチャを提供する場合は、次の手順を実行する必要があります。

- 顧客が SPF レコードを構成する方法について説明するドキュメントを顧客が持っていることを確認する

- 顧客が明示的に設定していない場合でも、送信メールの DKIM 署名に署名することを検討します (既定のドメインで署名)。 DKIM 署名では電子メールに二重署名することもできます (顧客のドメインで設定されている場合に 1 つ目の署名、会社の DKIM 署名で 2 つ目の署名)。

プラットフォームから送信されたメールを認証していても Microsoft への配信が可能であることが保証されるわけではありませんが、少なくとも、認証されていないという理由で Microsoft がそのメールを迷惑メールとして処理することはなくなります。

サービス プロバイダーのベスト プラクティスの詳細については、「[M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)」を参照してください。
