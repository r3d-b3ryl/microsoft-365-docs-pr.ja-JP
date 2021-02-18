---
title: スプーフィング対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: 管理者は、Exchange Online Protection (EOP) で利用できるスプーフィング対策機能について学ぶことができます。この機能を使用すると、なりすましの送信者とドメインからのフィッシング攻撃を軽減できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b20ae766ee308e9c59ed0d495df7c5a97c79b00
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287067"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="26c31-103">EOP のスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="26c31-103">Anti-spoofing protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="26c31-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="26c31-104">**Applies to**</span></span>
- [<span data-ttu-id="26c31-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="26c31-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="26c31-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="26c31-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="26c31-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26c31-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="26c31-108">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、なりすましの (偽装) 送信者から組織を保護するための機能が EOP に含まれています。</span><span class="sxs-lookup"><span data-stu-id="26c31-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="26c31-109">ユーザーの保護について、Microsoft はフィッシングの脅威を重大視しています。</span><span class="sxs-lookup"><span data-stu-id="26c31-109">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="26c31-110">スプーフィングは、攻撃者が一般的に使用する手法です。</span><span class="sxs-lookup"><span data-stu-id="26c31-110">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="26c31-111">**スプーフィングされたメッセージは、実際の送信元とは異なるユーザーまたは場所から発信されたように見えます**。</span><span class="sxs-lookup"><span data-stu-id="26c31-111">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="26c31-112">この手法は、多くの場合、ユーザーの認証情報を詐取しようとするフィッシング活動で使用されます。</span><span class="sxs-lookup"><span data-stu-id="26c31-112">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="26c31-113">EOP のスプーフィング対策テクノロジは、メッセージ本文の From ヘッダー (メール クライアントでメッセージ送信者を表示するために使用されます) の偽造を特に調べます。</span><span class="sxs-lookup"><span data-stu-id="26c31-113">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="26c31-114">EOP が From へッダーが偽造されていると判断する場合、メッセージはスプーフィングされたものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="26c31-114">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="26c31-115">EOP では、次のスプーフィング対策テクノロジを使用できます。</span><span class="sxs-lookup"><span data-stu-id="26c31-115">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="26c31-116">**スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="26c31-116">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="26c31-117">詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-117">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="26c31-118">**フィッシング詐欺対策ポリシー**: EOP では、フィッシング詐欺対策ポリシーにより、スプーフィング インテリジェンスを有効または無効にしたり、Outlook の認証されていない送信者識別情報を有効または無効にしたり、スプーフィングされた送信者をブロックするときのアクション ([迷惑メール] フォルダーまたは [検疫] に移動する) を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="26c31-118">**Anti-phishing policies**: In EOP, anti-phishing policies allow you to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to the Junk Email folder or quarantine).</span></span> <span data-ttu-id="26c31-119">Microsoft Defender for Office 365 で使用可能な高度なフィッシング詐欺対策ポリシーには、偽装対策設定 (送信者とドメインの保護)、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値も含まれています。</span><span class="sxs-lookup"><span data-stu-id="26c31-119">Advanced anti-phishing policies that are available in Microsoft Defender for Office 365 also contain anti-impersonation settings (protected senders and domains), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="26c31-120">詳細については、「[Microsoft 365 でのフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-120">For more information, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="26c31-121">**メール認証**: スプーフィング対策の不可欠な部分は、DNS のSPF、DKIM、DMARC レコードによるメール認証 (メール検証とも呼ばれます) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="26c31-121">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="26c31-122">ドメインのこれらのレコードを構成して、送信先のメール システムがドメインの送信者からのものであると主張するメッセージの有効性をチェックできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="26c31-122">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="26c31-123">受信メッセージの場合、Microsoft 365 では送信者のドメインのメール認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="26c31-123">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="26c31-124">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26c31-124">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

<span data-ttu-id="26c31-125">2018 年 10 月以降、スプーフィング対策保護は EOP で提供されています。</span><span class="sxs-lookup"><span data-stu-id="26c31-125">As of October 2018, anti-spoofing protection is available in EOP.</span></span>

<span data-ttu-id="26c31-126">EOP は、標準のメール認証方法と送信者評価手法の組み合わせによって認証されないメッセージを分析してブロックします。</span><span class="sxs-lookup"><span data-stu-id="26c31-126">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

![EOP のスプーフィング対策チェック](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="26c31-128">フィッシング攻撃でスプーフィングが使用される方法</span><span class="sxs-lookup"><span data-stu-id="26c31-128">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="26c31-129">スプーフィング メッセージは、ユーザーに次のようなの悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="26c31-129">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="26c31-130">**ユーザーがスプーフィングされたメッセージにだまされる**: スプーフィングされたメッセージが受信者にリンクをクリックするように誘導し、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりします (ビジネス メール詐欺または BEC と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="26c31-130">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="26c31-131">次のメッセージは、なりすましの送信者 msoutlook94@service.outlook.com を使用するフィッシングの例です。</span><span class="sxs-lookup"><span data-stu-id="26c31-131">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![service.outlook.com を偽装しているフィッシング メッセージ](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="26c31-133">このメッセージは service.outlook.com から送信されていまでしたが、攻撃者は **From** ヘッダー フィールドをスプーフィングして、そこから送信されたように見せかけていました。</span><span class="sxs-lookup"><span data-stu-id="26c31-133">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="26c31-134">これは、受信者をだまして、**パスワードを変更する** リンクをクリックさせたり、認証情報を提供させたりしようとする試みでした。</span><span class="sxs-lookup"><span data-stu-id="26c31-134">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="26c31-135">次のメッセージは、スプーフィングされたメールドメイン contoso.com を使用する BEC の例です。</span><span class="sxs-lookup"><span data-stu-id="26c31-135">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![フィッシング メッセージ - ビジネス メール詐欺](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="26c31-137">メッセージは正当なものに見えますが、送信者はスプーフィングされています。</span><span class="sxs-lookup"><span data-stu-id="26c31-137">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="26c31-138">**ユーザーが本物と偽物のメッセージを混同する**: フィッシング詐欺を知っているユーザーでも、実際のメッセージとスプーフィングされたメッセージの違いを見分けるのが難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-138">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="26c31-139">次のメッセージは、Microsoft Security アカウントからの実際のパスワード リセット メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="26c31-139">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft の正当なパスワード リセット](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="26c31-141">メッセージは実際には Microsoft から送信されたものですが、ユーザーは疑っています。</span><span class="sxs-lookup"><span data-stu-id="26c31-141">The message really did come from Microsoft, but users have been conditioned to be suspicious.</span></span> <span data-ttu-id="26c31-142">本物と偽物のパスワード リセット メッセージを見分けることが難しいため、ユーザーは、メッセージを無視したり、スパムとして報告したり、フィッシング詐欺として Microsoft に不要な報告を返したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="26c31-142">Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="26c31-143">スプーフィングのさまざまな種類</span><span class="sxs-lookup"><span data-stu-id="26c31-143">Different types of spoofing</span></span>

<span data-ttu-id="26c31-144">Microsoft では、2 種類のスプーフィングされたメッセージを区別しています。</span><span class="sxs-lookup"><span data-stu-id="26c31-144">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="26c31-145">**組織内スプーフィング**: _自己完結型_ スプーフィングとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="26c31-145">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="26c31-146">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-146">For example:</span></span>

  - <span data-ttu-id="26c31-147">送信者と受信者は同じドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="26c31-147">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="26c31-148">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="26c31-148">From: chris@contoso.com</span></span> <br> <span data-ttu-id="26c31-149">To: michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="26c31-149">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="26c31-150">送信者と受信者は同じドメインのサブドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="26c31-150">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="26c31-151">From: laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="26c31-151">From: laura@marketing.fabrikam.com</span></span> <br> <span data-ttu-id="26c31-152">To: julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="26c31-152">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="26c31-153">送信者と受信者は同じ組織に属する異なるドメインに属しています (つまり、両方のドメインが同じ組織内の[承認済みドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)として構成されています)。</span><span class="sxs-lookup"><span data-stu-id="26c31-153">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="26c31-154">From: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="26c31-154">From: sender @ microsoft.com</span></span> <br> <span data-ttu-id="26c31-155">To: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="26c31-155">To: recipient @ bing.com</span></span>

    <span data-ttu-id="26c31-156">スパムボットの収集活動を阻止するために、メールアドレスにスペースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="26c31-156">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="26c31-157">組織内のスプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="26c31-157">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="26c31-158">`reason=6xx` は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-158">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="26c31-159">SFTY はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="26c31-159">SFTY is the safety level of the message.</span></span> <span data-ttu-id="26c31-160">9 はフィッシング詐欺、11 は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-160">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="26c31-161">**クロスドメイン スプーフィング**: 送信者ドメインと受信者ドメインは異なり、互いに関係がありません (外部ドメインとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="26c31-161">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="26c31-162">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-162">For example:</span></span>
    > <span data-ttu-id="26c31-163">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="26c31-163">From: chris@contoso.com</span></span> <br> <span data-ttu-id="26c31-164">To: michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="26c31-164">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="26c31-165">クロスドメイン スプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="26c31-165">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="26c31-166">`reason=000` は、メッセージが明示的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-166">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="26c31-167">`reason=001` は、メッセージが暗黙的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-167">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="26c31-168">SFTY はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="26c31-168">SFTY is the safety level of the message.</span></span> <span data-ttu-id="26c31-169">9 はフィッシング詐欺、22 はクロスドメイン スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="26c31-169">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

<span data-ttu-id="26c31-170">スプーフィングに関連するカテゴリおよび複合認証 (compauth) 値の詳細については、「[Microsoft 365 のスパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26c31-170">For more information about the Category and composite authentication (compauth) values that are related to spoofing, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="26c31-171">DMARC の詳細については、「[DMARC を使用して Microsoft 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-171">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="26c31-172">スプーフィングのマークが付けられたメッセージの数量に関するレポート</span><span class="sxs-lookup"><span data-stu-id="26c31-172">Reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="26c31-173">EOP 組織は、セキュリティ/コンプライアンス センターのレポート ダッシュボードの **スプーフィング検出** レポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="26c31-173">EOP organizations can use the **Spoof detections** report in the Reports dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="26c31-174">詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-174">For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

<span data-ttu-id="26c31-175">Microsoft Defender for Office 365 組織は、セキュリティ/コンプライアンス センターで脅威エクスプローラーを使用して、フィッシング詐欺に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="26c31-175">Microsoft Defender for Office 365 organization can use Threat Explorer in the Security & Compliance Center to view information about phishing attempts.</span></span> <span data-ttu-id="26c31-176">詳細については、「[Microsoft 365 脅威の調査および対応](office-365-ti.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26c31-176">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="26c31-177">スプーフィング対策保護の問題</span><span class="sxs-lookup"><span data-stu-id="26c31-177">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="26c31-178">メーリング リスト (ディスカッション リストとも呼ばれます) では、メッセージの転送方法と変更方法が原因で、スプーフィング対策に関する問題があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="26c31-178">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="26c31-179">たとえば、Gabriela Laureano (glaureano @ contoso.com) はバード ウォッチングに興味があり、メーリングリスト birdwatchers @ fabrikam.com に参加し、リストに次のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="26c31-179">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="26c31-180">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="26c31-180">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="26c31-181">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="26c31-181">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="26c31-182">**件名:** 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="26c31-182">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="26c31-183">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="26c31-183">Rainier this week</span></span> <p> <span data-ttu-id="26c31-184">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="26c31-184">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="26c31-185">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="26c31-185">Rainier?</span></span>

<span data-ttu-id="26c31-186">メーリングリスト サーバーはメッセージを受信し、その内容を変更して、リストのメンバーにリプレイします。</span><span class="sxs-lookup"><span data-stu-id="26c31-186">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="26c31-187">リプレイされたメッセージの From アドレス (glaureano @ contoso.com) は同じですが、件名行にタグを追加して、メッセージの下側にフッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="26c31-187">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="26c31-188">この種の変更は、メーリング リストでは一般的なものですが、スプーフィングの誤検出の原因になることがあります。</span><span class="sxs-lookup"><span data-stu-id="26c31-188">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="26c31-189">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="26c31-189">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="26c31-190">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="26c31-190">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="26c31-191">**件名:** [BIRDWATCHERS] 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="26c31-191">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="26c31-192">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="26c31-192">Rainier this week</span></span> <p> <span data-ttu-id="26c31-193">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="26c31-193">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="26c31-194">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="26c31-194">Rainier?</span></span> <p> <span data-ttu-id="26c31-195">このメッセージは、Birdwatchers ディスカッション リストに送信されました。</span><span class="sxs-lookup"><span data-stu-id="26c31-195">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="26c31-196">いつでも購読を解除できます。</span><span class="sxs-lookup"><span data-stu-id="26c31-196">You can unsubscribe at any time.</span></span>

<span data-ttu-id="26c31-197">メーリング リストのメッセージがスプーフィング対策チェックにパスできるようにするには、メーリングリストを制御するかどうかに応じて、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="26c31-197">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="26c31-198">組織でメーリング リストを所有している場合:</span><span class="sxs-lookup"><span data-stu-id="26c31-198">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="26c31-199">DMARC.org で次のよくある質問を確認してください: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)。</span><span class="sxs-lookup"><span data-stu-id="26c31-199">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="26c31-200">次のブログ記事の手順を参照してください: [DMARC との相互運用で失敗を回避するためのメーリング リスト運営者向けのヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)。</span><span class="sxs-lookup"><span data-stu-id="26c31-200">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).</span></span>

  - <span data-ttu-id="26c31-201">メーリング リスト サーバーに ARC をサポートする更新プログラムをインストールすることを検討してください (<http://arc-spec.org> を参照)。</span><span class="sxs-lookup"><span data-stu-id="26c31-201">Consider installing updates on your mailing list server to support ARC, see <http://arc-spec.org>.</span></span>

- <span data-ttu-id="26c31-202">組織でメーリング リストを所有していない場合:</span><span class="sxs-lookup"><span data-stu-id="26c31-202">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="26c31-203">メーリング リストの管理者に、メーリング リストがリレーしているドメインのメール認証を構成するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="26c31-203">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="26c31-204">ドメインの所有者に対して相当数の送信者が電子メール認証レコードの設定が必要なことを返信することで、ドメインの所有者の行動を促します。</span><span class="sxs-lookup"><span data-stu-id="26c31-204">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="26c31-205">Microsoft は必要なレコードを公開するためにドメインの所有者と協力しますが、個々のユーザーの要求が大きな支援になります。</span><span class="sxs-lookup"><span data-stu-id="26c31-205">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="26c31-206">メール クライアントで、メッセージを受信トレイに移動する受信トレイ ルールを作成してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-206">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="26c31-207">「[スプーフィング インテリジェンスを使用して、認証されていないメールの許可された送信者を構成する](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email)」で説明されているように、管理者にオーバーライドの構成を依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="26c31-207">You can also ask your admins to configure overrides as discussed in the [Use spoof intelligence to configure permitted senders of unauthenticated email](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email).</span></span>

  - <span data-ttu-id="26c31-208">Microsoft 365 でサポート チケットを作成して、メーリング リストを正当なものとして扱うためのオーバーライドを作成します。</span><span class="sxs-lookup"><span data-stu-id="26c31-208">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="26c31-209">詳細については、「[一般法人向けサポートへのお問い合わせ - 管理者向けヘルプ](../../admin/contact-support-for-business-products.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-209">For more information, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="26c31-210">他のすべてが失敗した場合は、Microsoft に対してメッセージを誤検知として報告できます。</span><span class="sxs-lookup"><span data-stu-id="26c31-210">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="26c31-211">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-211">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="26c31-212">また、サポート チケットとして Microsoft にこの件を提出できる管理者に問い合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="26c31-212">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="26c31-213">Microsoft のエンジニアリング チームは、メッセージにスプーフィングのマークが付けられた理由を調査します。</span><span class="sxs-lookup"><span data-stu-id="26c31-213">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="26c31-214">スプーフィング対策保護に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="26c31-214">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="26c31-215">現在、Microsoft 365 にメッセージを送信している管理者である場合は、メールが正しく認証されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-215">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="26c31-216">それ以外の場合は、スパムまたはフィッシング詐欺としてマークされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-216">Otherwise, it might be marked as spam or phishing.</span></span> <span data-ttu-id="26c31-217">詳細については、「[認証されていないメールを送信している正当な送信者のためのソリューション](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26c31-217">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>

<span data-ttu-id="26c31-218">個人ユーザー (または管理者) の [信頼できる差出人のリスト] に含まれる送信者は、スプーフィング保護を含む、フィルター処理スタックの一部をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="26c31-218">Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection.</span></span> <span data-ttu-id="26c31-219">詳細については、「[Outlook の信頼できる差出人](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-219">For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).</span></span>

<span data-ttu-id="26c31-220">管理者は、可能な場合、許可された送信者リストまたは許可されたドメイン リストを使用して回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26c31-220">Admins should avoid (when possible) using allowed sender lists or allowed domain lists.</span></span> <span data-ttu-id="26c31-221">これらの送信者は、迷惑メール、スプーフィング、およびフィッシング詐欺保護をすべてバイパスします。また、送信者認証 (SPF、DKIM、DMARC) も使用できません。</span><span class="sxs-lookup"><span data-stu-id="26c31-221">These senders bypass all spam, spoofing, and phishing protection, and also sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="26c31-222">詳細については、「[許可された送信者リストまたは許可されたドメイン リストを使用する](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26c31-222">For more information, see [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).</span></span>
