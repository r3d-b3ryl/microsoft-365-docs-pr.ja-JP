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
ms.openlocfilehash: 7680c2f4eae54aa53eba72b328baf1bf92fbcf98
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537969"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="f046c-103">EOP のスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="f046c-103">Anti-spoofing protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f046c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f046c-104">**Applies to**</span></span>
- [<span data-ttu-id="f046c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f046c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f046c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f046c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f046c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f046c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f046c-108">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、なりすましの (偽装) 送信者から組織を保護するための機能が EOP に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f046c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="f046c-109">ユーザーの保護について、Microsoft はフィッシングの脅威を重大視しています。</span><span class="sxs-lookup"><span data-stu-id="f046c-109">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="f046c-110">スプーフィングは、攻撃者が一般的に使用する手法です。</span><span class="sxs-lookup"><span data-stu-id="f046c-110">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="f046c-111">**スプーフィングされたメッセージは、実際の送信元とは異なるユーザーまたは場所から発信されたように見えます**。</span><span class="sxs-lookup"><span data-stu-id="f046c-111">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="f046c-112">この手法は、多くの場合、ユーザーの認証情報を詐取しようとするフィッシング活動で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f046c-112">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="f046c-113">EOP のスプーフィング対策テクノロジは、メッセージ本文の From ヘッダー (メール クライアントでメッセージ送信者を表示するために使用されます) の偽造を特に調べます。</span><span class="sxs-lookup"><span data-stu-id="f046c-113">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="f046c-114">EOP が From へッダーが偽造されていると判断する場合、メッセージはスプーフィングされたものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="f046c-114">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="f046c-115">EOP では、次のスプーフィング対策テクノロジを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f046c-115">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="f046c-116">**メール認証**: スプーフィング対策の不可欠な部分は、DNS のSPF、DKIM、DMARC レコードによるメール認証 (メール検証とも呼ばれます) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="f046c-116">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="f046c-117">ドメインのこれらのレコードを構成して、送信先のメール システムがドメインの送信者からのものであると主張するメッセージの有効性をチェックできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f046c-117">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="f046c-118">受信メッセージの場合、Microsoft 365 では送信者のドメインのメール認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="f046c-118">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="f046c-119">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f046c-119">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

  <span data-ttu-id="f046c-120">EOP は、標準のメール認証方法と送信者評価手法の組み合わせによって認証されないメッセージを分析してブロックします。</span><span class="sxs-lookup"><span data-stu-id="f046c-120">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

  ![EOP のスプーフィング対策チェック](../../media/eop-anti-spoofing-protection.png)

- <span data-ttu-id="f046c-122">**スプーフィング インテリジェンス分析**: 7 日間で内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="f046c-122">**Spoof intelligence insight**: Review spoofed messages from senders in internal and external domains during the last 7 days, and allow or block those senders.</span></span> <span data-ttu-id="f046c-123">詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-123">For more information, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="f046c-124">**テナント許可/ブロック リストでなりすましされた送信者を許可またはブロックする**: スプーフィング インテリジェンス分析の判定を上書きすると、なりすましされた送信者は、手動で許可またはブロックするエントリとなり、「テナント許可/ブロックリスト」の **[なりすまし]** タブにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f046c-124">**Allow or block spoofed senders in the Tenant Allow/Block List**: When you override the verdict in the spoof intelligence insight, the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="f046c-125">また、スプーフィング インテリジェンスで検出される前に、手動でなりすまし送信者の許可またはブロック エントリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f046c-125">You can also manually create allow or block entries for spoof senders before they're detected by spoof intelligence.</span></span> <span data-ttu-id="f046c-126">詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-126">For more information, see [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="f046c-127">**フィッシング詐欺対策ポリシー**: EOP では、フィッシング詐欺対策ポリシーに以下のなりすまし対策の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f046c-127">**Anti-phishing policies**: In EOP, anti-phishing policies contain the following anti-spoofing settings:</span></span>
  - <span data-ttu-id="f046c-128">スプーフィング インテリジェンスのオン/オフを切り替える。</span><span class="sxs-lookup"><span data-stu-id="f046c-128">Turn spoof intelligence on or off.</span></span>
  - <span data-ttu-id="f046c-129">Outlook の認証されていない送信者の特定をオンまたはオフにする。</span><span class="sxs-lookup"><span data-stu-id="f046c-129">Turn unauthenticated sender identification in Outlook on or off.</span></span>
  - <span data-ttu-id="f046c-130">なりすまし送信者をブロックするアクションを指定する。</span><span class="sxs-lookup"><span data-stu-id="f046c-130">Specify the action for blocked spoofed senders.</span></span>

  <span data-ttu-id="f046c-131">詳細については、「[フィッシング詐欺対策ポリシーでのなりすまし設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-131">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

  <span data-ttu-id="f046c-132">**注**: Microsoft Defender for Office 365 のフィッシング対策ポリシーには、**なりすまし** 保護などの保護機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f046c-132">**Note**: Anti-phishing policies in Microsoft Defender for Office 365 contain addition protections, including **impersonation** protection.</span></span> <span data-ttu-id="f046c-133">詳細については、「[Microsoft Defender for Office 365 のフィッシング対策ポリシーにおける排他的な設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-133">For more information, see [Exclusive settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="f046c-134">**スプーフィング検出レポート**: 詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-134">**Spoof detections report**: For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

  <span data-ttu-id="f046c-135">**注**: Microsoft Defender for Office 365 の組織は、「リアルタイム検出」(プラン 1) または「Threat Explorer」(プラン 2) を使用して、フィッシングの試行に関する情報を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f046c-135">**Note**: Defender for Office 365 organizations can also use Real-time detections (Plan 1) or Threat Explorer (Plan 2) to view information about phishing attempts.</span></span> <span data-ttu-id="f046c-136">詳細については、「[Microsoft 365 脅威の調査と対応](office-365-ti.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f046c-136">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="f046c-137">フィッシング攻撃でスプーフィングが使用される方法</span><span class="sxs-lookup"><span data-stu-id="f046c-137">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="f046c-138">スプーフィング メッセージは、ユーザーに次のようなの悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="f046c-138">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="f046c-139">**ユーザーがスプーフィングされたメッセージにだまされる**: スプーフィングされたメッセージが受信者にリンクをクリックするように誘導し、認証情報を提出させたり、マルウェアをダウンロードさせたり、機密コンテンツを含めてメッセージに返信させたりします (ビジネス メール詐欺または BEC と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="f046c-139">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="f046c-140">次のメッセージは、なりすましの送信者 msoutlook94@service.outlook.com を使用するフィッシングの例です。</span><span class="sxs-lookup"><span data-stu-id="f046c-140">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![service.outlook.com を偽装しているフィッシング メッセージ](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="f046c-142">このメッセージは service.outlook.com から送信されていまでしたが、攻撃者は **From** ヘッダー フィールドをスプーフィングして、そこから送信されたように見せかけていました。</span><span class="sxs-lookup"><span data-stu-id="f046c-142">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="f046c-143">これは、受信者をだまして、**パスワードを変更する** リンクをクリックさせたり、認証情報を提供させたりしようとする試みでした。</span><span class="sxs-lookup"><span data-stu-id="f046c-143">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="f046c-144">次のメッセージは、スプーフィングされたメールドメイン contoso.com を使用する BEC の例です。</span><span class="sxs-lookup"><span data-stu-id="f046c-144">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![フィッシング メッセージ - ビジネス メール詐欺](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="f046c-146">メッセージは正当なものに見えますが、送信者はスプーフィングされています。</span><span class="sxs-lookup"><span data-stu-id="f046c-146">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="f046c-147">**ユーザーが本物と偽物のメッセージを混同する**: フィッシング詐欺を知っているユーザーでも、実際のメッセージとスプーフィングされたメッセージの違いを見分けるのが難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f046c-147">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="f046c-148">次のメッセージは、Microsoft Security アカウントからの実際のパスワード リセット メッセージの例です。</span><span class="sxs-lookup"><span data-stu-id="f046c-148">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft の正当なパスワード リセット](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="f046c-p108">このメッセージは Microsoft から本当に送信されたものですが、ユーザーには疑う習慣がついています。本物と偽物のパスワード リセット メッセージを見分けることが難しいため、ユーザーは、メッセージを無視したり、スパムとして報告したり、フィッシング詐欺として Microsoft に不要な報告を返したりしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f046c-p108">The message really did come from Microsoft, but users have been conditioned to be suspicious. Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="f046c-152">スプーフィングのさまざまな種類</span><span class="sxs-lookup"><span data-stu-id="f046c-152">Different types of spoofing</span></span>

<span data-ttu-id="f046c-153">Microsoft では、2 種類のスプーフィングされたメッセージを区別しています。</span><span class="sxs-lookup"><span data-stu-id="f046c-153">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="f046c-154">**組織内スプーフィング**: _自己完結型_ スプーフィングとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f046c-154">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="f046c-155">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-155">For example:</span></span>

  - <span data-ttu-id="f046c-156">送信者と受信者は同じドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="f046c-156">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="f046c-157">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f046c-157">From: chris@contoso.com</span></span> <br> <span data-ttu-id="f046c-158">To: michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f046c-158">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="f046c-159">送信者と受信者は同じドメインのサブドメインにあります。</span><span class="sxs-lookup"><span data-stu-id="f046c-159">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="f046c-160">From: laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f046c-160">From: laura@marketing.fabrikam.com</span></span> <br> <span data-ttu-id="f046c-161">To: julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f046c-161">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="f046c-162">送信者と受信者は同じ組織に属する異なるドメインに属しています (つまり、両方のドメインが同じ組織内の[承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)として構成されています)。</span><span class="sxs-lookup"><span data-stu-id="f046c-162">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="f046c-163">From: sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f046c-163">From: sender @ microsoft.com</span></span> <br> <span data-ttu-id="f046c-164">To: recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="f046c-164">To: recipient @ bing.com</span></span>

    <span data-ttu-id="f046c-165">スパムボットの収集活動を阻止するために、メールアドレスにスペースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f046c-165">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="f046c-166">組織内のスプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f046c-166">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="f046c-167">`reason=6xx` は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-167">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="f046c-168">SFTY はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="f046c-168">SFTY is the safety level of the message.</span></span> <span data-ttu-id="f046c-169">9 はフィッシング詐欺、11 は組織内スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-169">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="f046c-170">**クロスドメイン スプーフィング**: 送信者ドメインと受信者ドメインは異なり、互いに関係がありません (外部ドメインとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="f046c-170">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="f046c-171">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-171">For example:</span></span>
    > <span data-ttu-id="f046c-172">From: chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f046c-172">From: chris@contoso.com</span></span> <br> <span data-ttu-id="f046c-173">To: michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="f046c-173">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="f046c-174">クロスドメイン スプーフィングのために[複合認証](email-validation-and-authentication.md#composite-authentication)に失敗したメッセージには、次のヘッダー値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f046c-174">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="f046c-175">`reason=000` は、メッセージが明示的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-175">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="f046c-176">`reason=001` は、メッセージが暗黙的なメール認証に失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-176">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="f046c-177">`SFTY` はメッセージの安全レベルです。</span><span class="sxs-lookup"><span data-stu-id="f046c-177">`SFTY` is the safety level of the message.</span></span> <span data-ttu-id="f046c-178">9 はフィッシング詐欺、22 はクロスドメイン スプーフィングを示します。</span><span class="sxs-lookup"><span data-stu-id="f046c-178">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

> [!NOTE]
> <span data-ttu-id="f046c-179">\***compauth=fail reason=###** _ のようなメッセージが表示され、複合認証 (compauth) とスプーフィングに関する値について知る必要がある場合、[_Microsoft 365 のスパム対策メッセージ ヘッダー\*](anti-spam-message-headers.md) をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f046c-179">If you've gotten a message like \***compauth=fail reason=###** _ and need to know about composite authentication (compauth), and the values related to spoofing, see [_Anti-spam message headers in Microsoft 365\*](anti-spam-message-headers.md).</span></span> <span data-ttu-id="f046c-180">または、 [*reason*](anti-spam-message-headers.md) コードに直接移動します。</span><span class="sxs-lookup"><span data-stu-id="f046c-180">Or go directly to the [*reason*](anti-spam-message-headers.md) codes.</span></span>

<span data-ttu-id="f046c-181">DMARC の詳細については、「[DMARC を使用して Microsoft 365 でメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-181">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="f046c-182">スプーフィング対策保護の問題</span><span class="sxs-lookup"><span data-stu-id="f046c-182">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="f046c-183">メーリング リスト (ディスカッション リストとも呼ばれます) では、メッセージの転送方法と変更方法が原因で、スプーフィング対策に関する問題があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="f046c-183">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="f046c-184">たとえば、Gabriela Laureano (glaureano @ contoso.com) はバード ウォッチングに興味があり、メーリングリスト birdwatchers @ fabrikam.com に参加し、リストに次のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f046c-184">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="f046c-185">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="f046c-185">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="f046c-186">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="f046c-186">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="f046c-187">**件名:** 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="f046c-187">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="f046c-188">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="f046c-188">Rainier this week</span></span> <p> <span data-ttu-id="f046c-p116">今週のレーニア山からの風景を眺めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="f046c-p116">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>

<span data-ttu-id="f046c-191">メーリングリスト サーバーはメッセージを受信し、その内容を変更して、リストのメンバーにリプレイします。</span><span class="sxs-lookup"><span data-stu-id="f046c-191">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="f046c-192">リプレイされたメッセージの From アドレス (glaureano @ contoso.com) は同じですが、件名行にタグを追加して、メッセージの下側にフッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="f046c-192">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="f046c-193">この種の変更は、メーリング リストでは一般的なものですが、スプーフィングの誤検出の原因になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f046c-193">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="f046c-194">**差出人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="f046c-194">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="f046c-195">**宛先:** Birdwatcher のディスカッション リスト\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="f046c-195">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="f046c-196">**件名:** [BIRDWATCHERS] 今週、レーニア山からアオカケス</span><span class="sxs-lookup"><span data-stu-id="f046c-196">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="f046c-197">を見ることができます</span><span class="sxs-lookup"><span data-stu-id="f046c-197">Rainier this week</span></span> <p> <span data-ttu-id="f046c-p119">今週のレーニア山からの風景を眺めてみませんか? </span><span class="sxs-lookup"><span data-stu-id="f046c-p119">Anyone want to check out the viewing this week from Mt. Rainier? </span></span><p> <span data-ttu-id="f046c-200">このメッセージは、Birdwatchers ディスカッション リストに送信されました。</span><span class="sxs-lookup"><span data-stu-id="f046c-200">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="f046c-201">いつでも購読を解除できます。</span><span class="sxs-lookup"><span data-stu-id="f046c-201">You can unsubscribe at any time.</span></span>

<span data-ttu-id="f046c-202">メーリング リストのメッセージがスプーフィング対策チェックにパスできるようにするには、メーリングリストを制御するかどうかに応じて、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f046c-202">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="f046c-203">組織でメーリング リストを所有している場合:</span><span class="sxs-lookup"><span data-stu-id="f046c-203">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="f046c-204">DMARC.org で次のよくある質問を確認してください: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)。</span><span class="sxs-lookup"><span data-stu-id="f046c-204">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="f046c-205">次のブログ記事の手順を参照してください: [DMARC との相互運用で失敗を回避するためのメーリング リスト運営者向けのヒント](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures)。</span><span class="sxs-lookup"><span data-stu-id="f046c-205">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures).</span></span>

  - <span data-ttu-id="f046c-206">メーリング リスト サーバーに ARC をサポートする更新プログラムをインストールすることを検討してください (<http://arc-spec.org> を参照)。</span><span class="sxs-lookup"><span data-stu-id="f046c-206">Consider installing updates on your mailing list server to support ARC, see <http://arc-spec.org>.</span></span>

- <span data-ttu-id="f046c-207">組織でメーリング リストを所有していない場合:</span><span class="sxs-lookup"><span data-stu-id="f046c-207">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="f046c-208">メーリング リストの管理者に、メーリング リストがリレーしているドメインのメール認証を構成するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="f046c-208">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="f046c-209">ドメインの所有者に対して相当数の送信者が電子メール認証レコードの設定が必要なことを返信することで、ドメインの所有者の行動を促します。</span><span class="sxs-lookup"><span data-stu-id="f046c-209">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="f046c-210">Microsoft は必要なレコードを公開するためにドメインの所有者と協力しますが、個々のユーザーの要求が大きな支援になります。</span><span class="sxs-lookup"><span data-stu-id="f046c-210">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="f046c-211">メール クライアントで、メッセージを受信トレイに移動する受信トレイ ルールを作成してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-211">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="f046c-212">また、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」や「[テナントの許可/ブロック リストを管理する](tenant-allow-block-list.md)」で説明しているように、管理者に上書きの構成を依頼することもできます。</span><span class="sxs-lookup"><span data-stu-id="f046c-212">You can also ask your admins to configure overrides as described in [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) and [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

  - <span data-ttu-id="f046c-213">Microsoft 365 でサポート チケットを作成して、メーリング リストを正当なものとして扱うためのオーバーライドを作成します。</span><span class="sxs-lookup"><span data-stu-id="f046c-213">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="f046c-214">詳細については、「[一般法人向けサポートへのお問い合わせ - 管理者向けヘルプ](../../business-video/get-help-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-214">For more information, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="f046c-215">他のすべてが失敗した場合は、Microsoft に対してメッセージを誤検知として報告できます。</span><span class="sxs-lookup"><span data-stu-id="f046c-215">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="f046c-216">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-216">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="f046c-217">また、サポート チケットとして Microsoft にこの件を提出できる管理者に問い合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="f046c-217">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="f046c-218">Microsoft のエンジニアリング チームは、メッセージにスプーフィングのマークが付けられた理由を調査します。</span><span class="sxs-lookup"><span data-stu-id="f046c-218">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="f046c-219">スプーフィング対策保護に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f046c-219">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="f046c-220">現在、Microsoft 365 にメッセージを送信している管理者である場合は、メールが正しく認証されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f046c-220">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="f046c-221">それ以外の場合は、スパムまたはフィッシング詐欺としてマークされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f046c-221">Otherwise, it might be marked as spam or phishing.</span></span> <span data-ttu-id="f046c-222">詳細については、「[認証されていないメールを送信している正当な送信者のためのソリューション](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f046c-222">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>

<span data-ttu-id="f046c-223">個人ユーザー (または管理者) の [信頼できる差出人のリスト] に含まれる送信者は、スプーフィング保護を含む、フィルター処理スタックの一部をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="f046c-223">Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection.</span></span> <span data-ttu-id="f046c-224">詳細については、「[Outlook の信頼できる差出人](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-224">For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).</span></span>

<span data-ttu-id="f046c-225">管理者は、可能な場合、許可された送信者リストまたは許可されたドメイン リストを使用して回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f046c-225">Admins should avoid (when possible) using allowed sender lists or allowed domain lists.</span></span> <span data-ttu-id="f046c-226">これらの送信者は、迷惑メール、スプーフィング、およびフィッシング詐欺保護をすべてバイパスします。また、送信者認証 (SPF、DKIM、DMARC) も使用できません。</span><span class="sxs-lookup"><span data-stu-id="f046c-226">These senders bypass all spam, spoofing, and phishing protection, and also sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="f046c-227">詳細については、「[許可された送信者リストまたは許可されたドメイン リストを使用する](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046c-227">For more information, see [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).</span></span>
