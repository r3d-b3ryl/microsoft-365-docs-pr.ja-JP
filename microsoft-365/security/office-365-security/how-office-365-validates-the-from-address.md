---
title: EOP がフィッシング詐欺を防ぐために From アドレスを検証する方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) によって受け付けまたは拒否される電子メール アドレスの種類と、フィッシングOutlook.comに役立つ情報を確認できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25fbca8fa5d264a212ac25e2035bffde0819383d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659656"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="85454-103">EOP がフィッシングを防止するために From アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="85454-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="85454-104">フィッシング攻撃は、すべての電子メール組織にとって絶え間ない脅威です。</span><span class="sxs-lookup"><span data-stu-id="85454-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="85454-105">攻撃者は、スプーフィング [された (偽造された)](anti-spoofing-protection.md)送信者の電子メール アドレスを使用する以外に、インターネット標準に違反する差出人アドレスの値を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="85454-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="85454-106">この種のフィッシングを防止するために、Exchange Online Protection (EOP) と Outlook.com では、この記事で説明するように、RFC 準拠の差出人アドレスを含める受信メッセージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="85454-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="85454-107">この実施は、2017 年 11 月に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="85454-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="85454-108">**注**:</span><span class="sxs-lookup"><span data-stu-id="85454-108">**Notes**:</span></span>

- <span data-ttu-id="85454-109">この記事で説明したように、From アドレスの形式が正しい組織からメールを定期的に受信する場合は、最新のセキュリティ標準に準拠するように電子メール サーバーを更新するよう組織に勧めします。</span><span class="sxs-lookup"><span data-stu-id="85454-109">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="85454-110">関連する Sender フィールド ([代理送信] および [郵送リスト] で使用) は、これらの要件の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="85454-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="85454-111">詳細については、次のブログ投稿を参照してください。メールの「送信者」を参照すると、どのような[意味がありますか?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="85454-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="85454-112">電子メール メッセージの標準の概要</span><span class="sxs-lookup"><span data-stu-id="85454-112">An overview of email message standards</span></span>

