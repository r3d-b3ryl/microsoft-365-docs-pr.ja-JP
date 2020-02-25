---
title: DNSMadeEasy で Office 365 用の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: ドメインを確認し、電子メール、Skype for Business Online、および Dnsat for Office 365 の他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248826"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="5760b-103">DNSMadeEasy で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="5760b-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="5760b-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5760b-105">使用している DNS ホスティング プロバイダーが DNSMadeEasy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5760b-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5760b-106">これらのレコードを DNSMadeEasy で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="5760b-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5760b-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5760b-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5760b-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5760b-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5760b-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5760b-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5760b-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5760b-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5760b-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5760b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5760b-117">Dnsが簡単なアカウントの場合、追加したドメインは別のドメインレジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="5760b-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="5760b-118">Dns は簡単にドメイン登録サービスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="5760b-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="5760b-119">Dnsて簡単にログインし、DNS レコードを作成することで、所有権を十分に証明できます。</span><span class="sxs-lookup"><span data-stu-id="5760b-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="5760b-120">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5760b-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5760b-121">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5760b-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5760b-122">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5760b-123">[管理された**DNS** ] ページの [ **TXT Records** ] 領域で**+**、() コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="5760b-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5760b-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="5760b-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5760b-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5760b-126">**名前**</span><span class="sxs-lookup"><span data-stu-id="5760b-126">**Name**</span></span> <br/> |<span data-ttu-id="5760b-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="5760b-127">**Value**</span></span> <br/> |<span data-ttu-id="5760b-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5760b-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5760b-129">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="5760b-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5760b-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5760b-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5760b-131">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="5760b-131">**Note:** This is an example.</span></span> <span data-ttu-id="5760b-132">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="5760b-133">確認する方法</span><span class="sxs-lookup"><span data-stu-id="5760b-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5760b-134">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="5760b-135">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="5760b-136">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="5760b-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5760b-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="5760b-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5760b-138">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="5760b-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5760b-139">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5760b-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5760b-140">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5760b-141">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5760b-142">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5760b-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5760b-146">MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする</span><span class="sxs-lookup"><span data-stu-id="5760b-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5760b-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5760b-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5760b-p108">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5760b-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5760b-150">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="5760b-151">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![Dnsの簡単な設定-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="5760b-153">[管理された**DNS** ] ページの [ **MX Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5760b-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5760b-154">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="5760b-156">[ **Add MX Records**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5760b-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5760b-157">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="5760b-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5760b-158">**名前**</span><span class="sxs-lookup"><span data-stu-id="5760b-158">**Name**</span></span>|<span data-ttu-id="5760b-159">**サーバー**</span><span class="sxs-lookup"><span data-stu-id="5760b-159">**Server**</span></span>|<span data-ttu-id="5760b-160">**MX レベル**</span><span class="sxs-lookup"><span data-stu-id="5760b-160">**MX Level**</span></span>|<span data-ttu-id="5760b-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5760b-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5760b-162">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="5760b-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5760b-163">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5760b-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5760b-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="5760b-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5760b-165">**注:**\<Office 365 アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="5760b-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="5760b-166">確認する方法</span><span class="sxs-lookup"><span data-stu-id="5760b-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5760b-167">10 </span><span class="sxs-lookup"><span data-stu-id="5760b-167">10</span></span>  <br/> <span data-ttu-id="5760b-168">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5760b-169">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-169">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="5760b-171">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-171">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="5760b-173">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、1 つずつ選択してそれらを全部削除します。</span><span class="sxs-lookup"><span data-stu-id="5760b-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![Dnsの簡単な設定-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="5760b-175">すべてのレコードが選択されたら、[**選択した**ものを削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![Dnsの簡単な設定-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="5760b-177">[ **MX レコードの削除**] ダイアログボックスで、[**削除**] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="5760b-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![Dnsの簡単な設定-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5760b-179">Office 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5760b-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5760b-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5760b-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5760b-p110">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5760b-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5760b-183">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5760b-184">[管理された**DNS** ] ページの [ **CNAME Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5760b-185">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="5760b-185">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="5760b-187">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5760b-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5760b-188">[ **Add CNAME Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5760b-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5760b-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="5760b-189">**Name**</span></span>|<span data-ttu-id="5760b-190">**Alias to (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="5760b-190">**Alias to**</span></span>|<span data-ttu-id="5760b-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5760b-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5760b-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5760b-192">autodiscover</span></span>  <br/> |<span data-ttu-id="5760b-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5760b-194">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-195">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-195">1800</span></span>  <br/> |
    |<span data-ttu-id="5760b-196">sip</span><span class="sxs-lookup"><span data-stu-id="5760b-196">sip</span></span>  <br/> |<span data-ttu-id="5760b-197">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5760b-198">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-199">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-199">1800</span></span>  <br/> |
    |<span data-ttu-id="5760b-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5760b-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5760b-201">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5760b-202">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-203">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-203">1800</span></span>  <br/> |
    |<span data-ttu-id="5760b-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5760b-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5760b-205">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="5760b-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5760b-206">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-207">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-207">1800</span></span>  <br/> |
    |<span data-ttu-id="5760b-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5760b-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5760b-209">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5760b-210">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-211">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-211">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="5760b-213">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-213">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="5760b-215">他の4つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="5760b-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="5760b-216">[ **CNAME Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="5760b-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="5760b-217">この手順を繰り返し、5つの CNAME レコードをすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="5760b-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5760b-218">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5760b-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5760b-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5760b-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5760b-220">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="5760b-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5760b-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="5760b-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5760b-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5760b-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5760b-223">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="5760b-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5760b-224">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5760b-224">Need examples?</span></span> <span data-ttu-id="5760b-225">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="5760b-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="5760b-226">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5760b-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5760b-227">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5760b-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5760b-228">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5760b-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5760b-229">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5760b-230">[管理された**DNS** ] ページの [ **TXT Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5760b-231">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="5760b-231">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="5760b-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5760b-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5760b-234">**名前**</span><span class="sxs-lookup"><span data-stu-id="5760b-234">**Name**</span></span>|<span data-ttu-id="5760b-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="5760b-235">**Value**</span></span>|<span data-ttu-id="5760b-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5760b-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5760b-237">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="5760b-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5760b-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5760b-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5760b-239">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5760b-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5760b-240">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-240">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="5760b-242">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-242">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5760b-244">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5760b-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5760b-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5760b-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5760b-p113">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5760b-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5760b-248">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5760b-249">[管理された**DNS** ] ページの [ **SRV Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5760b-250">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="5760b-250">(You may have to scroll down)</span></span>
    
    ![Dnsの簡単な設定-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="5760b-252">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5760b-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5760b-253">[ **Add SRV Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5760b-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5760b-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="5760b-254">**Name**</span></span>|<span data-ttu-id="5760b-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5760b-255">**Priority**</span></span>|<span data-ttu-id="5760b-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5760b-256">**Weight**</span></span>|<span data-ttu-id="5760b-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="5760b-257">**Port**</span></span>|<span data-ttu-id="5760b-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="5760b-258">**Host**</span></span>|<span data-ttu-id="5760b-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5760b-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5760b-260">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="5760b-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="5760b-261">100</span><span class="sxs-lookup"><span data-stu-id="5760b-261">100</span></span>  <br/> |<span data-ttu-id="5760b-262">1-d</span><span class="sxs-lookup"><span data-stu-id="5760b-262">1</span></span>  <br/> |<span data-ttu-id="5760b-263">443</span><span class="sxs-lookup"><span data-stu-id="5760b-263">443</span></span>  <br/> |<span data-ttu-id="5760b-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5760b-265">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-266">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-266">1800</span></span>  <br/> |
    |<span data-ttu-id="5760b-267">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="5760b-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5760b-268">100</span><span class="sxs-lookup"><span data-stu-id="5760b-268">100</span></span>  <br/> |<span data-ttu-id="5760b-269">1-d</span><span class="sxs-lookup"><span data-stu-id="5760b-269">1</span></span>  <br/> |<span data-ttu-id="5760b-270">5061</span><span class="sxs-lookup"><span data-stu-id="5760b-270">5061</span></span>  <br/> |<span data-ttu-id="5760b-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="5760b-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5760b-272">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="5760b-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5760b-273">1800</span><span class="sxs-lookup"><span data-stu-id="5760b-273">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="5760b-275">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5760b-275">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="5760b-277">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5760b-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5760b-278">[ **SRV Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="5760b-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5760b-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5760b-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

