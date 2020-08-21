---
title: EOP がフィッシングを防止するために送信元アドレスを検証する方法
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
description: 管理者は、Exchange Online Protection (EOP) によって承諾または拒否された電子メール アドレスの種類とフィッシング対策に役立つ Outlook.com の種類について学習することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827423"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="7ec7b-103">EOP がフィッシングを防止するために送信元アドレスを検証する方法</span><span class="sxs-lookup"><span data-stu-id="7ec7b-103">How EOP validates the From address to prevent phishing</span></span>

<span data-ttu-id="7ec7b-104">フィッシング攻撃は、すべてのメール組織に対して常に脅威を引き出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="7ec7b-105">スプーフィング [された (偽の) 送信者](anti-spoofing-protection.md)のメール アドレスに加えて、攻撃者は、インターネット標準に反する差出人アドレスの値をよく使用します。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="7ec7b-106">この種類のフィッシングを防止するために、このトピックで説明したように、Exchange Online Protection (EOP) および Outlook.com では、受信メッセージに RFC に準拠した送信者アドレスを含めるように要求しています。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="7ec7b-107">この強制は、2017 年 11 月に有効になりました。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="7ec7b-108">**注**:</span><span class="sxs-lookup"><span data-stu-id="7ec7b-108">**Notes**:</span></span>

- <span data-ttu-id="7ec7b-109">このトピックで説明されているとおり、差出先アドレスの形式が正しい組織からメールを定期的に受信する場合は、最新のセキュリティ基準に準拠するように組織の電子メール サーバーを更新するようにします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-109">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="7ec7b-110">関連する送信者フィールド (代理人として送信する、メール送信リストによって使用される) は、これらの要件の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="7ec7b-111">詳細については、次のブログ投稿を参照してください。メールの「送信者」を参照する[場合はどうやっても何を意味しますか?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="7ec7b-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="7ec7b-112">電子メール メッセージ標準の概要</span><span class="sxs-lookup"><span data-stu-id="7ec7b-112">An overview of email message standards</span></span>

