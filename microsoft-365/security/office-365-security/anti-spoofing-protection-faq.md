---
title: スプーフィング対策保護に関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Exchange Online Protection (EOP) のスプーフィング対策保護に関してよく寄せられる質問と回答を表示できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288911"
---
# <a name="anti-spoofing-protection-faq"></a>スプーフィング対策保護に関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

この記事では、Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織のスプーフィング対策保護に関してよく寄せられる質問と回答を提供します。

スパム対策保護に関する質問と回答については、スパム対策保護に関する [FAQ を参照してください](anti-spam-protection-faq.md)。

マルウェア対策保護に関する質問と回答については、「マルウェア対策保護に関する [FAQ」を参照してください。](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft が認証されていない受信メールを迷惑メールにした理由

Microsoft は、認証されていない受信メールを許可し続けるリスクは、正当な受信メールを失うリスクよりも高いと考える。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>認証されていない受信メールを迷惑メールにした場合、正当な電子メールはスパムとしてマークされますか?

Microsoft が 2018 年にこの機能を有効にした場合、誤検知が発生しました (良好なメッセージは無効とマークされています)。 ただし、時間の長い間、送信者は要件に合わせて調整しました。 スプーフィングと誤って特定されたメッセージの数は、ほとんどの電子メール パスでごくわずかになりました。

Microsoft 自体は、最初に新しい電子メール認証要件を数週間前に採用してから、顧客に展開しました。 最初のうちは混乱もありましたが、それも次第に収まりました。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>スプーフィング インテリジェンスは、Defender を使用しない Microsoft 365 ユーザーが Office 365 に対応していますか?

はい。 2018 年 10 月の現在、スプーフィング インテリジェンスは、Exchange Online のメールボックスを持つすべての組織、および Exchange Online メールボックスのないスタンドアロンの EOP 組織で利用できます。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか

「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>I'm an admin and I don't know all of sources for messages in my email domain!

See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>組織のスプーフィング対策保護を無効にした場合は、どうなるでしょうか。

スプーフィング対策保護を無効にすることをお勧めしません。 保護を無効にすると、組織内に配信されるフィッシングメッセージとスパム メッセージの数が多くなります。 すべてのフィッシングがスプーフィングであるのではなく、すべてのスプーフィングされたメッセージが見逃されるとは言えな。 ただし、リスクは高くなります。

コネクタの [拡張フィルタリング](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) が使用可能になったので、EOP の前に電子メールが別のサービスを経由してルーティングされる場合に、スプーフィング対策保護を無効にしなくなりました。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護は、すべてのフィッシングから保護されるという意味ですか?

残念ながら、いいえ。 攻撃者は、他の手法 (侵害されたアカウントや無料のメール サービスのアカウントなど) を使用する方法に適応します。 ただし、フィッシング対策保護は、これらの他の種類のフィッシング方法を検出する方が優れた機能を提供します。 EOP の保護レイヤーは、互いに機能し、互いに上に構築するように設計されています。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>その他の大規模な電子メール サービスは、認証されていない受信メールをブロックしますか?

大部分の大規模な電子メール サービスは、従来の SPF、DKIM、および DMARC チェックを実装しています。 一部のサービスには、より厳密なチェックが他にもあります。ただし、認証されていない電子メールをブロックしてスプーフィングされたメッセージとして扱う EOP まで行くサービスはありません。 ただし、業界では、特にフィッシングの問題が理由で、認証されていない電子メールに関する問題に対する認識が増えています。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>スプーフィング対策を有効にした場合でも、高度なスパム フィルター設定 "SPF レコード: hard fail"_(MarkAsSpamSpfRecordHardFail)_ を有効にする必要がありますか。

いいえ。 この ASF 設定は不要です。 スプーフィング対策保護では、SPF ハード障害と、より広範な条件のセットの両方が考慮されます。 スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。

スパムやフィッシングメッセージを検出する追加の利点はほとんど提供されないので、この機能を無効にすることをお勧めします。その代わりに、ほとんどが誤検知を生成します。 詳細については [、「EOP の高度なスパム フィルター (ASF) 設定」を参照してください](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>送信者書き換えスキームは、転送された電子メールの修正に役立ちますか?

SRS は転送された電子メールの問題を部分的にしか解決しません。 SMTP MAIL **FROM** を書き換える場合、SRS は転送されたメッセージが次の宛先で SPF を渡すのを保証できます。 ただし、スプーフィング対策は MAIL FROMまたは DKIM 署名ドメイン (または他のシグナル) と組み合わせて From アドレスに基づくため **、SRS** 転送された電子メールがスプーフィングとしてマークされるのを防ぐには不十分です。
