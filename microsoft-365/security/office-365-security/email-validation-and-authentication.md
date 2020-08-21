---
title: Microsoft 365 のメール認証
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
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
ms.openlocfilehash: cc9489a258608080118e88bf1375e4d5f35f8c77
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826651"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="21a39-103">EOP のメール認証</span><span class="sxs-lookup"><span data-stu-id="21a39-103">Email authentication in EOP</span></span>

<span data-ttu-id="21a39-104">メール認証 (メール検証とも呼ばれます) は、スプーフィング (偽造された差出人からのメール メッセージ) を阻止しようとする標準のグループです。</span><span class="sxs-lookup"><span data-stu-id="21a39-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="21a39-105">Exchange online のメールボックスを使用している Microsoft 365 の組織、およびExchange Online のメールボックスを使用していないスタンドアローンの Exchange Online Protection (EOP) 組織内で、EOP は受信メールを確認するために次の基準を使用します。</span><span class="sxs-lookup"><span data-stu-id="21a39-105">In Microsoft 365 organizations with mailboxes in Exchange Online, and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="21a39-106">SPF</span><span class="sxs-lookup"><span data-stu-id="21a39-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="21a39-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="21a39-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="21a39-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="21a39-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="21a39-109">メール認証では、差出人 (laura@contoso.com など) からのメール メッセージが正当であり、そのメール ドメイン (contoso.com など) の期待される送信元からのものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a39-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="21a39-110">このトピックの残りの部分では、これらのテクノロジのしくみ、EOP がこれらのテクノロジを使用して受信メールをチェックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21a39-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="21a39-111">メール認証を使用してスプーフィングを防止する</span><span class="sxs-lookup"><span data-stu-id="21a39-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="21a39-112">DMARC では、メッセージの**差出人**アドレス (メール クライアントでユーザーに表示される差出人のメール アドレス) を調べて、スプーフィングを防止します。</span><span class="sxs-lookup"><span data-stu-id="21a39-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="21a39-113">送信先のメール組織では、メール ドメインが SPF または DKIM にパスしたことも確認できます。これは、ドメインが認証されたため、スプーフィングされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="21a39-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span>