<span data-ttu-id="7ec7b-113">標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ*とメッセージのコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="7ec7b-114">メッセージ エンベロープには、SMTP サーバー間でのメッセージの送信と配信に必要な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="7ec7b-115">メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="7ec7b-116">メッセージ エンベロープは [RFC 5321 で](https://tools.ietf.org/html/rfc5321)説明され、メッセージ ヘッダーは [RFC 5322 で表されます](https://tools.ietf.org/html/rfc5322)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="7ec7b-117">実際のメッセージ エンベロープはメッセージ送信プロセスによって生成されるもので、実際にはメッセージの一部ではないため、受信者が実際のメッセージ エンベロープを認識することはない。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="7ec7b-118">アドレス `5321.MailFrom` **(MAIL FROM** アドレス、P1 送信者、またはエンベロープの差出人とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="7ec7b-119">通常、この電子メール アドレスはメッセージ ヘッダー **の Return-Path** ヘッダー フィールドに記録されます (ただし、差出人は異なる **Return-Path メール アドレスを指定** することができます)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="7ec7b-120">From アドレスまたは P2 送信者とも呼ばれる) は From ヘッダー フィールドのメール アドレスで、メール クライアントに表示される差出人 `5322.From` のメール アドレスです。 **From**</span><span class="sxs-lookup"><span data-stu-id="7ec7b-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="7ec7b-121">From アドレスは、このトピックの要件の中で重点的に説明します。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-121">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="7ec7b-122">From アドレスは、複数の RFC の詳細で定義されます (RFC 5322 セクション 3.2.3、3.4、3.4.1、RFC [3696](https://tools.ietf.org/html/rfc3696)など)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="7ec7b-123">アドレス指定に関するバリエーションは数多く、有効または無効と見なされるものがあります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="7ec7b-124">簡単にするために、次の形式と定義をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="7ec7b-125">**表示名**: メール アドレスの所有者を説明するオプションの語句。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="7ec7b-126">表示名は、表示されているように常に二重引用符 (") で囲むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="7ec7b-127">表示名にコンマが含まれる場合_must_、RFC 5322 ごとに文字列を二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="7ec7b-128">From アドレスに表示名が含まれている場合は、示すように、EmailAddress の値を角かっこ (< >) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="7ec7b-129">表示名と電子メール アドレスの間にスペースを挿入するのを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="7ec7b-130">**EmailAddress**: メール アドレスに次の形式が使用されます `local-part@domain` 。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="7ec7b-131">**local-part**: そのアドレスに関連付けられているメールボックスを識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="7ec7b-132">この値はドメイン内で一意です。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-132">This value is unique within the domain.</span></span> <span data-ttu-id="7ec7b-133">多くの場合、メールボックス所有者のユーザー名または GUID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="7ec7b-134">**domain:** 電子メール アドレスのローカル部分によって識別されるメールボックスをホストする電子メール サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="7ec7b-135">EmailAddress 値に関するその他の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="7ec7b-136">電子メール アドレスは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-136">Only one email address.</span></span>
  - <span data-ttu-id="7ec7b-137">角かっこはスペースで区切ないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="7ec7b-138">メール アドレスの後に追加のテキストを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="7ec7b-139">有効な、無効な送信元アドレスの例</span><span class="sxs-lookup"><span data-stu-id="7ec7b-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="7ec7b-140">次の送信元メール アドレスが有効です。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="7ec7b-141">`From: < sender@contoso.com >` 角かっこと電子メール アドレスの間にスペースがあるため、推奨しません。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="7ec7b-142">`From: Microsoft 365 <sender@contoso.com>` (表示名が二重引用符で囲されていないため推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="7ec7b-143">次の [送信元のメール アドレスが無効です]</span><span class="sxs-lookup"><span data-stu-id="7ec7b-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="7ec7b-144">**[いいえ]**: 一部の自動メッセージに From アドレスが含まれていない。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="7ec7b-145">Microsoft 365 または Outlook.com が From アドレスのないメッセージを受信すると、メッセージを配信可能にするために、サービスは次の既定の From: アドレスを追加しました。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="7ec7b-146">この時点で、送信元アドレスが空白のメッセージを受け入れながらしなけれなけれなけれなけれなけ開始されました。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="7ec7b-147">`From: Microsoft 365 sender@contoso.com` (表示名が存在しますが、電子メール アドレスは角かっこで囲む表は囲じません)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="7ec7b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (メール アドレスの後のテキスト。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="7ec7b-149">`From: Sender, Example <sender.example@contoso.com>` 表示名にカンマが含まれますが、二重引用符で囲んではいません。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="7ec7b-150">`From: "Microsoft 365 <sender@contoso.com>"` 値全体が二重引用符で囲まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="7ec7b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (表示名が存在しますが、電子メール アドレスは角かっこで囲む表は囲じません)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="7ec7b-152">`From: Microsoft 365<sender@contoso.com>` 表示名と左角かっこの間にスペースは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="7ec7b-153">`From: "Microsoft 365"<sender@contoso.com>` 二重引用符と左角かっこの間にスペースを空けません。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="7ec7b-154">カスタム ドメインへの自動返信を抑制する</span><span class="sxs-lookup"><span data-stu-id="7ec7b-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="7ec7b-155">この値を使用して `From: <>` 自動応答を表示しない。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="7ec7b-156">代わりに、カスタム ドメインに対して NULL MX レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="7ec7b-157">自動応答 (およびすべての返信) は、応答サーバーがメッセージを送信できる公開済みアドレスがないため、当然に抑制されます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="7ec7b-158">メールを受信しないメール ドメインを選む。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="7ec7b-159">たとえば、プライマリ ドメインがプライマリ ドメインであるcontoso.com場合に、ユーザーのドメインnoreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="7ec7b-160">このドメインの null の MX レコードは、1 つの期間で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="7ec7b-161">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="7ec7b-162">MX レコードの設定の詳細については、「任意の [DNS ホスティング プロバイダーで Microsoft 365 用の DNS レコードを作成する」を参照してください](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="7ec7b-163">Null MX の公開の詳細については [、RFC 7505 をご覧ください](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="7ec7b-164">From アドレスの適用を上書きする</span><span class="sxs-lookup"><span data-stu-id="7ec7b-164">Override From address enforcement</span></span>

<span data-ttu-id="7ec7b-165">受信メールの差出人アドレスの要件をバイパスするには [、Microsoft 365](create-safe-sender-lists-in-office-365.md)で安全な送信者のリストを作成する方法に規されている IP 許可一覧 (接続フィルター) またはメール フロー ルール (別名: トランスポート ルール) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="7ec7b-166">Microsoft 365 から送信される送信メールの From アドレスの要件を上書きしてはいけない。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="7ec7b-167">また、サポートOutlook.com上書きが許可されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="7ec7b-168">Microsoft 365 のサイバーキルを防止および保護するその他の方法</span><span class="sxs-lookup"><span data-stu-id="7ec7b-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="7ec7b-169">フィッシング、スパム、データ侵害、その他の脅威から組織を強度に強度化する方法の詳細については、 [上位 10 の方法によるビジネス向け Microsoft 365 プランをセキュリティで保護する方法をご覧ください](../../admin/security-and-compliance/secure-your-business-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7ec7b-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
