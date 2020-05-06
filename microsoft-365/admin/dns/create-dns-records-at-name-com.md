---
title: Microsoft の name.com で DNS レコードを作成する
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: ドメインを確認し、電子メール、Skype for Business Online、および name.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: e9133b3701c2b454cad11b9579dc7463f1a74460
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048965"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="4b428-103">Microsoft の name.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4b428-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="4b428-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4b428-105">使用している DNS ホスティング プロバイダーが name.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="4b428-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4b428-106">これらのレコードを name.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b428-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="4b428-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4b428-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b428-110">Add a TXT record for verification</span></span>
<span data-ttu-id="4b428-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4b428-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4b428-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b428-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4b428-p104">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4b428-119">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4b428-121">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4b428-123">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b428-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4b428-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b428-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b428-125">**型**</span><span class="sxs-lookup"><span data-stu-id="4b428-125">**Type**</span></span> <br/> |<span data-ttu-id="4b428-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b428-126">**Host**</span></span> <br/> |<span data-ttu-id="4b428-127">**応答**</span><span class="sxs-lookup"><span data-stu-id="4b428-127">**Answer**</span></span> <br/> |<span data-ttu-id="4b428-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b428-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="4b428-129">TXT</span><span class="sxs-lookup"><span data-stu-id="4b428-129">TXT</span></span>  <br/> |<span data-ttu-id="4b428-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4b428-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4b428-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4b428-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4b428-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="4b428-132">**Note:** This is an example.</span></span> <span data-ttu-id="4b428-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="4b428-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4b428-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4b428-135">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4b428-135">Use the default value (300).</span></span>  <br/> |
   
    ![名前-BP-検証-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="4b428-137">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="4b428-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="4b428-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4b428-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="4b428-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="4b428-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="4b428-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4b428-142">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4b428-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4b428-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4b428-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4b428-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="4b428-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b428-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="4b428-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="4b428-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4b428-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4b428-p107">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4b428-154">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4b428-156">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4b428-158">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b428-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4b428-159">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b428-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4b428-160">**型**</span><span class="sxs-lookup"><span data-stu-id="4b428-160">**Type**</span></span>|<span data-ttu-id="4b428-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b428-161">**Host**</span></span>|<span data-ttu-id="4b428-162">**応答**</span><span class="sxs-lookup"><span data-stu-id="4b428-162">**Answer**</span></span>|<span data-ttu-id="4b428-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b428-163">**TTL**</span></span>|<span data-ttu-id="4b428-164">**優先度**</span><span class="sxs-lookup"><span data-stu-id="4b428-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b428-165">MX</span><span class="sxs-lookup"><span data-stu-id="4b428-165">MX</span></span>  <br/> |<span data-ttu-id="4b428-166">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="4b428-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="4b428-167">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b428-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4b428-168">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b428-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="4b428-169">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4b428-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4b428-170">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4b428-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="4b428-171">.0</span><span class="sxs-lookup"><span data-stu-id="4b428-171">0</span></span>  <br/> <span data-ttu-id="4b428-172">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="4b428-174">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="4b428-176">MX レコードがほかにも存在する場合は、次の 2 段階のステップを実行して 1 つずつ削除してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="4b428-177">その他の MX レコードごとに、[**操作**] 列の [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="4b428-179">各削除を確認するには、再度 [**操作**] 列で [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="4b428-181">ほかの MX レコードがすべて削除されるまで、上記の 2 段階ステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4b428-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b428-182">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b428-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="4b428-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4b428-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4b428-p109">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4b428-187">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4b428-189">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4b428-191">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="4b428-192">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b428-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4b428-193">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b428-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4b428-194">**型**</span><span class="sxs-lookup"><span data-stu-id="4b428-194">**Type**</span></span>|<span data-ttu-id="4b428-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b428-195">**Host**</span></span>|<span data-ttu-id="4b428-196">**応答**</span><span class="sxs-lookup"><span data-stu-id="4b428-196">**Answer**</span></span>|<span data-ttu-id="4b428-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b428-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b428-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b428-198">CNAME</span></span>  <br/> |<span data-ttu-id="4b428-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4b428-199">autodiscover</span></span>  <br/> |<span data-ttu-id="4b428-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4b428-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="4b428-201">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4b428-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b428-202">CNAME</span></span>  <br/> |<span data-ttu-id="4b428-203">sip</span><span class="sxs-lookup"><span data-stu-id="4b428-203">sip</span></span>  <br/> |<span data-ttu-id="4b428-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b428-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b428-205">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4b428-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b428-206">CNAME</span></span>  <br/> |<span data-ttu-id="4b428-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4b428-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4b428-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b428-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4b428-209">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4b428-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b428-210">CNAME</span></span>  <br/> |<span data-ttu-id="4b428-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4b428-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4b428-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4b428-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="4b428-213">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="4b428-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="4b428-214">CNAME</span></span>  <br/> |<span data-ttu-id="4b428-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4b428-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4b428-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4b428-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="4b428-217">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="4b428-219">[ **Add record** ] を選択して、最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="4b428-221">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="4b428-222">上の表の2行目の値を使用し、[ **Add record** ] を選択して2番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="4b428-223">同様に、表の 3 行目、4 行目、5 行目、6 行目の値を使用して、残りのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4b428-224">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b428-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4b428-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4b428-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b428-226">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b428-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4b428-227">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="4b428-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4b428-228">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="4b428-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="4b428-229">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4b428-p111">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4b428-233">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4b428-235">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4b428-237">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b428-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="4b428-238">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="4b428-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4b428-239">**型**</span><span class="sxs-lookup"><span data-stu-id="4b428-239">**Type**</span></span>|<span data-ttu-id="4b428-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="4b428-240">**Host**</span></span>|<span data-ttu-id="4b428-241">**応答**</span><span class="sxs-lookup"><span data-stu-id="4b428-241">**Answer**</span></span>|<span data-ttu-id="4b428-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b428-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b428-243">TXT</span><span class="sxs-lookup"><span data-stu-id="4b428-243">TXT</span></span>  <br/> |<span data-ttu-id="4b428-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="4b428-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="4b428-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4b428-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4b428-246">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b428-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4b428-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="4b428-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="4b428-249">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="4b428-251">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4b428-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="4b428-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4b428-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="4b428-p112">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="4b428-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="4b428-256">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="4b428-258">[**詳細**] 列で、[ **DNS レコード +**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="4b428-260">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="4b428-261">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4b428-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="4b428-262">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="4b428-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="4b428-263">**Type**</span><span class="sxs-lookup"><span data-stu-id="4b428-263">**Type**</span></span>|<span data-ttu-id="4b428-264">**サービス**</span><span class="sxs-lookup"><span data-stu-id="4b428-264">**Service**</span></span>|<span data-ttu-id="4b428-265">**加重**</span><span class="sxs-lookup"><span data-stu-id="4b428-265">**Weight**</span></span>|<span data-ttu-id="4b428-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4b428-266">**TTL**</span></span>|<span data-ttu-id="4b428-267">**優先度**</span><span class="sxs-lookup"><span data-stu-id="4b428-267">**Prio**</span></span>|<span data-ttu-id="4b428-268">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="4b428-268">**Protocol**</span></span>|<span data-ttu-id="4b428-269">**ポート**</span><span class="sxs-lookup"><span data-stu-id="4b428-269">**Port**</span></span>|<span data-ttu-id="4b428-270">**Target**</span><span class="sxs-lookup"><span data-stu-id="4b428-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4b428-271">SRV</span><span class="sxs-lookup"><span data-stu-id="4b428-271">SRV</span></span>|<span data-ttu-id="4b428-272">sip</span><span class="sxs-lookup"><span data-stu-id="4b428-272">sip</span></span>|<span data-ttu-id="4b428-273">1-d</span><span class="sxs-lookup"><span data-stu-id="4b428-273">1</span></span>|<span data-ttu-id="4b428-274">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-274">Use the default value (300).</span></span>|<span data-ttu-id="4b428-275">100</span><span class="sxs-lookup"><span data-stu-id="4b428-275">100</span></span>|<span data-ttu-id="4b428-276">tls</span><span class="sxs-lookup"><span data-stu-id="4b428-276">tls</span></span>|<span data-ttu-id="4b428-277">443</span><span class="sxs-lookup"><span data-stu-id="4b428-277">443</span></span>|<span data-ttu-id="4b428-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b428-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="4b428-279">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b428-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="4b428-280">SRV</span><span class="sxs-lookup"><span data-stu-id="4b428-280">SRV</span></span>|<span data-ttu-id="4b428-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4b428-281">sipfederationtls</span></span>|<span data-ttu-id="4b428-282">1-d</span><span class="sxs-lookup"><span data-stu-id="4b428-282">1</span></span>|<span data-ttu-id="4b428-283">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b428-283">Use the default value (300).</span></span>|<span data-ttu-id="4b428-284">100</span><span class="sxs-lookup"><span data-stu-id="4b428-284">100</span></span>|<span data-ttu-id="4b428-285">tcp</span><span class="sxs-lookup"><span data-stu-id="4b428-285">tcp</span></span>|<span data-ttu-id="4b428-286">5061</span><span class="sxs-lookup"><span data-stu-id="4b428-286">5061</span></span>|<span data-ttu-id="4b428-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4b428-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="4b428-288">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b428-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="4b428-290">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b428-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="4b428-292">2 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-292">Add the second SRV record:</span></span>

<span data-ttu-id="4b428-293">上の表の次の行の値を使用し、[ **Add record** ] を選択して2番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b428-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="4b428-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b428-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
