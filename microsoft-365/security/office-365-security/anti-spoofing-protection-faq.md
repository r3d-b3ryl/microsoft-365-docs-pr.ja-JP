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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) でのスプーフィング対策保護に関してよく寄せられる質問と回答を表示できます。
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826675"
---
# <a name="anti-spoofing-protection-faq"></a>スプーフィング対策保護に関する FAQ

このトピックでは、Exchange Online メールボックスを使用している Microsoft 365 組織または Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織向けのスプーフィング対策保護に関するよく寄せられる質問と回答について取り上示します。

スパム対策保護に関する質問と回答については、「スパム対策保護 [のよく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。

マルウェア対策保護に関する質問と回答については、「マルウェア対策保護 [」に関してよく寄せられる質問を参照してください。](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Microsoft が認証されていない受信メールを迷惑メールとして選択したのはなぜですか?

フィッシング攻撃の影響により、15 年以上前から電子メール認証が行われたため、Microsoft は認証されていない受信電子メールを許可するリスクが、合当の受信メールを失う危険性よりも高いと考えています。

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>迷惑メールの受信メールに対して、問題があるメールはスパムとしてマークされますか?

Microsoft が 2018 年にこの機能を有効にすると、一部の誤検知が発生しました (有用なメッセージは無効なマークになりました)。 しかし、時間の過とおり、送信者は新しい送信者認証の要件を満たすと調整され、多くのメール パスでスプーフィングされたと識別されなかったメッセージの数も調整されました。

Microsoft はまず、新しいメール認証要件を数週間前に導入してからお客様に展開しました。 最初のうちは混乱もありましたが、それも次第に収まりました。

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>スプーフィング インテリジェンスは ATP なしで Microsoft 365 のお客様が利用できますか?

はい。 2018 年 10 月の後、スプーフィング インテリジェンスは Exchange Online のメールボックスを持つすべての組織、Exchange Online メールボックスを持たないスタンドアロン EOP 組織で利用できます。

スプーフィング対策テクノロジは、Office 365 Enterprise E5 サブスクリプションまたは Office 365 Advanced Threat Protection (Office 365 ATP) アドオンをサブスクリプション用に取得した組織にのみ展開されました。

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか

「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>管理者ですが、メール ドメイン内のメッセージのすべての送信元がわかっているわけだりません。

メール [のすべての送信元がわからない場合に見てください](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>組織のスプーフィング対策保護を無効にした場合はどうなりますか?

これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。 すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。 ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。

コネクタの [拡張フィルターが使用可能になった](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ため、MX レコードが EOP にメールを配信する前に別のサーバーまたはサービスをポイントしている場合、スプーフィング対策保護を無効にしておくことをお勧めしません。

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>スプーフィング対策保護とは、すべてのフィッシングから保護されるという意味ですか?

残り、いいえ、 攻撃者は、他の方法 (侵害されたアカウントや無料のメール サービスのアカウントなど) を使用するのを受け入れます。 ただし、フィッシング対策保護は、この他の種類のフィッシング方法を検出するほうが優れていません。 EOP では保護層が連携して機能し、積み重ねて動作します。

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>他の大規模な電子メール サービスは認証されていない受信メールをブロックしますか。

大規模な電子メール サービスには、従来の SPF、DKIM、および DMARC のチェックが実装されています。 一部のサービスには、さらに複雑なチェックが他に含まれますが、認証されていないメールをブロックし、スプーフィングされたメッセージとして処理する EOP にはあくまで少しありません。 ただし、このこの情報の方は、特にフィッシングの問題のため、認証されていない電子メールの問題をより多く認識しています。

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>スプーフィング対策を有効にした場合でも、高度なスパム フィルターの設定「SPF レコード: Hard_Fail」(MarkAsSpamSpfRecordHardFail)_ を有効にする必要がありますか?

いいえ。 スプーフィング対策では SPF Hard Fail を考慮するだけでなく、それほど広範囲な条件のセットが考慮され、この ASF 設定は不要になりました。 スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。

スパムやフィッシング メッセージを検出する追加のメリットをほとんどなく、多くの場合誤検出が発生するので、この機能を無効にすることをお勧めします。 詳細については [、EOP の高度なスパム フィルター (ASF) の設定を参照してください](advanced-spam-filtering-asf-options.md)。

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>送信者書き換えスキームは転送される電子メールの修正に役立ちますか?

SRS は転送された電子メールの問題を部分的にしか解決しません。 SMTP MAIL FROM を書き **換え**ることで、SRS では転送されたメッセージが次の宛先で SPF をパスするようにできます。 ただし、スプーフィング対策は**MAIL FROM、DKIM**署名ドメイン (またはその他のシグナル) と組み合わせた From アドレスに基づけられているため、SRS 転送された電子メールにスプーフィングのマークが付けられることを防止する十分な数ではありません。 **From**
