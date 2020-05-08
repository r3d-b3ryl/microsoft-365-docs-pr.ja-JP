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
ms.openlocfilehash: a7567688ad9935b30c0749cb7aeffdbe128506ef
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048881"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="9b68a-103">Microsoft の web.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9b68a-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="9b68a-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9b68a-105">DNS ホスティングプロバイダーが web.com の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9b68a-106">これらのレコードを web.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="9b68a-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9b68a-110">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="9b68a-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9b68a-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b68a-112">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9b68a-113">Web.com にサインアップしたときに、web.com**セットアップ**プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="9b68a-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="9b68a-114">Microsoft でドメインの DNS レコードを確認および作成するには、最初にドメインレジストラーでネームサーバーを変更して、web .com のネームサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="9b68a-115">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9b68a-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9b68a-116">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9b68a-117">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9b68a-118">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="9b68a-118">First nameserver</span></span>  <br/> |<span data-ttu-id="9b68a-119">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="9b68a-120">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="9b68a-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="9b68a-121">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9b68a-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="9b68a-122">You should use at least two name server records.</span></span> <span data-ttu-id="9b68a-123">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9b68a-124">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b68a-125">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9b68a-126">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9b68a-127">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b68a-127">Add a TXT record for verification</span></span>
<span data-ttu-id="9b68a-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9b68a-p104">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b68a-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9b68a-133">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9b68a-134">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-134">Log in first.</span></span>
  
2. <span data-ttu-id="9b68a-135">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9b68a-136">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="9b68a-137">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b68a-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="9b68a-138">**Host**</span></span>|<span data-ttu-id="9b68a-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b68a-139">**TTL**</span></span>|<span data-ttu-id="9b68a-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="9b68a-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="9b68a-141">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-141">3600</span></span>  <br/> |<span data-ttu-id="9b68a-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9b68a-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9b68a-143">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9b68a-143">**Note:** This is an example.</span></span> <span data-ttu-id="9b68a-144">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9b68a-145">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9b68a-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="9b68a-146">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="9b68a-147">新しい TXT レコードが確認されるまで数分待ってから、作成したレコードがインターネットを介して更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9b68a-148">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9b68a-149">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9b68a-150">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9b68a-151">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9b68a-152">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9b68a-153">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9b68a-p108">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9b68a-157">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9b68a-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9b68a-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9b68a-159">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9b68a-160">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-160">Log in first.</span></span>
  
