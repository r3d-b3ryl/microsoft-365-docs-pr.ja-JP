---
title: Office 365 メールのスパム対策保護
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Exchange Online および Office 365 でスパムを防止するのに役立つスパム対策設定とフィルターについて説明します。 Office 365 で迷惑メールを過剰に取得する スパムフィルターとスパム対策ポリシー設定をカスタマイズできます。
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633835"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 メールのスパム対策保護

Office 365 で懸念されるスパム数 Office 365 または Exchange Online Protection (EOP) サービスに複数のスパムフィルターを作成しています。そのため、最初のメッセージを受信した時点からメールを保護することができます。 Office 365 でスパムを防止するために、組織内の特定の問題に対処するために保護設定を変更する必要があります (たとえば、特定の送信者から多数のスパムを受信している場合など)。または、設定を微調整して、それらの情報が表示されるようにしてください。お客様の組織のニーズを満たすように調整します。 これを行うには、Office 365 セキュリティ&amp;コンプライアンスセンターでスパム対策設定を変更することができます。

この記事は、Office 365 管理者を対象としています。 管理者ではなく、Office 365 ユーザーで、受信したスパムを処理する方法について知りたい場合は、お探しの記事に記載されている内容ではありません。 代わりに、Outlook for PC または Outlook for Mac を使用している場合は、[迷惑メールフィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)から始めます。 Outlook on the web を使用する場合は、まず「[迷惑メールとフィッシングについて](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)」を参照してください。

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>これらのオプションは、Office 365 でスパムを防止するのに役立ちます。

 **接続フィルター**: 接続フィルターを使用すると、Office 365 は、メッセージの受信を許可する前に、送信者の評価をチェックします。 許可リストまたは差出人セーフリストを作成して、特定の IP アドレスまたは IP アドレスの範囲から送信されたすべてのメッセージを受信するようにすることができます。 また、禁止一覧と呼ばれる、メッセージをブロックする IP アドレスの一覧を作成することもできます。 詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。 Office 365 でスパムを懸念している場合は、接続フィルターを使用してスパムを防止します。

Office 365 Enterprise E5 を使用しているか、Advanced Threat Protection (ATP) ライセンスを購入しているお客様の場合、接続フィルターは、ドメインをスプーフィングしている送信者の許可と禁止の一覧を作成するために、スプーフィングインテリジェンスによって使用されます。 詳細については、「[スプーフィングインテリジェンスの詳細](learn-about-spoof-intelligence.md)」を参照してください。

 **スパムフィルター**: Office 365 は、スパムフィルタリングを使用して、スパムと一貫性のあるメッセージ特性をチェックします。 スパムとして識別されたメッセージに実行する処理を選択し、特定の言語で記述されたメッセージ、または特定の国や地域から送信されたメッセージをフィルターするかどうかを選択できます。 高度なスパム フィルター オプションを有効にして、スパム フィルターに対する積極的なアプローチを実行することもできます。 さらに、エンド ユーザーのスパム通知を構成すると、ユーザー宛てのメッセージが検疫に送信された場合にユーザーに通知が送信されます。 (検疫にメッセージを送信することは、構成可能なアクションの1つです。)これらの通知から、エンドユーザーは誤検知をリリースし、それらを分析のために Microsoft に報告することができます。 詳細については、「[スパム フィルター ポリシーを構成する](configure-your-spam-filter-policies.md)」 を参照してください。 Office 365 でスパムを防止するために、スパムフィルター処理を使用します。 Office 365 ではスパムの数が多くなりすぎる場合は、接続フィルターを使用してスパムの防止に役立ちます。

