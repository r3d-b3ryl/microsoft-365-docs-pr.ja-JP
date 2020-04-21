---
title: Cloudflare で Microsoft 用の DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および Cloudflare for Microsoft の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629709"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="de405-103">Cloudflare で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="de405-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="de405-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de405-105">使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="de405-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="de405-106">Cloudflare でこれらのレコードを追加すると、使用しているドメインが、Microsoft 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="de405-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="de405-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="de405-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="de405-111">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="de405-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="de405-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de405-113">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de405-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="de405-114">Cloudflare にサインアップしたときに、Cloudflare の [ **Setup**] プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="de405-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="de405-115">追加したドメインは、別のドメインレジストラーから購入されました。Cloudflare では、ドメイン登録サービスは提供されていません。</span><span class="sxs-lookup"><span data-stu-id="de405-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="de405-116">Microsoft 365 でドメインの DNS レコードを確認および作成するには、まず、Cloudflare のネームサーバーを使用するようにドメインレジストラーでネームサーバーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de405-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="de405-117">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="de405-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="de405-118">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="de405-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="de405-119">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="de405-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="de405-120">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="de405-120">First nameserver</span></span>  <br/> |<span data-ttu-id="de405-121">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="de405-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="de405-122">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="de405-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="de405-123">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="de405-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="de405-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="de405-124">You should use at least two name server records.</span></span> <span data-ttu-id="de405-125">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de405-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="de405-126">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="de405-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="de405-127">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de405-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="de405-128">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="de405-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de405-129">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de405-129">Add a TXT record for verification</span></span>
<span data-ttu-id="de405-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="de405-131">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de405-131">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="de405-132">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="de405-132">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de405-p106">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="de405-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="de405-135">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de405-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="de405-136">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de405-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="de405-137">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="de405-138">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="de405-139">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="de405-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="de405-140">**Type**</span></span>|<span data-ttu-id="de405-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="de405-141">**Name**</span></span>|<span data-ttu-id="de405-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="de405-142">**Automatic TTL**</span></span>|<span data-ttu-id="de405-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="de405-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="de405-144">TXT</span><span class="sxs-lookup"><span data-stu-id="de405-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="de405-145">30 分</span><span class="sxs-lookup"><span data-stu-id="de405-145">30 minutes</span></span>  <br/> |<span data-ttu-id="de405-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="de405-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="de405-147">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="de405-147">**Note:** This is an example.</span></span> <span data-ttu-id="de405-148">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="de405-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="de405-149">確認する方法</span><span class="sxs-lookup"><span data-stu-id="de405-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="de405-150">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="de405-151">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="de405-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de405-152">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="de405-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="de405-153">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="de405-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de405-154">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="de405-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="de405-155">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="de405-156">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="de405-157">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="de405-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="de405-161">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="de405-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="de405-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="de405-p110">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de405-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="de405-165">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="de405-166">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="de405-167">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="de405-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="de405-168">**Type**</span></span>|<span data-ttu-id="de405-169">**名前**</span><span class="sxs-lookup"><span data-stu-id="de405-169">**Name**</span></span>|<span data-ttu-id="de405-170">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="de405-170">**Mail server**</span></span>|<span data-ttu-id="de405-171">**Priority**</span><span class="sxs-lookup"><span data-stu-id="de405-171">**Priority**</span></span>|<span data-ttu-id="de405-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de405-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de405-173">MX</span><span class="sxs-lookup"><span data-stu-id="de405-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="de405-174">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de405-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="de405-175">**注:** Microsoft 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="de405-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="de405-176">確認する方法</span><span class="sxs-lookup"><span data-stu-id="de405-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="de405-177">1-d</span><span class="sxs-lookup"><span data-stu-id="de405-177">1</span></span>  <br/> <span data-ttu-id="de405-178">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="de405-179">30 分</span><span class="sxs-lookup"><span data-stu-id="de405-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="de405-180">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="de405-181">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、[ **Delete (X)**] アイコンを選択してそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="de405-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="de405-182">確認ダイアログボックスで、[**削除**] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="de405-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="de405-183">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de405-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="de405-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="de405-p112">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de405-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="de405-187">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="de405-188">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="de405-189">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="de405-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="de405-190">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="de405-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="de405-191">**Type**</span></span>|<span data-ttu-id="de405-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="de405-192">**Name**</span></span>|<span data-ttu-id="de405-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="de405-193">**Target**</span></span>|<span data-ttu-id="de405-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de405-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de405-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-195">CNAME</span></span>  <br/> |<span data-ttu-id="de405-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="de405-196">autodiscover</span></span>  <br/> |<span data-ttu-id="de405-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de405-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="de405-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="de405-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-199">CNAME</span></span>  <br/> |<span data-ttu-id="de405-200">sip</span><span class="sxs-lookup"><span data-stu-id="de405-200">sip</span></span>  <br/> |<span data-ttu-id="de405-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de405-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="de405-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="de405-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-203">CNAME</span></span>  <br/> |<span data-ttu-id="de405-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="de405-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="de405-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de405-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="de405-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="de405-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-207">CNAME</span></span>  <br/> |<span data-ttu-id="de405-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="de405-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="de405-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="de405-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="de405-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="de405-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-211">CNAME</span></span>  <br/> |<span data-ttu-id="de405-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="de405-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="de405-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="de405-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="de405-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="de405-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="de405-215">CNAME</span></span>  <br/> |<span data-ttu-id="de405-216">msoid</span><span class="sxs-lookup"><span data-stu-id="de405-216">msoid</span></span>  <br/> |<span data-ttu-id="de405-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="de405-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="de405-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="de405-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="de405-219">[ **DNS トラフィック**] アイコン (オレンジのクラウド) を選択して、cloudflare サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="de405-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="de405-220">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="de405-221">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="de405-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="de405-222">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de405-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="de405-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de405-224">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="de405-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="de405-225">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="de405-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="de405-226">ドメインに対して既に SPF レコードがある場合は、Microsoft 365 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="de405-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="de405-227">代わりに、必要な Microsoft 365 値を現在のレコードに追加して、両方の値が含まれる*1 つ*の SPF レコードを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="de405-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="de405-228">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de405-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="de405-229">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de405-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="de405-230">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="de405-231">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="de405-232">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="de405-233">**Type**</span><span class="sxs-lookup"><span data-stu-id="de405-233">**Type**</span></span>|<span data-ttu-id="de405-234">**名前**</span><span class="sxs-lookup"><span data-stu-id="de405-234">**Name**</span></span>|<span data-ttu-id="de405-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de405-235">**TTL**</span></span>|<span data-ttu-id="de405-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="de405-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de405-237">TXT</span><span class="sxs-lookup"><span data-stu-id="de405-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="de405-238">30 分</span><span class="sxs-lookup"><span data-stu-id="de405-238">30 minutes</span></span>  <br/> |<span data-ttu-id="de405-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="de405-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="de405-240">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de405-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="de405-241">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="de405-242">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de405-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="de405-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="de405-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de405-244">Cloudflare は、この機能を使用できるようにする必要があることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="de405-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="de405-245">次の手順と現在の Cloudflare GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Cloudflare コミュニティ](https://community.cloudflare.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="de405-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="de405-246">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de405-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="de405-247">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de405-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="de405-248">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="de405-249">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="de405-250">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="de405-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="de405-251">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の1行目の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="de405-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="de405-252">**Type**</span></span>|<span data-ttu-id="de405-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="de405-253">**Service**</span></span>|<span data-ttu-id="de405-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="de405-254">**Protocol**</span></span>|<span data-ttu-id="de405-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="de405-255">**Name**</span></span>|<span data-ttu-id="de405-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de405-256">**TTL**</span></span>|<span data-ttu-id="de405-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="de405-257">**Priority**</span></span>|<span data-ttu-id="de405-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="de405-258">**Weight**</span></span>|<span data-ttu-id="de405-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="de405-259">**Port**</span></span>|<span data-ttu-id="de405-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="de405-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de405-261">SRV</span><span class="sxs-lookup"><span data-stu-id="de405-261">SRV</span></span>|<span data-ttu-id="de405-262">_sip</span><span class="sxs-lookup"><span data-stu-id="de405-262">_sip</span></span> |<span data-ttu-id="de405-263">TLS</span><span class="sxs-lookup"><span data-stu-id="de405-263">TLS</span></span> |<span data-ttu-id="de405-264">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="de405-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="de405-265">30 分</span><span class="sxs-lookup"><span data-stu-id="de405-265">30 minutes</span></span> | <span data-ttu-id="de405-266">100</span><span class="sxs-lookup"><span data-stu-id="de405-266">100</span></span>|<span data-ttu-id="de405-267">1-d</span><span class="sxs-lookup"><span data-stu-id="de405-267">1</span></span> |<span data-ttu-id="de405-268">443</span><span class="sxs-lookup"><span data-stu-id="de405-268">443</span></span> |<span data-ttu-id="de405-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de405-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="de405-270">SRV</span><span class="sxs-lookup"><span data-stu-id="de405-270">SRV</span></span>|<span data-ttu-id="de405-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="de405-271">_sipfederationtls</span></span> | <span data-ttu-id="de405-272">TCP</span><span class="sxs-lookup"><span data-stu-id="de405-272">TCP</span></span>|<span data-ttu-id="de405-273">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="de405-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="de405-274">30 分</span><span class="sxs-lookup"><span data-stu-id="de405-274">30 minutes</span></span> |<span data-ttu-id="de405-275">100</span><span class="sxs-lookup"><span data-stu-id="de405-275">100</span></span> |<span data-ttu-id="de405-276">1-d</span><span class="sxs-lookup"><span data-stu-id="de405-276">1</span></span> |<span data-ttu-id="de405-277">5061</span><span class="sxs-lookup"><span data-stu-id="de405-277">5061</span></span> | <span data-ttu-id="de405-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de405-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="de405-279">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de405-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="de405-280">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="de405-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="de405-p117">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de405-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
