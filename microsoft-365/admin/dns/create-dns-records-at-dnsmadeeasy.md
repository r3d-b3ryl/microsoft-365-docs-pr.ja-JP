---
title: Microsoft にとって簡単に DNS レコードを Dnsで作成する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: ドメインを確認し、電子メール、Skype for Business Online、および Dnsat の他のサービスの DNS レコードを Microsoft にとって簡単にセットアップする方法について説明します。
ms.openlocfilehash: 07cf79b86e02fa79d59882fa51402cccc922c2b6
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307105"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="54181-103">Microsoft にとって簡単に DNS レコードを Dnsで作成する</span><span class="sxs-lookup"><span data-stu-id="54181-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="54181-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="54181-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="54181-105">使用している DNS ホスティング プロバイダーが DNSMadeEasy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="54181-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="54181-106">これらのレコードを Dnsで追加すると、ドメインは Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="54181-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="54181-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54181-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="54181-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="54181-110">Add a TXT record for verification</span></span>
<span data-ttu-id="54181-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="54181-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="54181-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="54181-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54181-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="54181-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="54181-116">Dnsが簡単なアカウントの場合、追加したドメインは別のドメインレジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="54181-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="54181-117">Dns は簡単にドメイン登録サービスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="54181-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="54181-118">Dnsて簡単にログインし、DNS レコードを作成することで、所有権を十分に証明できます。</span><span class="sxs-lookup"><span data-stu-id="54181-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="54181-119">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="54181-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="54181-120">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="54181-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="54181-121">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="54181-122">[管理された **DNS** ] ページの [ **TXT Records** ] 領域で、( **+** ) コントロール ([ **新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="54181-123">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="54181-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="54181-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="54181-125">**名前**</span><span class="sxs-lookup"><span data-stu-id="54181-125">**Name**</span></span> <br/> |<span data-ttu-id="54181-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="54181-126">**Value**</span></span> <br/> |<span data-ttu-id="54181-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54181-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="54181-128">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="54181-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="54181-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="54181-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="54181-130">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="54181-130">**Note:** This is an example.</span></span> <span data-ttu-id="54181-131">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="54181-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="54181-132">確認する方法</span><span class="sxs-lookup"><span data-stu-id="54181-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="54181-133">1800</span><span class="sxs-lookup"><span data-stu-id="54181-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="54181-134">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="54181-135">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="54181-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="54181-136">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="54181-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="54181-137">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="54181-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="54181-138">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="54181-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="54181-139">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="54181-140">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="54181-141">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="54181-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54181-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="54181-145">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="54181-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="54181-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="54181-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="54181-p108">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="54181-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="54181-149">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="54181-150">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![Dnsの簡単な設定-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="54181-152">[管理された **DNS** ] ページの [ **MX Records** ] 領域で、 **(+)** コントロール ([ **新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="54181-153">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-153">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="54181-155">[ **Add MX Records**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="54181-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="54181-156">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="54181-157">**名前**</span><span class="sxs-lookup"><span data-stu-id="54181-157">**Name**</span></span>|<span data-ttu-id="54181-158">**サーバー**</span><span class="sxs-lookup"><span data-stu-id="54181-158">**Server**</span></span>|<span data-ttu-id="54181-159">**MX レベル**</span><span class="sxs-lookup"><span data-stu-id="54181-159">**MX Level**</span></span>|<span data-ttu-id="54181-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54181-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54181-161">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="54181-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="54181-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="54181-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="54181-163">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="54181-164">**注: Microsoft アカウントから**取得\<*domain-key*\> します。</span><span class="sxs-lookup"><span data-stu-id="54181-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="54181-165">確認する方法</span><span class="sxs-lookup"><span data-stu-id="54181-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="54181-166">10 </span><span class="sxs-lookup"><span data-stu-id="54181-166">10</span></span>  <br/> <span data-ttu-id="54181-167">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54181-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="54181-168">1800</span><span class="sxs-lookup"><span data-stu-id="54181-168">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="54181-170">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-170">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="54181-172">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、1 つずつ選択してそれらを全部削除します。</span><span class="sxs-lookup"><span data-stu-id="54181-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![Dnsの簡単な設定-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="54181-174">すべてのレコードが選択されたら、[ **選択した**ものを削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![Dnsの簡単な設定-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="54181-176">[ **MX レコードの削除** ] ダイアログボックスで、[ **削除** ] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="54181-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![Dnsの簡単な設定-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="54181-178">Microsoft に必要な 5 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="54181-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="54181-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="54181-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="54181-p110">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="54181-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="54181-182">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="54181-183">[管理された **DNS** ] ページの [ **CNAME Records** ] 領域で、 **(+)** コントロール ([ **新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="54181-184">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-184">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="54181-186">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="54181-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="54181-187">[ **Add CNAME Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="54181-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="54181-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="54181-188">**Name**</span></span>|<span data-ttu-id="54181-189">**Alias to (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="54181-189">**Alias to**</span></span>|<span data-ttu-id="54181-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54181-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="54181-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="54181-191">autodiscover</span></span>  <br/> |<span data-ttu-id="54181-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="54181-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="54181-193">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-194">1800</span><span class="sxs-lookup"><span data-stu-id="54181-194">1800</span></span>  <br/> |
    |<span data-ttu-id="54181-195">sip</span><span class="sxs-lookup"><span data-stu-id="54181-195">sip</span></span>  <br/> |<span data-ttu-id="54181-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54181-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="54181-197">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-198">1800</span><span class="sxs-lookup"><span data-stu-id="54181-198">1800</span></span>  <br/> |
    |<span data-ttu-id="54181-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="54181-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="54181-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="54181-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="54181-201">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-202">1800</span><span class="sxs-lookup"><span data-stu-id="54181-202">1800</span></span>  <br/> |
    |<span data-ttu-id="54181-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="54181-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="54181-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="54181-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="54181-205">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-206">1800</span><span class="sxs-lookup"><span data-stu-id="54181-206">1800</span></span>  <br/> |
    |<span data-ttu-id="54181-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="54181-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="54181-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="54181-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="54181-209">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-210">1800</span><span class="sxs-lookup"><span data-stu-id="54181-210">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="54181-212">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-212">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="54181-214">他の4つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="54181-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="54181-215">[ **CNAME Records** ] セクションで、 **(+)** コントロール ([ **新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="54181-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="54181-216">この手順を繰り返し、5つの CNAME レコードをすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="54181-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="54181-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="54181-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="54181-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="54181-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="54181-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="54181-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="54181-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="54181-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="54181-221">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="54181-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="54181-222">代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="54181-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="54181-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="54181-223">Need examples?</span></span> <span data-ttu-id="54181-224">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54181-224">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="54181-225">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="54181-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="54181-226">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="54181-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="54181-227">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="54181-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="54181-228">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="54181-229">[管理された **DNS** ] ページの [ **TXT Records** ] 領域で、 **(+)** コントロール ([ **新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="54181-230">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-230">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="54181-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="54181-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="54181-233">**名前**</span><span class="sxs-lookup"><span data-stu-id="54181-233">**Name**</span></span>|<span data-ttu-id="54181-234">**Value**</span><span class="sxs-lookup"><span data-stu-id="54181-234">**Value**</span></span>|<span data-ttu-id="54181-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54181-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="54181-236">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="54181-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="54181-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="54181-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="54181-238">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54181-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="54181-239">1800</span><span class="sxs-lookup"><span data-stu-id="54181-239">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="54181-241">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-241">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="54181-243">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="54181-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="54181-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="54181-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="54181-p113">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="54181-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="54181-247">[ **管理コンソール** ] ページの [ **最近更新さ** れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="54181-248">[管理された **DNS** ] ページの [ **SRV Records** ] 領域で、 **(+)** コントロール ([ **新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="54181-249">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="54181-249">(You may have to scroll down)</span></span>
    
    ![Dnsの簡単な設定-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="54181-251">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="54181-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="54181-252">[ **Add SRV Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="54181-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="54181-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="54181-253">**Name**</span></span>|<span data-ttu-id="54181-254">**Priority**</span><span class="sxs-lookup"><span data-stu-id="54181-254">**Priority**</span></span>|<span data-ttu-id="54181-255">**Weight**</span><span class="sxs-lookup"><span data-stu-id="54181-255">**Weight**</span></span>|<span data-ttu-id="54181-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="54181-256">**Port**</span></span>|<span data-ttu-id="54181-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="54181-257">**Host**</span></span>|<span data-ttu-id="54181-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="54181-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="54181-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="54181-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="54181-260">100</span><span class="sxs-lookup"><span data-stu-id="54181-260">100</span></span>  <br/> |<span data-ttu-id="54181-261">1 </span><span class="sxs-lookup"><span data-stu-id="54181-261">1</span></span>  <br/> |<span data-ttu-id="54181-262">443</span><span class="sxs-lookup"><span data-stu-id="54181-262">443</span></span>  <br/> |<span data-ttu-id="54181-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="54181-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="54181-264">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-265">1800</span><span class="sxs-lookup"><span data-stu-id="54181-265">1800</span></span>  <br/> |
    |<span data-ttu-id="54181-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="54181-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="54181-267">100</span><span class="sxs-lookup"><span data-stu-id="54181-267">100</span></span>  <br/> |<span data-ttu-id="54181-268">1 </span><span class="sxs-lookup"><span data-stu-id="54181-268">1</span></span>  <br/> |<span data-ttu-id="54181-269">5061</span><span class="sxs-lookup"><span data-stu-id="54181-269">5061</span></span>  <br/> |<span data-ttu-id="54181-270">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="54181-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="54181-271">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="54181-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="54181-272">1800</span><span class="sxs-lookup"><span data-stu-id="54181-272">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="54181-274">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54181-274">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="54181-276">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="54181-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="54181-277">[ **SRV Records** ] セクションで、 **(+)** コントロール ([ **新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="54181-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="54181-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54181-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