> [!NOTE]
> EOP スタンドアロンのお客様の場合、既定では、EOP スパムフィルターはスパム検出メッセージを各受信者の迷惑メールフォルダーに送信します。 ただし、[**メッセージを迷惑メールフォルダーに移動する**] アクションがオンプレミスのメールボックスに対して機能するようにするには、EOP によって追加されたスパムヘッダーを検出するために、オンプレミスサーバー上で2つの Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成する必要があります。 詳細については、「[スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Office 365 で受信するスパムの数が多すぎる場合のその他の情報

次のビデオでは、EOP でスパムフィルターを構成する方法の概要を説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」トピックを参照してください。

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Office 365 で送信メッセージを確認してスパムを防ぐ

 **送信フィルター**: Office 365 は、ユーザーがスパムを送信していないかどうかも確認します。 たとえば、ユーザーのコンピューターがスパムメッセージを送信するマルウェアに感染する可能性があるため、*送信フィルター*と呼ばれる保護を構築しています。 送信フィルターを無効にすることはできませんが、「[送信スパムポリシーを構成](configure-the-outbound-spam-policy.md)する」で説明されている設定を構成できます。 Office 365 で多くのスパムを懸念している場合は、送信フィルターを使用して Exchange Online でスパムを防止します。

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>基本的な機能: Office 365 でスパム対策を防ぐ方法

 **メールフロールール**: 組み込みのスパムフィルターを超えて、ビジネスポリシーに基づくカスタムルールを作成する場合、_[メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_(_トランスポートルール_とも呼ばれます) は、Office 365 でスパムを防止するのに役立つ別のフィルターです。 たとえば、メールフロールールを使用すると、「[メールフロールールを使用してメッセージにスパム信頼レベル (scl) を設定](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)する」の説明に従って、特定の条件に一致するメッセージに対してスパム信頼レベル (scl) の値を設定できます。

 **電子メール認証**ドメインネームシステム (DNS) を使用して、電子メールメッセージの送信者に関する検証可能な情報を電子メールメッセージに追加する手法を、電子メール認証と呼びます。 より高度な Office 365 管理者は、これらの電子メール認証方法を利用できます。

- **Sender Policy Framework (spf)**: spf は、送信側ドメインの申し立て所有者に対して送信者の IP アドレスを確認することによって、電子メールメッセージの送信元を検証します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- **Domainkeys で識別されたメール (dkim)**: dkim を使用すると、送信する電子メールのメッセージヘッダー内の電子メールメッセージにデジタル署名を添付することができます。 ドメインから電子メールを受信する電子メールシステムこのデジタル署名を使用して、受信した受信メールが正当であるかどうかを判断します。 DKIM と Office 365 の詳細については、「 [DKIM を使用して、office 365 のカスタムドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。

- **ドメインベースのメッセージの認証、報告、および準拠 (DMARC)**: DMARC はメールシステムの受信をサポートします。 SPF または dkim チェックに失敗したメッセージの処理方法を決定し、電子メールパートナーに対して別のレベルの信頼を提供します。 DMARC のセットアップの詳細については、「 [USE DMARC to validate email In Office 365](use-dmarc-to-validate-email.md)」を参照してください。

Office 365 でスパム、フィッシング、およびスプーフィングについて懸念している場合は、SPF、DKIM、DMARC を一緒に使用して、スパムや不要なスプーフィングを防止します。

 **エンドユーザー**による管理の設定: エンドユーザーが自分のスパム設定を管理する方法については、「[迷惑メールフィルターの概要」](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (Microsoft Outlook ユーザーの場合) または「[迷惑メールとフィッシング](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)(web 上の outlook の場合)」を参照してください。 EOP を使用してオンプレミスのメールボックスを保護している場合は、必ずディレクトリ同期を使用して、これらの設定がサービスに同期されるようにしてください。 ディレクトリ同期のセットアップ方法については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。

## <a name="for-more-information"></a>詳細情報

[ブログ: スパムとフィッシングが Office 365 によって取得されるのはなぜですか?](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)

[セーフリストまたはその他の手法で誤検知の電子メールがスパムとしてマークされないようにする](prevent-email-from-being-marked-as-spam.md)

[迷惑メールをブロックするために Office 365 スパムフィルターを設定する方法](reduce-spam-email.md)

[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)

[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)

[バックスキャター メッセージと EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>その他のリソース

[Office 365 コミュニティ フォーラムで情報を入手](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[管理者向け: サインインとサービス リクエストの作成](https://portal.office.com/AdminPortal/Home?ref=support)

[AContact support for business products-管理者向けヘルプ](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
