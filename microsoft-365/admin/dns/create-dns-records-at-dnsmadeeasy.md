---
title: DnsMadeEasy for Microsoft で DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードをセットアップする方法については、「DNSMadeEasy for Microsoft」を参照してください。
ms.openlocfilehash: 11e8072ab3c798ed550043370d0e6e79c7370b4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910392"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="b56df-103">DnsMadeEasy for Microsoft で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="b56df-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="b56df-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b56df-105">使用している DNS ホスティング プロバイダーが DNSMadeEasy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="b56df-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b56df-106">DNSMadeEasy でこれらのレコードを追加すると、ドメインが Microsoft サービスで動作するために設定されます。</span><span class="sxs-lookup"><span data-stu-id="b56df-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b56df-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b56df-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b56df-110">Add a TXT record for verification</span></span>
<span data-ttu-id="b56df-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b56df-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b56df-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b56df-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b56df-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b56df-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b56df-116">DNSMadeEasy アカウントの場合、追加したドメインは別のドメイン レジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="b56df-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="b56df-117">DNSMadeEasy はドメイン登録サービスを提供しない。</span><span class="sxs-lookup"><span data-stu-id="b56df-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="b56df-118">DNSMadeEasy でログインし、DNS レコードを作成する機能は、十分な所有権の証明です。</span><span class="sxs-lookup"><span data-stu-id="b56df-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="b56df-119">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b56df-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="b56df-120">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b56df-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b56df-121">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b56df-122">[ **管理された DNS] ページ** の **[TXT レコード** ] 領域で、[ ( ) コントロール ( 新しい追加 ] ) **+** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="b56df-123">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="b56df-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b56df-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b56df-125">**名前**</span><span class="sxs-lookup"><span data-stu-id="b56df-125">**Name**</span></span> <br/> |<span data-ttu-id="b56df-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="b56df-126">**Value**</span></span> <br/> |<span data-ttu-id="b56df-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56df-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="b56df-128">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="b56df-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b56df-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b56df-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b56df-130">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="b56df-130">**Note:** This is an example.</span></span> <span data-ttu-id="b56df-131">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b56df-132">確認する方法</span><span class="sxs-lookup"><span data-stu-id="b56df-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b56df-133">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="b56df-134">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="b56df-135">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="b56df-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b56df-136">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="b56df-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b56df-137">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="b56df-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b56df-138">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b56df-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b56df-139">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b56df-140">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b56df-141">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b56df-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b56df-145">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="b56df-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b56df-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b56df-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b56df-p108">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b56df-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b56df-149">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="b56df-150">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="b56df-152">**[Managed DNS] ページ** の **[MX レコード**] 領域で **、(+) コントロール (新しい追加)** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b56df-153">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="b56df-155">[ **Add MX Records**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b56df-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b56df-156">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="b56df-157">**名前**</span><span class="sxs-lookup"><span data-stu-id="b56df-157">**Name**</span></span>|<span data-ttu-id="b56df-158">**サーバー**</span><span class="sxs-lookup"><span data-stu-id="b56df-158">**Server**</span></span>|<span data-ttu-id="b56df-159">**MX レベル**</span><span class="sxs-lookup"><span data-stu-id="b56df-159">**MX Level**</span></span>|<span data-ttu-id="b56df-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56df-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56df-161">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="b56df-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="b56df-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b56df-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b56df-163">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b56df-164">**注: Microsoft アカウントから** 取得\<*domain-key*\> します。</span><span class="sxs-lookup"><span data-stu-id="b56df-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="b56df-165">確認する方法</span><span class="sxs-lookup"><span data-stu-id="b56df-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b56df-166">10  </span><span class="sxs-lookup"><span data-stu-id="b56df-166">10</span></span>  <br/> <span data-ttu-id="b56df-167">優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-167">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="b56df-168">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="b56df-170">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="b56df-172">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、1 つずつ選択してそれらを全部削除します。</span><span class="sxs-lookup"><span data-stu-id="b56df-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="b56df-174">すべてのレコードが選択されている場合は、[選択した **レコードの削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="b56df-176">[MX **レコードの削除] ダイアログ** ボックスで、[削除] **を選択して** 変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="b56df-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b56df-178">Microsoft に必要な 5 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b56df-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b56df-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b56df-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b56df-p110">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b56df-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b56df-182">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b56df-183">**[Managed DNS] ページ** の **[CNAME レコード**] 領域で **、(+) コントロール (新しい追加)** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b56df-184">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="b56df-186">5 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b56df-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="b56df-187">[ **Add CNAME Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b56df-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="b56df-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="b56df-188">**Name**</span></span>|<span data-ttu-id="b56df-189">**Alias to (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="b56df-189">**Alias to**</span></span>|<span data-ttu-id="b56df-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56df-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b56df-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b56df-191">autodiscover</span></span>  <br/> |<span data-ttu-id="b56df-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b56df-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b56df-193">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-194">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-194">1800</span></span>  <br/> |
    |<span data-ttu-id="b56df-195">sip</span><span class="sxs-lookup"><span data-stu-id="b56df-195">sip</span></span>  <br/> |<span data-ttu-id="b56df-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b56df-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56df-197">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-198">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-198">1800</span></span>  <br/> |
    |<span data-ttu-id="b56df-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b56df-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b56df-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b56df-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56df-201">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-202">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-202">1800</span></span>  <br/> |
    |<span data-ttu-id="b56df-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b56df-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b56df-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b56df-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="b56df-205">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-206">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-206">1800</span></span>  <br/> |
    |<span data-ttu-id="b56df-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b56df-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b56df-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b56df-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="b56df-209">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-210">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="b56df-212">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="b56df-214">他の 4 つの CNAME レコードのそれぞれを追加します。</span><span class="sxs-lookup"><span data-stu-id="b56df-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="b56df-215">**[CNAME レコード**] セクションで **、(+)** コントロール (新しい追加) を選択し、テーブルの次の行の値を使用してレコードを作成し、もう一度 [送信] を選択してそのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="b56df-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="b56df-216">5 つの CNAME レコードすべてが作成されるまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b56df-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b56df-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b56df-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b56df-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b56df-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b56df-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b56df-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b56df-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="b56df-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b56df-221">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="b56df-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b56df-222">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="b56df-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b56df-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b56df-223">Need examples?</span></span> <span data-ttu-id="b56df-224">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](../../enterprise/external-domain-name-system-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-224">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="b56df-225">SPF レコードを検証するには、次のいずれかの[SPF 検証ツールを使用できます](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="b56df-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="b56df-226">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b56df-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="b56df-227">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b56df-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b56df-228">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b56df-229">[ **管理された DNS] ページ** の **[TXT レコード** ] 領域で、(+) コントロール **(新しい追加)** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b56df-230">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="b56df-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b56df-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b56df-233">**名前**</span><span class="sxs-lookup"><span data-stu-id="b56df-233">**Name**</span></span>|<span data-ttu-id="b56df-234">**Value**</span><span class="sxs-lookup"><span data-stu-id="b56df-234">**Value**</span></span>|<span data-ttu-id="b56df-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56df-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b56df-236">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="b56df-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b56df-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b56df-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b56df-238">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b56df-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="b56df-239">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="b56df-241">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b56df-243">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b56df-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b56df-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b56df-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b56df-p113">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b56df-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b56df-247">[管理 **コンソール] ページ** の[最近更新されたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="b56df-248">[ **管理された DNS] ページ** の **[SRV レコード** ] 領域で **、(+) コントロール (新しい追加)** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b56df-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="b56df-249">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="b56df-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="b56df-251">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b56df-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b56df-252">[ **Add SRV Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b56df-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="b56df-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="b56df-253">**Name**</span></span>|<span data-ttu-id="b56df-254">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b56df-254">**Priority**</span></span>|<span data-ttu-id="b56df-255">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b56df-255">**Weight**</span></span>|<span data-ttu-id="b56df-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="b56df-256">**Port**</span></span>|<span data-ttu-id="b56df-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="b56df-257">**Host**</span></span>|<span data-ttu-id="b56df-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b56df-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b56df-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b56df-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="b56df-260">100</span><span class="sxs-lookup"><span data-stu-id="b56df-260">100</span></span>  <br/> |<span data-ttu-id="b56df-261">1</span><span class="sxs-lookup"><span data-stu-id="b56df-261">1</span></span>  <br/> |<span data-ttu-id="b56df-262">443</span><span class="sxs-lookup"><span data-stu-id="b56df-262">443</span></span>  <br/> |<span data-ttu-id="b56df-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b56df-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56df-264">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-265">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-265">1800</span></span>  <br/> |
    |<span data-ttu-id="b56df-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b56df-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b56df-267">100</span><span class="sxs-lookup"><span data-stu-id="b56df-267">100</span></span>  <br/> |<span data-ttu-id="b56df-268">1</span><span class="sxs-lookup"><span data-stu-id="b56df-268">1</span></span>  <br/> |<span data-ttu-id="b56df-269">5061</span><span class="sxs-lookup"><span data-stu-id="b56df-269">5061</span></span>  <br/> |<span data-ttu-id="b56df-270">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b56df-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="b56df-271">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b56df-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b56df-272">1800</span><span class="sxs-lookup"><span data-stu-id="b56df-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="b56df-274">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b56df-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="b56df-276">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b56df-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="b56df-277">**[SRV レコード**] セクションで **、(+)** コントロール (新しい追加) を選択し、テーブルの次の行の値を使用してレコードを作成し、もう一度 [送信] を選択してそのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="b56df-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b56df-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b56df-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