<span data-ttu-id="21a39-114">ただし、問題は、メール認証用のDNS 内 SPF、DKIM、および DMARC レコード (総称してメール認証ポリシーと呼ばれます) は完全にオプションであるということです。</span><span class="sxs-lookup"><span data-stu-id="21a39-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="21a39-115">そのため、microsoft.com や skype.com などの強力なメール認証ポリシーを公開しているドメインはスプーフィングから保護されますが、公開しているメール認証ポリシーが弱いドメインや認証ポリシーがまったく存在しないドメインはスプーフィングの主な対象になります。</span><span class="sxs-lookup"><span data-stu-id="21a39-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="21a39-116">2018 年 3 月の時点で、Fortune 500 の企業のうち強力なメール認証ポリシーを公開しているドメインは 9% のみです。</span><span class="sxs-lookup"><span data-stu-id="21a39-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="21a39-117">残りの91% の企業は、攻撃者により、なりすまされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="21a39-118">他のメール フィルタリング メカニズムが組み込まれていない場合、これらのドメインの成りすましの装差出人からのメールがユーザーに配信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Fortune 500 企業の DMARC ポリシー](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="21a39-120">Fortune 500 に含まれない中小規模の企業で強力なメール認証ポリシーを公開している割合はさらに少なくなり、北米と西ヨーロッパ以外のメール ドメインでは、それよりも少ない割合になります。</span><span class="sxs-lookup"><span data-stu-id="21a39-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="21a39-121">これは重大な問題です。企業はメール認証のしくみを認識していないことがありますが、攻撃者はそのしくみを完全に理解して利用するためです。</span><span class="sxs-lookup"><span data-stu-id="21a39-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="21a39-122">フィッシングは大きな問題であり、強力なメール認証ポリシーの導入は限られているため、Microsoft は受信メールをチェックするために*暗黙的なメール認証*を使用しています。</span><span class="sxs-lookup"><span data-stu-id="21a39-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="21a39-123">暗示的なメール認証は、通常のメール認証ポリシーに対する多くの拡張機能に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="21a39-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="21a39-124">これらの拡張機能には、送信者評価、送信者の履歴、受信者の履歴、行動分析、他の高度な手法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21a39-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="21a39-125">メール認証ポリシーを使用しないドメインから送信されたメッセージは、そのメッセージが正当であることを示す別のシグナルが含まれていないときには、スプーフィングのマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="21a39-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="21a39-126">Microsoft の一般発表については、「[大量のフィッシング詐欺: 第 2 部 - 強化された Microsoft 365 のスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21a39-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="21a39-127">複合認証</span><span class="sxs-lookup"><span data-stu-id="21a39-127">Composite authentication</span></span>

<span data-ttu-id="21a39-128">SPF、DKIM、および DMARC は、いずれも単独で役立つものですが、メッセージに明示的な認証レコードが存在していないときには、認証の状態を十分に伝達しません。</span><span class="sxs-lookup"><span data-stu-id="21a39-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="21a39-129">そのため、Microsoft は、複数のシグナルを 1 つの値に結合する_複合認証_ (略称: compauth) と呼ばれる暗黙的なメール認証用のアルゴリズムを開発しました。</span><span class="sxs-lookup"><span data-stu-id="21a39-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="21a39-130">メッセージのヘッダーに含まれる **Authentication-Results** ヘッダーに compauth の値がスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="21a39-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="21a39-131">Authentication-Results:</span><span class="sxs-lookup"><span data-stu-id="21a39-131">Authentication-Results:</span></span><br/><span data-ttu-id="21a39-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="21a39-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="21a39-133">これらの値については、「[Authentication-results メッセージ ヘッダー](anti-spam-message-headers.md#authentication-results-message-header)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="21a39-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="21a39-134">メッセージ ヘッダーを調べることによって、管理者またはエンド ユーザーは、Microsoft 365 が送信者がなりすましであることを判断する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="21a39-135">メール認証がスプーフィングの阻止には不十分なことがある理由</span><span class="sxs-lookup"><span data-stu-id="21a39-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="21a39-136">受信メッセージがなりすましであるかどうかを判断するためにメール認証のみに依存すると、次の制限が発生します。</span><span class="sxs-lookup"><span data-stu-id="21a39-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="21a39-137">送信側ドメインに必要な DNS レコードがないか、レコードが正しく構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="21a39-138">送信元ドメインに正しく構成された DNS レコードがありますが、そのドメインが差出人アドレスのドメインと一致しません。</span><span class="sxs-lookup"><span data-stu-id="21a39-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="21a39-139">SPF と DKIM には、差出人アドレスで使用するドメインは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="21a39-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="21a39-140">攻撃者や合法的サービスは、ドメインを登録したり、ドメインの SPF および DKIM を構成したり、差出人アドレスに完全に異なるドメインを使用したりすることができ、そのメッセージは SPF および DKIM にパスします。</span><span class="sxs-lookup"><span data-stu-id="21a39-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="21a39-141">複合認証は、メール認証チェックに失敗するメッセージをパスさせることで、これらの制限に対処できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="21a39-142">前述したように、暗黙的なメール認証は複数のシグナルを使用して、メッセージが正当であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="21a39-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="21a39-143">簡単にするために、次の例では、メール認証の結果に焦点を置いています。</span><span class="sxs-lookup"><span data-stu-id="21a39-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="21a39-144">他のバックエンド インテリジェンス要因は、メール認証にパスするメッセージをなりすましとして識別したり、メール認証に失敗したメッセージを正当として識別したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="21a39-145">たとえば、fabrikam.com ドメインには、SPF、DKIM、または DMARC レコードがありません。</span><span class="sxs-lookup"><span data-stu-id="21a39-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="21a39-146">fabrikam.com ドメインの送信者からのメッセージは、複合認証に失敗する可能性があります (`compauth` の値と理由に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="21a39-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="21a39-147">fabrikam.com が DKIM レコードなしで SPF を構成する場合、SPF にパスしたドメインは差出人アドレスのドメインと一致しているため、メッセージは複合認証にパスできます。</span><span class="sxs-lookup"><span data-stu-id="21a39-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="21a39-148">fabrikam.com が SPF レコードなしで DKIM レコードを構成する場合、パスした DKIM 署名のドメインは差出人アドレスのドメインと一致しているため、メッセージは複合認証にパスできます。</span><span class="sxs-lookup"><span data-stu-id="21a39-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="21a39-149">SPF または DKIM 署名のドメインが差出人アドレスのドメインと一致しない場合、メッセージは複合認証に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="21a39-150">認証されていないメールを送信している正当な送信者のためのソリューション</span><span class="sxs-lookup"><span data-stu-id="21a39-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="21a39-151">Microsoft 365 は、認証されていないメールを組織に送信している送信者を追跡しています。</span><span class="sxs-lookup"><span data-stu-id="21a39-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="21a39-152">その送信者がサービスによって正当ではないと判断されると、複合認証失敗のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="21a39-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="21a39-153">この問題を回避するには、このセクションの推奨事項を使用できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="21a39-154">所有しているドメインのメール認証を構成する</span><span class="sxs-lookup"><span data-stu-id="21a39-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="21a39-155">この方法は、組織内スプーフィングの解決に使用できます。また、複数のテナントを所有している場合や複数のテナントとやり取りする場合のクロスドメイン スプーフィングの解決にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="21a39-156">さらに、Microsoft 365 内の別のユーザー、または別のプロバイダーによりホストされているサード パーティに送信する場合のクロスドメイン スプーフィングを解決する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21a39-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="21a39-157">ドメインの [SPF レコードを構成します](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="21a39-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="21a39-158">プライマリ ドメインの [DKIM レコードを構成します](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="21a39-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="21a39-159">正当な送信者を判断するために、ドメインに [DMARC レコードを設定することを検討します](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="21a39-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="21a39-160">Microsoft は、SPF、DKIM、および DMARC レコードの詳細な実装ガイドラインを提供しません。</span><span class="sxs-lookup"><span data-stu-id="21a39-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="21a39-161">ただし、オンラインで利用できる大量の情報があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="21a39-162">また、組織がメール認証レコードを設定する際の支援を専門としているサード パーティ企業もあります。</span><span class="sxs-lookup"><span data-stu-id="21a39-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="21a39-163">メールのすべての送信元がわからない</span><span class="sxs-lookup"><span data-stu-id="21a39-163">You don't know all sources for your email</span></span>

<span data-ttu-id="21a39-164">多くのドメインは、ドメイン内のメッセージのすべてのメール送信元を認識していないため、SPF レコードを公開しません。</span><span class="sxs-lookup"><span data-stu-id="21a39-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="21a39-165">自分が知っているすべてのメール送信元を含む SPF レコード (特に会社のトラフィックがある場所にある) を公開することから始めて、次のニュートラル SPF ポリシー (`?all`) を公開します。</span><span class="sxs-lookup"><span data-stu-id="21a39-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="21a39-166">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="21a39-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="21a39-167">この例では、会社のインフラストラクチャからのメールはメール認証にパスしますが、不明な送信元からのメールはニュートラルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="21a39-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="21a39-168">Microsoft 365 は、会社のインフラストラクチャからの受信メールを認証済みとして扱いますが、識別されていない送信元からのメールは、(Microsoft 365 が暗黙的に認証できるかどうかによって) スプーフィングとしてマークされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="21a39-169">ただし、これは Microsoft 365 によってすべてのメールにスプーフィングのマークが付けられることからの改善に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="21a39-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="21a39-170">`?all` の SPF フォールバック ポリシーの使用を開始したら、メッセージのメール送信元を徐々に見つけて含めることができ、より厳しいポリシーを使用して SPF レコードを更新できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="21a39-171">スプーフィング インテリジェンスを使用して、認証されていないメールが許可された送信者を構成する</span><span class="sxs-lookup"><span data-stu-id="21a39-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="21a39-172">認証されていないメッセージを組織に送信する送信者を許可するために、[スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="21a39-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="21a39-173">外部ドメインの場合、スプーフィングされたユーザーは差出人アドレスのドメインですが、送信側インフラストラクチャは、送信元 IP アドレス (最大 /24 CIDR 範囲に分割)、または逆引き DNS (PTR) レコードの組織ドメインのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="21a39-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="21a39-174">以下のスクリーンショットでは、送信元 IP は PTR レコード outbound.mail.protection.outlook.com を使用して 131.107.18.4 となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="21a39-175">これは、送信側インフラストラクチャの outlook.com として表示されます。</span><span class="sxs-lookup"><span data-stu-id="21a39-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="21a39-176">この送信者に認証されていない電子メールの送信を許可するには、**[いいえ]** を **[はい]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="21a39-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![スプーフィング対策の許可された送信者の設定](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="21a39-178">送信者/受信者ペアの許可エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="21a39-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="21a39-179">スパム フィルタリングをバイパスし、フィッシング フィルタリングの一部をバイパスし、特定の送信者のマルウェア フィルタリングをバイパスしない場合は、「[Microsoft 365 で安全な送信者の一覧を作成する](create-safe-sender-lists-in-office-365.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="21a39-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="21a39-180">所有していないドメインのメール認証を構成するように送信者に依頼する</span><span class="sxs-lookup"><span data-stu-id="21a39-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="21a39-181">スパムとフィッシングの問題があるため、Microsoft は、すべてのメール組織にメール認証をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21a39-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="21a39-182">組織の手動オーバーライドを構成する代わりに、送信側ドメインの管理者にメール認証レコードを構成するように依頼できます。</span><span class="sxs-lookup"><span data-stu-id="21a39-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="21a39-183">過去にメール認証レコードを公開する必要がなかった場合でも、Microsoft にメールを送信する場合は公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="21a39-184">SPF を設定してドメインの送信側 IP アドレスを公開します。DKIM (使用可能な場合) を設定してメッセージにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="21a39-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="21a39-185">また、DMARC レコードの設定も検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="21a39-186">一括送信者を使用してメールを送信する場合は、(アドレスが属する場合) 差出人アドレスのドメインが、SPF または DMARC にパスするドメインに一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a39-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="21a39-187">次の場所 (使用している場合) が SPF レコードに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a39-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="21a39-188">オンプレミスのメールサーバー。</span><span class="sxs-lookup"><span data-stu-id="21a39-188">On-premises email servers.</span></span>
  - <span data-ttu-id="21a39-189">SaaS (サービスとしてのソフトウェア) プロバイダーから送信されたメール。</span><span class="sxs-lookup"><span data-stu-id="21a39-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="21a39-190">クラウドホスティング サービス (Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services など) から送信されたメール。</span><span class="sxs-lookup"><span data-stu-id="21a39-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="21a39-191">ISP によってホストされている小規模なドメインについては、ISP の指示に従って SPF レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="21a39-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="21a39-192">送信側ドメインで認証することは最初は難しい場合もありますが、そのドメインからの電子メールを迷惑メールとして処理したり拒否したりする電子メール フィルターが時間の経過と共に増え続け、適切に配信されるようにするために適切なレコードを設定することになります。</span><span class="sxs-lookup"><span data-stu-id="21a39-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="21a39-193">また、それらを参加させることにより、フィッシング対策を行うことができます。また、メールの送信先の組織や組織内のフィッシング詐欺の可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="21a39-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="21a39-194">インフラストラクチャプ ロバイダー (ISP、ESP、クラウド ホスティング サービス) の情報</span><span class="sxs-lookup"><span data-stu-id="21a39-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="21a39-195">ドメインのメールをホストする場合、またはメールを送信できるホスティング インフラストラクチャを提供する場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21a39-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="21a39-196">顧客が SPF レコードを構成する方法について説明するドキュメントを顧客が持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="21a39-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="21a39-197">顧客が明示的に設定していない場合でも、送信メールの DKIM 署名に署名することを検討します (既定のドメインで署名)。</span><span class="sxs-lookup"><span data-stu-id="21a39-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="21a39-198">DKIM 署名では電子メールに二重署名することもできます (顧客のドメインで設定されている場合に 1 つ目の署名、会社の DKIM 署名で 2 つ目の署名)。</span><span class="sxs-lookup"><span data-stu-id="21a39-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="21a39-199">プラットフォームから送信されたメールを認証していても Microsoft への配信が可能であることが保証されるわけではありませんが、少なくとも、認証されていないという理由で Microsoft がそのメールを迷惑メールとして処理することはなくなります。</span><span class="sxs-lookup"><span data-stu-id="21a39-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="21a39-200">サービス プロバイダーのベスト プラクティスの詳細については、「[M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21a39-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