<span data-ttu-id="85454-113">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="85454-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="85454-114">メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="85454-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="85454-115">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="85454-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="85454-116">メッセージ エンベロープは [RFC 5321](https://tools.ietf.org/html/rfc5321)で記述され、メッセージ ヘッダーは [RFC 5322 で記述されています](https://tools.ietf.org/html/rfc5322)。</span><span class="sxs-lookup"><span data-stu-id="85454-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="85454-117">実際のメッセージ エンベロープはメッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、受信者には表示されません。</span><span class="sxs-lookup"><span data-stu-id="85454-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="85454-118">アドレス (MAIL FROM アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。 </span><span class="sxs-lookup"><span data-stu-id="85454-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="85454-119">この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="85454-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="85454-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span><span class="sxs-lookup"><span data-stu-id="85454-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="85454-121">From アドレスは、この記事の要件の焦点です。</span><span class="sxs-lookup"><span data-stu-id="85454-121">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="85454-122">From アドレスは、いくつかの RFC (RFC 5322 セクション 3.2.3、3.4、3.4.1、RFC [3696](https://tools.ietf.org/html/rfc3696)など) で詳細に定義されます。</span><span class="sxs-lookup"><span data-stu-id="85454-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="85454-123">アドレス指定には多くのバリエーションが存在し、有効または無効と見なされるものがあります。</span><span class="sxs-lookup"><span data-stu-id="85454-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="85454-124">シンプルに保つために、次の形式と定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85454-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="85454-125">**表示名**: 電子メール アドレスの所有者を説明するオプションの語句。</span><span class="sxs-lookup"><span data-stu-id="85454-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="85454-126">次に示すように、表示名は常に二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="85454-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="85454-127">表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。 </span><span class="sxs-lookup"><span data-stu-id="85454-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="85454-128">From アドレスに表示名が含まれる場合は、次に示すように EmailAddress 値を角かっこ (< >) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="85454-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="85454-129">表示名と電子メール アドレスの間にスペースを挿入強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="85454-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="85454-130">**EmailAddress**: 電子メール アドレスは次の形式を使用します `local-part@domain` 。</span><span class="sxs-lookup"><span data-stu-id="85454-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="85454-131">**local-part**: アドレスに関連付けられているメールボックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="85454-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="85454-132">この値はドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="85454-132">This value is unique within the domain.</span></span> <span data-ttu-id="85454-133">多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="85454-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="85454-134">**domain**: 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="85454-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="85454-135">EmailAddress 値に関する追加の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="85454-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="85454-136">1 つのメール アドレスのみ。</span><span class="sxs-lookup"><span data-stu-id="85454-136">Only one email address.</span></span>
  - <span data-ttu-id="85454-137">角かっこはスペースで区切らはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="85454-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="85454-138">メール アドレスの後にテキストを追加しない。</span><span class="sxs-lookup"><span data-stu-id="85454-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="85454-139">有効な From アドレスと無効な From アドレスの例</span><span class="sxs-lookup"><span data-stu-id="85454-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="85454-140">次の From 電子メール アドレスが有効です。</span><span class="sxs-lookup"><span data-stu-id="85454-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="85454-141">`From: < sender@contoso.com >` (角かっこと電子メール アドレスの間にスペースが含まれているため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="85454-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="85454-142">`From: Microsoft 365 <sender@contoso.com>` (表示名は二重引用符で囲んでいないので、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="85454-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="85454-143">次の From 電子メール アドレスは無効です。</span><span class="sxs-lookup"><span data-stu-id="85454-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="85454-144">**[From アドレスなし**]: 一部の自動メッセージには From アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="85454-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="85454-145">Microsoft 365 または Outlook.com が From アドレスのないメッセージを受信した場合、サービスは次の既定の From: アドレスを追加してメッセージを配信可能にしました。</span><span class="sxs-lookup"><span data-stu-id="85454-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="85454-146">これで、空の From アドレスを持つメッセージは受け付けなくなりました。</span><span class="sxs-lookup"><span data-stu-id="85454-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="85454-147">`From: Microsoft 365 sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。</span><span class="sxs-lookup"><span data-stu-id="85454-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="85454-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト)。</span><span class="sxs-lookup"><span data-stu-id="85454-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="85454-149">`From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれますが、二重引用符で囲む必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="85454-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="85454-150">`From: "Microsoft 365 <sender@contoso.com>"` (値全体が誤って二重引用符で囲まれている。</span><span class="sxs-lookup"><span data-stu-id="85454-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="85454-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は表示されますが、電子メール アドレスは角かっこで囲む必要があります)。</span><span class="sxs-lookup"><span data-stu-id="85454-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="85454-152">`From: Microsoft 365<sender@contoso.com>` (表示名と左の角かっこの間にはスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="85454-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="85454-153">`From: "Microsoft 365"<sender@contoso.com>` (終了二重引用符と左の角かっこの間にはスペースはありません。</span><span class="sxs-lookup"><span data-stu-id="85454-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="85454-154">カスタム ドメインへの自動返信を抑制する</span><span class="sxs-lookup"><span data-stu-id="85454-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="85454-155">この値を使用して `From: <>` 自動応答を抑制することはできません。</span><span class="sxs-lookup"><span data-stu-id="85454-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="85454-156">代わりに、カスタム ドメインの NULL MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85454-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="85454-157">自動応答 (およびすべての返信) は、応答側サーバーがメッセージを送信できる発行済みアドレスが存在しないので、自然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="85454-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="85454-158">メールを受信できないメール ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="85454-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="85454-159">たとえば、プライマリ ドメインがcontoso.com場合は、次のnoreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="85454-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="85454-160">このドメインの NULL MX レコードは、1 つのピリオドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="85454-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="85454-161">例:</span><span class="sxs-lookup"><span data-stu-id="85454-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="85454-162">MX レコードの設定の詳細については [、「Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)の任意の DNS ホスティング プロバイダーで DNS レコードを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85454-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="85454-163">NULL MX の公開の詳細については [、RFC 7505 を参照](https://tools.ietf.org/html/rfc7505)してください。</span><span class="sxs-lookup"><span data-stu-id="85454-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="85454-164">アドレスの適用による上書き</span><span class="sxs-lookup"><span data-stu-id="85454-164">Override From address enforcement</span></span>

<span data-ttu-id="85454-165">受信メールの差出人アドレスの要件を回避するには [、「Microsoft 365](create-safe-sender-lists-in-office-365.md)で差出人セーフ リストを作成する」の説明に従って、IP 許可一覧 (接続フィルター) またはメール フロー ルール (トランスポート ルールとも呼ばれる) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85454-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="85454-166">Microsoft 365 から送信する送信メールの From アドレス要件を上書きできない。</span><span class="sxs-lookup"><span data-stu-id="85454-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="85454-167">また、サポートOutlook.com、どのような種類のオーバーライドも許可されていません。</span><span class="sxs-lookup"><span data-stu-id="85454-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="85454-168">Microsoft 365 でのサイバー犯罪を防止して保護するその他の方法</span><span class="sxs-lookup"><span data-stu-id="85454-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="85454-169">フィッシング、スパム、データ侵害、その他の脅威に対して組織を強化する方法の詳細については、「ビジネス プラン向け [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)をセキュリティで保護するトップ 10 の方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85454-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
