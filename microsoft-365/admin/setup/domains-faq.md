---
title: ドメインに関する FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: ドメインの詳細については、よく寄せられる質問への回答を検索してください。
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049738"
---
# <a name="domains-faq"></a><span data-ttu-id="bac55-103">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="bac55-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bac55-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="bac55-104">The admin center is changing.</span></span> <span data-ttu-id="bac55-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac55-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="bac55-106">この記事では、Microsoft 365 のドメインに関してよく寄せられる質問に対する回答を示します。</span><span class="sxs-lookup"><span data-stu-id="bac55-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="bac55-107">質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="bac55-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="bac55-108">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="bac55-108">In this article</span></span>

<span data-ttu-id="bac55-109">[MX 優先度](#what-is-mx-priority) 
 とは[自分のドメインの SPF レコードを検証するにはどうすればよいですか?](#how-can-i-validate-spf-records-for-my-domain) 
[ドメイン名](#what-is-a-domain-name) 
 とは[DNS プロバイダーが特定のレコードの種類をサポートしていない場合はどうなりますか?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
[Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
[Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
["Onmicrosoft.com" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftcom-domain) 
["Onmicrosoft.de" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftde-domain) 
非[営利団体または教育機関の状態を確認するには](#how-do-i-verify-my-nonprofit-or-education-status)どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="bac55-110">MX 優先度とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-110">What is MX priority?</span></span>

<span data-ttu-id="bac55-111">メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="bac55-112">MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="bac55-113">ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bac55-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="bac55-114">数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bac55-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="bac55-115">MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。</span><span class="sxs-lookup"><span data-stu-id="bac55-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="bac55-116">複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bac55-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="bac55-117">SPF レコードはどうやって検証できますか?</span><span class="sxs-lookup"><span data-stu-id="bac55-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="bac55-118">**SPF の TXT レコードを1つだけ**持っているか作成しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="bac55-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="bac55-119">既に SPF レコードがある場合は、新しい Microsoft 365 値を作成するのではなく、新しい Microsoft 値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="bac55-120">Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bac55-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="bac55-121">SPF レコード テスト ツール</span><span class="sxs-lookup"><span data-stu-id="bac55-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="bac55-122">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="bac55-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="bac55-123">Dig Web インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bac55-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="bac55-124">ドメイン名とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-124">What is a domain name?</span></span>

<span data-ttu-id="bac55-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="bac55-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="bac55-126">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="bac55-126">in web addresses.</span></span> <span data-ttu-id="bac55-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="bac55-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="bac55-128">Microsoft 365 で "**渡 \@ contoso.com**" のようなカスタムドメインを使用すると、ブランドの信頼性と認識を構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bac55-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="bac55-129">[Microsoft 365 でドメインを購入し、自動的に設定](../get-help-with-domains/buy-a-domain-name.md)することも、ドメインレジストラーで購入したり、既に所有しているドメインを購入したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bac55-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="bac55-130">DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="bac55-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="bac55-131">独自の DNS レコードを管理していて、DNS ホストが Microsoft 365 に必要なすべての DNS レコードをサポートしていない場合は、一部の Microsoft 365 機能が動作しません。</span><span class="sxs-lookup"><span data-stu-id="bac55-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="bac55-132">必要な DNS レコードをすべてサポートしているレジストラーにドメインを移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bac55-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="bac55-133">すべての必須の DNS レコードをサポートするプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="bac55-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="bac55-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="bac55-134">Dynadot</span></span>
    
- <span data-ttu-id="bac55-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="bac55-135">eNomCentral</span></span>
    
- <span data-ttu-id="bac55-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="bac55-136">Europe Registry</span></span>
    
- <span data-ttu-id="bac55-137">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="bac55-137">GoDaddy</span></span>
    
- <span data-ttu-id="bac55-138">Hover</span><span class="sxs-lookup"><span data-stu-id="bac55-138">Hover</span></span>
    
- <span data-ttu-id="bac55-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="bac55-139">MyHosting.com</span></span>
    
- <span data-ttu-id="bac55-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="bac55-140">Name.com</span></span>
    
- <span data-ttu-id="bac55-141">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="bac55-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="bac55-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="bac55-142">Nettica</span></span>
    
- <span data-ttu-id="bac55-143">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="bac55-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="bac55-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="bac55-144">Network Solutions</span></span>
    
- <span data-ttu-id="bac55-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="bac55-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="bac55-146">Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="bac55-147">既定のドメインを選択するには、少なくとも1つのカスタムドメインが Microsoft 365 に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bac55-148">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bac55-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bac55-149">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bac55-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bac55-150">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bac55-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="bac55-151">[**ドメイン**] ページで、新しいメール アドレスの既定として設定するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bac55-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="bac55-152">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bac55-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="bac55-153">*.onmicrosoft.com* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="bac55-154">*.onmicrosoft.de* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="bac55-155">*.partner.onmschina.cn* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="bac55-156">Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。</span><span class="sxs-lookup"><span data-stu-id="bac55-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="bac55-157">はい。</span><span class="sxs-lookup"><span data-stu-id="bac55-157">Yes.</span></span> <span data-ttu-id="bac55-158">サブドメインを追加するには、レジストラーの web サイトで独自の DNS 設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bac55-159">NS レコードでの DNS 設定の管理を行う場合や、Microsoft からドメインを購入した場合は、サブドメインを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="bac55-160">Yes!</span><span class="sxs-lookup"><span data-stu-id="bac55-160">Yes!</span></span> <span data-ttu-id="bac55-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="bac55-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bac55-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span><span class="sxs-lookup"><span data-stu-id="bac55-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="bac55-163">Yes!</span><span class="sxs-lookup"><span data-stu-id="bac55-163">Yes!</span></span> <span data-ttu-id="bac55-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="bac55-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="bac55-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span><span class="sxs-lookup"><span data-stu-id="bac55-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="bac55-166">通常、Microsoft 365 サブスクリプションには最大900のドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bac55-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="bac55-167">例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="bac55-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="bac55-168">サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。</span><span class="sxs-lookup"><span data-stu-id="bac55-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="bac55-169">Microsoft 365 に複数のドメインを追加する場合は、追加した任意のドメインで任意のサービス (電子メールなど) をホストできます。</span><span class="sxs-lookup"><span data-stu-id="bac55-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="bac55-170">*電子メールを Microsoft 365 に変更すると、ドメインの MX レコードを更新すると、そのドメインに送信されるすべての電子メールが Microsoft 365 に送られ始めます。*</span><span class="sxs-lookup"><span data-stu-id="bac55-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="bac55-171">Contoso.com ドメインを Microsoft 365 サブスクリプションに追加した場合は、他の Microsoft 365 組織にサブドメイン xyz.contoso.com を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bac55-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="bac55-172">サブドメインを追加する際に、DNS ホスティングプロバイダーに TXT レコードを追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bac55-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="bac55-173">"onmicrosoft.com" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="bac55-174">Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.com*などのドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="bac55-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="bac55-175">サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.com*のようなドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bac55-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="bac55-176">\***Alan \@ contoso.com\*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="bac55-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="bac55-177">**サインアップ後に onmicrosoft ドメインの名前は変更できません** 。</span><span class="sxs-lookup"><span data-stu-id="bac55-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="bac55-178">たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.com の場合、fabrikam.onmicrosoft.com に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="bac55-179">別の onmicrosoft.com ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="bac55-180">**You can't rename your team site URL.**</span><span class="sxs-lookup"><span data-stu-id="bac55-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="bac55-181">Your team site URL is based on your onmicrosoft.com domain name.</span><span class="sxs-lookup"><span data-stu-id="bac55-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="bac55-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span><span class="sxs-lookup"><span data-stu-id="bac55-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="bac55-183">**onmicrosoft ドメインは、削除できません。**</span><span class="sxs-lookup"><span data-stu-id="bac55-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="bac55-184">Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="bac55-185">カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bac55-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="bac55-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="bac55-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="bac55-187">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="bac55-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="bac55-188">"onmicrosoft.de" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="bac55-189">Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.de*などのドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="bac55-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="bac55-190">サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.de*のようなドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bac55-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="bac55-191">\***Alan@contoso.de\*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="bac55-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="bac55-192">**サインアップ後に onmicrosoft ドメインの名前は変更できません** 。</span><span class="sxs-lookup"><span data-stu-id="bac55-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="bac55-193">たとえば、選択した初期ドメインが fourthcoffee.onmicrosoft.de の場合、fabrikam.onmicrosoft.de に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bac55-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="bac55-194">別の onmicrosoft.de ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="bac55-195">**You can't rename your team site URL.**</span><span class="sxs-lookup"><span data-stu-id="bac55-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="bac55-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span><span class="sxs-lookup"><span data-stu-id="bac55-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="bac55-197">**onmicrosoft ドメインは、削除できません。**</span><span class="sxs-lookup"><span data-stu-id="bac55-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="bac55-198">Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac55-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="bac55-199">カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bac55-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="bac55-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="bac55-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="bac55-201">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="bac55-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="bac55-202">非営利団体または教育機関のステータスを確認するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="bac55-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="bac55-203">[管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="bac55-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="bac55-204">(必ず Microsoft 365 にサインインしてください)。</span><span class="sxs-lookup"><span data-stu-id="bac55-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="bac55-205">学校の管理者になるには、Microsoft 365 で [**管理者になる**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bac55-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="bac55-206">ドメインの DNS ホスト web サイトに TXT DNS レコードを追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bac55-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="bac55-207">それはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bac55-207">Why?</span></span> <span data-ttu-id="bac55-208">DNS ホストでサインインし、ドメインのレコードを追加することにより、Microsoft 365 にドメイン名を所有していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="bac55-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="bac55-209">レコードを追加した後、Microsoft 365 ポータルに戻り、追加されたことを確認して、Microsoft 365 で確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bac55-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="bac55-210">非営利団体があり、Microsoft 365 を入手する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="bac55-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="bac55-211">[組織に資格](https://www.microsoft.com/en-us/nonprofits/eligibility)があることを確認してから、サービスにサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bac55-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="bac55-212">学校の管理者になる方法の詳細については、</span><span class="sxs-lookup"><span data-stu-id="bac55-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="bac55-213">[こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="bac55-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>