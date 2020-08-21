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
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="bbda5-103">スプーフィング対策保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="bbda5-103">Anti-spoofing protection FAQ</span></span>

<span data-ttu-id="bbda5-104">このトピックでは、Exchange Online メールボックスを使用している Microsoft 365 組織または Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織向けのスプーフィング対策保護に関するよく寄せられる質問と回答について取り上示します。</span><span class="sxs-lookup"><span data-stu-id="bbda5-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="bbda5-105">スパム対策保護に関する質問と回答については、「スパム対策保護 [のよく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="bbda5-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="bbda5-106">マルウェア対策保護に関する質問と回答については、「マルウェア対策保護 [」に関してよく寄せられる質問を参照してください。](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="bbda5-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="bbda5-107">Microsoft が認証されていない受信メールを迷惑メールとして選択したのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="bbda5-108">フィッシング攻撃の影響により、15 年以上前から電子メール認証が行われたため、Microsoft は認証されていない受信電子メールを許可するリスクが、合当の受信メールを失う危険性よりも高いと考えています。</span><span class="sxs-lookup"><span data-stu-id="bbda5-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="bbda5-109">迷惑メールの受信メールに対して、問題があるメールはスパムとしてマークされますか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="bbda5-110">Microsoft が 2018 年にこの機能を有効にすると、一部の誤検知が発生しました (有用なメッセージは無効なマークになりました)。</span><span class="sxs-lookup"><span data-stu-id="bbda5-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="bbda5-111">しかし、時間の過とおり、送信者は新しい送信者認証の要件を満たすと調整され、多くのメール パスでスプーフィングされたと識別されなかったメッセージの数も調整されました。</span><span class="sxs-lookup"><span data-stu-id="bbda5-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="bbda5-112">Microsoft はまず、新しいメール認証要件を数週間前に導入してからお客様に展開しました。</span><span class="sxs-lookup"><span data-stu-id="bbda5-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="bbda5-113">最初のうちは混乱もありましたが、それも次第に収まりました。</span><span class="sxs-lookup"><span data-stu-id="bbda5-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="bbda5-114">スプーフィング インテリジェンスは ATP なしで Microsoft 365 のお客様が利用できますか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-114">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="bbda5-115">はい。</span><span class="sxs-lookup"><span data-stu-id="bbda5-115">Yes.</span></span> <span data-ttu-id="bbda5-116">2018 年 10 月の後、スプーフィング インテリジェンスは Exchange Online のメールボックスを持つすべての組織、Exchange Online メールボックスを持たないスタンドアロン EOP 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="bbda5-116">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="bbda5-117">スプーフィング対策テクノロジは、Office 365 Enterprise E5 サブスクリプションまたは Office 365 Advanced Threat Protection (Office 365 ATP) アドオンをサブスクリプション用に取得した組織にのみ展開されました。</span><span class="sxs-lookup"><span data-stu-id="bbda5-117">Anti-spoofing technology was initially deployed only to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (Office 365 ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="bbda5-118">スパムまたは非スパムのメッセージについて、どのように Microsoft に報告すればよいですか</span><span class="sxs-lookup"><span data-stu-id="bbda5-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="bbda5-119">「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbda5-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="bbda5-120">管理者ですが、メール ドメイン内のメッセージのすべての送信元がわかっているわけだりません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="bbda5-121">メール [のすべての送信元がわからない場合に見てください](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="bbda5-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="bbda5-122">組織のスプーフィング対策保護を無効にした場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="bbda5-123">これについては、お勧めできません。より多くの見逃されたフィッシング メッセージやスパム メッセージにさらされるようになります。</span><span class="sxs-lookup"><span data-stu-id="bbda5-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="bbda5-124">すべてのフィッシングがスプーフィングであるわけでなく、すべてのスプーフィングが見逃されるわけでもありません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="bbda5-125">ただし、スプーフィング対策を有効にしているお客様よりもリスクは高くなります。</span><span class="sxs-lookup"><span data-stu-id="bbda5-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="bbda5-126">コネクタの [拡張フィルターが使用可能になった](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ため、MX レコードが EOP にメールを配信する前に別のサーバーまたはサービスをポイントしている場合、スプーフィング対策保護を無効にしておくことをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="bbda5-127">スプーフィング対策保護とは、すべてのフィッシングから保護されるという意味ですか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="bbda5-128">残り、いいえ、</span><span class="sxs-lookup"><span data-stu-id="bbda5-128">Unfortunately, no.</span></span> <span data-ttu-id="bbda5-129">攻撃者は、他の方法 (侵害されたアカウントや無料のメール サービスのアカウントなど) を使用するのを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="bbda5-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="bbda5-130">ただし、フィッシング対策保護は、この他の種類のフィッシング方法を検出するほうが優れていません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="bbda5-131">EOP では保護層が連携して機能し、積み重ねて動作します。</span><span class="sxs-lookup"><span data-stu-id="bbda5-131">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="bbda5-132">他の大規模な電子メール サービスは認証されていない受信メールをブロックしますか。</span><span class="sxs-lookup"><span data-stu-id="bbda5-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="bbda5-133">大規模な電子メール サービスには、従来の SPF、DKIM、および DMARC のチェックが実装されています。</span><span class="sxs-lookup"><span data-stu-id="bbda5-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="bbda5-134">一部のサービスには、さらに複雑なチェックが他に含まれますが、認証されていないメールをブロックし、スプーフィングされたメッセージとして処理する EOP にはあくまで少しありません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-134">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="bbda5-135">ただし、このこの情報の方は、特にフィッシングの問題のため、認証されていない電子メールの問題をより多く認識しています。</span><span class="sxs-lookup"><span data-stu-id="bbda5-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="bbda5-136">スプーフィング対策を有効にした場合でも、高度なスパム フィルターの設定「SPF レコード: Hard_Fail」(MarkAsSpamSpfRecordHardFail)_ を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="bbda5-137">いいえ。</span><span class="sxs-lookup"><span data-stu-id="bbda5-137">No.</span></span> <span data-ttu-id="bbda5-138">スプーフィング対策では SPF Hard Fail を考慮するだけでなく、それほど広範囲な条件のセットが考慮され、この ASF 設定は不要になりました。</span><span class="sxs-lookup"><span data-stu-id="bbda5-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="bbda5-139">スプーフィング対策を有効にしているときに、**SPF レコード: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) も有効にすると、誤検出が多くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bbda5-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="bbda5-140">スパムやフィッシング メッセージを検出する追加のメリットをほとんどなく、多くの場合誤検出が発生するので、この機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bbda5-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="bbda5-141">詳細については [、EOP の高度なスパム フィルター (ASF) の設定を参照してください](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="bbda5-141">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="bbda5-142">送信者書き換えスキームは転送される電子メールの修正に役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="bbda5-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="bbda5-143">SRS は転送された電子メールの問題を部分的にしか解決しません。</span><span class="sxs-lookup"><span data-stu-id="bbda5-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="bbda5-144">SMTP MAIL FROM を書き **換え**ることで、SRS では転送されたメッセージが次の宛先で SPF をパスするようにできます。</span><span class="sxs-lookup"><span data-stu-id="bbda5-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="bbda5-145">ただし、スプーフィング対策は**MAIL FROM、DKIM**署名ドメイン (またはその他のシグナル) と組み合わせた From アドレスに基づけられているため、SRS 転送された電子メールにスプーフィングのマークが付けられることを防止する十分な数ではありません。 **From**</span><span class="sxs-lookup"><span data-stu-id="bbda5-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
