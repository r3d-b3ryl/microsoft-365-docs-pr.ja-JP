---
title: Microsoft の web.com で DNS レコードを作成する
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
description: ドメインを確認し、電子メール、Skype for Business Online、および web.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629253"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="f4d2e-103">Microsoft の web.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="f4d2e-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f4d2e-105">DNS ホスティングプロバイダーが web.com の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f4d2e-106">これらのレコードを web.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="f4d2e-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f4d2e-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f4d2e-111">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f4d2e-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4d2e-113">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f4d2e-114">Web.com にサインアップしたときに、web.com**セットアップ**プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="f4d2e-115">Microsoft でドメインの DNS レコードを確認および作成するには、最初にドメインレジストラーでネームサーバーを変更して、web .com のネームサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="f4d2e-116">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f4d2e-117">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f4d2e-118">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="f4d2e-119">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f4d2e-119">First nameserver</span></span>  <br/> |<span data-ttu-id="f4d2e-120">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-121">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f4d2e-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="f4d2e-122">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="f4d2e-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f4d2e-123">You should use at least two name server records.</span></span> <span data-ttu-id="f4d2e-124">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="f4d2e-125">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4d2e-126">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f4d2e-127">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f4d2e-128">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-128">Add a TXT record for verification</span></span>
<span data-ttu-id="f4d2e-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f4d2e-130">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="f4d2e-131">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4d2e-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f4d2e-134">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f4d2e-135">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-135">Log in first.</span></span>
  
2. <span data-ttu-id="f4d2e-136">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f4d2e-137">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f4d2e-138">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f4d2e-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-139">**Host**</span></span>|<span data-ttu-id="f4d2e-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-140">**TTL**</span></span>|<span data-ttu-id="f4d2e-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="f4d2e-142">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-142">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f4d2e-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f4d2e-144">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-144">**Note:** This is an example.</span></span> <span data-ttu-id="f4d2e-145">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="f4d2e-146">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f4d2e-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="f4d2e-147">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="f4d2e-148">新しい TXT レコードが確認されるまで数分待ってから、作成したレコードがインターネットを介して更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f4d2e-149">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f4d2e-150">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f4d2e-151">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f4d2e-152">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f4d2e-153">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f4d2e-154">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f4d2e-p108">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f4d2e-158">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="f4d2e-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f4d2e-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f4d2e-160">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f4d2e-161">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-161">Log in first.</span></span>
  
