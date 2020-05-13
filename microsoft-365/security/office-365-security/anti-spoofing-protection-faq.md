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
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="461a6-103">スプーフィング対策保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="461a6-103">Anti-spoofing protection FAQ</span></span>

<span data-ttu-id="461a6-104">このトピックでは、exchange Online のメールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織に対するスプーフィング対策保護に関するよく寄せられる質問と回答について説明します。</span><span class="sxs-lookup"><span data-stu-id="461a6-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="461a6-105">スパム対策保護に関する質問と回答については、「[スパム対策保護](anti-spam-protection-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="461a6-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="461a6-106">マルウェア対策保護に関する質問と回答については、「[マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="461a6-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="461a6-107">Microsoft が認証されていない受信メールを選択したのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="461a6-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="461a6-108">フィッシング攻撃が影響を及ぼし、電子メール認証が15年以上にわたっているため、Microsoft は、認証されていない受信メールを引き続き許可するリスクが正当な受信電子メールを失うリスクよりも高いと考えています。</span><span class="sxs-lookup"><span data-stu-id="461a6-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="461a6-109">Junking 認証されていない受信電子メールによって正当な電子メールがスパムとしてマークされるのか。</span><span class="sxs-lookup"><span data-stu-id="461a6-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="461a6-110">Microsoft が2018でこの機能を有効にすると、誤検知が発生しました (良好なメッセージが不良としてマークされた)。</span><span class="sxs-lookup"><span data-stu-id="461a6-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="461a6-111">ただし、時間の経過と共に、送信者は新しい送信者の認証要件に合わせて調整され、多くの電子メールパスでは、misidentified されていたメッセージ数は無視されました。</span><span class="sxs-lookup"><span data-stu-id="461a6-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="461a6-112">Microsoft は、お客様への展開を開始する前に、新しい電子メール認証要件を数週間、初めて採用しています。</span><span class="sxs-lookup"><span data-stu-id="461a6-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="461a6-113">最初のうちは混乱もありましたが、それも次第に収まりました。</span><span class="sxs-lookup"><span data-stu-id="461a6-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="461a6-114">ATP がない場合、Microsoft 365 のお客様はスプーフィングインテリジェンスを利用できますか?</span><span class="sxs-lookup"><span data-stu-id="461a6-114">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="461a6-115">はい。</span><span class="sxs-lookup"><span data-stu-id="461a6-115">Yes.</span></span> <span data-ttu-id="461a6-116">2018年10月の時点で、Exchange Online にメールボックスを持つすべての組織と、Exchange Online メールボックスがないスタンドアロン EOP 組織では、スプーフィングインテリジェンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="461a6-116">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="461a6-117">スプーフィング対策テクノロジは、最初は Office 365 Enterprise E5 サブスクリプションまたは office 365 Advanced Threat Protection (Office 365 ATP) アドオンを備えた組織にのみ、サブスクリプションに展開されていました。</span><span class="sxs-lookup"><span data-stu-id="461a6-117">Anti-spoofing technology was initially deployed only to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (Office 365 ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="461a6-118">スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか</span><span class="sxs-lookup"><span data-stu-id="461a6-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="461a6-119">「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="461a6-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="461a6-120">自分が管理者であり、電子メールドメイン内のメッセージのソースがすべてわからない。</span><span class="sxs-lookup"><span data-stu-id="461a6-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="461a6-121">「[電子メールのすべてのソースがわからない」を](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)参照してください。</span><span class="sxs-lookup"><span data-stu-id="461a6-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="461a6-122">組織のスプーフィング対策保護を無効にした場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="461a6-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="461a6-123">これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。</span><span class="sxs-lookup"><span data-stu-id="461a6-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="461a6-124">すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。</span><span class="sxs-lookup"><span data-stu-id="461a6-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="461a6-125">ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。</span><span class="sxs-lookup"><span data-stu-id="461a6-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="461a6-126">これで[コネクタのフィルター処理が拡張](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)されたので、MX レコードが EOP に電子メールを配信する前に別のサーバーまたはサービスを指している場合、スプーフィング対策保護を無効にすることは推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="461a6-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="461a6-127">スプーフィング対策保護は、すべてのフィッシングから保護されることを意味しますか?</span><span class="sxs-lookup"><span data-stu-id="461a6-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="461a6-128">残念ですが、ありません。</span><span class="sxs-lookup"><span data-stu-id="461a6-128">Unfortunately, no.</span></span> <span data-ttu-id="461a6-129">攻撃者は、他の手法 (たとえば、無料の電子メールサービスのアカウントやアカウントなど) を使用するために適応します。</span><span class="sxs-lookup"><span data-stu-id="461a6-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="461a6-130">ただし、フィッシング対策保護は、これらの他の種類のフィッシング方法を検出する方がはるかに優れています。</span><span class="sxs-lookup"><span data-stu-id="461a6-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="461a6-131">EOP の保護レイヤーは相互に連携して設計されており、互いに重ねて構築されています。</span><span class="sxs-lookup"><span data-stu-id="461a6-131">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="461a6-132">その他の大規模な電子メールサービスは、認証されていない受信メールをブロックするか</span><span class="sxs-lookup"><span data-stu-id="461a6-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="461a6-133">ほぼすべての大規模な電子メールサービスは、従来の SPF、DKIM、DMARC のチェックを実装しています。</span><span class="sxs-lookup"><span data-stu-id="461a6-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="461a6-134">一部のサービスでは、その他の厳密なチェックが行われますが、認証されていない電子メールをブロックして EOP については、スプーフィングされたメッセージとして処理します。</span><span class="sxs-lookup"><span data-stu-id="461a6-134">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="461a6-135">しかし、特にフィッシングの問題により、認証されていない電子メールに関する問題について、業界はより多くの情報を把握してきています。</span><span class="sxs-lookup"><span data-stu-id="461a6-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="461a6-136">まだスプーフィング対策を有効にしている場合は、高度なスパムフィルター設定 "SPF レコード: hard fail" (_MarkAsSpamSpfRecordHardFail_) を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="461a6-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="461a6-137">いいえ。</span><span class="sxs-lookup"><span data-stu-id="461a6-137">No.</span></span> <span data-ttu-id="461a6-138">この ASF 設定は必要なくなりました。これは、SPF によるハード障害を考慮するだけでなく、非常に幅広い条件セットを考慮しているためです。</span><span class="sxs-lookup"><span data-stu-id="461a6-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="461a6-139">スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="461a6-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="461a6-140">この機能を無効にすることをお勧めします。これにより、スパムやフィッシングメッセージを検出するための追加のメリットはほとんど提供されず、その代わりに、ほとんどが誤検知を生成することになります。</span><span class="sxs-lookup"><span data-stu-id="461a6-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="461a6-141">詳細については、「 [Advanced Spam Filter (ASF) settings IN EOP](advanced-spam-filtering-asf-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="461a6-141">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="461a6-142">送信者の書き換えスキームは転送された電子メールの修正に役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="461a6-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="461a6-143">SRS は転送された電子メールの問題を部分的にしか解決しません。</span><span class="sxs-lookup"><span data-stu-id="461a6-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="461a6-144">SMTP**メールをから**再書き込みすることで、SRS は転送されたメッセージが次の宛先に SPF を通過することを保証できます。</span><span class="sxs-lookup"><span data-stu-id="461a6-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="461a6-145">ただし、スプーフィング対策は、**差出人**アドレスと (または他の信号の) **from**または dkim 署名ドメイン (またはその他の信号) との組み合わせに基づいているため、SRS で転送された電子メールがスプーフィングとしてマークされることを防ぐだけではありません。</span><span class="sxs-lookup"><span data-stu-id="461a6-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
