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
ms.service: O365-seccomp
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
ms.openlocfilehash: 57d6dc8d9c1935578db15abdbb3e17e72bb64257
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130831"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="c20fb-103">EOP のスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="c20fb-103">Anti-spoofing protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c20fb-104">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、なりすましの (偽装) 送信者から組織を保護するための機能が EOP に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="c20fb-105">ユーザーの保護について、Microsoft はフィッシングの脅威を重大視しています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-105">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="c20fb-106">スプーフィングは、攻撃者が一般的に使用する手法です。</span><span class="sxs-lookup"><span data-stu-id="c20fb-106">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="c20fb-107">**スプーフィングされたメッセージは、実際の送信元とは異なるユーザーまたは場所から発信されたように見えます**。</span><span class="sxs-lookup"><span data-stu-id="c20fb-107">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="c20fb-108">この手法は、多くの場合、ユーザーの認証情報を詐取しようとするフィッシング活動で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-108">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="c20fb-109">EOP のスプーフィング対策テクノロジは、メッセージ本文の From ヘッダー (メール クライアントでメッセージ送信者を表示するために使用されます) の偽造を特に調べます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-109">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="c20fb-110">EOP が From へッダーが偽造されていると判断する場合、メッセージはスプーフィングされたものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-110">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="c20fb-111">EOP では、次のスプーフィング対策テクノロジを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-111">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="c20fb-112">**スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="c20fb-112">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="c20fb-113">詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-113">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="c20fb-114">**フィッシング詐欺対策ポリシー**: EOP では、フィッシング詐欺対策ポリシーにより、スプーフィング インテリジェンスを有効または無効にしたり、Outlook の認証されていない送信者識別情報を有効または無効にしたり、スプーフィングされた送信者をブロックするときのアクション ([迷惑メール] フォルダーまたは [検疫] に移動する) を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-114">**Anti-phishing policies**: In EOP, anti-phishing policies allow you to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to the Junk Email folder or quarantine).</span></span> <span data-ttu-id="c20fb-115">Microsoft Defender for Office 365 で使用可能な高度なフィッシング詐欺対策ポリシーには、偽装対策設定 (送信者とドメインの保護)、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-115">Advanced anti-phishing policies that are available in Microsoft Defender for Office 365 also contain anti-impersonation settings (protected senders and domains), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="c20fb-116">詳細については、「[Microsoft 365 でのフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-116">For more information, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="c20fb-117">**メール認証**: スプーフィング対策の不可欠な部分は、DNS のSPF、DKIM、DMARC レコードによるメール認証 (メール検証とも呼ばれます) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="c20fb-117">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="c20fb-118">ドメインのこれらのレコードを構成して、送信先のメール システムがドメインの送信者からのものであると主張するメッセージの有効性をチェックできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-118">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="c20fb-119">受信メッセージの場合、Microsoft 365 では送信者のドメインのメール認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="c20fb-119">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="c20fb-120">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-120">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

<span data-ttu-id="c20fb-121">2018 年 10 月以降、スプーフィング対策保護は EOP で提供されています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-121">As of October 2018, anti-spoofing protection is available in EOP.</span></span>

<span data-ttu-id="c20fb-122">EOP は、標準のメール認証方法と送信者評価手法の組み合わせによって認証されないメッセージを分析してブロックします。</span><span class="sxs-lookup"><span data-stu-id="c20fb-122">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

![EOP のスプーフィング対策チェック](../../media/eop-anti-spoofing-protection.png)

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="c20fb-124">フィッシング攻撃でスプーフィングが使用される方法</span><span class="sxs-lookup"><span data-stu-id="c20fb-124">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="c20fb-125">スプーフィング メッセージは、ユーザーに次のようなの悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="c20fb-125">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="c20fb-126">**ユーザーがスプーフィングされたメッセージにだまされる**: スプーフィングされたメッセージが受信者にリンクをクリックするように誘導し、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりします (ビジネス メール詐欺または BEC と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-126">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="c20fb-127">次のメッセージは、なりすましの送信者 msoutlook94@service.outlook.com を使用するフィッシングの例です。</span><span class="sxs-lookup"><span data-stu-id="c20fb-127">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![service.outlook.com を偽装しているフィッシング メッセージ](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="c20fb-129">このメッセージは service.outlook.com から送信されていまでしたが、攻撃者は **From** ヘッダー フィールドをスプーフィングして、そこから送信されたように見せかけていました。</span><span class="sxs-lookup"><span data-stu-id="c20fb-129">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="c20fb-130">これは、受信者をだまして、**パスワードを変更する** リンクをクリックさせたり、認証情報を提供させたりしようとする試みでした。</span><span class="sxs-lookup"><span data-stu-id="c20fb-130">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="c20fb-131">次のメッセージは、スプーフィングされたメールドメイン contoso.com を使用する BEC の例です。</span><span class="sxs-lookup"><span data-stu-id="c20fb-131">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![フィッシング メッセージ - ビジネス メール詐欺](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="c20fb-133">メッセージは正当なものに見えますが、送信者はスプーフィングされています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-133">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="c20fb-134">**ユーザーが本物と偽物のメッセージを混同する**: フィッシング詐欺を知っているユーザーでも、実際のメッセージとスプーフィングされたメッセージの違いを見分けるのが難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-134">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="c20fb-135">次のメッセージは、Microsoft Security アカウントからの実際のパスワード リセット メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="c20fb-135">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft の正当なパスワード リセット](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="c20fb-137">メッセージは実際には Microsoft から送信されたものですが、ユーザーは疑っています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-137">The message really did come from Microsoft, but users have been conditioned to be suspicious.</span></span> <span data-ttu-id="c20fb-138">本物と偽物のパスワード リセット メッセージを見分けることが難しいため、ユーザーは、メッセージを無視したり、スパムとして報告したり、フィッシング詐欺として Microsoft に不要な報告を返したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-138">Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="c20fb-139">スプーフィングのさまざまな種類</span><span class="sxs-lookup"><span data-stu-id="c20fb-139">Different types of spoofing</span></span>

<span data-ttu-id="c20fb-140">Microsoft では、2 種類のスプーフィングされたメッセージを区別しています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-140">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="c20fb-141">**組織内スプーフィング**: _自己完結型_ スプーフィングとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-141">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="c20fb-142">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-142">For example:</span></span>

  - <span data-ttu-id="c20fb-143">送信者と受信者は同じドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-143">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="c20fb-144">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-144">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="c20fb-145">To: michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-145">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="c20fb-146">送信者と受信者は同じドメインのサブドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-146">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="c20fb-147">From: laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-147">From: laura@marketing.fabrikam.com</span></span> <br/> <span data-ttu-id="c20fb-148">To: julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-148">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="c20fb-149">送信者と受信者は同じ組織に属する異なるドメインに属しています (つまり、両方のドメインが同じ組織内の[承認済みドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)として構成されています)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-149">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="c20fb-150">From: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-150">From: sender @ microsoft.com</span></span> <br/> <span data-ttu-id="c20fb-151">To: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-151">To: recipient @ bing.com</span></span>

    <span data-ttu-id="c20fb-152">スパムボットの収集活動を阻止するために、メールアドレスにスペースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-152">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="c20fb-153">組織内のスプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-153">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="c20fb-154">`reason=6xx` は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-154">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="c20fb-155">SFTY はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="c20fb-155">SFTY is the safety level of the message.</span></span> <span data-ttu-id="c20fb-156">9 はフィッシング詐欺、11 は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-156">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="c20fb-157">**クロスドメイン スプーフィング**: 送信者ドメインと受信者ドメインは異なり、互いに関係がありません (外部ドメインとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-157">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="c20fb-158">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-158">For example:</span></span>
    > <span data-ttu-id="c20fb-159">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-159">From: chris@contoso.com</span></span> <br/> <span data-ttu-id="c20fb-160">To: michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="c20fb-160">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="c20fb-161">クロスドメイン スプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-161">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="c20fb-162">`reason=000` は、メッセージが明示的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-162">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="c20fb-163">`reason=001` は、メッセージが暗黙的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-163">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="c20fb-164">SFTY はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="c20fb-164">SFTY is the safety level of the message.</span></span> <span data-ttu-id="c20fb-165">9 はフィッシング詐欺、22 はクロスドメイン スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-165">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

<span data-ttu-id="c20fb-166">スプーフィングに関連するカテゴリおよび複合認証 (compauth) 値の詳細については、「[Microsoft 365 のスパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-166">For more information about the Category and composite authentication (compauth) values that are related to spoofing, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="c20fb-167">DMARC の詳細については、「[DMARC を使用して Microsoft 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-167">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="c20fb-168">スプーフィングのマークが付けられたメッセージの数量に関するレポート</span><span class="sxs-lookup"><span data-stu-id="c20fb-168">Reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="c20fb-169">EOP 組織は、セキュリティ/コンプライアンス センターのレポート ダッシュボードの **スプーフィング検出** レポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-169">EOP organizations can use the **Spoof detections** report in the Reports dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="c20fb-170">詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-170">For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

<span data-ttu-id="c20fb-171">Microsoft Defender for Office 365 組織は、セキュリティ/コンプライアンス センターで脅威エクスプローラーを使用して、フィッシング詐欺に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-171">Microsoft Defender for Office 365 organization can use Threat Explorer in the Security & Compliance Center to view information about phishing attempts.</span></span> <span data-ttu-id="c20fb-172">詳細については、「[Microsoft 365 脅威の調査と対応](office-365-ti.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-172">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="c20fb-173">スプーフィング対策保護の問題</span><span class="sxs-lookup"><span data-stu-id="c20fb-173">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="c20fb-174">メーリング リスト (ディスカッション リストとも呼ばれます) では、メッセージの転送方法と変更方法が原因で、スプーフィング対策に関する問題があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="c20fb-174">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="c20fb-175">たとえば、Gabriela Laureano (glaureano @ contoso.com) はバード ウォッチングに興味があり、メーリングリスト birdwatchers @ fabrikam.com に参加し、リストに次のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-175">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="c20fb-176">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="c20fb-176">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="c20fb-177">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="c20fb-177">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/> <span data-ttu-id="c20fb-178">**件名:** 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="c20fb-178">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="c20fb-179">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="c20fb-179">Rainier this week</span></span> <p> <span data-ttu-id="c20fb-180">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="c20fb-180">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="c20fb-181">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="c20fb-181">Rainier?</span></span>

<span data-ttu-id="c20fb-182">メーリングリスト サーバーはメッセージを受信し、その内容を変更して、リストのメンバーにリプレイします。</span><span class="sxs-lookup"><span data-stu-id="c20fb-182">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="c20fb-183">リプレイされたメッセージの From アドレス (glaureano @ contoso.com) は同じですが、件名行にタグを追加して、メッセージの下側にフッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-183">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="c20fb-184">この種の変更は、メーリング リストでは一般的なものですが、スプーフィングの誤検出の原因になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-184">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="c20fb-185">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="c20fb-185">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br/> <span data-ttu-id="c20fb-186">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="c20fb-186">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br/> <span data-ttu-id="c20fb-187">**件名:** [BIRDWATCHERS] 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="c20fb-187">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="c20fb-188">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="c20fb-188">Rainier this week</span></span> <p> <span data-ttu-id="c20fb-189">今週、レーニア山からの風景を</span><span class="sxs-lookup"><span data-stu-id="c20fb-189">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="c20fb-190">眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="c20fb-190">Rainier?</span></span> <p> <span data-ttu-id="c20fb-191">このメッセージは、Birdwatchers ディスカッション リストに送信されました。</span><span class="sxs-lookup"><span data-stu-id="c20fb-191">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="c20fb-192">いつでも購読を解除できます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-192">You can unsubscribe at any time.</span></span>

<span data-ttu-id="c20fb-193">メーリング リストのメッセージがスプーフィング対策チェックにパスできるようにするには、メーリングリストを制御するかどうかに応じて、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-193">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="c20fb-194">組織でメーリング リストを所有している場合:</span><span class="sxs-lookup"><span data-stu-id="c20fb-194">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="c20fb-195">DMARC.org で次のよくある質問を確認してください: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-195">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="c20fb-196">次のブログ記事の手順を参照してください: [DMARC との相互運用で失敗を回避するためのメーリング リスト運営者向けのヒント](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-196">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/).</span></span>

  - <span data-ttu-id="c20fb-197">メーリング リスト サーバーに ARC をサポートする更新プログラムをインストールすることを検討してください (<http://arc-spec.org> を参照)。</span><span class="sxs-lookup"><span data-stu-id="c20fb-197">Consider installing updates on your mailing list server to support ARC, see <http://arc-spec.org>.</span></span>

- <span data-ttu-id="c20fb-198">組織でメーリング リストを所有していない場合:</span><span class="sxs-lookup"><span data-stu-id="c20fb-198">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="c20fb-199">メーリング リストの管理者に、メーリング リストがリレーしているドメインのメール認証を構成するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-199">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="c20fb-200">ドメインの所有者に対して相当数の送信者が電子メール認証レコードの設定が必要なことを返信することで、ドメインの所有者の行動を促します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-200">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="c20fb-201">Microsoft は必要なレコードを公開するためにドメインの所有者と協力しますが、個々のユーザーの要求が大きな支援になります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-201">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="c20fb-202">メール クライアントで、メッセージを受信トレイに移動する受信トレイ ルールを作成してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-202">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="c20fb-203">「[スプーフィング インテリジェンスを使用して、認証されていないメールの許可された送信者を構成する](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email)」で説明されているように、管理者にオーバーライドの構成を依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-203">You can also ask your admins to configure overrides as discussed in the [Use spoof intelligence to configure permitted senders of unauthenticated email](email-validation-and-authentication.md#use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email).</span></span>

  - <span data-ttu-id="c20fb-204">Microsoft 365 でサポート チケットを作成して、メーリング リストを正当なものとして扱うためのオーバーライドを作成します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-204">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="c20fb-205">詳細については、「[一般法人向けサポートへのお問い合わせ - 管理者向けヘルプ](../../admin/contact-support-for-business-products.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-205">For more information, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="c20fb-206">他のすべてが失敗した場合は、Microsoft に対してメッセージを誤検知として報告できます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-206">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="c20fb-207">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-207">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="c20fb-208">また、サポート チケットとして Microsoft にこの件を提出できる管理者に問い合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="c20fb-208">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="c20fb-209">Microsoft のエンジニアリング チームは、メッセージにスプーフィングのマークが付けられた理由を調査します。</span><span class="sxs-lookup"><span data-stu-id="c20fb-209">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="c20fb-210">スプーフィング対策保護に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c20fb-210">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="c20fb-211">現在、Microsoft 365 にメッセージを送信している管理者である場合は、メールが正しく認証されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-211">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="c20fb-212">それ以外の場合は、スパムまたはフィッシング詐欺としてマークされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-212">Otherwise, it might be marked as spam or phishing.</span></span> <span data-ttu-id="c20fb-213">詳細については、「[認証されていないメールを送信している正当な送信者のためのソリューション](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-213">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>

<span data-ttu-id="c20fb-214">個人ユーザー (または管理者) の [信頼できる差出人のリスト] に含まれる送信者は、スプーフィング保護を含む、フィルター処理スタックの一部をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="c20fb-214">Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection.</span></span> <span data-ttu-id="c20fb-215">詳細については、「[Outlook の信頼できる差出人](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-215">For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).</span></span>

<span data-ttu-id="c20fb-216">管理者は、可能な場合、許可された送信者リストまたは許可されたドメイン リストを使用して回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c20fb-216">Admins should avoid (when possible) using allowed sender lists or allowed domain lists.</span></span> <span data-ttu-id="c20fb-217">これらの送信者は、迷惑メール、スプーフィング、およびフィッシング詐欺保護をすべてバイパスします。また、送信者認証 (SPF、DKIM、DMARC) も使用できません。</span><span class="sxs-lookup"><span data-stu-id="c20fb-217">These senders bypass all spam, spoofing, and phishing protection, and also sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="c20fb-218">詳細については、「[許可された送信者リストまたは許可されたドメイン リストを使用する](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c20fb-218">For more information, see [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).</span></span>
