---
title: EOP がフィッシングを防ぐために From アドレスを検証する方法
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
description: 管理者は、Exchange Online Protection (EOP) および Outlook.com によって承諾または拒否される電子メールアドレスの種類について学び、フィッシングを防ぐことができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196061"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="a59f6-103">EOP がフィッシングを防ぐために From アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="a59f6-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a59f6-104">フィッシング攻撃は、電子メール組織にとって常に脅威となります。</span><span class="sxs-lookup"><span data-stu-id="a59f6-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="a59f6-105">[スプーフィング (偽造) された送信者電子メールアドレス](anti-spoofing-protection.md)を使用することに加えて、多くの場合、攻撃者は、インターネット標準に違反した From アドレスの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a59f6-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="a59f6-106">この種のフィッシングを防ぐために、Exchange Online Protection (EOP) と Outlook.com では、このトピックで説明するように、受信メッセージに RFC 準拠の差出人のアドレスを含めるように要求されています。</span><span class="sxs-lookup"><span data-stu-id="a59f6-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="a59f6-107">この強制は、2017年11月に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a59f6-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="a59f6-108">**注**:</span><span class="sxs-lookup"><span data-stu-id="a59f6-108">**Notes**:</span></span>

- <span data-ttu-id="a59f6-109">このトピックで説明されているように、アドレスが正しくない組織から電子メールを定期的に受信している場合は、最新のセキュリティ標準に準拠するように電子メールサーバーを更新するように組織を促します。</span><span class="sxs-lookup"><span data-stu-id="a59f6-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="a59f6-110">関連する Sender フィールド (代理人とメーリングリストで使用) は、これらの要件の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="a59f6-111">詳細については、次のブログ投稿を参照してください。 [電子メールの ' sender ' を参照するとどういう](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)ことですか。</span><span class="sxs-lookup"><span data-stu-id="a59f6-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="a59f6-112">電子メールメッセージの標準の概要</span><span class="sxs-lookup"><span data-stu-id="a59f6-112">An overview of email message standards</span></span>

