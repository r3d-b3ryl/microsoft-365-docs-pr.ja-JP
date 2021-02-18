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
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 管理者は、Exchange Online Protection (EOP) がメール認証 (SPF、DKIM、および DMARC) を使用してスプーフィング、フィッシング、およびスパムを防ぐ方法を確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0fbe8a00b17e871adf65f86a337a0a94493ed
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286515"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="fcac4-103">EOP のメール認証</span><span class="sxs-lookup"><span data-stu-id="fcac4-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fcac4-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fcac4-104">**Applies to**</span></span>
- [<span data-ttu-id="fcac4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fcac4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fcac4-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fcac4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fcac4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcac4-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="fcac4-108">メール認証 (メール検証とも呼ばれます) は、スプーフィング (偽造された差出人からのメール メッセージ) を阻止しようとする標準のグループです。</span><span class="sxs-lookup"><span data-stu-id="fcac4-108">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="fcac4-109">すべての Microsoft 365 組織では、EOP は次の基準を使用して受信メールを検証します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-109">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="fcac4-110">SPF</span><span class="sxs-lookup"><span data-stu-id="fcac4-110">SPF</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [<span data-ttu-id="fcac4-111">DKIM</span><span class="sxs-lookup"><span data-stu-id="fcac4-111">DKIM</span></span>](use-dkim-to-validate-outbound-email.md)

- [<span data-ttu-id="fcac4-112">DMARC</span><span class="sxs-lookup"><span data-stu-id="fcac4-112">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="fcac4-113">メール認証では、差出人 (laura@contoso.com など) からのメール メッセージが正当であり、そのメール ドメイン (contoso.com など) の期待される送信元からのものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-113">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="fcac4-114">この記事の残りの部分では、これらのテクノロジのしくみ、EOP がこれらのテクノロジを使用して受信メールをチェックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-114">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="fcac4-115">メール認証を使用してスプーフィングを防止する</span><span class="sxs-lookup"><span data-stu-id="fcac4-115">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="fcac4-116">DMARC では、メッセージの **差出人** アドレスを調べることでスプーフィングを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-116">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="fcac4-117">**差出人** アドレスは、ユーザーが自分のメール クライアントに表示する送信者のメール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="fcac4-117">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="fcac4-118">また、送信先のメール組織は、メール ドメインが SPF または DKIM をパスしたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-118">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="fcac4-119">つまり、ドメインは認証されており、送信者のメール アドレスはスプーフィングされていません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-119">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="fcac4-120">ただし、SPF、DKIM、および DMARC ("電子メール認証ポリシー" とも呼ばれます) の DNS レコードは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fcac4-120">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="fcac4-121">microsoft.com や skype.com のような強力なメール認証ポリシーを持つドメインは、スプーフィングから保護されます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-121">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="fcac4-122">しかし、メール認証ポリシーが脆弱なドメイン、またはまったくポリシーがないドメインは、スプーフィングの主要な標的となります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-122">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="fcac4-123">2018 年 3 月の時点で、Fortune 500 の企業のうち強力なメール認証ポリシーを公開しているドメインは 9% のみです。</span><span class="sxs-lookup"><span data-stu-id="fcac4-123">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="fcac4-124">残りの 91% の企業は、攻撃者により、スプーフィングされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-124">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="fcac4-125">他のメール フィルタリング メカニズムが組み込まれていない場合、これらのドメインの成りすましの装差出人からのメールがユーザーに配信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-125">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![Fortune 500 企業の DMARC ポリシー](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="fcac4-127">強力なメール認証ポリシーを公開している中小規模企業の割合は、より小さくなります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-127">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="fcac4-128">北米や西ヨーロッパ以外のメールドメインの場合、この数字はさらに小さくなります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-128">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="fcac4-129">強力なメール認証ポリシーがないことは、大きな問題です。</span><span class="sxs-lookup"><span data-stu-id="fcac4-129">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="fcac4-130">組織はメール認証のしくみについて理解していない場合がありますが、攻撃者は完全に理解していて、それを利用します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-130">W while organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="fcac4-131">フィッシングは大きな問題でありながら、強力なメール認証ポリシーの導入は限られているため、Microsoft は受信メールをチェックするために *暗黙的なメール認証* を使用しています。</span><span class="sxs-lookup"><span data-stu-id="fcac4-131">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="fcac4-132">暗黙的なメール認証は、通常のメール認証ポリシーの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="fcac4-132">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="fcac4-133">これらの拡張機能には、送信者評価、送信者の履歴、受信者の履歴、行動分析、他の高度な手法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-133">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="fcac4-134">これらの拡張機能からの他のシグナルが存在しない場合、メール認証ポリシーを使用していないドメインから送信されたメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-134">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="fcac4-135">Microsoft の一般発表については、「[大量のフィッシング詐欺: 第 2 部 - 強化された Microsoft 365 のスプーフィング対策](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcac4-135">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="fcac4-136">複合認証</span><span class="sxs-lookup"><span data-stu-id="fcac4-136">Composite authentication</span></span>

<span data-ttu-id="fcac4-137">ドメインに従来の SPF、DKIM、および DMARC レコードが含まれていない場合、これらのレコード チェックでは、認証状態に関する情報が十分に伝達されません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-137">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="fcac4-138">そのため、Microsoft では、暗黙的なメール認証のアルゴリズムを開発しました。</span><span class="sxs-lookup"><span data-stu-id="fcac4-138">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="fcac4-139">このアルゴリズムは、複数のシグナルを結合して、_複合認証_ (略称: `compauth`) という単一の値にします。</span><span class="sxs-lookup"><span data-stu-id="fcac4-139">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="fcac4-140">この `compauth` の値は、メッセージ ヘッダーの **Authentication-Results** にスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-140">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="fcac4-141">これらの値については、「[Authentication-results メッセージ ヘッダー](anti-spam-message-headers.md#authentication-results-message-header)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="fcac4-141">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="fcac4-142">メッセージ ヘッダーを調べることによって、管理者またはエンド ユーザーは、Microsoft 365 が送信者がなりすましであることを判断する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-142">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="fcac4-143">メール認証がスプーフィングの阻止には不十分なことがある理由</span><span class="sxs-lookup"><span data-stu-id="fcac4-143">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="fcac4-144">受信メッセージがなりすましであるかどうかを判断するためにメール認証のみに依存すると、次の制限が発生します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-144">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="fcac4-145">送信側ドメインに必要な DNS レコードがないか、レコードが正しく構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-145">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="fcac4-146">送信元ドメインに正しく構成された DNS レコードがありますが、そのドメインが差出人アドレスのドメインと一致しません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-146">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="fcac4-147">SPF と DKIM には、差出人アドレスで使用するドメインは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-147">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="fcac4-148">攻撃者や合法的サービスは、ドメインを登録したり、ドメインの SPF および DKIM を構成したり、差出人アドレスに完全に異なるドメインを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-148">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="fcac4-149">このドメインの送信者からのメッセージは、SPF および DKIM にパスします。</span><span class="sxs-lookup"><span data-stu-id="fcac4-149">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="fcac4-150">複合認証は、メール認証チェックに失敗するメッセージをパスさせることで、これらの制限に対処できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-150">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="fcac4-151">簡単にするために、次の例では、メール認証の結果に焦点を置いています。</span><span class="sxs-lookup"><span data-stu-id="fcac4-151">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="fcac4-152">他のバックエンド インテリジェンス要因は、メール認証にパスするメッセージをなりすましとして識別したり、メール認証に失敗したメッセージを正当として識別したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-152">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="fcac4-153">たとえば、fabrikam.com ドメインには、SPF、DKIM、または DMARC レコードがありません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-153">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="fcac4-154">fabrikam.com ドメインの送信者からのメッセージは、複合認証に失敗する可能性があります (`compauth` の値と理由に注意してください)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-154">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="fcac4-155">fabrikam.com で DKIM レコードがない SPF が構成されている場合、メッセージは複合認証をパスできます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-155">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="fcac4-156">SPF チェックをパスしたドメインは、差出人アドレスのドメインに一致します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-156">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="fcac4-157">fabrikam.com で SPF レコードがない DKIM レコードが構成されている場合、メッセージは複合認証をパスできます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-157">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="fcac4-158">DKIM 署名のドメインは、差出人アドレスのドメインに一致します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-158">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="fcac4-159">SPF または DKIM 署名のドメインが差出人アドレスのドメインと一致しない場合、メッセージは複合認証に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-159">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="fcac4-160">認証されていないメールを送信している正当な送信者のためのソリューション</span><span class="sxs-lookup"><span data-stu-id="fcac4-160">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="fcac4-161">Microsoft 365 は、認証されていないメールを組織に送信している送信者を追跡しています。</span><span class="sxs-lookup"><span data-stu-id="fcac4-161">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="fcac4-162">その送信者がサービスによって正当ではないと判断されると、この送信者からのメッセージは複合認証失敗のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-162">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="fcac4-163">この判定を回避するには、このセクションの推奨事項を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-163">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="fcac4-164">所有しているドメインのメール認証を構成する</span><span class="sxs-lookup"><span data-stu-id="fcac4-164">Configure email authentication for domains you own</span></span>

<span data-ttu-id="fcac4-165">この方法は、組織内スプーフィングの解決に使用できます。また、複数のテナントを所有している場合や複数のテナントとやり取りする場合のクロスドメイン スプーフィングの解決にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-165">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="fcac4-166">さらに、Microsoft 365 内の別のユーザー、または別のプロバイダーによりホストされているサード パーティに送信する場合のクロスドメイン スプーフィングを解決する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-166">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="fcac4-167">ドメインの [SPF レコードを構成します](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-167">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="fcac4-168">プライマリ ドメインの [DKIM レコードを構成します](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-168">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="fcac4-169">正当な送信者を判断するために、ドメインに [DMARC レコードを設定することを検討します](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-169">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="fcac4-170">Microsoft は、SPF、DKIM、および DMARC レコードの詳細な実装ガイドラインを提供しません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-170">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="fcac4-171">ただし、オンラインで利用できる大量の情報があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-171">However, there's many information available online.</span></span> <span data-ttu-id="fcac4-172">また、組織がメール認証レコードを設定する際の支援を専門とするサード パーティ企業もあります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-172">There are also third party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="fcac4-173">メールのすべての送信元がわからない</span><span class="sxs-lookup"><span data-stu-id="fcac4-173">You don't know all sources for your email</span></span>

<span data-ttu-id="fcac4-174">多くのドメインは、ドメイン内のメッセージのすべてのメール送信元を認識していないため、SPF レコードを公開しません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-174">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="fcac4-175">自分が知っているすべてのメール送信元を含む SPF レコード (特に会社のトラフィックがある場所にある) を公開することから始めて、次のニュートラル SPF ポリシー (`?all`) を公開します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-175">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="fcac4-176">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-176">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="fcac4-177">この例では、会社のインフラストラクチャからのメールはメール認証にパスしますが、不明な送信元からのメールはニュートラルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-177">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="fcac4-178">Microsoft 365 は、会社のインフラストラクチャからの受信メールを認証済みとして扱います。</span><span class="sxs-lookup"><span data-stu-id="fcac4-178">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="fcac4-179">不明な送信元からのメールは、暗黙的な認証が失敗した場合は、スプーフィングとしてマークされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-179">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="fcac4-180">ただし、これは Microsoft 365 によってすべてのメールにスプーフィングのマークが付けられることからの改善に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="fcac4-180">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="fcac4-181">`?all` の SPF フォールバック ポリシーの使用を開始したら、メッセージのメール送信元を徐々に見つけて含めることができ、より厳しいポリシーを使用して SPF レコードを更新できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-181">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="fcac4-182">スプーフィング インテリジェンスを使用して、認証されていないメールが許可された送信者を構成する</span><span class="sxs-lookup"><span data-stu-id="fcac4-182">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="fcac4-183">認証されていないメッセージを組織に送信する送信者を許可するために、[スプーフィング インテリジェンス](learn-about-spoof-intelligence.md)を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-183">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="fcac4-184">外部ドメインの場合、スプーフィングされたユーザーは差出人アドレスのドメインですが、送信側インフラストラクチャは、送信元 IP アドレス (最大 /24 CIDR 範囲に分割)、または逆引き DNS (PTR) レコードの組織ドメインのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-184">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="fcac4-185">以下のスクリーンショットでは、送信元 IP は PTR レコード outbound.mail.protection.outlook.com を使用して 131.107.18.4 となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-185">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="fcac4-186">これは、送信側インフラストラクチャの outlook.com として表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-186">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="fcac4-187">この送信者に認証されていない電子メールの送信を許可するには、**[いいえ]** を **[はい]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-187">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![スプーフィング対策の許可された送信者の設定](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="fcac4-189">送信者/受信者ペアの許可エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="fcac4-189">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="fcac4-190">スパム フィルタリングをバイパスし、フィッシング フィルタリングの一部をバイパスし、特定の送信者のマルウェア フィルタリングをバイパスしない場合は、「[Microsoft 365 で安全な送信者の一覧を作成する](create-safe-sender-lists-in-office-365.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fcac4-190">To bypass spam filtering, some parts of filtering for phishing, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="fcac4-191">所有していないドメインのメール認証を構成するように送信者に依頼する</span><span class="sxs-lookup"><span data-stu-id="fcac4-191">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="fcac4-192">スパムとフィッシングの問題があるため、Microsoft は、すべてのメール組織にメール認証をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcac4-192">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="fcac4-193">組織の手動オーバーライドを構成する代わりに、送信側ドメインの管理者にメール認証レコードを構成するように依頼できます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-193">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="fcac4-194">過去にメール認証レコードを公開する必要がなかった場合でも、Microsoft にメールを送信する場合は公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-194">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="fcac4-195">SPF を設定してドメインの送信側 IP アドレスを公開します。DKIM (使用可能な場合) を設定してメッセージにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-195">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="fcac4-196">また、DMARC レコードの設定も検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-196">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="fcac4-197">一括送信者を使用してメールを送信する場合は、(アドレスが属する場合) 差出人アドレスのドメインが、SPF または DMARC にパスするドメインに一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-197">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="fcac4-198">次の場所 (使用している場合) が SPF レコードに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-198">Verify the following locations (if they use them) are included in the SPF record:</span></span>

  - <span data-ttu-id="fcac4-199">オンプレミスのメールサーバー。</span><span class="sxs-lookup"><span data-stu-id="fcac4-199">On-premises email servers.</span></span>
  - <span data-ttu-id="fcac4-200">SaaS (サービスとしてのソフトウェア) プロバイダーから送信されたメール。</span><span class="sxs-lookup"><span data-stu-id="fcac4-200">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="fcac4-201">クラウドホスティング サービス (Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services など) から送信されたメール。</span><span class="sxs-lookup"><span data-stu-id="fcac4-201">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="fcac4-202">ISP によってホストされている小規模なドメインについては、ISP の指示に従って SPF レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-202">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="fcac4-203">送信側ドメインで認証することは最初は難しい場合もありますが、そのドメインからの電子メールを迷惑メールとして処理したり拒否したりする電子メール フィルターが時間の経過と共に増え続け、適切に配信されるようにするために適切なレコードを設定することになります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-203">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="fcac4-204">また、それらを参加させることにより、フィッシング対策を行うことができます。また、メールの送信先の組織や組織内のフィッシング詐欺の可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="fcac4-204">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="fcac4-205">インフラストラクチャプ ロバイダー (ISP、ESP、クラウド ホスティング サービス) の情報</span><span class="sxs-lookup"><span data-stu-id="fcac4-205">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="fcac4-206">ドメインのメールをホストする場合、またはメールを送信できるホスティング インフラストラクチャを提供する場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-206">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="fcac4-207">顧客が SPF レコードを構成する方法について説明するドキュメントを顧客が持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="fcac4-207">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="fcac4-208">顧客が明示的に設定していない場合でも、送信メールの DKIM 署名に署名することを検討します (既定のドメインで署名)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-208">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="fcac4-209">DKIM 署名では電子メールに二重署名することもできます (顧客のドメインで設定されている場合に 1 つ目の署名、会社の DKIM 署名で 2 つ目の署名)。</span><span class="sxs-lookup"><span data-stu-id="fcac4-209">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="fcac4-210">プラットフォームから送信されたメールを認証していても Microsoft への配信が可能であることが保証されるわけではありませんが、少なくとも、認証されていないという理由で Microsoft がそのメールを迷惑メールとして処理することはなくなります。</span><span class="sxs-lookup"><span data-stu-id="fcac4-210">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="fcac4-211">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fcac4-211">Related links</span></span>

<span data-ttu-id="fcac4-212">サービス プロバイダーのベスト プラクティスについては、「[サービス プロバイダー向けの M3AAWG モバイル メッセージングのベスト プラクティス](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcac4-212">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="fcac4-213">Office 365 が SPF を使用し、DKIM 検証をサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcac4-213">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="fcac4-214">SPF の詳細</span><span class="sxs-lookup"><span data-stu-id="fcac4-214">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="fcac4-215">DKIM の詳細</span><span class="sxs-lookup"><span data-stu-id="fcac4-215">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