2. <span data-ttu-id="9b68a-161">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9b68a-162">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="9b68a-163">[**メールサーバー (Mx records)**] で、[ **Mx レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b68a-164">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9b68a-164">**Priority**</span></span>|<span data-ttu-id="9b68a-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b68a-165">**TTL**</span></span>|<span data-ttu-id="9b68a-166">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="9b68a-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9b68a-167">1-d</span><span class="sxs-lookup"><span data-stu-id="9b68a-167">1</span></span>  <br/> <span data-ttu-id="9b68a-168">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="9b68a-169">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-169">3600</span></span>  <br/> |<span data-ttu-id="9b68a-170">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9b68a-171">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="9b68a-172">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9b68a-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="9b68a-173">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="9b68a-174">その他の MX レコードが [ **Mx records** ] セクションに表示されている場合は、[**削除**] でそのレコードの横にあるチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="9b68a-175">確認画面で、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9b68a-176">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b68a-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9b68a-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9b68a-178">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9b68a-179">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="9b68a-180">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9b68a-181">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="9b68a-182">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9b68a-183">[ **Host alias (Cname records)**] で [ **Cname レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="9b68a-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9b68a-184">**Alias**</span></span>|<span data-ttu-id="9b68a-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b68a-185">**TTL**</span></span>|<span data-ttu-id="9b68a-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="9b68a-186">**Refers to Host Name**</span></span>|<span data-ttu-id="9b68a-187">**その他のホスト**</span><span class="sxs-lookup"><span data-stu-id="9b68a-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b68a-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9b68a-188">autodiscover</span></span>  <br/> |<span data-ttu-id="9b68a-189">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-189">3600</span></span>  <br/> |<span data-ttu-id="9b68a-190">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-190">@ (none)</span></span>  <br/> |<span data-ttu-id="9b68a-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9b68a-192">sip</span><span class="sxs-lookup"><span data-stu-id="9b68a-192">sip</span></span>  <br/> |<span data-ttu-id="9b68a-193">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-193">3600</span></span>  <br/> |<span data-ttu-id="9b68a-194">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-194">@ (none)</span></span>  <br/> |<span data-ttu-id="9b68a-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b68a-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9b68a-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9b68a-197">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-197">3600</span></span>  <br/> |<span data-ttu-id="9b68a-198">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-198">@ (none)</span></span>  <br/> | <span data-ttu-id="9b68a-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b68a-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9b68a-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9b68a-201">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-201">3600</span></span>  <br/> |<span data-ttu-id="9b68a-202">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-202">@ (none)</span></span>  <br/> |<span data-ttu-id="9b68a-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9b68a-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9b68a-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9b68a-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9b68a-205">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-205">3600</span></span>  <br/> |<span data-ttu-id="9b68a-206">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-206">@ (none)</span></span>  <br/> |<span data-ttu-id="9b68a-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="9b68a-208">msoid</span><span class="sxs-lookup"><span data-stu-id="9b68a-208">msoid</span></span>  <br/> |<span data-ttu-id="9b68a-209">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-209">3600</span></span>  <br/> |<span data-ttu-id="9b68a-210">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="9b68a-210">@ (none)</span></span>  <br/> |<span data-ttu-id="9b68a-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9b68a-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="9b68a-212">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="9b68a-213">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9b68a-214">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b68a-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9b68a-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b68a-216">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b68a-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9b68a-217">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9b68a-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9b68a-218">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9b68a-219">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9b68a-220">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9b68a-221">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="9b68a-222">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9b68a-223">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="9b68a-224">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="9b68a-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="9b68a-225">**Host**</span></span>|<span data-ttu-id="9b68a-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b68a-226">**TTL**</span></span>|<span data-ttu-id="9b68a-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="9b68a-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9b68a-228">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-228">3600</span></span>  <br/> |<span data-ttu-id="9b68a-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9b68a-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9b68a-230">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9b68a-231">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-231">Select **Continue**.</span></span>

6. <span data-ttu-id="9b68a-232">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9b68a-233">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b68a-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9b68a-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9b68a-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b68a-235">Web.com は、この機能を使用できるようにする責任があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="9b68a-236">次の手順と現在の web.com GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Web.com コミュニティ](https://community.web.com.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="9b68a-237">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="9b68a-238">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="9b68a-238">Log in first.</span></span>
      
2. <span data-ttu-id="9b68a-239">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b68a-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="9b68a-240">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="9b68a-241">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9b68a-242">[**サービス (Srv レコード)**] で、[ **Srv レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="9b68a-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="9b68a-243">**Service**</span></span>|<span data-ttu-id="9b68a-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="9b68a-244">**Protocol**</span></span>|<span data-ttu-id="9b68a-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b68a-245">**TTL**</span></span>|<span data-ttu-id="9b68a-246">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9b68a-246">**Priority**</span></span>|<span data-ttu-id="9b68a-247">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9b68a-247">**Weight**</span></span>|<span data-ttu-id="9b68a-248">**Port**</span><span class="sxs-lookup"><span data-stu-id="9b68a-248">**Port**</span></span>|<span data-ttu-id="9b68a-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="9b68a-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b68a-250">_sip</span><span class="sxs-lookup"><span data-stu-id="9b68a-250">_sip</span></span> |<span data-ttu-id="9b68a-251">_tls</span><span class="sxs-lookup"><span data-stu-id="9b68a-251">_tls</span></span> |<span data-ttu-id="9b68a-252">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-252">3600</span></span> | <span data-ttu-id="9b68a-253">100</span><span class="sxs-lookup"><span data-stu-id="9b68a-253">100</span></span>|<span data-ttu-id="9b68a-254">1-d</span><span class="sxs-lookup"><span data-stu-id="9b68a-254">1</span></span> |<span data-ttu-id="9b68a-255">443</span><span class="sxs-lookup"><span data-stu-id="9b68a-255">443</span></span> |<span data-ttu-id="9b68a-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9b68a-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9b68a-257">_sipfederationtls</span></span> |<span data-ttu-id="9b68a-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="9b68a-258">_tcp</span></span> |<span data-ttu-id="9b68a-259">3600</span><span class="sxs-lookup"><span data-stu-id="9b68a-259">3600</span></span> |<span data-ttu-id="9b68a-260">100</span><span class="sxs-lookup"><span data-stu-id="9b68a-260">100</span></span> |<span data-ttu-id="9b68a-261">1-d</span><span class="sxs-lookup"><span data-stu-id="9b68a-261">1</span></span> |<span data-ttu-id="9b68a-262">5061</span><span class="sxs-lookup"><span data-stu-id="9b68a-262">5061</span></span> | <span data-ttu-id="9b68a-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b68a-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9b68a-264">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="9b68a-265">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-265">Select **Continue**.</span></span>

7. <span data-ttu-id="9b68a-266">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b68a-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="9b68a-p116">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b68a-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
