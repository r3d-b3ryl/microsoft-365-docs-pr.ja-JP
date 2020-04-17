---
title: Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Office 365 の受信メッセージ用の電子メールアドレスの要件に関する Lear。 2017年11月現在、このサービスでは、スプーフィングを防止するために RFC 準拠のアドレスが必要になりました。
ms.openlocfilehash: 4df073cfff3c36f60a013237d95548cb48fa7b5f
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529003"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="8d87f-104">Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="8d87f-104">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="8d87f-105">Office 365 の電子メールアカウントには、次第に大量のフィッシング攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="8d87f-105">Office 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="8d87f-106">[スプーフィング (偽造) された送信者電子メールアドレス](anti-spoofing-protection.md)を使用することに加えて、多くの場合、攻撃者は、インターネット標準に違反した From アドレスの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d87f-106">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="8d87f-107">この種のフィッシングを防止するために、Office 365 と Outlook.com では、このトピックで説明するように、受信メッセージに RFC 準拠の差出人のアドレスを含めるように要求されています。</span><span class="sxs-lookup"><span data-stu-id="8d87f-107">To help prevent this type of phishing, Office 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="8d87f-108">この強制は、2017年11月に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8d87f-108">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="8d87f-109">**注**:</span><span class="sxs-lookup"><span data-stu-id="8d87f-109">**Notes**:</span></span>

- <span data-ttu-id="8d87f-110">このトピックで説明されているように、アドレスが正しくない組織から電子メールを定期的に受信している場合は、最新のセキュリティ標準に準拠するように電子メールサーバーを更新するように組織を促します。</span><span class="sxs-lookup"><span data-stu-id="8d87f-110">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="8d87f-111">関連する Sender フィールド (代理人とメーリングリストで使用) は、これらの要件の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-111">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="8d87f-112">詳細については、次のブログ投稿を参照してください。[電子メールの ' sender ' を参照するとどういう](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)ことですか。</span><span class="sxs-lookup"><span data-stu-id="8d87f-112">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="8d87f-113">電子メールメッセージの標準の概要</span><span class="sxs-lookup"><span data-stu-id="8d87f-113">An overview of email message standards</span></span>

