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
description: 管理者は、Exchange Online Protection (EOP) でスプーフィング防止保護に関するよく寄せられる質問と回答を表示できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065539"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="0ec9d-103">スプーフィング対策保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="0ec9d-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ec9d-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0ec9d-104">**Applies to**</span></span>
- [<span data-ttu-id="0ec9d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ec9d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ec9d-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0ec9d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ec9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ec9d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ec9d-108">この記事では、Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織に対するスプーフィング防止保護に関するよく寄せられる質問と回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="0ec9d-109">スパム対策保護に関する質問と回答については、「スパム対策保護に関する [よく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="0ec9d-110">マルウェア対策保護に関する質問と回答については、「マルウェア対策の [保護に関するよく寄せられる質問」を参照してください。](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="0ec9d-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="0ec9d-111">Microsoft が認証されていない受信メールを迷惑メールにした理由</span><span class="sxs-lookup"><span data-stu-id="0ec9d-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="0ec9d-112">Microsoft は、認証されていない受信メールを引き続き許可するリスクは、正当な受信メールを失うリスクよりも高いと考っています。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="0ec9d-113">認証されていない受信メールを迷惑メールに送信すると、正当なメールがスパムとしてマークされますか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="0ec9d-114">Microsoft が 2018 年にこの機能を有効にした場合、誤検知が発生しました (良いメッセージは無効とマークされました)。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="0ec9d-115">ただし、時間の長い間、送信者は要件に合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="0ec9d-116">スプーフィングとして誤認されたメッセージの数は、ほとんどの電子メール パスでは無視できる数になりました。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="0ec9d-117">Microsoft 自体は、最初に新しい電子メール認証要件を数週間前に採用してから、顧客に展開しました。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="0ec9d-118">最初のうちは混乱もありましたが、それも次第に収まりました。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="0ec9d-119">スプーフィング インテリジェンスは、365 の場合、Defender なしで Microsoft 365 Officeできますか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="0ec9d-120">はい。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-120">Yes.</span></span> <span data-ttu-id="0ec9d-121">2018 年 10 月現在、スプーフィング インテリジェンスは、Exchange Online のメールボックスを持つすべての組織、および Exchange Online メールボックスのないスタンドアロンの EOP 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="0ec9d-122">スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか</span><span class="sxs-lookup"><span data-stu-id="0ec9d-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="0ec9d-123">「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="0ec9d-124">私は管理者であり、メール ドメイン内のメッセージのすべてのソースを知りません。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="0ec9d-125">「 [メールのすべてのソースを知らない」を参照してください](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="0ec9d-126">組織のスプーフィング対策保護を無効にした場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="0ec9d-127">スプーフィング対策保護を無効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="0ec9d-128">保護を無効にすると、組織内で配信されるフィッシングメッセージとスパム メッセージの数が多くなります。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="0ec9d-129">すべてのフィッシング詐欺がスプーフィングである必要があります。また、すべてのスプーフィングされたメッセージが見逃される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="0ec9d-130">ただし、リスクは高くなります。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-130">However, your risk will be higher.</span></span>

<span data-ttu-id="0ec9d-131">コネクタの [拡張フィルター](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 処理が利用可能になったので、EOP の前にメールが別のサービスを経由してルーティングされる場合、スプーフィング防止保護を無効にした方が推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-131">Now that [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="0ec9d-132">スプーフィング対策保護は、すべてのフィッシングから保護されるという意味ですか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="0ec9d-133">残念ながら、いいえ。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-133">Unfortunately, no.</span></span> <span data-ttu-id="0ec9d-134">攻撃者は、他の手法 (たとえば、侵害されたアカウントや無料の電子メール サービスのアカウント) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="0ec9d-135">ただし、フィッシング対策保護は、これらの他の種類のフィッシング方法を検出する方が優れた機能です。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="0ec9d-136">EOP の保護層は、一緒に動作するように設計され、互いに上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="0ec9d-137">他の大規模な電子メール サービスは、認証されていない受信メールをブロックしますか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="0ec9d-138">大部分の大規模なメール サービスは、従来の SPF、DKIM、DMARC チェックを実装しています。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="0ec9d-139">一部のサービスでは、より厳密なチェックが行われるサービスがありますが、認証されていない電子メールをブロックしてスプーフィングされたメッセージとして扱う EOP まで行くサービスもあります。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="0ec9d-140">しかし、業界は、特にフィッシングの問題のために、認証されていない電子メールに関する問題についてより多くの認識を得てきている。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="0ec9d-141">スプーフィング対策を有効にした場合でも、高度なスパム フィルター設定 "SPF レコード: hard fail"_(MarkAsSpamSpfRecordHardFail)_ を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="0ec9d-142">いいえ。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-142">No.</span></span> <span data-ttu-id="0ec9d-143">この ASF 設定は不要です。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="0ec9d-144">スプーフィング防止保護では、SPF ハード障害と、より広範な条件の両方が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="0ec9d-145">スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="0ec9d-146">スパムやフィッシング メッセージを検出する利点はほとんど提供されないので、この機能を無効にし、その代わりにほとんど誤検知を生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="0ec9d-147">詳細については [、「EOP の高度なスパム フィルター (ASF) 設定」を参照してください](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="0ec9d-148">送信者書き換えスキームは、転送されたメールを修正するのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="0ec9d-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="0ec9d-149">SRS は転送された電子メールの問題を部分的にしか解決しません。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="0ec9d-150">SMTP MAIL **FROM** を書き換える場合、SRS は転送されたメッセージが次の宛先で SPF を渡すのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="0ec9d-151">ただし、スプーフィング対策は MAIL FROMまたは DKIM 署名ドメイン (または他のシグナル) と組み合わせて From アドレスに基づくため **、SRS** 転送メールがスプーフィングとしてマークされるのを防ぐには不十分です。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>