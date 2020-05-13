---
title: スプーフィング対策保護に関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) のスプーフィング対策保護についてよく寄せられる質問と回答を参照できます。
ms.openlocfilehash: 603293dd00100e3b93a225d94f2ed8fd9baae6a5
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209097"
---
# <a name="anti-spoofing-protection-faq"></a>スプーフィング対策保護に関する FAQ

このトピックでは、exchange Online のメールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織に対するスプーフィング対策保護に関するよく寄せられる質問と回答について説明します。

スパム対策保護に関する質問と回答については、「[スパム対策保護](anti-spam-protection-faq.md)に関する FAQ」を参照してください。

マルウェア対策保護に関する質問と回答については、「[マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft が認証されていない受信メールを選択したのはなぜですか?

フィッシング攻撃が影響を及ぼし、電子メール認証が15年以上にわたっているため、Microsoft は、認証されていない受信メールを引き続き許可するリスクが正当な受信電子メールを失うリスクよりも高いと考えています。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Junking 認証されていない受信電子メールによって正当な電子メールがスパムとしてマークされるのか。

Microsoft が2018でこの機能を有効にすると、誤検知が発生しました (良好なメッセージが不良としてマークされた)。 ただし、時間の経過と共に、送信者は新しい送信者の認証要件に合わせて調整され、多くの電子メールパスでは、misidentified されていたメッセージ数は無視されました。

Microsoft は、お客様への展開を開始する前に、新しい電子メール認証要件を数週間、初めて採用しています。 最初のうちは混乱もありましたが、それも次第に収まりました。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>ATP がない場合、Microsoft 365 のお客様はスプーフィングインテリジェンスを利用できますか?

はい。 2018年10月の時点で、Exchange Online にメールボックスを持つすべての組織と、Exchange Online メールボックスがないスタンドアロン EOP 組織では、スプーフィングインテリジェンスを使用できます。

スプーフィング対策テクノロジは、最初は Office 365 Enterprise E5 サブスクリプションまたは office 365 Advanced Threat Protection (Office 365 ATP) アドオンを備えた組織にのみ、サブスクリプションに展開されていました。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか

「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>自分が管理者であり、電子メールドメイン内のメッセージのソースがすべてわからない。

「[電子メールのすべてのソースがわからない」を](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)参照してください。

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>組織のスプーフィング対策保護を無効にした場合はどうなりますか?

これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。 すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。 ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。

これで[コネクタのフィルター処理が拡張](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)されたので、MX レコードが EOP に電子メールを配信する前に別のサーバーまたはサービスを指している場合、スプーフィング対策保護を無効にすることは推奨されなくなりました。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護は、すべてのフィッシングから保護されることを意味しますか?

残念ですが、ありません。 攻撃者は、他の手法 (たとえば、無料の電子メールサービスのアカウントやアカウントなど) を使用するために適応します。 ただし、フィッシング対策保護は、これらの他の種類のフィッシング方法を検出する方がはるかに優れています。 EOP の保護レイヤーは相互に連携して設計されており、互いに重ねて構築されています。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>その他の大規模な電子メールサービスは、認証されていない受信メールをブロックするか

ほぼすべての大規模な電子メールサービスは、従来の SPF、DKIM、DMARC のチェックを実装しています。 一部のサービスでは、その他の厳密なチェックが行われますが、認証されていない電子メールをブロックして EOP については、スプーフィングされたメッセージとして処理します。 しかし、特にフィッシングの問題により、認証されていない電子メールに関する問題について、業界はより多くの情報を把握してきています。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>まだスプーフィング対策を有効にしている場合は、高度なスパムフィルター設定 "SPF レコード: hard fail" (_MarkAsSpamSpfRecordHardFail_) を有効にする必要がありますか?

いいえ。 この ASF 設定は必要なくなりました。これは、SPF によるハード障害を考慮するだけでなく、非常に幅広い条件セットを考慮しているためです。 スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。

この機能を無効にすることをお勧めします。これにより、スパムやフィッシングメッセージを検出するための追加のメリットはほとんど提供されず、その代わりに、ほとんどが誤検知を生成することになります。 詳細については、「 [Advanced Spam Filter (ASF) settings IN EOP](advanced-spam-filtering-asf-options.md)」を参照してください。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>送信者の書き換えスキームは転送された電子メールの修正に役立ちますか?

SRS は転送された電子メールの問題を部分的にしか解決しません。 SMTP**メールをから**再書き込みすることで、SRS は転送されたメッセージが次の宛先に SPF を通過することを保証できます。 ただし、スプーフィング対策は、**差出人**アドレスと (または他の信号の) **from**または dkim 署名ドメイン (またはその他の信号) との組み合わせに基づいているため、SRS で転送された電子メールがスプーフィングとしてマークされることを防ぐだけではありません。