<span data-ttu-id="8d87f-114">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-114">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="8d87f-115">メッセージエンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d87f-115">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="8d87f-116">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="8d87f-116">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="8d87f-117">メッセージエンベロープは[rfc 5321](https://tools.ietf.org/html/rfc5321)で説明されており、メッセージヘッダーについては[rfc 5322](https://tools.ietf.org/html/rfc5322)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="8d87f-117">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="8d87f-118">メッセージの送信プロセスによって生成されたメッセージエンベロープがメッセージの一部ではないため、受信者に実際のメッセージエンベロープが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-118">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="8d87f-119">`5321.MailFrom`アドレス ( **MAIL FROM** address、P1 sender、または envelope sender とも呼ばれます) は、メッセージの SMTP 送信で使用される電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="8d87f-119">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="8d87f-120">通常、この電子メールアドレスは、メッセージヘッダーの**リターンパス**ヘッダーフィールドに記録されます (ただし、送信者は別の**リターンパス**電子メールアドレスを指定することもできます)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-120">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="8d87f-121">`5322.From` (From アドレスまたは P2 送信者とも呼ばれる) は、[送信**元**アドレス] フィールドの電子メールアドレスであり、電子メールクライアントに表示される送信者の電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="8d87f-121">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="8d87f-122">From アドレスは、このトピックに記載されている要件の焦点です。</span><span class="sxs-lookup"><span data-stu-id="8d87f-122">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="8d87f-123">From アドレスは、いくつかの Rfc (たとえば、RFC 5322 セクション3.2.3、3.4、3.4.1、 [rfc 3696](https://tools.ietf.org/html/rfc3696)) にわたって詳細に定義されています。</span><span class="sxs-lookup"><span data-stu-id="8d87f-123">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="8d87f-124">アドレス指定には多くのバリエーションがあり、どのような意味があるかは無効です。</span><span class="sxs-lookup"><span data-stu-id="8d87f-124">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="8d87f-125">簡単にするために、次の形式と定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d87f-125">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="8d87f-126">[**表示名**: 電子メールアドレスの所有者を説明する省略可能な語句です。</span><span class="sxs-lookup"><span data-stu-id="8d87f-126">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="8d87f-127">表示名は常に二重引用符 (") で囲むようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d87f-127">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="8d87f-128">表示名にコンマが含まれている場合は、RFC 5322 ごとに文字列を二重引用符で囲む_必要があり_ます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-128">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="8d87f-129">[差出人] アドレスに表示名を指定する場合は、EmailAddress の値を山かっこ (< >) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d87f-129">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="8d87f-130">Microsoft では、表示名と電子メールアドレスの間にスペースを挿入することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d87f-130">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="8d87f-131">**EmailAddress**: 電子メールアドレスの形式`local-part@domain`は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d87f-131">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="8d87f-132">**ローカルパート**: アドレスに関連付けられているメールボックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="8d87f-132">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="8d87f-133">この値は、ドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="8d87f-133">This value is unique within the domain.</span></span> <span data-ttu-id="8d87f-134">多くの場合、メールボックスの所有者のユーザー名または GUID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-134">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="8d87f-135">**ドメイン**: 電子メールアドレスのローカル部分で識別されたメールボックスをホストする電子メールサーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-135">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="8d87f-136">EmailAddress の値に関するその他の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d87f-136">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="8d87f-137">電子メールアドレスは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="8d87f-137">Only one email address.</span></span>
  - <span data-ttu-id="8d87f-138">角かっこは、スペースで区切り文字として使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d87f-138">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="8d87f-139">電子メールアドレスの後に追加のテキストを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="8d87f-139">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="8d87f-140">有効な/無効なアドレスの例</span><span class="sxs-lookup"><span data-stu-id="8d87f-140">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="8d87f-141">以下は、有効な電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="8d87f-141">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="8d87f-142">`From: < sender@contoso.com >`(角かっこと電子メールアドレスの間にスペースがあるため、この方法は推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-142">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Office 365" <sender@contoso.com>`

- <span data-ttu-id="8d87f-143">`From: Office 365 <sender@contoso.com>`(表示名が二重引用符で囲まれていないため、推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-143">`From: Office 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="8d87f-144">次の電子メールアドレスは無効です。</span><span class="sxs-lookup"><span data-stu-id="8d87f-144">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="8d87f-145">**From アドレスなし**: 一部の自動メッセージに差出人住所が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-145">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="8d87f-146">以前は、Office 365 または Outlook.com が差出人アドレスを持たないメッセージを受信すると、サービスによってメッセージが配信されるように、次の既定の From: address が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8d87f-146">In the past, when Office 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="8d87f-147">これで、空の差出人アドレスを持つメッセージは受け付けられなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8d87f-147">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="8d87f-148">`From: Office 365 sender@contoso.com`(表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-148">`From: Office 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="8d87f-149">`From: "Office 365" <sender@contoso.com> (Sent by a process)`(電子メールアドレスの後のテキスト)</span><span class="sxs-lookup"><span data-stu-id="8d87f-149">`From: "Office 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="8d87f-150">`From: Sender, Example <sender.example@contoso.com>`(表示名にはコンマが含まれていますが、二重引用符で囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-150">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="8d87f-151">`From: "Office 365 <sender@contoso.com>"`(全体の値が誤って二重引用符で囲まれています。)</span><span class="sxs-lookup"><span data-stu-id="8d87f-151">`From: "Office 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="8d87f-152">`From: "Office 365 <sender@contoso.com>" sender@contoso.com`(表示名は存在しますが、電子メールアドレスは角かっこで囲まれていません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-152">`From: "Office 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="8d87f-153">`From: Office 365<sender@contoso.com>`(表示名と左山かっこの間にスペースはありません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-153">`From: Office 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="8d87f-154">`From: "Office 365"<sender@contoso.com>`(閉じる二重引用符と左山かっこの間にスペースを入れることはできません)。</span><span class="sxs-lookup"><span data-stu-id="8d87f-154">`From: "Office 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="8d87f-155">カスタムドメインへの自動返信を抑制する</span><span class="sxs-lookup"><span data-stu-id="8d87f-155">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="8d87f-156">この値`From: <>`を使用して自動応答を抑制することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-156">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="8d87f-157">代わりに、カスタムドメインの null MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d87f-157">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="8d87f-158">応答サーバーがメッセージを送信できる公開アドレスがないため、自動応答 (およびすべての返信) は自然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-158">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="8d87f-159">電子メールを受信できない電子メールドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d87f-159">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="8d87f-160">たとえば、プライマリドメインが contoso.com の場合は、noreply.contoso.com を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-160">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="8d87f-161">このドメインの null MX レコードは、1つのピリオドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-161">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="8d87f-162">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8d87f-162">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="8d87f-163">MX レコードのセットアップの詳細については、「[任意の dns ホスティングプロバイダーで Office 365 用の dns レコードを作成](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d87f-163">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="8d87f-164">Null MX の公開の詳細については、「 [RFC 7505](https://tools.ietf.org/html/rfc7505)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d87f-164">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="8d87f-165">アドレスの強制/無効化</span><span class="sxs-lookup"><span data-stu-id="8d87f-165">Override From address enforcement</span></span>

<span data-ttu-id="8d87f-166">受信電子メールの From アドレス要件をバイパスするには、「 [Office 365 の安全な送信者リストを作成](create-safe-sender-lists-in-office-365.md)する」の説明に従って、IP 許可一覧 (接続フィルター) またはメールフロールール (トランスポートルールとも呼ばれます) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d87f-166">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="8d87f-167">Office 365 から送信する送信電子メールについては、From アドレスの要件を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-167">You can't override the From address requirements for outbound email that you send from Office 365.</span></span> <span data-ttu-id="8d87f-168">さらに、Outlook.com では、サポートによっても、あらゆる種類の上書きを許可しません。</span><span class="sxs-lookup"><span data-stu-id="8d87f-168">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="8d87f-169">Office 365 で cybercrimes を防止し、保護するためのその他の方法</span><span class="sxs-lookup"><span data-stu-id="8d87f-169">Other ways to prevent and protect against cybercrimes in Office 365</span></span>

<span data-ttu-id="8d87f-170">フィッシング、スパム、データ侵害、およびその他の脅威から組織を強化する方法の詳細については、「[上位10の方法で Office 365 と Microsoft 365 のビジネスプランを保護する](../../admin/security-and-compliance/secure-your-business-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d87f-170">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Office 365 and Microsoft 365 Business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
