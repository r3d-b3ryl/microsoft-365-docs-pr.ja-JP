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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 で Sender Policy Framework (SPF) をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。
ms.openlocfilehash: 536f727ee71db70490259179ff8e47009c547f89
ms.sourcegitcommit: 64262f6f42dcce6a4608b2e3c7ca6190b7009093
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905225"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="3195a-103">SPF を設定して、スプーフィングを防止する</span><span class="sxs-lookup"><span data-stu-id="3195a-103">Set up SPF to help prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

- [<span data-ttu-id="3195a-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3195a-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="3195a-105">SPF TXT レコードを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="3195a-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)   
  - [<span data-ttu-id="3195a-106">サブドメインの処理方法</span><span class="sxs-lookup"><span data-stu-id="3195a-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="3195a-107">SPF メール認証で実際に行う操作</span><span class="sxs-lookup"><span data-stu-id="3195a-107">What does SPF email authentication actually do?</span></span>](#what-does-spf-email-authentication-actually-do)   
   - [<span data-ttu-id="3195a-108">SPF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3195a-108">Troubleshooting SPF</span></span>](#troubleshooting-spf)
- [<span data-ttu-id="3195a-109">SPF の詳細情報</span><span class="sxs-lookup"><span data-stu-id="3195a-109">More information about SPF</span></span>](#more-information-about-spf)

<span data-ttu-id="3195a-110">この記事では、Office 365 で Sender Policy Framework (SPF) のメール認証をカスタム ドメインと併用できるように、ドメイン ネーム サービス (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3195a-110">This article describes how to update an Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="3195a-111">SPF を使うと、カスタム ドメインから送信される送信電子メールを検証できます。</span><span class="sxs-lookup"><span data-stu-id="3195a-111">Using SPF helps to validate outbound email sent from your custom domain.</span></span> <span data-ttu-id="3195a-112">推奨されているメール認証方法のDMARC と DKIM (Office 365 でサポートされている他の 2 つのメール認証方法) を設定する最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="3195a-112">It's a first step in setting up other recommended email authentication methods DMARC and DKIM (two further email authentication methods supported in Office 365).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3195a-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="3195a-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3195a-114">**中小企業のビジネス** または IP アドレスまたは DNS の構成に慣れていない場合は、インターネット ドメイン レジストラーに電話してください (例:</span><span class="sxs-lookup"><span data-stu-id="3195a-114">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="3195a-115">GoDaddy、Bluehost、web.com)。SPF の DNS 構成 (および他のメール認証方法) に関するヘルプを求めることができます。</span><span class="sxs-lookup"><span data-stu-id="3195a-115">GoDaddy, Bluehost, web.com) to ask for help with DNS configuration of SPF (and any other email authentication method).</span></span> <span data-ttu-id="3195a-116">*また*、ユーザー設定の URL (つまり、ユーザーと顧客が Office 365 にアクセスする URL が **onmicrosoft.com** で終了の場合) を購入していない場合、またはカスタム URL を使用していない場合は、Office 365 サービスで SPF が設定されています。</span><span class="sxs-lookup"><span data-stu-id="3195a-116">*Also*, if you haven't bought, or don't use a custom URL (in other words the URL you and your customers browse to reach Office 365 ends in **onmicrosoft.com**), SPF has been set up for you in the Office 365 service.</span></span> <span data-ttu-id="3195a-117">その場合は、それ以上の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3195a-117">No further steps are required in that case.</span></span> <span data-ttu-id="3195a-118">ご確認ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="3195a-118">Thanks for reading.</span></span>

<span data-ttu-id="3195a-119">外部 DNS で Office 365 の SPF TXT レコードを作成または更新する前に、レコード作成に必要な情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195a-119">Before you create or update the SPF TXT record for Office 365 in external DNS, you need to gather some information needed to make the record.</span></span> <span data-ttu-id="3195a-120">サポートされている SPF 構文の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3195a-120">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="3195a-121">次の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="3195a-121">Gather this information:</span></span>

- <span data-ttu-id="3195a-122">もしあれば、カスタム ドメインの現在の SPF TXT レコード。</span><span class="sxs-lookup"><span data-stu-id="3195a-122">The current SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="3195a-123">手順に関しては、「[Office 365 の DNS レコードの作成に必要な情報を収集する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3195a-123">For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span>

- <span data-ttu-id="3195a-124">メッセージング サーバーに移動して、(すべてのオンプレミス メッセージング サーバーからの必要な) 外部 IP アドレスを発見します。</span><span class="sxs-lookup"><span data-stu-id="3195a-124">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="3195a-125">たとえば、**131.107.2.200** などです。</span><span class="sxs-lookup"><span data-stu-id="3195a-125">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="3195a-p106">SPF TXT レコードに含める必要があるサードパーティ製のすべてのドメインに使用するドメイン名。一部のバルク メール プロバイダーは、顧客用のサブドメインを設定しています。たとえば、会社 MailChimp に **servers.mcsv.net** を設定するなどです。</span><span class="sxs-lookup"><span data-stu-id="3195a-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="3195a-129">SPF TXT レコードで使う強制ルールを決定します。</span><span class="sxs-lookup"><span data-stu-id="3195a-129">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="3195a-130">**-all** ルールが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3195a-130">The **-all** rule is recommended.</span></span> <span data-ttu-id="3195a-131">その他の構文オプションについて詳しくは、「[Office 365 用の SPF TXT レコードの構文](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3195a-131">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3195a-132">カスタム ドメインを使用するには、Office 365 では、Sender Policy Framework (SPF) TXT レコードを DNS レコードに追加してスプーフィングを防止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195a-132">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="3195a-133">SPF TXT レコードを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="3195a-133">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="3195a-134">以下の表の SFP 構文について、十分に理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="3195a-134">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="3195a-135">要素</span><span class="sxs-lookup"><span data-stu-id="3195a-135">Element</span></span>|<span data-ttu-id="3195a-136">もし今使っているとしたら...</span><span class="sxs-lookup"><span data-stu-id="3195a-136">If you're using...</span></span>|<span data-ttu-id="3195a-137">お客様に共通のことでは?</span><span class="sxs-lookup"><span data-stu-id="3195a-137">Common for customers?</span></span>|<span data-ttu-id="3195a-138">追加対象</span><span class="sxs-lookup"><span data-stu-id="3195a-138">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="3195a-139">1</span><span class="sxs-lookup"><span data-stu-id="3195a-139">1</span></span>|<span data-ttu-id="3195a-140">いずれかの電子メール システム (必須)</span><span class="sxs-lookup"><span data-stu-id="3195a-140">Any email system (required)</span></span>|<span data-ttu-id="3195a-p108">共通。この値で始まるすべての SPF レコード</span><span class="sxs-lookup"><span data-stu-id="3195a-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="3195a-143">2</span><span class="sxs-lookup"><span data-stu-id="3195a-143">2</span></span>|<span data-ttu-id="3195a-144">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3195a-144">Exchange Online</span></span>|<span data-ttu-id="3195a-145">共通</span><span class="sxs-lookup"><span data-stu-id="3195a-145">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="3195a-146">3</span><span class="sxs-lookup"><span data-stu-id="3195a-146">3</span></span>|<span data-ttu-id="3195a-147">Exchange Online 専用のみ</span><span class="sxs-lookup"><span data-stu-id="3195a-147">Exchange Online dedicated only</span></span>|<span data-ttu-id="3195a-148">共通ではない</span><span class="sxs-lookup"><span data-stu-id="3195a-148">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="3195a-149">4</span><span class="sxs-lookup"><span data-stu-id="3195a-149">4</span></span>|<span data-ttu-id="3195a-150">Office 365 Germany、Microsoft Cloud Germany のみ</span><span class="sxs-lookup"><span data-stu-id="3195a-150">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="3195a-151">共通ではない</span><span class="sxs-lookup"><span data-stu-id="3195a-151">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="3195a-152">5</span><span class="sxs-lookup"><span data-stu-id="3195a-152">5</span></span>|<span data-ttu-id="3195a-153">サード パーティ製の電子メール システム</span><span class="sxs-lookup"><span data-stu-id="3195a-153">Third-party email system</span></span>|<span data-ttu-id="3195a-154">共通ではない</span><span class="sxs-lookup"><span data-stu-id="3195a-154">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="3195a-155">\<domain_name\> は、サード パーティ製の電子メール システムのドメインです。</span><span class="sxs-lookup"><span data-stu-id="3195a-155">\<domain_name\> is the domain of the third party email system.</span></span>|
   |<span data-ttu-id="3195a-156">6</span><span class="sxs-lookup"><span data-stu-id="3195a-156">6</span></span>|<span data-ttu-id="3195a-p109">オンプレミスの電子メール システム。たとえば、Exchange Online Protection と別のメール システム</span><span class="sxs-lookup"><span data-stu-id="3195a-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="3195a-159">共通ではない</span><span class="sxs-lookup"><span data-stu-id="3195a-159">Not common</span></span>|<span data-ttu-id="3195a-160">各追加メール システムで次のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="3195a-160">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="3195a-161">\<IP_address\> と \<domain_name\> は、ドメインの代理としてメールを送信する他のメールシステムの IP アドレスとドメインです。</span><span class="sxs-lookup"><span data-stu-id="3195a-161">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="3195a-162">7</span><span class="sxs-lookup"><span data-stu-id="3195a-162">7</span></span>|<span data-ttu-id="3195a-163">いずれかの電子メール システム (必須)</span><span class="sxs-lookup"><span data-stu-id="3195a-163">Any email system (required)</span></span>|<span data-ttu-id="3195a-p110">共通。この値で終わるすべての SPF レコード</span><span class="sxs-lookup"><span data-stu-id="3195a-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="3195a-166">これは、いくつかの値のどれか 1 つかもしれません。</span><span class="sxs-lookup"><span data-stu-id="3195a-166">This can be one of several values.</span></span> <span data-ttu-id="3195a-167">値 `-all` をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3195a-167">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="3195a-168">まだ行っていない場合は、表の構文を使用して SPF TXT レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3195a-168">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="3195a-169">たとえば、Office 365 で完全にホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、2 行目、7 行目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3195a-169">For example, if you are fully-hosted in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="3195a-170">これは、最も一般的な SPF TXT レコードです。</span><span class="sxs-lookup"><span data-stu-id="3195a-170">This is the most common SPF TXT record.</span></span> <span data-ttu-id="3195a-171">このレコードは、Microsoft データセンターが米国、ヨーロッパ (ドイツを含む)、または他の場所にあっても、ほぼすべてのユーザーに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="3195a-171">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="3195a-p113">ただし、Microsoft Cloud Germany の一部である Office 365 Germany を購入している場合は、2 行目ではなく 4 行目から include ステートメントを使用してください。たとえば、Office 365 Germany で完全にホストされている場合、つまり、オンプレミスのメール サーバーを使っていない場合は、SPF TXT レコードには、次のように 1 行目、4 行目、7 行目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3195a-p113">However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="3195a-174">Office 365 で既に展開し、カスタム ドメインの SPF TXT レコードをセットアップしている状態で Office 365 Germany に移行する場合は、SPF TXT レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195a-174">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="3195a-175">これを行うには、`include:spf.protection.outlook.com` を`include:spf.protection.outlook.de`に変更します。</span><span class="sxs-lookup"><span data-stu-id="3195a-175">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="3195a-176">SPF TXT レコードを構成した後、DNS でレコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195a-176">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="3195a-177">ドメインに配置できる SPF TXT レコードは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="3195a-177">You can only have one SPF TXT record for a domain.</span></span> <span data-ttu-id="3195a-178">SPF TXT レコードが存在する場合、新しいレコードを追加するのではなく、既存のレコードを更新しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3195a-178">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="3195a-179">「[Office 365 の DNS レコードを作成する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」に移動し、DNS ホストのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3195a-179">Go to [Create DNS records for Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), and then click the link for your DNS host.</span></span>

4. <span data-ttu-id="3195a-180">SPF TXT レコードをテストします。</span><span class="sxs-lookup"><span data-stu-id="3195a-180">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="3195a-181">サブドメインの処理方法とは?</span><span class="sxs-lookup"><span data-stu-id="3195a-181">How to handle subdomains?</span></span>

<span data-ttu-id="3195a-182">*サブドメインは、トップ レベル ドメインの SPF レコードを継承しないので、サブドメインごとに、別々のレコードを作成する必要がある* ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3195a-182">It is important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top level domain*.</span></span>

<span data-ttu-id="3195a-183">存在しないサブドメインからのメールを、攻撃者が送信することを防ぐために、すべてのドメインとサブドメインに対して追加のワイルドカード SPF レコード (`*.`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="3195a-183">An additional wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="3195a-184">例:</span><span class="sxs-lookup"><span data-stu-id="3195a-184">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="3195a-185">SPF のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3195a-185">Troubleshooting SPF</span></span>

<span data-ttu-id="3195a-186">SPF TXT レコードで問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="3195a-186">Having trouble with your SPF TXT record?</span></span> <span data-ttu-id="3195a-187">[「トラブルシューティング: Office 365 における SPF のベスト プラクティス」](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="3195a-187">Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="3195a-188">SPF メール認証は、実際に何を行いますか?</span><span class="sxs-lookup"><span data-stu-id="3195a-188">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="3195a-189">SPF は、ユーザーのためにメールを送信できるメール サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="3195a-189">SPF identifies which mail servers are allowed to send mail on your behalf.</span></span> <span data-ttu-id="3195a-190">基本的には、SPF を DKIM、DMARC、その他の Office 365 でサポートされているテクノロジと併用することによって、スプーフィングとフィッシング詐欺を防止できます。</span><span class="sxs-lookup"><span data-stu-id="3195a-190">Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing.</span></span> <span data-ttu-id="3195a-191">SPF は TXT レコードとして追加され、DNS はこのレコードを使って、カスタム ドメインの代わりにメールを送信できるメール サーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="3195a-191">SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain.</span></span> <span data-ttu-id="3195a-192">受信側のメール システムは、この SPF TXT レコードを参照して、カスタム ドメインからのメッセージが、承認されたメッセージング サーバーからのものであるかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="3195a-192">Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="3195a-p119">たとえば、カスタム ドメイン contoso.com が Office 365 を使用しているとします。ユーザーのドメインの正当なメール サーバーとして Office 365 メッセージング サーバーを一覧表示する SPF TXT レコードを追加します。受信メッセージング サーバーが joe@contoso.com からのメッセージを取得すると、サーバーによって contoso.com の SPF TXT レコードが検索され、適切なメッセージであるかどうかが検出されます。受信サーバーで、SPF レコードに一覧表示されている Office 365 メッセージング サーバー以外のサーバーからメッセージを取得していることが検出された場合、受信メール サーバーはそのメッセージを迷惑メールとして拒否できます。</span><span class="sxs-lookup"><span data-stu-id="3195a-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="3195a-p120">また、カスタム ドメインに SPF TXT レコードが含まれていないと、一部の受信サーバーはメッセージを完全に拒否することがあります。これは、受信サーバーが、承認されたメッセージング サーバーからのメッセージであることを検証できないためです。</span><span class="sxs-lookup"><span data-stu-id="3195a-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="3195a-p121">既に Office 365 のメールを設定している場合、SPF TXT レコードとして Microsoft のメッセージング サーバーが DNS に含まれています。ただし、場合によっては DNS で SPF TXT レコードを更新する必要があります。たとえば、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="3195a-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="3195a-p122">以前は、SharePoint Online を使用している場合、カスタム ドメインに別の SPF TXT レコードを追加する必要がありました。この作業を行う必要はなくなりました。この変更により、SharePoint Online の通知メッセージが [迷惑メール] フォルダーに振り分けられるリスクが軽減されます。参照の制限数である 10 に達し、"参照制限を超えました"、"ホップが多すぎます" などのメッセージを示すエラーが表示される場合は、SPF TXT レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="3195a-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="3195a-206">Office 365 とオンプレミスの Exchange を使用したハイブリッド環境の場合。</span><span class="sxs-lookup"><span data-stu-id="3195a-206">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="3195a-207">DKIM と DMARC をセットアップする場合 (推奨)。</span><span class="sxs-lookup"><span data-stu-id="3195a-207">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="3195a-208">SPF の詳細情報</span><span class="sxs-lookup"><span data-stu-id="3195a-208">More information about SPF</span></span>

<span data-ttu-id="3195a-209">サポートされている SPF 構文、スプーフィング、トラブルシューティング、Office 365 が SPF をサポートする方法の高度な例や詳細については、「[Office 365 において SPF がスプーフィングとフィッシングを防ぐしくみ](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3195a-209">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="links-to-configure-dkim-and-dmarc"></a><span data-ttu-id="3195a-210">DKIM と DMARC を構成するリンク</span><span class="sxs-lookup"><span data-stu-id="3195a-210">Links to configure DKIM and DMARC</span></span>

 <span data-ttu-id="3195a-211">SPF はスプーフィングの防止に役立ちますが、SPF では保護できないスプーフィング テクニックがあります。</span><span class="sxs-lookup"><span data-stu-id="3195a-211">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="3195a-212">それらから保護するには、SPF のセットアップ後に、DKIM と DMARC を Office 365 用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3195a-212">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="3195a-213">[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) メール認証の目標は、メールの内容が改ざんされていないと証明することです。</span><span class="sxs-lookup"><span data-stu-id="3195a-213">[DKIM](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="3195a-214">[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) メール認証の目標は、SPF と DKIM の情報が From アドレスと確実に一致していることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="3195a-214">[DMARC](https://docs.microsoft.com/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>