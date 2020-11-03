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
- m365initiative-defender-office365
description: 管理者は、Exchange Online Protection (EOP) のスプーフィング対策保護についてよく寄せられる質問と回答を参照できます。
ms.openlocfilehash: a5b0484e41e3df7a7b6ad16e69a4f7062b19b554
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844394"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="11996-103">スプーフィング対策保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="11996-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="11996-104">この記事では、exchange Online のメールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織に対するスプーフィング対策保護に関するよく寄せられる質問と回答について説明します。</span><span class="sxs-lookup"><span data-stu-id="11996-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="11996-105">スパム対策保護に関する質問と回答については、「 [スパム対策保護](anti-spam-protection-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11996-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="11996-106">マルウェア対策保護に関する質問と回答については、「[マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11996-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="11996-107">Microsoft が認証されていない受信メールを選択したのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="11996-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="11996-108">Microsoft は、認証されていない受信メールを引き続き許可するリスクが正当な受信電子メールを失うリスクよりも高いと考えています。</span><span class="sxs-lookup"><span data-stu-id="11996-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="11996-109">Junking 認証されていない受信電子メールによって正当な電子メールがスパムとしてマークされるのか。</span><span class="sxs-lookup"><span data-stu-id="11996-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="11996-110">Microsoft が2018でこの機能を有効にすると、誤検知が発生しました (良好なメッセージが不良としてマークされた)。</span><span class="sxs-lookup"><span data-stu-id="11996-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="11996-111">しかし、時間の経過により、送信者は要件に合わせて調整されています。</span><span class="sxs-lookup"><span data-stu-id="11996-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="11996-112">多くの電子メールパスでは、スプーフィングとして misidentified されたメッセージ数は無視されました。</span><span class="sxs-lookup"><span data-stu-id="11996-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="11996-113">Microsoft は、お客様への展開を開始する前に、新しい電子メール認証要件を数週間、初めて採用しています。</span><span class="sxs-lookup"><span data-stu-id="11996-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="11996-114">最初のうちは混乱もありましたが、それも次第に収まりました。</span><span class="sxs-lookup"><span data-stu-id="11996-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="11996-115">Microsoft 365 のお客様は、Office 365 の Defender を使用せずに、スプーフィングインテリジェンスを利用できますか?</span><span class="sxs-lookup"><span data-stu-id="11996-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="11996-116">はい。</span><span class="sxs-lookup"><span data-stu-id="11996-116">Yes.</span></span> <span data-ttu-id="11996-117">2018年10月の時点で、Exchange Online にメールボックスを持つすべての組織と、Exchange Online メールボックスがないスタンドアロン EOP 組織では、スプーフィングインテリジェンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11996-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="11996-118">スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか</span><span class="sxs-lookup"><span data-stu-id="11996-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="11996-119">「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11996-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="11996-120">自分が管理者であり、電子メールドメイン内のメッセージのソースがすべてわからない。</span><span class="sxs-lookup"><span data-stu-id="11996-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="11996-121">「 [電子メールのすべてのソースがわからない」を](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)参照してください。</span><span class="sxs-lookup"><span data-stu-id="11996-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="11996-122">組織のスプーフィング対策保護を無効にした場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="11996-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="11996-123">スプーフィング対策保護を無効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="11996-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="11996-124">保護を無効にすると、組織内でより多くのフィッシングおよびスパムメッセージが配信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="11996-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="11996-125">すべてのフィッシングがスプーフィングされるわけではなく、すべてのスプーフィングされたメッセージが失われるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="11996-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="11996-126">ただし、リスクは高くなります。</span><span class="sxs-lookup"><span data-stu-id="11996-126">However, your risk will be higher.</span></span>

