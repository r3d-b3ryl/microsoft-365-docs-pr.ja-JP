---
title: SPF を設定して、スプーフィングを防止する
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 で Sender Policy Framework (SPF) をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 828d76b95a1e3f8d1a1851121d28603a1922f486
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538989"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="eccd4-103">SPF を設定して、スプーフィングを防止する</span><span class="sxs-lookup"><span data-stu-id="eccd4-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="eccd4-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="eccd4-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="eccd4-105">SPF TXT レコードを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="eccd4-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="eccd4-106">サブドメインの処理方法</span><span class="sxs-lookup"><span data-stu-id="eccd4-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="eccd4-107">SPF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eccd4-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="eccd4-108">この記事では、Office 365 で Sender Policy Framework (SPF) のメール認証をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="eccd4-109">SPF は、カスタム ドメイン(実際の送信元) から来た送信メールを *検証* するのに役立ちます。 </span><span class="sxs-lookup"><span data-stu-id="eccd4-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="eccd4-110">これは、全体的に推奨している SPF、 [DKIM](use-dkim-to-validate-outbound-email.md)、[DMARC](use-dmarc-to-validate-email.md) 認証において電子メール認証方法を設定する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="eccd4-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

- [<span data-ttu-id="eccd4-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="eccd4-111">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="eccd4-112">SPF TXT レコードを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="eccd4-112">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
  - [<span data-ttu-id="eccd4-113">サブドメインの処理方法</span><span class="sxs-lookup"><span data-stu-id="eccd4-113">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="eccd4-114">SPF メール認証で実際に行う操作</span><span class="sxs-lookup"><span data-stu-id="eccd4-114">What does SPF email authentication actually do?</span></span>](#what-does-spf-email-authentication-actually-do)
  - [<span data-ttu-id="eccd4-115">SPF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eccd4-115">Troubleshooting SPF</span></span>](#troubleshooting-spf)
- [<span data-ttu-id="eccd4-116">SPF の詳細情報</span><span class="sxs-lookup"><span data-stu-id="eccd4-116">More information about SPF</span></span>](#more-information-about-spf)

## <a name="prerequisites"></a><span data-ttu-id="eccd4-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="eccd4-117">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eccd4-118">**中小企業のビジネス** または IP アドレスまたは DNS の構成に慣れていない場合は、インターネット ドメイン レジストラーに電話してください (例:</span><span class="sxs-lookup"><span data-stu-id="eccd4-118">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="eccd4-119">GoDaddy、Bluehost、web.com)。また、*SPF のDNS 構成* (および他のメール認証方法) に関してお尋ねください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-119">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="eccd4-120">**カスタム URL** を使用していない場合 (Office 365 に使用されている URL が **onmicrosoft.com** で終わっている場合) は、Office 365 サービスで SPF が既に設定されています。</span><span class="sxs-lookup"><span data-stu-id="eccd4-120">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="eccd4-121">では、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="eccd4-121">Let's get started.</span></span>

<span data-ttu-id="eccd4-122">Office 365 の SPF TXT レコードは、カスタム ドメインまたはサブドメインの外部の DNS で作成されます。</span><span class="sxs-lookup"><span data-stu-id="eccd4-122">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="eccd4-123">レコードを作成するには、いくつかの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="eccd4-123">You need some information to make the record.</span></span> <span data-ttu-id="eccd4-124">次の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-124">Gather this information:</span></span>

- <span data-ttu-id="eccd4-125">カスタム ドメインの SPF TXT レコード (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="eccd4-125">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="eccd4-126">手順に関しては、「[Office 365 の DNS レコードの作成に必要な情報を収集する](../../admin/get-help-with-domains/information-for-dns-records.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-126">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="eccd4-127">メッセージング サーバーに移動して、(すべてのオンプレミス メッセージング サーバーからの必要な) 外部 IP アドレスを発見します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-127">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="eccd4-128">たとえば、**131.107.2.200** などです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-128">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="eccd4-p106">SPF TXT レコードに含める必要があるサードパーティ製のすべてのドメインに使用するドメイン名。一部のバルク メール プロバイダーは、顧客用のサブドメインを設定しています。たとえば、会社 MailChimp に **servers.mcsv.net** を設定するなどです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="eccd4-132">SPF TXT レコードで使う強制ルールを決定します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-132">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="eccd4-133">**-all** ルールが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="eccd4-133">The **-all** rule is recommended.</span></span> <span data-ttu-id="eccd4-134">その他の構文オプションについて詳しくは、「[Office 365 用の SPF TXT レコードの構文](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-134">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eccd4-135">カスタム ドメインを使用するには、Office 365 では、Sender Policy Framework (SPF) TXT レコードを DNS レコードに追加してスプーフィングを防止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eccd4-135">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="eccd4-136">SPF TXT レコードを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="eccd4-136">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="eccd4-137">以下の表の SFP 構文について、十分に理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-137">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="eccd4-138">要素</span><span class="sxs-lookup"><span data-stu-id="eccd4-138">Element</span></span>|<span data-ttu-id="eccd4-139">もし今使っているとしたら...</span><span class="sxs-lookup"><span data-stu-id="eccd4-139">If you're using...</span></span>|<span data-ttu-id="eccd4-140">お客様に共通のことでは?</span><span class="sxs-lookup"><span data-stu-id="eccd4-140">Common for customers?</span></span>|<span data-ttu-id="eccd4-141">追加対象</span><span class="sxs-lookup"><span data-stu-id="eccd4-141">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="eccd4-142">1</span><span class="sxs-lookup"><span data-stu-id="eccd4-142">1</span></span>|<span data-ttu-id="eccd4-143">いずれかの電子メール システム (必須)</span><span class="sxs-lookup"><span data-stu-id="eccd4-143">Any email system (required)</span></span>|<span data-ttu-id="eccd4-p108">共通。この値で始まるすべての SPF レコード</span><span class="sxs-lookup"><span data-stu-id="eccd4-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="eccd4-146">2</span><span class="sxs-lookup"><span data-stu-id="eccd4-146">2</span></span>|<span data-ttu-id="eccd4-147">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="eccd4-147">Exchange Online</span></span>|<span data-ttu-id="eccd4-148">共通</span><span class="sxs-lookup"><span data-stu-id="eccd4-148">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="eccd4-149">3</span><span class="sxs-lookup"><span data-stu-id="eccd4-149">3</span></span>|<span data-ttu-id="eccd4-150">Exchange Online 専用のみ</span><span class="sxs-lookup"><span data-stu-id="eccd4-150">Exchange Online dedicated only</span></span>|<span data-ttu-id="eccd4-151">共通ではない</span><span class="sxs-lookup"><span data-stu-id="eccd4-151">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="eccd4-152">4</span><span class="sxs-lookup"><span data-stu-id="eccd4-152">4</span></span>|<span data-ttu-id="eccd4-153">Office 365 Germany、Microsoft Cloud Germany のみ</span><span class="sxs-lookup"><span data-stu-id="eccd4-153">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="eccd4-154">共通ではない</span><span class="sxs-lookup"><span data-stu-id="eccd4-154">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="eccd4-155">5</span><span class="sxs-lookup"><span data-stu-id="eccd4-155">5</span></span>|<span data-ttu-id="eccd4-156">サード パーティ製の電子メール システム</span><span class="sxs-lookup"><span data-stu-id="eccd4-156">Third-party email system</span></span>|<span data-ttu-id="eccd4-157">共通ではない</span><span class="sxs-lookup"><span data-stu-id="eccd4-157">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="eccd4-158">\<domain_name\> は、他社製の電子メール システムのドメインです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-158">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="eccd4-159">6</span><span class="sxs-lookup"><span data-stu-id="eccd4-159">6</span></span>|<span data-ttu-id="eccd4-p109">オンプレミスの電子メール システム。たとえば、Exchange Online Protection と別のメール システム</span><span class="sxs-lookup"><span data-stu-id="eccd4-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="eccd4-162">共通ではない</span><span class="sxs-lookup"><span data-stu-id="eccd4-162">Not common</span></span>|<span data-ttu-id="eccd4-163">各追加メール システムで次のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-163">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="eccd4-164">\<IP_address\> と \<domain_name\> は、ドメインの代理としてメールを送信する他のメールシステムの IP アドレスとドメインです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-164">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="eccd4-165">7</span><span class="sxs-lookup"><span data-stu-id="eccd4-165">7</span></span>|<span data-ttu-id="eccd4-166">いずれかの電子メール システム (必須)</span><span class="sxs-lookup"><span data-stu-id="eccd4-166">Any email system (required)</span></span>|<span data-ttu-id="eccd4-p110">共通。この値で終わるすべての SPF レコード</span><span class="sxs-lookup"><span data-stu-id="eccd4-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="eccd4-169">これは、いくつかの値のどれか 1 つかもしれません。</span><span class="sxs-lookup"><span data-stu-id="eccd4-169">This can be one of several values.</span></span> <span data-ttu-id="eccd4-170">値 `-all` をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eccd4-170">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="eccd4-171">まだ行っていない場合は、表の構文を使用して SPF TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-171">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="eccd4-172">たとえば、Office 365 で完全にホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、2 行目、7 行目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eccd4-172">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="eccd4-173">**上記は、SPF TXT レコード の最も一般的な例です**。</span><span class="sxs-lookup"><span data-stu-id="eccd4-173">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="eccd4-174">このレコードは、Microsoft データセンターが米国、ヨーロッパ (ドイツを含む)、または他の場所にあっても、ほぼすべてのユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-174">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="eccd4-p113">ただし、Microsoft Cloud Germany の一部である Office 365 Germany を購入している場合は、2 行目ではなく 4 行目から include ステートメントを使用してください。たとえば、Office 365 Germany で全体がホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、4 行目、7 行目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="eccd4-177">Office 365 で既に展開し、カスタム ドメインの SPF TXT レコードをセットアップしている状態で Office 365 Germany に移行する場合は、SPF TXT レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eccd4-177">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="eccd4-178">これを行うには、`include:spf.protection.outlook.com` を`include:spf.protection.outlook.de`に変更します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-178">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="eccd4-179">SPF TXT レコードを構成した後、DNS でレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eccd4-179">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="eccd4-180">**ドメインに配置できる SPF TXT レコードは 1 つのみです**。</span><span class="sxs-lookup"><span data-stu-id="eccd4-180">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="eccd4-181">SPF TXT レコードが存在する場合、新しいレコードを追加するのではなく、既存のレコードを更新しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="eccd4-181">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="eccd4-182">「[Office 365 の DNS レコードを作成する](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」に移動し、DNS ホストのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eccd4-182">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="eccd4-183">SPF TXT レコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="eccd4-183">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="eccd4-184">サブドメインの処理方法とは?</span><span class="sxs-lookup"><span data-stu-id="eccd4-184">How to handle subdomains?</span></span>

<span data-ttu-id="eccd4-185">*サブドメインは、上位ドメインの SPF レコードを継承しないので、サブドメインごとに、別々のレコードを作成する必要がある* ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-185">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="eccd4-186">存在しないサブドメインからのメールを、攻撃者が送信することを防ぐために、すべてのドメインとサブドメインに対して追加のワイルドカード SPF レコード (`*.`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="eccd4-186">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="eccd4-187">例:</span><span class="sxs-lookup"><span data-stu-id="eccd4-187">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="eccd4-188">SPF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eccd4-188">Troubleshooting SPF</span></span>

<span data-ttu-id="eccd4-p117">SPF TXT レコードで問題が発生している場合「[トラブルシューティング:Office 365 における SPF のベスト プラクティス](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)」をお読みください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="eccd4-191">SPF メール認証では、実際に何が行われますか?</span><span class="sxs-lookup"><span data-stu-id="eccd4-191">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="eccd4-p118">SPF は、ユーザーの代わりにメールを送信できるメール サーバを識別します。 SPF は基本的に、DKIM、DMARC、および Office 365 でサポートされているその他のテクノロジーとともにスプーフィングとフィッシングを防止します。 SPF は、カスタム ドメインの代わりにメールを送信できるメール サーバを識別するために DNS によって使用される TXT レコードとして追加されます。 受信者のメール システムは、SPF TXT レコードを参照して、カスタム ドメインからのメッセージが許可されたメッセージ サーバから送信されたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="eccd4-p119">たとえば、カスタム ドメイン contoso.com が Office 365 を使用しているとします。ユーザーのドメインの正当なメール サーバーとして Office 365 メッセージング サーバーを一覧表示する SPF TXT レコードを追加します。受信メッセージング サーバーが joe@contoso.com からのメッセージを取得すると、サーバーによって contoso.com の SPF TXT レコードが検索され、適切なメッセージであるかどうかが検出されます。受信サーバーで、SPF レコードに一覧表示されている Office 365 メッセージング サーバー以外のサーバーからメッセージを取得していることが検出された場合、受信メール サーバーはそのメッセージを迷惑メールとして拒否できます。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="eccd4-p120">また、カスタム ドメインに SPF TXT レコードが含まれていないと、一部の受信サーバーはメッセージを完全に拒否することがあります。これは、受信サーバーが、承認されたメッセージング サーバーからのメッセージであることを検証できないためです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="eccd4-p121">既に Office 365 のメールを設定している場合、SPF TXT レコードとして Microsoft のメッセージング サーバーが DNS に含まれています。ただし、場合によっては DNS で SPF TXT レコードを更新する必要があります。たとえば、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="eccd4-p122">以前は、SharePoint Online を使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。この作業を行う必要はなくなりました。この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。参照の制限数である 10 に達し、"参照制限を超えました"、"ホップが多すぎます" などのメッセージを示すエラーが表示される場合は、SPF TXT レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="eccd4-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="eccd4-209">Office 365 とオンプレミスの Exchange を使用したハイブリッド環境の場合。</span><span class="sxs-lookup"><span data-stu-id="eccd4-209">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="eccd4-210">DKIM と DMARC をセットアップする場合 (推奨)。</span><span class="sxs-lookup"><span data-stu-id="eccd4-210">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="eccd4-211">SPF の詳細情報</span><span class="sxs-lookup"><span data-stu-id="eccd4-211">More information about SPF</span></span>

<span data-ttu-id="eccd4-212">サポートされている SPF 構文、スプーフィング、トラブルシューティング、Office 365 が SPF をサポートする方法の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-212">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="eccd4-213">次の手順: DKIM と DMARC</span><span class="sxs-lookup"><span data-stu-id="eccd4-213">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="eccd4-214">SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング テクニックがあります。</span><span class="sxs-lookup"><span data-stu-id="eccd4-214">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="eccd4-215">それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Office 365 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eccd4-215">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="eccd4-216">[DKIM](use-dkim-to-validate-outbound-email.md) メール認証の目標は、メールの内容が改ざんされていないと証明することです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-216">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="eccd4-217">[DMARC](use-dmarc-to-validate-email.md) メール認証の目標は、SPF と DKIM の情報が From アドレスと確実に一致していることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="eccd4-217">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="eccd4-218">サポートされている SPF 構文の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eccd4-218">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="eccd4-219">*このドキュメントに関してフィードバックがある場合は、[フィードバック] の下にある [このページ] を選択してください。*</span><span class="sxs-lookup"><span data-stu-id="eccd4-219">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
