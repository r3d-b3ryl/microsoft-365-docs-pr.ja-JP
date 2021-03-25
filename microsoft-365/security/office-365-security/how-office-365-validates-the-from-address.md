---
title: EOP がフィッシングを防止するために From アドレスを検証する方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) によって受け入れまたは拒否される電子メール アドレスの種類と、フィッシング Outlook.com に役立つメール アドレスについて説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205376"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="18766-103">EOP がフィッシングを防止するために From アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="18766-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="18766-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="18766-104">**Applies to**</span></span>
- [<span data-ttu-id="18766-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="18766-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="18766-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="18766-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="18766-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18766-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="18766-108">フィッシング攻撃は、メール組織にとって絶え間ない脅威です。</span><span class="sxs-lookup"><span data-stu-id="18766-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="18766-109">攻撃者は、ス [プーフィングされた (偽造された)](anti-spoofing-protection.md)送信者の電子メール アドレスの使用に加えて、インターネット標準に違反する差出人アドレスの値を使用する場合が多い。</span><span class="sxs-lookup"><span data-stu-id="18766-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="18766-110">この種類のフィッシングを防止するために、Exchange Online Protection (EOP) と Outlook.com では、この記事で説明するように RFC 準拠の From アドレスを含める受信メッセージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="18766-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="18766-111">この適用は 2017 年 11 月に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="18766-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="18766-112">**注**:</span><span class="sxs-lookup"><span data-stu-id="18766-112">**Notes**:</span></span>

- <span data-ttu-id="18766-113">この記事の説明に従って、不正な形式のアドレスを持つ組織から定期的にメールを受信する場合は、これらの組織に最新のセキュリティ標準に準拠するように電子メール サーバーを更新するようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18766-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="18766-114">関連する [送信者] フィールド ([Send on Behalf and mailing lists] で使用) は、これらの要件の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="18766-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="18766-115">詳細については、次のブログ投稿を参照してください。 電子メールの ['sender'](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)を参照する場合の意味は?</span><span class="sxs-lookup"><span data-stu-id="18766-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="18766-116">電子メール メッセージ標準の概要</span><span class="sxs-lookup"><span data-stu-id="18766-116">An overview of email message standards</span></span>

<span data-ttu-id="18766-117">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="18766-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="18766-118">メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18766-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="18766-119">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="18766-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="18766-120">メッセージ エンベロープは [RFC 5321](https://tools.ietf.org/html/rfc5321)で説明され、メッセージ ヘッダーは [RFC 5322 で説明されています](https://tools.ietf.org/html/rfc5322)。</span><span class="sxs-lookup"><span data-stu-id="18766-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="18766-121">受信者は、メッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、実際のメッセージ エンベロープは表示されません。</span><span class="sxs-lookup"><span data-stu-id="18766-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="18766-122">アドレス (MAIL FROM アドレス、P1 送信者、封筒送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。 </span><span class="sxs-lookup"><span data-stu-id="18766-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="18766-123">この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="18766-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="18766-124">(From アドレスまたは P2 送信者とも呼ばれる) は、[差出人] ヘッダー フィールドの電子メール アドレスであり、電子メール クライアントに表示される送信者の電子メール アドレス `5322.From` です。 </span><span class="sxs-lookup"><span data-stu-id="18766-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="18766-125">From アドレスは、この記事の要件の焦点です。</span><span class="sxs-lookup"><span data-stu-id="18766-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="18766-126">From アドレスは、複数の RFC (たとえば、RFC 5322 セクション 3.2.3、3.4、および 3.4.1、 [および RFC 3696)](https://tools.ietf.org/html/rfc3696)で詳細に定義されます。</span><span class="sxs-lookup"><span data-stu-id="18766-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="18766-127">アドレス指定には多くのバリエーションがあります。また、有効または無効と見なされるものがあります。</span><span class="sxs-lookup"><span data-stu-id="18766-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="18766-128">シンプルに保つために、次の形式と定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18766-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="18766-129">**[表示名**]: 電子メール アドレスの所有者を表すオプションの語句です。</span><span class="sxs-lookup"><span data-stu-id="18766-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="18766-130">表示名は、常に二重引用符 (") で囲んで表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18766-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="18766-131">表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。 </span><span class="sxs-lookup"><span data-stu-id="18766-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="18766-132">From アドレスに表示名が含まれる場合、EmailAddress 値は、図のように角かっこ (< >) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="18766-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="18766-133">表示名と電子メール アドレスの間にスペースを挿入強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="18766-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="18766-134">**EmailAddress**: 電子メール アドレスは、次の形式を使用します `local-part@domain` 。</span><span class="sxs-lookup"><span data-stu-id="18766-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="18766-135">**local-part**: アドレスに関連付けられたメールボックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="18766-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="18766-136">この値は、ドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="18766-136">This value is unique within the domain.</span></span> <span data-ttu-id="18766-137">多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="18766-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="18766-138">**domain**: 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="18766-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="18766-139">EmailAddress 値に関する追加の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18766-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="18766-140">メール アドレスは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="18766-140">Only one email address.</span></span>
  - <span data-ttu-id="18766-141">角かっこはスペースで区切らすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18766-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="18766-142">電子メール アドレスの後に追加のテキストを含めない。</span><span class="sxs-lookup"><span data-stu-id="18766-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="18766-143">有効で無効な From アドレスの例</span><span class="sxs-lookup"><span data-stu-id="18766-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="18766-144">次の From 電子メール アドレスが有効です。</span><span class="sxs-lookup"><span data-stu-id="18766-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="18766-145">`From: < sender@contoso.com >` (角かっこと電子メール アドレスの間にスペースが含まれているため、お勧めしません)。</span><span class="sxs-lookup"><span data-stu-id="18766-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="18766-146">`From: Microsoft 365 <sender@contoso.com>` (表示名は二重引用符で囲まないので、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="18766-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="18766-147">次の From 電子メール アドレスが無効です。</span><span class="sxs-lookup"><span data-stu-id="18766-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="18766-148">**No From address**: 一部の自動メッセージには From アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18766-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="18766-149">過去に、Microsoft 365 または Outlook.com が From アドレスなしでメッセージを受信した場合、サービスは次の既定の From: アドレスを追加してメッセージを配信可能にしました。</span><span class="sxs-lookup"><span data-stu-id="18766-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="18766-150">これで、From アドレスが空白のメッセージは受け入れなくなりました。</span><span class="sxs-lookup"><span data-stu-id="18766-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="18766-151">`From: Microsoft 365 sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。</span><span class="sxs-lookup"><span data-stu-id="18766-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="18766-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト。</span><span class="sxs-lookup"><span data-stu-id="18766-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="18766-153">`From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれますが、二重引用符で囲む必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="18766-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="18766-154">`From: "Microsoft 365 <sender@contoso.com>"` (値全体が誤って二重引用符で囲まれます)。</span><span class="sxs-lookup"><span data-stu-id="18766-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="18766-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。</span><span class="sxs-lookup"><span data-stu-id="18766-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="18766-156">`From: Microsoft 365<sender@contoso.com>` (表示名と左かっこの間にスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="18766-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="18766-157">`From: "Microsoft 365"<sender@contoso.com>` (閉じる二重引用符と左かっこの間にスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="18766-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="18766-158">カスタム ドメインへの自動返信を抑制する</span><span class="sxs-lookup"><span data-stu-id="18766-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="18766-159">値を使用して自動 `From: <>` 返信を抑制することはできません。</span><span class="sxs-lookup"><span data-stu-id="18766-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="18766-160">代わりに、カスタム ドメインの NULL MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18766-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="18766-161">応答側サーバーがメッセージを送信できる公開アドレスが存在しないので、自動返信 (およびすべての返信) は自然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="18766-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="18766-162">メールを受信できないメール ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18766-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="18766-163">たとえば、プライマリ ドメインが使用されている場合 contoso.com を選択 noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="18766-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="18766-164">このドメインの NULL MX レコードは、1 つの期間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="18766-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="18766-165">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="18766-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="18766-166">MX レコードの設定の詳細については [、「Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)の任意の DNS ホスティング プロバイダーで DNS レコードを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18766-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="18766-167">NULL MX の発行の詳細については [、「RFC 7505」を参照してください](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="18766-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="18766-168">Override From address enforcement</span><span class="sxs-lookup"><span data-stu-id="18766-168">Override From address enforcement</span></span>

<span data-ttu-id="18766-169">受信メールの差出人アドレス要件をバイパスするには [、「Microsoft 365](create-safe-sender-lists-in-office-365.md)で差出人セーフ リストを作成する」の説明に従って、IP 許可一覧 (接続フィルター) またはメール フロー ルール (トランスポート ルールとも呼ばれる) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="18766-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="18766-170">Microsoft 365 から送信する送信メールの From アドレス要件を上書きできない。</span><span class="sxs-lookup"><span data-stu-id="18766-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="18766-171">また、サポート Outlook.com を通じても、任意の種類の上書きを許可しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="18766-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="18766-172">Microsoft 365 のサイバー犯罪を防止して保護するその他の方法</span><span class="sxs-lookup"><span data-stu-id="18766-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="18766-173">フィッシング、スパム、データ侵害、その他の脅威に対して組織を強化する方法の詳細については、「ビジネス プラン向け [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)をセキュリティで保護する上位 10 の方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18766-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>