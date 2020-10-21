---
title: ドメインに関する FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: b51b5fe56bbae56dd473dd831ec91e629d9233f3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644586"
---
# <a name="domains-faq"></a><span data-ttu-id="609dc-103">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="609dc-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="609dc-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="609dc-104">The admin center is changing.</span></span> <span data-ttu-id="609dc-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="609dc-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="609dc-106">この記事では、Microsoft 365 のドメインに関してよく寄せられる質問に対する回答を示します。</span><span class="sxs-lookup"><span data-stu-id="609dc-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="609dc-107">質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="609dc-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="609dc-108">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="609dc-108">In this article</span></span>

- [<span data-ttu-id="609dc-109">MX 優先度とは</span><span class="sxs-lookup"><span data-stu-id="609dc-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="609dc-110">自分のドメインの SPF レコードを検証するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="609dc-111">ドメイン名とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="609dc-112">自分の DNS プロバイダーが特定のレコードの種類をサポートしていない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="609dc-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="609dc-113">Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="609dc-114">Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。</span><span class="sxs-lookup"><span data-stu-id="609dc-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="609dc-115">Microsoft 365 から別のホストにドメインを移行するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="609dc-116">"onmicrosoft.com" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="609dc-117">"onmicrosoft.de" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="609dc-118">非営利団体または教育機関のステータスを確認するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="609dc-119">MX 優先度とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-119">What is MX priority?</span></span>

<span data-ttu-id="609dc-120">メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="609dc-121">MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="609dc-122">ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="609dc-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="609dc-123">数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="609dc-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="609dc-124">MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。</span><span class="sxs-lookup"><span data-stu-id="609dc-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="609dc-125">複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="609dc-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="609dc-126">SPF レコードはどうやって検証できますか?</span><span class="sxs-lookup"><span data-stu-id="609dc-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="609dc-127">**SPF の TXT レコードを1つだけ**持っているか作成しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="609dc-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="609dc-128">既に SPF レコードがある場合は、新しい Microsoft 365 値を作成するのではなく、新しい Microsoft 値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="609dc-129">Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="609dc-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="609dc-130">SPF レコード テスト ツール</span><span class="sxs-lookup"><span data-stu-id="609dc-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="609dc-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="609dc-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="609dc-132">Dig Web インターフェイス</span><span class="sxs-lookup"><span data-stu-id="609dc-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="609dc-133">ドメイン名とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-133">What is a domain name?</span></span>

<span data-ttu-id="609dc-p103">ドメインとは、メール アドレスの **@** 記号の後や、Web アドレスの **www.** の後に表示される固有の名前です。通常は、  *yourbusiness.com*  や  *stateuniversity.edu*  のように、組織の名前と標準的なインターネット サフィックスの形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="609dc-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="609dc-137">Microsoft 365 で "**渡 \@ contoso.com**" のようなカスタムドメインを使用すると、ブランドの信頼性と認識を構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="609dc-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="609dc-138">[Microsoft 365 でドメインを購入し、自動的に設定](../get-help-with-domains/buy-a-domain-name.md)することも、ドメインレジストラーで購入したり、既に所有しているドメインを購入したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="609dc-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="609dc-139">DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="609dc-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="609dc-140">独自の DNS レコードを管理していて、DNS ホストが Microsoft 365 に必要なすべての DNS レコードをサポートしていない場合は、一部の Microsoft 365 機能が動作しません。</span><span class="sxs-lookup"><span data-stu-id="609dc-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="609dc-141">必要な DNS レコードをすべてサポートしているレジストラーにドメインを移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="609dc-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="609dc-142">すべての必須の DNS レコードをサポートするプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="609dc-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="609dc-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="609dc-143">Dynadot</span></span>
    
- <span data-ttu-id="609dc-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="609dc-144">eNomCentral</span></span>
    
- <span data-ttu-id="609dc-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="609dc-145">Europe Registry</span></span>
    
- <span data-ttu-id="609dc-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="609dc-146">GoDaddy</span></span>
    
- <span data-ttu-id="609dc-147">Hover</span><span class="sxs-lookup"><span data-stu-id="609dc-147">Hover</span></span>
    
- <span data-ttu-id="609dc-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="609dc-148">MyHosting.com</span></span>
    
- <span data-ttu-id="609dc-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="609dc-149">Name.com</span></span>
    
- <span data-ttu-id="609dc-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="609dc-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="609dc-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="609dc-151">Nettica</span></span>
    
- <span data-ttu-id="609dc-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="609dc-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="609dc-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="609dc-153">Network Solutions</span></span>
    
- <span data-ttu-id="609dc-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="609dc-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="609dc-155">Microsoft 365 で既定のドメインを設定または変更するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="609dc-156">既定のドメインを選択するには、少なくとも1つのカスタムドメインが Microsoft 365 に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="609dc-157">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="609dc-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="609dc-158">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="609dc-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="609dc-159">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="609dc-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="609dc-160">[**ドメイン**] ページで、新しいメール アドレスの既定として設定するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="609dc-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="609dc-161">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="609dc-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="609dc-162">*.onmicrosoft.com* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="609dc-163">*.onmicrosoft.de* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="609dc-164">*.partner.onmschina.cn* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="609dc-165">Microsoft 365 にカスタムサブドメインまたは複数のドメインを追加できますか。</span><span class="sxs-lookup"><span data-stu-id="609dc-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="609dc-166">はい。</span><span class="sxs-lookup"><span data-stu-id="609dc-166">Yes.</span></span> <span data-ttu-id="609dc-167">サブドメインを追加するには、レジストラーの web サイトで独自の DNS 設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="609dc-168">NS レコードでの DNS 設定の管理を行う場合や、Microsoft からドメインを購入した場合は、サブドメインを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="609dc-p106">はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を Microsoft が行っている場合または Microsoft からドメインを購入した場合は、サブドメインを追加できません。</span><span class="sxs-lookup"><span data-stu-id="609dc-p106">Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="609dc-p107">はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を 21Vianet が行っている場合は、サブドメインを追加できません。</span><span class="sxs-lookup"><span data-stu-id="609dc-p107">Yes! To add subdomains, you must manage your own DNS settings at your registrar's website. If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="609dc-175">通常、Microsoft 365 サブスクリプションには最大900のドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="609dc-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="609dc-176">例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="609dc-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="609dc-177">サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。</span><span class="sxs-lookup"><span data-stu-id="609dc-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="609dc-178">Microsoft 365 に複数のドメインを追加する場合は、追加した任意のドメインで任意のサービス (電子メールなど) をホストできます。</span><span class="sxs-lookup"><span data-stu-id="609dc-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="609dc-179">*電子メールを Microsoft 365 に変更すると、ドメインの MX レコードを更新すると、そのドメインに送信されるすべての電子メールが Microsoft 365 に送られ始めます。*</span><span class="sxs-lookup"><span data-stu-id="609dc-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="609dc-180">Contoso.com ドメインを Microsoft 365 サブスクリプションに追加した場合は、他の Microsoft 365 組織にサブドメイン xyz.contoso.com を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="609dc-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="609dc-181">サブドメインを追加する際に、DNS ホスティングプロバイダーに TXT レコードを追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="609dc-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="609dc-182">Microsoft 365 から別のホストにドメインを移行するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="609dc-183">ドメインを移行する手順については、「 [Microsoft から別のホストへのドメインの移行](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="609dc-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="609dc-184">カスタムドメインから Microsoft 365 をパイロットする</span><span class="sxs-lookup"><span data-stu-id="609dc-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="609dc-185">Microsoft 365 の電子メール機能をカスタムドメインから Microsoft 365 メールボックスにパイロットする手順については、「 [カスタムドメインからの microsoft 365 のパイロット](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="609dc-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="609dc-186">"onmicrosoft.com" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="609dc-187">Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.com*などのドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="609dc-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="609dc-188">サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.com*のようなドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="609dc-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="609dc-189">\***Alan \@ contoso.com\*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="609dc-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="609dc-190">**サインアップ後に onmicrosoft ドメインの名前は変更できません** 。</span><span class="sxs-lookup"><span data-stu-id="609dc-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="609dc-191">たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.com の場合、fabrikam.onmicrosoft.com に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="609dc-192">別の onmicrosoft.com ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="609dc-p112">**チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.com ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="609dc-p112">**You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.com domain name. Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="609dc-196">**onmicrosoft ドメインは、削除できません。**</span><span class="sxs-lookup"><span data-stu-id="609dc-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="609dc-197">Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="609dc-198">カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="609dc-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="609dc-p114">ドメインを追加した後でも、初期の onmicrosoft.com ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="609dc-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="609dc-201">"onmicrosoft.de" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="609dc-202">Microsoft 365 は、サービスにサインアップするときに、 *contoso.onmicrosoft.de*などのドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="609dc-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="609dc-203">サインアップ時に作成するユーザー ID には、 *alan@contoso.onmicrosoft.de*のようなドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="609dc-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="609dc-204">\***Alan@contoso.de\*のように電子メールを表示する場合**は[、ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、既に所有している場合は「[ユーザーとドメインを Microsoft 365 に追加](add-domain.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="609dc-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="609dc-205">**サインアップ後に onmicrosoft ドメインの名前は変更できません** 。</span><span class="sxs-lookup"><span data-stu-id="609dc-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="609dc-206">たとえば、選択した初期ドメインが fourthcoffee.onmicrosoft.de の場合、fabrikam.onmicrosoft.de に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="609dc-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="609dc-207">別の onmicrosoft.de ドメインを使用するには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="609dc-p117">**チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.de ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="609dc-p117">**You can't rename your team site URL.** Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="609dc-210">**onmicrosoft ドメインは、削除できません。**</span><span class="sxs-lookup"><span data-stu-id="609dc-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="609dc-211">Microsoft 365 は、サブスクリプションの背後で使用されているため、これを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="609dc-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="609dc-212">カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="609dc-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="609dc-p119">ドメインを追加した後でも、初期の onmicrosoft.de ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="609dc-p119">You can keep using the initial onmicrosoft.de domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="609dc-215">非営利団体または教育機関のステータスを確認するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="609dc-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="609dc-216">[管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="609dc-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="609dc-217">(必ず Microsoft 365 にサインインしてください)。</span><span class="sxs-lookup"><span data-stu-id="609dc-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="609dc-218">学校の管理者になるには、Microsoft 365 で [  **管理者になる** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="609dc-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="609dc-219">ドメインの DNS ホスト web サイトに TXT DNS レコードを追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="609dc-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="609dc-220">それはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="609dc-220">Why?</span></span> <span data-ttu-id="609dc-221">DNS ホストでサインインし、ドメインのレコードを追加することにより、Microsoft 365 にドメイン名を所有していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="609dc-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="609dc-222">レコードを追加した後、Microsoft 365 ポータルに戻り、追加されたことを確認して、Microsoft 365 で確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="609dc-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="609dc-223">非営利団体があり、Microsoft 365 を入手する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="609dc-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="609dc-224">[組織に資格](https://www.microsoft.com/en-us/nonprofits/eligibility) があることを確認してから、サービスにサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="609dc-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="609dc-225">学校の管理者になる方法の詳細については、</span><span class="sxs-lookup"><span data-stu-id="609dc-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="609dc-226">[こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="609dc-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>