2. <span data-ttu-id="f4d2e-162">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f4d2e-163">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f4d2e-164">[**メールサーバー (Mx records)**] で、[ **Mx レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f4d2e-165">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-165">**Priority**</span></span>|<span data-ttu-id="f4d2e-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-166">**TTL**</span></span>|<span data-ttu-id="f4d2e-167">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f4d2e-168">1-d</span><span class="sxs-lookup"><span data-stu-id="f4d2e-168">1</span></span>  <br/> <span data-ttu-id="f4d2e-169">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="f4d2e-170">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-170">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-171">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f4d2e-172">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="f4d2e-173">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f4d2e-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="f4d2e-174">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="f4d2e-175">その他の MX レコードが [ **Mx records** ] セクションに表示されている場合は、[**削除**] でそのレコードの横にあるチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="f4d2e-176">確認画面で、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f4d2e-177">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f4d2e-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f4d2e-179">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f4d2e-180">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="f4d2e-181">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f4d2e-182">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f4d2e-183">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="f4d2e-184">[ **Host alias (Cname records)**] で [ **Cname レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="f4d2e-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-185">**Alias**</span></span>|<span data-ttu-id="f4d2e-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-186">**TTL**</span></span>|<span data-ttu-id="f4d2e-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-187">**Refers to Host Name**</span></span>|<span data-ttu-id="f4d2e-188">**その他のホスト**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f4d2e-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f4d2e-189">autodiscover</span></span>  <br/> |<span data-ttu-id="f4d2e-190">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-190">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-191">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-191">@ (none)</span></span>  <br/> |<span data-ttu-id="f4d2e-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-193">sip</span><span class="sxs-lookup"><span data-stu-id="f4d2e-193">sip</span></span>  <br/> |<span data-ttu-id="f4d2e-194">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-194">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-195">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-195">@ (none)</span></span>  <br/> |<span data-ttu-id="f4d2e-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f4d2e-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f4d2e-198">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-198">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-199">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-199">@ (none)</span></span>  <br/> | <span data-ttu-id="f4d2e-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f4d2e-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f4d2e-202">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-202">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-203">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-203">@ (none)</span></span>  <br/> |<span data-ttu-id="f4d2e-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f4d2e-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f4d2e-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f4d2e-206">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-206">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-207">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-207">@ (none)</span></span>  <br/> |<span data-ttu-id="f4d2e-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="f4d2e-209">msoid</span><span class="sxs-lookup"><span data-stu-id="f4d2e-209">msoid</span></span>  <br/> |<span data-ttu-id="f4d2e-210">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-210">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-211">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="f4d2e-211">@ (none)</span></span>  <br/> |<span data-ttu-id="f4d2e-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="f4d2e-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="f4d2e-213">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="f4d2e-214">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f4d2e-215">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f4d2e-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4d2e-217">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f4d2e-218">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f4d2e-219">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f4d2e-220">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f4d2e-221">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f4d2e-222">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="f4d2e-223">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f4d2e-224">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f4d2e-225">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="f4d2e-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-226">**Host**</span></span>|<span data-ttu-id="f4d2e-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-227">**TTL**</span></span>|<span data-ttu-id="f4d2e-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f4d2e-229">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-229">3600</span></span>  <br/> |<span data-ttu-id="f4d2e-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f4d2e-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f4d2e-231">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="f4d2e-232">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-232">Select **Continue**.</span></span>

6. <span data-ttu-id="f4d2e-233">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f4d2e-234">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f4d2e-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f4d2e-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f4d2e-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4d2e-236">Web.com は、この機能を使用できるようにする責任があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="f4d2e-237">次の手順と現在の web.com GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Web.com コミュニティ](https://community.web.com.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="f4d2e-238">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f4d2e-239">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-239">Log in first.</span></span>
      
2. <span data-ttu-id="f4d2e-240">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f4d2e-241">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="f4d2e-242">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="f4d2e-243">[**サービス (Srv レコード)**] で、[ **Srv レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="f4d2e-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-244">**Service**</span></span>|<span data-ttu-id="f4d2e-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-245">**Protocol**</span></span>|<span data-ttu-id="f4d2e-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-246">**TTL**</span></span>|<span data-ttu-id="f4d2e-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-247">**Priority**</span></span>|<span data-ttu-id="f4d2e-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-248">**Weight**</span></span>|<span data-ttu-id="f4d2e-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-249">**Port**</span></span>|<span data-ttu-id="f4d2e-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="f4d2e-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f4d2e-251">_sip</span><span class="sxs-lookup"><span data-stu-id="f4d2e-251">_sip</span></span> |<span data-ttu-id="f4d2e-252">_tls</span><span class="sxs-lookup"><span data-stu-id="f4d2e-252">_tls</span></span> |<span data-ttu-id="f4d2e-253">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-253">3600</span></span> | <span data-ttu-id="f4d2e-254">100</span><span class="sxs-lookup"><span data-stu-id="f4d2e-254">100</span></span>|<span data-ttu-id="f4d2e-255">1-d</span><span class="sxs-lookup"><span data-stu-id="f4d2e-255">1</span></span> |<span data-ttu-id="f4d2e-256">443</span><span class="sxs-lookup"><span data-stu-id="f4d2e-256">443</span></span> |<span data-ttu-id="f4d2e-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="f4d2e-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f4d2e-258">_sipfederationtls</span></span> |<span data-ttu-id="f4d2e-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="f4d2e-259">_tcp</span></span> |<span data-ttu-id="f4d2e-260">3600</span><span class="sxs-lookup"><span data-stu-id="f4d2e-260">3600</span></span> |<span data-ttu-id="f4d2e-261">100</span><span class="sxs-lookup"><span data-stu-id="f4d2e-261">100</span></span> |<span data-ttu-id="f4d2e-262">1-d</span><span class="sxs-lookup"><span data-stu-id="f4d2e-262">1</span></span> |<span data-ttu-id="f4d2e-263">5061</span><span class="sxs-lookup"><span data-stu-id="f4d2e-263">5061</span></span> | <span data-ttu-id="f4d2e-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f4d2e-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="f4d2e-265">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="f4d2e-266">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-266">Select **Continue**.</span></span>

7. <span data-ttu-id="f4d2e-267">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="f4d2e-p116">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d2e-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
