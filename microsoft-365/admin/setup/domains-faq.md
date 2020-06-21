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
description: ドメインの詳細については、よく寄せられる質問の回答を参照してください。
ms.openlocfilehash: a52513130f9bbbf7c4cd25d4c4827e833700d992
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739154"
---
# <a name="domains-faq"></a><span data-ttu-id="dbba8-103">ドメイン FAQ</span><span class="sxs-lookup"><span data-stu-id="dbba8-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dbba8-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-104">The admin center is changing.</span></span> <span data-ttu-id="dbba8-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbba8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="dbba8-106">この記事では、Office 365 のドメインに関してよく寄せられる質問にお答えします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="dbba8-107">質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="dbba8-108">MX 優先度とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-108">What is MX priority?</span></span>

<span data-ttu-id="dbba8-109">メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="dbba8-110">MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="dbba8-111">ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="dbba8-112">数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="dbba8-113">MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="dbba8-114">複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="dbba8-115">SPF レコードはどうやって検証できますか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="dbba8-116">**SPF の TXT レコードを 1 つだけ** 持っているか作成していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="dbba8-117">既に SPF レコードがある場合は、新規に作成せずに、新しい Office 365 の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="dbba8-118">Microsoft メールの SPF レコードを追加または更新した後、次のいずれかのツールを使用して構文が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbba8-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="dbba8-119">SPF レコード テスト ツール</span><span class="sxs-lookup"><span data-stu-id="dbba8-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="dbba8-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="dbba8-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="dbba8-121">Dig Web インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbba8-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="dbba8-122">Office 365 では DNS レコードはどのように管理されますか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="dbba8-123">Office 365 での DNS 管理には 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="dbba8-124">ネームサーバー (NS) レコードを変更すると、メール用の MX レコードを設定するのと同様に、Microsoft はすべてのサービス固有のレコードを処理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="dbba8-125">**(推奨)**</span><span class="sxs-lookup"><span data-stu-id="dbba8-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="dbba8-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span><span class="sxs-lookup"><span data-stu-id="dbba8-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="dbba8-127">**(Experts only)**</span><span class="sxs-lookup"><span data-stu-id="dbba8-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="dbba8-128">Office 365 で DNS レコードが作成され、ホストされます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="dbba8-129">**メリット**</span><span class="sxs-lookup"><span data-stu-id="dbba8-129">**Advantages**</span></span> 
- <span data-ttu-id="dbba8-130">Office 365 サービスの DNS レコードの入力ミスについて心配する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="dbba8-131">ドメインレジストラーと DNS ホストを自由に選べます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="dbba8-132">ネーム サーバー レコードの変更を許可しているプロバイダーであれば、必要なレコード タイプの一部をサポートしていないプロバイダーであっても、問題なく機能します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="dbba8-133">Office 365 が新しい DNS レコードを追加しても、ユーザーは更新を行う必要がありません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="dbba8-134">デメリット</span><span class="sxs-lookup"><span data-stu-id="dbba8-134">Disadvantages</span></span> 
- <span data-ttu-id="dbba8-135">Office 365 の外部では、DNS レコードを変更してメールをホストすることができません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="dbba8-136">一般向け Web サイトのアドレス (例: www.fourthcoffee.com) としてドメインをすでに使用している場合、ユーザーを Office 365 からそのアドレスにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="dbba8-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span><span class="sxs-lookup"><span data-stu-id="dbba8-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="dbba8-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span><span class="sxs-lookup"><span data-stu-id="dbba8-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="dbba8-139">DNS レコードを自分で管理する</span><span class="sxs-lookup"><span data-stu-id="dbba8-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="dbba8-140">メリット</span><span class="sxs-lookup"><span data-stu-id="dbba8-140">Advantages</span></span>
- <span data-ttu-id="dbba8-141">Office 365 サービスの DNS レコードを自分で管理できます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="dbba8-142">アドレスに自分のドメインが含まれる公開 Web サイト (www.fourthcoffee.com など) がある場合は、Office 365 でドメインをセットアップした後、ユーザーが引き続きその Web サイトを表示できるようにするために、リダイレクションの使用について考える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="dbba8-143">メールをオンプレミスの Exchange サーバーなどでホストすることができる柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="dbba8-144">デメリット</span><span class="sxs-lookup"><span data-stu-id="dbba8-144">Disadvantages</span></span>
<span data-ttu-id="dbba8-145">Office 365 の DNS レコードを自分で設定する必要があります (GoDaddy ドメインを所有している場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="dbba8-146">現在の DNS ホストが Microsoft 365 に必要なレコードの種類の一部をサポートしていない場合は、一部の機能を使用できないため、別の DNS ホストに切り替える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="dbba8-147">Office 365 で DNS レコードの要件が変更されたり新しいサービスが追加されたりした場合、DNS ホストでの更新を自分で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="dbba8-148">ドメイン名とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-148">What is a domain name?</span></span>


<span data-ttu-id="dbba8-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="dbba8-150">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="dbba8-150">in web addresses.</span></span> <span data-ttu-id="dbba8-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="dbba8-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="dbba8-152">Office 365 で「**rob\@contoso.com**」のようなカスタム ドメインを使用すると、ブランドの信頼性や認知度を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="dbba8-153">[Office 365 でドメインを購入して](../get-help-with-domains/buy-a-domain-name.md) 自動的に設定するか、ドメイン レジストラーで購入したり、入手済みのドメインを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="dbba8-154">Microsoft から購入したドメインを別のプロバイダーに移行できますか。</span><span class="sxs-lookup"><span data-stu-id="dbba8-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="dbba8-155">はい。ただし Office 365 での購入後 60 日を経過するまでは、他のレジストラーに Office 365 ドメインを移行できません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="dbba8-156">*Whois* クエリ上では Office 365 で購入したドメイン レジストラーが Wild West Domains LLC として表示されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="dbba8-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="dbba8-157">ただし Office 365 で購入したドメインに関しては Office 365 にのみお問い合わせ可能です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="dbba8-158">以下の手順に従って Office 365 からコードを取得し、その後別のドメイン レジストラーの Web サイトで、そのレジストラーへのドメイン名の移行を設定します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dbba8-159">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="dbba8-160">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dbba8-161">管理センターで、[**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="dbba8-162">[**ドメイン**] ページで、別のドメイン レジストラーへ移行させる Office 365 ドメインを選択し、[**ドメインの移行**]  >  [**ドメインの移行の有効化**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="dbba8-163">手順に従って、ドメインの移行を準備します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="dbba8-164">コードを取得したら、ドメイン名の管理に使用するドメイン レジストラーの Web サイトに移動し、サイトの指示に従って、ドメインを移行します (方法についてはレジストラーのヘルプを参照)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="dbba8-165">コードをもう一度表示する必要がある場合は、Office 365 の [**ドメイン設定**] ページで、[**ドメイン移行の認証コードの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="dbba8-166">移行の完了後は、新しいドメイン レジストラーでドメインの更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="dbba8-167">手順を完了するには、管理センターの [**ドメイン**] ページに戻り、[**ドメイン移行の完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="dbba8-168">*注: Office 365 で購入したドメインは、ネーム サーバーの変更または Office 365 テナント間でのドメインの移行の対象外です。 これらのいずれかが必要な場合、ドメイン登録を別のレジストラーに移行する必要があります。*</span><span class="sxs-lookup"><span data-stu-id="dbba8-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="dbba8-169">Office 365 での DNS レコードの管理方法はどうやって変えるのですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="dbba8-170">DNS の管理を Office 365 以外の DNS ホストで行うように変更する</span><span class="sxs-lookup"><span data-stu-id="dbba8-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="dbba8-171">自分のドメインのドメイン レジストラーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="dbba8-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span><span class="sxs-lookup"><span data-stu-id="dbba8-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="dbba8-173">(The DNS host is often the domain registrar.)</span><span class="sxs-lookup"><span data-stu-id="dbba8-173">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="dbba8-174">リンクにアクセスし、ドメインのセットアップ ウィザードに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="dbba8-175">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="dbba8-176">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="dbba8-177">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="dbba8-178">[**ドメイン**] ページで、切り替えを行うドメインを選び、[**DNSの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="dbba8-179">ドメインのセットアップ ウィザードの [**オンライン サービスの設定**] ページで、[**自分の DNS レコードを管理する**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="dbba8-180">[**DNS 設定の更新**] ページのウィザードが推奨する DNS レコードを自分のレジストラーの Web サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="dbba8-181">レコードを追加したら、Office 365 に戻って [**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="dbba8-182">DNS 管理を Office 365 に変更する</span><span class="sxs-lookup"><span data-stu-id="dbba8-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dbba8-183">管理センターで、[ドメインの**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="dbba8-184">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dbba8-185">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="dbba8-186">[**ドメイン**] ページで、切り替えを行うドメインを選び、[**DNS の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="dbba8-187">ドメインのセットアップ ウィザードの [**オンライン サービスの設定**] ページで、[**自分用にオンライン サービスをセットアップします。(推奨)**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="dbba8-188">ドメインの確認をまだ行っていない場合は、手順に従って最初にそれを行います。</span><span class="sxs-lookup"><span data-stu-id="dbba8-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="dbba8-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbba8-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="dbba8-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span><span class="sxs-lookup"><span data-stu-id="dbba8-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="dbba8-191">ネームサーバーを更新したら、**1 時間以上待ちます**。</span><span class="sxs-lookup"><span data-stu-id="dbba8-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="dbba8-192">その後、Office 365 のウィザードに戻り、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="dbba8-193">DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="dbba8-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span><span class="sxs-lookup"><span data-stu-id="dbba8-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="dbba8-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span><span class="sxs-lookup"><span data-stu-id="dbba8-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="dbba8-196">すべての必須の DNS レコードをサポートするプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="dbba8-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="dbba8-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="dbba8-197">Dynadot</span></span>
    
- <span data-ttu-id="dbba8-198">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="dbba8-198">eNomCentral</span></span>
    
- <span data-ttu-id="dbba8-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="dbba8-199">Europe Registry</span></span>
    
- <span data-ttu-id="dbba8-200">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="dbba8-200">GoDaddy</span></span>
    
- <span data-ttu-id="dbba8-201">Hover</span><span class="sxs-lookup"><span data-stu-id="dbba8-201">Hover</span></span>
    
- <span data-ttu-id="dbba8-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="dbba8-202">MyHosting.com</span></span>
    
- <span data-ttu-id="dbba8-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="dbba8-203">Name.com</span></span>
    
- <span data-ttu-id="dbba8-204">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="dbba8-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="dbba8-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="dbba8-205">Nettica</span></span>
    
- <span data-ttu-id="dbba8-206">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="dbba8-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="dbba8-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="dbba8-207">Network Solutions</span></span>
    
- <span data-ttu-id="dbba8-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="dbba8-208">Register.com</span></span>
    
 <span data-ttu-id="dbba8-209">**SRV レコードがサポートされない場合** 、次の Office 365 機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="dbba8-210">Skype for Business Online IM およびプレゼンスの Outlook Web App との統合</span><span class="sxs-lookup"><span data-stu-id="dbba8-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="dbba8-211">他の組織の Skype for Business Online ユーザーとの外部通信 (フェデレーション)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="dbba8-212">公衆インターネット接続 (PIC) (Skype for Business Online のユーザーが Microsoft アカウント (旧称: Windows Live ID) を使用してサインインする場合)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="dbba8-213">**複数の CNAME レコードがサポートされてない場合は、** 次の Skype for Business Online の機能の中から機能を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="dbba8-214">メール デスクトップ クライアントとモバイル クライアントでは、自動検出を使用して Exchange Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="dbba8-215">Skype for Business Online デスクトップ クライアントでは、自動検出を使用して Skype for Business Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="dbba8-216">Skype for Business Online モバイル クライアントでは、自動検出を使用して Skype for Business Online サービスが自動的に検出されるため、ユーザーはサーバー名を入力せずにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>

- <span data-ttu-id="dbba8-217">Microsoft Teams は、オンプレミスまたはオンラインのいずれかの Skype for Business とフェデレーションを行います。</span><span class="sxs-lookup"><span data-stu-id="dbba8-217">Microsoft Teams federation with Skype for Business, either on-premises or online.</span></span> <span data-ttu-id="dbba8-218">詳細については、「 [Microsoft Teams 用に組織のネットワークを準備](https://docs.microsoft.com/microsoftteams/prepare-network)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbba8-218">For more information, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>
    
 <span data-ttu-id="dbba8-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span><span class="sxs-lookup"><span data-stu-id="dbba8-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="dbba8-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="dbba8-221">Office 365 の既定のドメインを設定または変更する方法</span><span class="sxs-lookup"><span data-stu-id="dbba8-221">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="dbba8-222">既定のドメインを選択するには、1 つ以上のカスタム ドメインが Office 365 に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-222">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="dbba8-223">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-223">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="dbba8-224">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-224">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="dbba8-225">管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-225">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="dbba8-226">[**ドメイン**] ページで、新しいメール アドレスの既定として設定するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-226">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="dbba8-227">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-227">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="dbba8-228">*.onmicrosoft.com* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-228">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="dbba8-229">*.onmicrosoft.de* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-229">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="dbba8-230">*.partner.onmschina.cn* ドメインの最初の部分の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-230">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="dbba8-231">Office 365 でカスタム サブドメインまたは複数のドメインを追加することはできますか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-231">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="dbba8-232">Yes!</span><span class="sxs-lookup"><span data-stu-id="dbba8-232">Yes!</span></span> <span data-ttu-id="dbba8-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="dbba8-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="dbba8-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span><span class="sxs-lookup"><span data-stu-id="dbba8-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="dbba8-235">Yes!</span><span class="sxs-lookup"><span data-stu-id="dbba8-235">Yes!</span></span> <span data-ttu-id="dbba8-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="dbba8-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="dbba8-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span><span class="sxs-lookup"><span data-stu-id="dbba8-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="dbba8-238">Yes!</span><span class="sxs-lookup"><span data-stu-id="dbba8-238">Yes!</span></span> <span data-ttu-id="dbba8-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span><span class="sxs-lookup"><span data-stu-id="dbba8-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="dbba8-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span><span class="sxs-lookup"><span data-stu-id="dbba8-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="dbba8-241">通常、最大 900 のドメインを Office 365 サブスクリプションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-241">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="dbba8-242">例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-242">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="dbba8-243">サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-243">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="dbba8-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span><span class="sxs-lookup"><span data-stu-id="dbba8-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="dbba8-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span><span class="sxs-lookup"><span data-stu-id="dbba8-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="dbba8-246">contoso.com ドメインを既に Office 365 テナントに追加している場合は、サブドメイン xyz.contoso.com を別の Office 365 テナントに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-246">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="dbba8-247">サブドメインを追加すると、DNS ホスティング プロバイダーに TXT レコードを追加するように求められます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-247">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="dbba8-248">"onmicrosoft.com" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-248">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="dbba8-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span><span class="sxs-lookup"><span data-stu-id="dbba8-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="dbba8-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="dbba8-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="dbba8-251">***alan\@contoso.com* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-251">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="dbba8-252">**You can't rename the onmicrosoft domain after sign-up.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-252">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="dbba8-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="dbba8-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="dbba8-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbba8-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="dbba8-255">**You can't rename your team site URL.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-255">**You can't rename your team site URL.**</span></span> <span data-ttu-id="dbba8-256">Your team site URL is based on your onmicrosoft.com domain name.</span><span class="sxs-lookup"><span data-stu-id="dbba8-256">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="dbba8-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span><span class="sxs-lookup"><span data-stu-id="dbba8-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="dbba8-258">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-258">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="dbba8-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="dbba8-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="dbba8-260">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-260">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="dbba8-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="dbba8-262">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="dbba8-262">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="dbba8-263">"onmicrosoft.de" ドメインがあるのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-263">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="dbba8-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span><span class="sxs-lookup"><span data-stu-id="dbba8-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="dbba8-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="dbba8-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="dbba8-266">***alan@contoso.de* のように表示されるメール アドレスを希望する場合は、**[ドメインを購入](../get-help-with-domains/buy-a-domain-name.md)するか、または「[Office 365 にユーザーとドメインを追加する](add-domain.md)」の手順に従って操作します (既にドメインを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-266">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="dbba8-267">**You can't rename the onmicrosoft domain after sign-up.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-267">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="dbba8-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="dbba8-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="dbba8-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbba8-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="dbba8-270">**You can't rename your team site URL.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-270">**You can't rename your team site URL.**</span></span> <span data-ttu-id="dbba8-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span><span class="sxs-lookup"><span data-stu-id="dbba8-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="dbba8-272">**You can't remove your onmicrosoft domain.**</span><span class="sxs-lookup"><span data-stu-id="dbba8-272">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="dbba8-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span><span class="sxs-lookup"><span data-stu-id="dbba8-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="dbba8-274">But you don't have to use the domain yourself after you've added a custom domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-274">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="dbba8-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="dbba8-276">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="dbba8-276">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="dbba8-277">非営利団体または教育機関のステータスを確認するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-277">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="dbba8-278">[管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-278">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="dbba8-279">(最初に Office 365 にサインインしてください。)</span><span class="sxs-lookup"><span data-stu-id="dbba8-279">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="dbba8-280">学校の管理者になるには、Office 365 で [**管理者になる**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-280">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="dbba8-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span><span class="sxs-lookup"><span data-stu-id="dbba8-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="dbba8-282">Why?</span><span class="sxs-lookup"><span data-stu-id="dbba8-282">Why?</span></span> <span data-ttu-id="dbba8-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span><span class="sxs-lookup"><span data-stu-id="dbba8-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="dbba8-284">レコードを追加したら Office 365 ポータルに戻り、レコードを追加したことを確認します。そうすると、Office 365 で確認が行われます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-284">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="dbba8-285">Have a nonprofit and want to get Office 365?</span><span class="sxs-lookup"><span data-stu-id="dbba8-285">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="dbba8-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span><span class="sxs-lookup"><span data-stu-id="dbba8-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="dbba8-287">学校の管理者になる方法の詳細については、</span><span class="sxs-lookup"><span data-stu-id="dbba8-287">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="dbba8-288">[こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="dbba8-288">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="dbba8-289">カスタム ドメインの少数のメール アドレスだけを使用して Office 365 の試験運用をすることは可能ですか?</span><span class="sxs-lookup"><span data-stu-id="dbba8-289">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="dbba8-290">可能ですが、制約があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-290">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="dbba8-291">現在のメール プロバイダーで、メール転送のサービスが提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-291">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="dbba8-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span><span class="sxs-lookup"><span data-stu-id="dbba8-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="dbba8-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span><span class="sxs-lookup"><span data-stu-id="dbba8-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="dbba8-294">一部の Office 365 の機能は利用できません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-294">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="dbba8-295">ユーザーは、もう 1 つのメール プロバイダーを利用するユーザーの空き時間情報を表示できません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-295">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="dbba8-296">管理者は、1 か所からすべてのユーザーのアカウントを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-296">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="dbba8-297">ユーザーは Office 365 のスパム フィルターを利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-297">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="dbba8-298">Office 365 パイロットをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="dbba8-298">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="dbba8-299">Microsoft 365 管理センターにサインインする</span><span class="sxs-lookup"><span data-stu-id="dbba8-299">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="dbba8-300">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-300">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="dbba8-301">[**設定**] \> [**ドメイン**] の順に移動します。  </span><span class="sxs-lookup"><span data-stu-id="dbba8-301">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="dbba8-302">使用するドメインを所有していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-302">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="dbba8-303">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-303">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="dbba8-304">パネルで、ドメインを入力し (この例の場合、cohowinery.com)、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-304">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="dbba8-305">[**ドメインの確認**] ページで手順に沿って操作します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-305">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="dbba8-306">ドロップダウン リストから自分の DNS ホスティング プロバイダーを選択し、手順に沿って操作してこのドメインを所有していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-306">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="dbba8-307">[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-307">Select **Verify**.</span></span> <span data-ttu-id="dbba8-308">DNS の変更が有効になるまでの時間は、数分から 72 時間です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-308">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="dbba8-309">確認が成功すると、DNS レコードを変更するように求められます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-309">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="dbba8-310">Exchange Online で、このドメインを共有ドメインとして設定します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-310">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="dbba8-311">**Exchange 管理センター** (EAC) に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-311">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="dbba8-312">[**メール フロー**] セクションで [**承認済みドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-312">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="dbba8-313">変更するドメインをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-313">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="dbba8-314">開いたウィンドウで、[**内部の中継**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-314">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="dbba8-315">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-315">Select **Save**.</span></span> <span data-ttu-id="dbba8-316">設定が有効になるまでに数分間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-316">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="dbba8-317">オプションで、既存のメール サーバーのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-317">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="dbba8-318">Office 365 は、Exchange Online Protection (EOP) を使用してスパム保護を行います。</span><span class="sxs-lookup"><span data-stu-id="dbba8-318">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="dbba8-319">EOP が現在のメールサーバーによって転送された大量のスパムを検出した場合は、それをブロックすることで、転送が動作しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-319">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="dbba8-320">他の電子メールプロバイダーが使用するスパム保護に自信がある場合は、そのサーバーを Office 365 の許可一覧に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-320">If you are confident with the spam protection your other email provider uses, you can add their server to an allow list in Office 365.</span></span> <span data-ttu-id="dbba8-321">ただし、これにより、元のサーバー経由で受信したすべてのスパムが Office 365 メールボックスに届くようにすることもできます。これにより、Office 365 がスパムを阻止しているかどうかを評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-321">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="dbba8-322">Exchange 管理センター (EAC)に移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-322">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="dbba8-323">EAC で、[**保護**]、[**接続フィルター**] の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-323">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="dbba8-324">[**IP 許可一覧**] で **+** を選択し、現在のメール プロバイダーから入手できるメール サーバー IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-324">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="dbba8-325">ユーザー アカウントを作成してプライマリ (Reply-To) アドレスを設定する</span><span class="sxs-lookup"><span data-stu-id="dbba8-325">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="dbba8-326">Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-326">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="dbba8-327">左側のナビゲーション バーで、[**ユーザー**] \> [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-327">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="dbba8-328">ユーザー アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="dbba8-328">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="dbba8-329">各アカウントについて、**+ (新規)** を選択し、必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-329">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="dbba8-330">ユーザーのメールを現在のものと同じにするには、[**ユーザー名**] フィールドの内容はユーザーの現在のメール アドレスと完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-330">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="dbba8-331">ユーザー名の横のドロップダウン リストからカスタム ドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-331">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="dbba8-332">[**作成**] \> [**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-332">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="dbba8-333">DNS ホスティング プロバイダーで DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="dbba8-333">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="dbba8-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="dbba8-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="dbba8-335">**Make the following exceptions:**</span><span class="sxs-lookup"><span data-stu-id="dbba8-335">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="dbba8-336">新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-336">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="dbba8-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span><span class="sxs-lookup"><span data-stu-id="dbba8-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="dbba8-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="dbba8-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="dbba8-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="dbba8-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="dbba8-340">This authorizes outgoing messages from both email systems.</span><span class="sxs-lookup"><span data-stu-id="dbba8-340">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="dbba8-341">現在のプロバイダーでのメール転送を設定する</span><span class="sxs-lookup"><span data-stu-id="dbba8-341">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="dbba8-342">現在のメール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーのメール アカウントで設定します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-342">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="dbba8-343">ユーザー A のメールボックスからの転送先は usera@yourcompany.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-343">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="dbba8-344">ユーザー B のメールボックスからの転送先は userb@yourcompany.onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="dbba8-344">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="dbba8-345">この手順が完了すると、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-345">When you complete this step:</span></span>
        
    5. <span data-ttu-id="dbba8-346">usera@yourcompany.onmicrosoft.com と userb@yourcompany.onmicrosoft.com へ送信されるすべてのメールは Office 365 で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="dbba8-346">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="dbba8-347">注:</span><span class="sxs-lookup"><span data-stu-id="dbba8-347">Notes:</span></span>
        
        - <span data-ttu-id="dbba8-348">転送の設定の詳細は、現在のメール プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="dbba8-348">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="dbba8-349">現在のメール プロバイダーでメッセージのコピーを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-349">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="dbba8-350">ほとんどのプロバイダーは、転送をするメールに Reply-to アドレスを残すため、返信メッセージは元の送信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-350">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="dbba8-351">メール フローのテスト</span><span class="sxs-lookup"><span data-stu-id="dbba8-351">Test mail flow</span></span>
    
    1. <span data-ttu-id="dbba8-352">ユーザー A の資格情報を使用して Outlook Web App にサインインします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-352">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="dbba8-353">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-353">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="dbba8-354">ローカル Microsoft メールをテストします。</span><span class="sxs-lookup"><span data-stu-id="dbba8-354">Test local Microsoft email.</span></span> <span data-ttu-id="dbba8-355">たとえば、ユーザー B に電子メールを送信します。この電子メールはすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="dbba8-355">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="dbba8-356">このシナリオでは、Office 365 はメールボックスをローカルとして認識するため、メッセージは元のサーバー上のユーザー B のメールボックスにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="dbba8-356">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="dbba8-357">Test email to someone who's on the other email system.</span><span class="sxs-lookup"><span data-stu-id="dbba8-357">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="dbba8-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span><span class="sxs-lookup"><span data-stu-id="dbba8-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="dbba8-359">外部アカウントから、または他の電子メールシステムの従業員の電子メールアカウントから、他のメールシステムで転送が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-359">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="dbba8-360">たとえば、User C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信して、そのメールがユーザー A の Office 365 メールボックスに届くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbba8-360">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="dbba8-361">メールボックスのコンテンツの移動</span><span class="sxs-lookup"><span data-stu-id="dbba8-361">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="dbba8-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span><span class="sxs-lookup"><span data-stu-id="dbba8-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="dbba8-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span><span class="sxs-lookup"><span data-stu-id="dbba8-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="dbba8-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="dbba8-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="dbba8-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span><span class="sxs-lookup"><span data-stu-id="dbba8-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