<span data-ttu-id="a59f6-113">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="a59f6-114">メッセージエンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a59f6-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="a59f6-115">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="a59f6-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="a59f6-116">メッセージエンベロープは [rfc 5321](https://tools.ietf.org/html/rfc5321)で説明されており、メッセージヘッダーについては [rfc 5322](https://tools.ietf.org/html/rfc5322)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="a59f6-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="a59f6-117">メッセージの送信プロセスによって生成されたメッセージエンベロープがメッセージの一部ではないため、受信者に実際のメッセージエンベロープが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="a59f6-118">`5321.MailFrom`アドレス ( **MAIL FROM** address、P1 sender、または envelope sender とも呼ばれます) は、メッセージの SMTP 送信で使用される電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a59f6-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="a59f6-119">通常、この電子メールアドレスは、メッセージヘッダーの **リターンパス** ヘッダーフィールドに記録されます (ただし、送信者は別の **リターンパス** 電子メールアドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="a59f6-120">`5322.From`(From アドレスまたは P2 送信者とも呼ばれる) は、[送信**元**アドレス] フィールドの電子メールアドレスであり、電子メールクライアントに表示される送信者の電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a59f6-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="a59f6-121">From アドレスは、このトピックに記載されている要件の焦点です。</span><span class="sxs-lookup"><span data-stu-id="a59f6-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="a59f6-122">From アドレスは、いくつかの Rfc (たとえば、RFC 5322 セクション3.2.3、3.4、3.4.1、 [rfc 3696](https://tools.ietf.org/html/rfc3696)) にわたって詳細に定義されています。</span><span class="sxs-lookup"><span data-stu-id="a59f6-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="a59f6-123">アドレス指定には多くのバリエーションがあり、どのような意味があるかは無効です。</span><span class="sxs-lookup"><span data-stu-id="a59f6-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="a59f6-124">簡単にするために、次の形式と定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a59f6-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="a59f6-125">[**表示名**: 電子メールアドレスの所有者を説明する省略可能な語句です。</span><span class="sxs-lookup"><span data-stu-id="a59f6-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="a59f6-126">表示名は常に二重引用符 (") で囲むようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a59f6-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="a59f6-127">表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む _必要があり_ ます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="a59f6-128">[差出人] アドレスに表示名を指定する場合は、EmailAddress の値を山かっこ (< >) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a59f6-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="a59f6-129">Microsoft では、表示名と電子メールアドレスの間にスペースを挿入することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a59f6-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="a59f6-130">**EmailAddress**: 電子メールアドレスの形式は `local-part@domain` 次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a59f6-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="a59f6-131">**ローカルパート**: アドレスに関連付けられているメールボックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="a59f6-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="a59f6-132">この値は、ドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="a59f6-132">This value is unique within the domain.</span></span> <span data-ttu-id="a59f6-133">多くの場合、メールボックスの所有者のユーザー名または GUID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="a59f6-134">**ドメイン**: 電子メールアドレスのローカル部分で識別されたメールボックスをホストする電子メールサーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="a59f6-135">EmailAddress の値に関するその他の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a59f6-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="a59f6-136">電子メールアドレスは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="a59f6-136">Only one email address.</span></span>
  - <span data-ttu-id="a59f6-137">角かっこは、スペースで区切り文字として使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a59f6-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="a59f6-138">電子メールアドレスの後に追加のテキストを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="a59f6-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="a59f6-139">有効な/無効なアドレスの例</span><span class="sxs-lookup"><span data-stu-id="a59f6-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="a59f6-140">以下は、有効な電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a59f6-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="a59f6-141">`From: < sender@contoso.com >` (角かっこと電子メールアドレスの間にスペースがあるため、この方法は推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="a59f6-142">`From: Microsoft 365 <sender@contoso.com>` (表示名が二重引用符で囲まれていないため、推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="a59f6-143">次の電子メールアドレスは無効です。</span><span class="sxs-lookup"><span data-stu-id="a59f6-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="a59f6-144">**From アドレスなし**: 一部の自動メッセージに差出人住所が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="a59f6-145">以前は、Microsoft 365 または Outlook.com が差出人アドレスを持たないメッセージを受信すると、サービスは次の既定の From: address を追加して、メッセージを配信するようにしました。</span><span class="sxs-lookup"><span data-stu-id="a59f6-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="a59f6-146">これで、空の差出人アドレスを持つメッセージは受け付けられなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a59f6-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="a59f6-147">`From: Microsoft 365 sender@contoso.com` (表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="a59f6-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (電子メールアドレスの後のテキスト)</span><span class="sxs-lookup"><span data-stu-id="a59f6-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="a59f6-149">`From: Sender, Example <sender.example@contoso.com>` (表示名にはコンマが含まれていますが、二重引用符で囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="a59f6-150">`From: "Microsoft 365 <sender@contoso.com>"` (全体の値が誤って二重引用符で囲まれています。)</span><span class="sxs-lookup"><span data-stu-id="a59f6-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="a59f6-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="a59f6-152">`From: Microsoft 365<sender@contoso.com>` (表示名と左山かっこの間にスペースはありません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="a59f6-153">`From: "Microsoft 365"<sender@contoso.com>` (閉じる二重引用符と左山かっこの間にスペースを入れることはできません)。</span><span class="sxs-lookup"><span data-stu-id="a59f6-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="a59f6-154">カスタムドメインへの自動返信を抑制する</span><span class="sxs-lookup"><span data-stu-id="a59f6-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="a59f6-155">この値を使用して `From: <>` 自動応答を抑制することはできません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="a59f6-156">代わりに、カスタムドメインの null MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a59f6-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="a59f6-157">応答サーバーがメッセージを送信できる公開アドレスがないため、自動応答 (およびすべての返信) は自然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="a59f6-158">電子メールを受信できない電子メールドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a59f6-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="a59f6-159">たとえば、プライマリドメインが contoso.com の場合は、noreply.contoso.com を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="a59f6-160">このドメインの null MX レコードは、1つのピリオドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="a59f6-161">例:</span><span class="sxs-lookup"><span data-stu-id="a59f6-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="a59f6-162">MX レコードのセットアップの詳細については、「 [Microsoft 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a59f6-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="a59f6-163">Null MX の公開の詳細については、「 [RFC 7505](https://tools.ietf.org/html/rfc7505)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a59f6-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="a59f6-164">アドレスの強制/無効化</span><span class="sxs-lookup"><span data-stu-id="a59f6-164">Override From address enforcement</span></span>

<span data-ttu-id="a59f6-165">受信電子メールの From アドレス要件をバイパスするには、「 [Microsoft 365 の「差出人セーフリストを作成](create-safe-sender-lists-in-office-365.md)する」の説明に従って、IP 許可一覧 (接続フィルター) またはメールフロールール (トランスポートルールとも呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a59f6-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="a59f6-166">Microsoft 365 から送信する送信電子メールについては、From アドレスの要件を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="a59f6-167">さらに、Outlook.com では、サポートによっても、あらゆる種類の上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="a59f6-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="a59f6-168">Microsoft 365 で cybercrimes を防止および保護する他の方法</span><span class="sxs-lookup"><span data-stu-id="a59f6-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="a59f6-169">フィッシング、スパム、データ漏洩、およびその他の脅威から組織を強化する方法の詳細については、「 [Microsoft 365 for business プランをセキュリティで保護するための上位10の方法](../../admin/security-and-compliance/secure-your-business-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a59f6-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