<span data-ttu-id="11996-127">これで [コネクタのフィルター処理が拡張](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) されたので、EOP 前に他のサービスを経由してメールをルーティングするときに、スプーフィング対策保護を無効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="11996-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="11996-128">スプーフィング対策保護は、すべてのフィッシングから保護されることを意味しますか?</span><span class="sxs-lookup"><span data-stu-id="11996-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="11996-129">残念ですが、ありません。</span><span class="sxs-lookup"><span data-stu-id="11996-129">Unfortunately, no.</span></span> <span data-ttu-id="11996-130">攻撃者は、他の手法 (たとえば、無料の電子メールサービスのアカウントやアカウントなど) を使用するために適応します。</span><span class="sxs-lookup"><span data-stu-id="11996-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="11996-131">ただし、フィッシング対策保護は、これらの他の種類のフィッシング方法を検出する方がはるかに優れています。</span><span class="sxs-lookup"><span data-stu-id="11996-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="11996-132">EOP の保護レイヤーは相互に連携して設計されており、互いに重ねて構築されています。</span><span class="sxs-lookup"><span data-stu-id="11996-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="11996-133">その他の大規模な電子メールサービスは、認証されていない受信メールをブロックするか</span><span class="sxs-lookup"><span data-stu-id="11996-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="11996-134">ほぼすべての大規模な電子メールサービスは、従来の SPF、DKIM、DMARC のチェックを実装しています。</span><span class="sxs-lookup"><span data-stu-id="11996-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="11996-135">一部のサービスでは、他の厳密なチェックが行われますが、認証されていない電子メールをブロックし、それらをスプーフィングされたメッセージとして処理することはほとんどありません EOP。</span><span class="sxs-lookup"><span data-stu-id="11996-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="11996-136">しかし、特にフィッシングの問題により、認証されていない電子メールに関する問題について、業界はより多くの情報を把握してきています。</span><span class="sxs-lookup"><span data-stu-id="11996-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="11996-137">まだスプーフィング対策を有効にしている場合は、高度なスパムフィルター設定 "SPF レコード: hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="11996-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) if I enable anti-spoofing?</span></span>

<span data-ttu-id="11996-138">いいえ。</span><span class="sxs-lookup"><span data-stu-id="11996-138">No.</span></span> <span data-ttu-id="11996-139">この ASF 設定は不要になりました。</span><span class="sxs-lookup"><span data-stu-id="11996-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="11996-140">スプーフィング対策保護では、SPF に障害が発生した場合と、非常に幅広い条件セットがあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="11996-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="11996-141">スプーフィング対策を有効にしているときに、 **SPF レコード: Hard Fail** ( _MarkAsSpamSpfRecordHardFail_ ) も有効にすると、誤検出が多くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11996-141">If you have anti-spoofing enabled and the **SPF record: hard fail** ( _MarkAsSpamSpfRecordHardFail_ ) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="11996-142">この機能を無効にすることをお勧めします。これにより、スパムやフィッシングメッセージを検出するための追加のメリットはほとんど提供されず、その代わりに、ほとんどが誤検知を生成することになります。</span><span class="sxs-lookup"><span data-stu-id="11996-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="11996-143">詳細については、「 [Advanced Spam Filter (ASF) settings IN EOP](advanced-spam-filtering-asf-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11996-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="11996-144">送信者の書き換えスキームは転送された電子メールの修正に役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="11996-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="11996-145">SRS は転送された電子メールの問題を部分的にしか解決しません。</span><span class="sxs-lookup"><span data-stu-id="11996-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="11996-146">SMTP **メールをから** 再書き込みすることで、SRS は転送されたメッセージが次の宛先に SPF を通過することを保証できます。</span><span class="sxs-lookup"><span data-stu-id="11996-146">By rewriting the SMTP **MAIL FROM** , SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="11996-147">ただし、スプーフィング対策は、 **差出人** アドレスと (または他の信号の) **from** または dkim 署名ドメイン (またはその他の信号) との組み合わせに基づいているため、SRS で転送された電子メールがスプーフィングとしてマークされることを防ぐだけではありません。</span><span class="sxs-lookup"><span data-stu-id="11996-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
