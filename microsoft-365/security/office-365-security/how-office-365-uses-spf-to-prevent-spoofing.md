---
title: Sender Policy Framework (SPF) がスプーフィングを防止する方法
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 が DNS で Sender Policy Framework (SPF) TXT レコードを使用して、送信先の電子メール システムがカスタム ドメインから送信されたメッセージを信頼する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: daf170339f4a218c404114f9c82b1d465779100d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286870"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="d01c3-103">Microsoft 365 において Sender Policy Framework (SPF) を使用して、スプーフィングを防止する方法</span><span class="sxs-lookup"><span data-stu-id="d01c3-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d01c3-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="d01c3-104">**Applies to**</span></span>
- [<span data-ttu-id="d01c3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d01c3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d01c3-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="d01c3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d01c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d01c3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="d01c3-108">**概要:** この記事では、Microsoft 365 が DNS で Sender Policy Framework (SPF) TXT レコードを使用して、送信先の電子メール システムがカスタム ドメインから送信されたメッセージを信頼する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="d01c3-109">これは、Microsoft 365 から送信される送信メールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="d01c3-110">Microsoft 365 から Microsoft 365 内の受信者に送信されるメッセージは、常に SPF に合格します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="d01c3-p102">SPF TXT レコードは、DNS 形式のレコードです。SPF TXT レコードで、メール メッセージの送信元のドメイン名を確認すると、スプーフィングやフィッシングの防止に役立ちます。SPF は、送信者の IP アドレスを、送信側ドメインの所有者とされる名前と照合して、メール メッセージの発信元を確認します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p102">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d01c3-p103">SPF レコードの種類は、2014 年にインターネット技術標準化委員会 (IETF) によって廃止されました。代わりに、SPF 情報を公開するには、DNS で TXT レコードを必ず使用してください。この記事の以降の部分では、わかりやすいように SPF TXT レコードという用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p103">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="d01c3-116">ドメイン管理者は DNS の TXT レコードで SPF 情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="d01c3-117">この SPF 情報は、承認された送信メール サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="d01c3-118">送信先メール システムにより、承認された送信メール サーバーからメッセージが発信されたことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="d01c3-119">SPF に既に慣れ親しんだ場合、または単純な展開を使用している場合に、Microsoft 365 の DNS の SPF TXT レコードに含める必要があるものについてのみ知りたい場合は [、Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)で SPF のセットアップにアクセスして、スプーフィングを防止することができます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="d01c3-120">Microsoft 365 で完全にホストされた展開を使用していない場合、または SPF のしくみや Microsoft 365 の SPF のトラブルシューティング方法に関する詳細な情報が必要な場合は、続きを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d01c3-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="d01c3-121">以前は、SharePoint Online も使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d01c3-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="d01c3-122">この作業を行う必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d01c3-122">This is no longer required.</span></span> <span data-ttu-id="d01c3-123">この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="d01c3-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="d01c3-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="d01c3-125">Microsoft 365 でのスプーフィングとフィッシングを防止する SPF のしくみ</span><span class="sxs-lookup"><span data-stu-id="d01c3-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="d01c3-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="d01c3-p106">SPF は、送信者がドメインの代理として送信することを許可されているかどうかを判断します。送信者がこの操作を許可されていない場合、つまり、受信側のサーバーで電子メールの SPF チェックが失敗した場合は、そのサーバー上で構成されたスパム ポリシーが、メッセージについて行う処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p106">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="d01c3-129">各 SPF TXT レコードには、SPF TXT レコードである宣言、ドメインからメールを送信できる IP アドレス、ドメインに代わって送信できる外部ドメイン、および強制ルールの 3 つの部分が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="d01c3-130">有効な SPF TXT レコードには 3 つすべてが必要です。</span><span class="sxs-lookup"><span data-stu-id="d01c3-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="d01c3-131">この記事では、SPF TXT レコードの作成方法について説明し、Microsoft 365 のサービスを操作するためのベスト プラクティスを示します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="d01c3-132">ドメイン レジストラーを操作して DNS にレコードを発行する手順へのリンクも提供されています。</span><span class="sxs-lookup"><span data-stu-id="d01c3-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="d01c3-133">SPF の基本: カスタム ドメインからの送信が許可された IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d01c3-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="d01c3-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="d01c3-135">SPF ルールの基本的な構文を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d01c3-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="d01c3-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="d01c3-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="d01c3-137">たとえば、contoso.com に対して次の SPF ルールが存在するとします。</span><span class="sxs-lookup"><span data-stu-id="d01c3-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="d01c3-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="d01c3-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="d01c3-139">この例では、SPF ルールは、ドメイン contoso.com について、これらの IP アドレスからのメールのみを受け入れるように受信電子メール サーバーに指示します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="d01c3-140">IP アドレス #1</span><span class="sxs-lookup"><span data-stu-id="d01c3-140">IP address #1</span></span>

- <span data-ttu-id="d01c3-141">IP アドレス #2</span><span class="sxs-lookup"><span data-stu-id="d01c3-141">IP address #2</span></span>

- <span data-ttu-id="d01c3-142">IP アドレス #3</span><span class="sxs-lookup"><span data-stu-id="d01c3-142">IP address #3</span></span>

<span data-ttu-id="d01c3-p108">この SPF ルールは受信メール サーバーに、メッセージが contoso.com からのものであるものの、これら 3 つの IP アドレスのいずれからのものでもない場合、受信側サーバーはメッセージに対して強制ルールを適用する必要があることを指示します。通常、強制ルールは次のオプションのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p108">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="d01c3-p109">**Hard fail。** メッセージ エンベロープ内に 'hard fail' を含むメッセージをマークし、受信側サーバーでこの種類のメッセージに対して構成されたスパム ポリシーに従います。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p109">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="d01c3-p110">**Soft fail。** メッセージ エンベロープ内に 'soft fail' を含むメッセージをマークします。通常、電子メール サーバーはこれらのメッセージを配信するように構成されます。ほとんどのエンド ユーザーには、このマークは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p110">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="d01c3-p111">**Neutral。** 何もしません。つまり、メッセージ エンベロープをマークしません。通常、これはテスト用に予約されているものであり、ほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p111">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="d01c3-p112">次の例は、さまざまな状況での SPF のしくみを示しています。これらの例では、contoso.com は送信者、woodgrovebank.com は受信者です。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p112">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="d01c3-156">例 1:送信者から受信者に直接送信されるメッセージの電子メール認証</span><span class="sxs-lookup"><span data-stu-id="d01c3-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="d01c3-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="d01c3-158">SPF は、送信者から受信者へのパスが直接パスである場合に最適に機能します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![サーバーからサーバーへ直接送信されるときに SPF がメールを認証する方法を示す図。](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="d01c3-160">Woodgrovebank.com がメッセージを受け取る際に、IP アドレス # 1 が contoso.com の SPF TXT レコードにある場合は、メッセージは SPF チェックに合格し認証されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="d01c3-161">例 2:偽装された送信者のアドレスが SPF チェックに失敗する</span><span class="sxs-lookup"><span data-stu-id="d01c3-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="d01c3-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="d01c3-163">フィッシャーが contoso.com を偽装する方法を見つけたとします。</span><span class="sxs-lookup"><span data-stu-id="d01c3-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![偽装しているサーバーから送信されるときに SPF がメールを認証する方法を示す図。](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="d01c3-165">IP アドレスの#12 contoso.com の SPF TXT レコードに含めなされていないので、メッセージは SPF チェックに失敗し、受信者はメッセージをスパムとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="d01c3-166">例 3:SPF と転送されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="d01c3-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="d01c3-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="d01c3-168">SPF の欠点の 1 つは、電子メールが転送された場合には機能しないという点です。</span><span class="sxs-lookup"><span data-stu-id="d01c3-168">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="d01c3-169">たとえば、woodgrovebank.com のユーザーが、outlook.com アカウントにすべての電子メールを送信する転送ルールを設定しているとします。</span><span class="sxs-lookup"><span data-stu-id="d01c3-169">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![電子メール メッセージが転送される際に SPF がメールを認証できないことを示す図。](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="d01c3-171">メッセージは最初は woodgrovebank.com で SPF チェックに合格しますが、IP #25 が contoso.com の SPF TXT レコードに含めないので、outlook.com で SPF チェックに失敗します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-171">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="d01c3-172">このため、Outlook.com はメッセージをスパムとしてマークする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-172">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="d01c3-173">この問題を回避するには、SPF を DKIM や DMARC などの他の電子メールの認証方法と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-173">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="d01c3-174">SPF の基本:自分のドメインに代わってメールを送信できるサード パーティのドメインを含める</span><span class="sxs-lookup"><span data-stu-id="d01c3-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="d01c3-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="d01c3-176">IP アドレスに加えて、送信者としてドメインを含めるように SPF TXT レコードを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-176">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="d01c3-177">これらは、"include" ステートメントとして SPF TXT レコードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-177">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="d01c3-178">たとえば、contoso.com には、所有する contoso.net と contoso.org からメール サーバーのすべての IP アドレスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-178">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="d01c3-179">これを行うには、contoso.com は次のような SPF TXT レコードを発行します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-179">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="d01c3-180">受信側のサーバーが DNS でこのレコードを見た場合は、SPF TXT レコードに対して contoso.net の DNS 参照を実行し、次に contoso.org。レコード内で追加の include ステートメントが検索された場合は、contoso.netまたは contoso.orgに従います。</span><span class="sxs-lookup"><span data-stu-id="d01c3-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="d01c3-181">サービス拒否攻撃を防止するための、1 つの電子メール メッセージに対する DNS 参照の最大数は 10 です。</span><span class="sxs-lookup"><span data-stu-id="d01c3-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="d01c3-182">各 include ステートメントは追加の DNS 参照を表します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="d01c3-183">メッセージが上限 10 を超えると、メッセージは SPF チェックに失敗します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="d01c3-184">受信側サーバーの構成方法に応じて、メッセージがこの制限に達すると、送信者は、メッセージが 「ルックアップが多すぎます」または「メッセージの最大ホップ数を超えました」(ルックアップがループして DNS タイムアウトを超えたときに発生する可能性がある) というメッセージを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="d01c3-185">これを回避する方法のヒントについては、「トラブルシューティング [: Microsoft 365 の SPF](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)のベスト プラクティス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d01c3-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="d01c3-186">SPF TXT レコードと Microsoft 365 の要件</span><span class="sxs-lookup"><span data-stu-id="d01c3-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="d01c3-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="d01c3-188">Microsoft 365 のセットアップ時にメールをセットアップした場合、Microsoft メッセージング サーバーをドメインの正当なメール ソースとして識別する SPF TXT レコードが既に作成されています。</span><span class="sxs-lookup"><span data-stu-id="d01c3-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="d01c3-189">このレコードは、おそらく次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d01c3-190">完全にホストされる顧客の場合、つまり、送信メールを送信するオンプレミスのメール サーバーがない場合、これは Office 365 用に発行する必要がある唯一の SPF TXT レコードです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="d01c3-191">ハイブリッド展開がある場合 (つまり、オンプレミスのメールボックスと Microsoft 365 でホストされているメールボックスがある場合)、または Exchange Online Protection (EOP) スタンドアロンのお客様 (つまり、組織が EOP を使用してオンプレミスのメールボックスを保護している) の場合は、各オンプレミス エッジ メール サーバーの送信 IP アドレスを DNS の SPF TXT レコードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="d01c3-192">Microsoft 365 の SPF TXT レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="d01c3-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="d01c3-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="d01c3-p118">この記事に記載されている構文の情報を使って、カスタム ドメイン用の SPF TXT レコードを形成します。ここに記載されていない他の構文オプションもありますが、これらが最もよく使うオプションです。レコードを形成した後は、ドメイン レジストラーでレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p118">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="d01c3-197">Microsoft 365 に含める必要があるドメインの詳細については [、「SPF](../../enterprise/external-domain-name-system-records.md)に必要な外部 DNS レコード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d01c3-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="d01c3-198">ドメイン レジスト [ラーの](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) SPF (TXT) レコードを更新するための詳しい手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-198">Use the [step-by-step instructions](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="d01c3-199">Microsoft 365 の SPF TXT レコード構文</span><span class="sxs-lookup"><span data-stu-id="d01c3-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="d01c3-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="d01c3-201">Microsoft 365 の一般的な SPF TXT レコードの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="d01c3-202">たとえば、</span><span class="sxs-lookup"><span data-stu-id="d01c3-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d01c3-203">各部分の意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-203">where:</span></span>

- <span data-ttu-id="d01c3-p120">**v=spf1** は必須です。これは、SPF TXT レコードとして TXT レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p120">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="d01c3-p121">**ip4** は、IP バージョン 4 のアドレスを使用していることを示します。**ip6** は、IP バージョン 6 のアドレスを使用していることを示します。IPv6 の IP アドレスを使用している場合は、この記事の例の **ip4** を **ip6** に置き換えます。CIDR 表記を使用して IP アドレス範囲を指定することもできます (たとえば、**ip4:192.168.0.1/26**)。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p121">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="d01c3-210">_IP address_ は、SPF TXT レコードに追加する IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="d01c3-211">通常、これは組織の送信メール サーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="d01c3-212">複数の送信メール サーバーを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="d01c3-213">詳細については、「例: 複数の送信オンプレミス メール サーバーと [Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)の SPF TXT レコード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d01c3-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="d01c3-214">_domain name_ は、正当な送信者として追加するドメインです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="d01c3-215">Microsoft 365 に含める必要があるドメイン名の一覧については、「SPF に必要な [外部 DNS レコード」を参照してください](../../enterprise/external-domain-name-system-records.md)。</span><span class="sxs-lookup"><span data-stu-id="d01c3-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span>

- <span data-ttu-id="d01c3-216">通常、強制ルールは次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="d01c3-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="d01c3-217">-all</span><span class="sxs-lookup"><span data-stu-id="d01c3-217">-all</span></span>

    <span data-ttu-id="d01c3-p124">hard fail を示します。ドメインに対するすべての承認済みの IP アドレスが既知の場合は、SPF TXT レコードにそれらを一覧表示して、-all (hard fail) 修飾子を使用します。また、SPF のみを使用している場合、つまり、DMARC または DKIM のいずれも使用していない場合は、-all 修飾子を使用する必要もあります。常にこの修飾子を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p124">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="d01c3-222">~all</span><span class="sxs-lookup"><span data-stu-id="d01c3-222">~all</span></span>

    <span data-ttu-id="d01c3-223">soft fail を示します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-223">Indicates soft fail.</span></span> <span data-ttu-id="d01c3-224">IP アドレスの完全な一覧が不明な場合は、~all (soft fail) 修飾子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-224">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="d01c3-225">また、p=quarantine または p=reject と共に DMARC を使用している場合も、~all を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-225">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="d01c3-226">それ以外の場合は、-all を使用します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-226">Otherwise, use -all.</span></span>

  - <span data-ttu-id="d01c3-227">?all</span><span class="sxs-lookup"><span data-stu-id="d01c3-227">?all</span></span>

    <span data-ttu-id="d01c3-p126">neutral を示します。SPF のテスト時に使用されます。実際の展開でこの修飾子を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p126">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="d01c3-231">例: すべてのメールが Microsoft 365 によって送信される場合に使用する SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="d01c3-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="d01c3-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="d01c3-233">すべてのメールが Microsoft 365 によって送信される場合は、SPF TXT レコードでこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="d01c3-234">例: 1 つのオンプレミスネットワークと Microsoft 365 を使用するハイブリッド シナリオExchange Server SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="d01c3-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="d01c3-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="d01c3-236">ハイブリッド環境で、オンプレミスの Exchange Server の IP アドレスが 192.168.0.1 である場合、SPF の強制ルールを hard fail に設定するために、SPF TXT レコードを次のように形成します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="d01c3-237">例: 複数の送信オンプレミス メール サーバーと Microsoft 365 の SPF TXT レコード</span><span class="sxs-lookup"><span data-stu-id="d01c3-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="d01c3-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="d01c3-239">複数の送信メール サーバーがある場合は、SPF TXT レコード内の各メール サーバーの IP アドレスを含め、各 IP アドレスをスペースとそれに続く "ip4:" ステートメントで分離します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-239">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="d01c3-240">例:</span><span class="sxs-lookup"><span data-stu-id="d01c3-240">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="d01c3-241">次の手順: Microsoft 365 用に SPF をセットアップする</span><span class="sxs-lookup"><span data-stu-id="d01c3-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="d01c3-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="d01c3-243">SPF TXT レコードを作成したら [、「Microsoft 365 で SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) をセットアップする」の手順に従って、スプーフィングによってドメインに追加されるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="d01c3-244">SPF は、スプーフィングを防止するために設計されていますが、SPF で防御できないスプーフィングの手法があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="d01c3-245">これらを保護するために、SPF をセットアップしたら、Microsoft 365 用に DKIM と DMARC も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="d01c3-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="d01c3-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="d01c3-247">次に [、「DMARC を使用して Microsoft 365 でメールを検証する」を参照してください](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d01c3-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="d01c3-248">トラブルシューティング: Microsoft 365 の SPF のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d01c3-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="d01c3-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d01c3-p129">カスタム ドメインに作成できる SPF TXT レコードは 1 つのみです。複数のレコードを作成すると、ラウンド ロビン状況の原因となり、SPF が失敗します。これを避けるために、各サブドメインに対して個別にレコードを作成できます。たとえば、contoso.com に 1 つのレコードを作成し、bulkmail.contoso.com に別のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p129">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="d01c3-254">電子メール メッセージが配信される前に 10 を超える DNS 参照を引き起こす場合、受信側のメール サーバーは永続的なエラー  _(permerror_ とも呼ばれる) で応答し、メッセージが SPF チェックに失敗します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-254">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="d01c3-255">また、受信側のサーバーは、次のようなエラーを含む配信不能レポート (NDR) で応答することもあります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-255">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="d01c3-256">メッセージのホップ数を超えました。</span><span class="sxs-lookup"><span data-stu-id="d01c3-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="d01c3-257">メッセージに必要な参照数が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="d01c3-258">Microsoft 365 でサード パーティのドメインを使用する場合の "参照が多すぎます" エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="d01c3-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="d01c3-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d01c3-p131">サード パーティのドメインの SPF TXT レコードには、受信側のサーバーに多数の DNS 参照を実行するよう指示するものがあります。たとえば、この記事の執筆時には、Salesforce.com のレコードに 5 つの include ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p131">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="d01c3-p132">エラーを回避するために、(たとえばバルク メールを送信する) あらゆるユーザーがサブドメインを使用する必要があるというポリシーを、特にこの目的のために実装できます。次にバルク メールを含むサブドメイン用の別の SPF TXT レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="d01c3-p132">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="d01c3-264">salesforce.com の例などのように、SPF TXT レコードでドメインを使用する必要がある場合がありますが、サードパーティがこの目的のためにユーザーの使用するサブドメインを既に作成している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-264">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="d01c3-265">たとえば、exacttarget.com は、SPF TXT レコードに対して使用する必要があるサブドメインを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d01c3-265">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="d01c3-266">SPF TXT レコードにサード パーティのドメインを含む場合は、参照の上限値 10 に達することを回避するために、どのドメインまたはサブドメインを使用するかを、サードパーティに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="d01c3-267">現在の SPF TXT レコードを表示し、それに必要な参照数を決定する方法</span><span class="sxs-lookup"><span data-stu-id="d01c3-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="d01c3-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d01c3-269">nslookup を使用して、SPF TXT レコードなどの DNS レコードを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-269">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="d01c3-270">また、ご希望に応じて、無料のオンライン ツールを多数入手し、SPF TXT レコードの内容を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-270">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="d01c3-271">SPF TXT を参照し、一連の include ステートメントとリダイレクトに従って、レコードが必要とする DNS 参照数を判断できます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-271">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="d01c3-272">オンライン ツールには、これらの参照数をカウントして表示するものもあります。</span><span class="sxs-lookup"><span data-stu-id="d01c3-272">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="d01c3-273">この数を継続的に追跡することで、組織から送信されたメッセージが、受信側のサーバーからの permerror と呼ばれる永続的なエラーの要因にならないようにできます。</span><span class="sxs-lookup"><span data-stu-id="d01c3-273">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d01c3-274">関連情報</span><span class="sxs-lookup"><span data-stu-id="d01c3-274">For more information</span></span>
<span data-ttu-id="d01c3-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d01c3-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="d01c3-276">SPF TXT レコードの追加に関するヘルプが必要な場合</span><span class="sxs-lookup"><span data-stu-id="d01c3-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="d01c3-277">Microsoft 365 のカスタム ドメインで Sender Policy Framework を使用する方法の詳細については [、Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) の DNS ホスティング プロバイダーで DNS レコードを作成するに関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d01c3-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="d01c3-278">[スパム対策メッセージ ヘッダーには、Microsoft](anti-spam-message-headers.md) 365 で SPF チェックに使用される構文とヘッダー フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d01c3-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>
