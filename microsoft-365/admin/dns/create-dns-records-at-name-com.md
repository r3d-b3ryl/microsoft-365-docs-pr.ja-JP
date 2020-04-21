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
ms.openlocfilehash: 8b23ab4d324b5e6d023f10f8f1d11d95d3c579ba
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629349"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="d92ef-103">Microsoft の name.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="d92ef-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="d92ef-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d92ef-105">使用している DNS ホスティング プロバイダーが name.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="d92ef-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d92ef-106">これらのレコードを name.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d92ef-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d92ef-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d92ef-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d92ef-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d92ef-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d92ef-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d92ef-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d92ef-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d92ef-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d92ef-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d92ef-p104">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="d92ef-120">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="d92ef-122">[**詳細**] 列で、[\* \* DNS Records \* \*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="d92ef-124">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d92ef-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d92ef-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d92ef-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="d92ef-126">**Type**</span></span> <br/> |<span data-ttu-id="d92ef-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="d92ef-127">**Host**</span></span> <br/> |<span data-ttu-id="d92ef-128">**応答**</span><span class="sxs-lookup"><span data-stu-id="d92ef-128">**Answer**</span></span> <br/> |<span data-ttu-id="d92ef-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d92ef-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="d92ef-130">TXT</span><span class="sxs-lookup"><span data-stu-id="d92ef-130">TXT</span></span>  <br/> |<span data-ttu-id="d92ef-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d92ef-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d92ef-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d92ef-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d92ef-133">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="d92ef-133">**Note:** This is an example.</span></span> <span data-ttu-id="d92ef-134">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d92ef-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="d92ef-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d92ef-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="d92ef-136">Use the default value (300).</span></span>  <br/> |
   
    ![名前-BP-検証-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="d92ef-138">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="d92ef-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d92ef-141">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d92ef-142">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d92ef-143">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d92ef-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d92ef-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d92ef-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="d92ef-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d92ef-150">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="d92ef-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d92ef-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d92ef-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d92ef-p107">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="d92ef-155">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="d92ef-157">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="d92ef-159">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d92ef-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d92ef-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d92ef-161">**Type**</span><span class="sxs-lookup"><span data-stu-id="d92ef-161">**Type**</span></span>|<span data-ttu-id="d92ef-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="d92ef-162">**Host**</span></span>|<span data-ttu-id="d92ef-163">**応答**</span><span class="sxs-lookup"><span data-stu-id="d92ef-163">**Answer**</span></span>|<span data-ttu-id="d92ef-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d92ef-164">**TTL**</span></span>|<span data-ttu-id="d92ef-165">**優先度**</span><span class="sxs-lookup"><span data-stu-id="d92ef-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d92ef-166">MX</span><span class="sxs-lookup"><span data-stu-id="d92ef-166">MX</span></span>  <br/> |<span data-ttu-id="d92ef-167">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="d92ef-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="d92ef-168">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d92ef-169">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d92ef-170">確認する方法</span><span class="sxs-lookup"><span data-stu-id="d92ef-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d92ef-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="d92ef-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="d92ef-172">.0</span><span class="sxs-lookup"><span data-stu-id="d92ef-172">0</span></span>  <br/> <span data-ttu-id="d92ef-173">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="d92ef-175">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="d92ef-177">MX レコードがほかにも存在する場合は、次の 2 段階のステップを実行して 1 つずつ削除してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="d92ef-178">その他の MX レコードごとに、[**操作**] 列の [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="d92ef-180">各削除を確認するには、再度 [**操作**] 列で [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="d92ef-182">ほかの MX レコードがすべて削除されるまで、上記の 2 段階ステップを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d92ef-183">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d92ef-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d92ef-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d92ef-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d92ef-p109">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="d92ef-188">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="d92ef-190">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="d92ef-192">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d92ef-193">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="d92ef-194">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="d92ef-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d92ef-195">**Type**</span><span class="sxs-lookup"><span data-stu-id="d92ef-195">**Type**</span></span>|<span data-ttu-id="d92ef-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="d92ef-196">**Host**</span></span>|<span data-ttu-id="d92ef-197">**応答**</span><span class="sxs-lookup"><span data-stu-id="d92ef-197">**Answer**</span></span>|<span data-ttu-id="d92ef-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d92ef-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d92ef-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="d92ef-199">CNAME</span></span>  <br/> |<span data-ttu-id="d92ef-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d92ef-200">autodiscover</span></span>  <br/> |<span data-ttu-id="d92ef-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="d92ef-202">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="d92ef-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="d92ef-203">CNAME</span></span>  <br/> |<span data-ttu-id="d92ef-204">sip</span><span class="sxs-lookup"><span data-stu-id="d92ef-204">sip</span></span>  <br/> |<span data-ttu-id="d92ef-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d92ef-206">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="d92ef-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="d92ef-207">CNAME</span></span>  <br/> |<span data-ttu-id="d92ef-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d92ef-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d92ef-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="d92ef-210">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="d92ef-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="d92ef-211">CNAME</span></span>  <br/> |<span data-ttu-id="d92ef-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d92ef-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d92ef-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d92ef-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="d92ef-214">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="d92ef-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="d92ef-215">CNAME</span></span>  <br/> |<span data-ttu-id="d92ef-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d92ef-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d92ef-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="d92ef-218">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="d92ef-220">[ **Add record** ] を選択して、最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="d92ef-222">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="d92ef-223">上の表の2行目の値を使用し、[ **Add record** ] を選択して2番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="d92ef-224">同様に、表の 3 行目、4 行目、5 行目、6 行目の値を使用して、残りのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d92ef-225">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d92ef-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d92ef-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d92ef-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d92ef-227">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d92ef-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d92ef-228">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d92ef-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d92ef-229">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d92ef-230">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="d92ef-p111">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="d92ef-234">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="d92ef-236">[**詳細**] 列で、[ **DNS レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="d92ef-238">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d92ef-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d92ef-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d92ef-240">**Type**</span><span class="sxs-lookup"><span data-stu-id="d92ef-240">**Type**</span></span>|<span data-ttu-id="d92ef-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="d92ef-241">**Host**</span></span>|<span data-ttu-id="d92ef-242">**応答**</span><span class="sxs-lookup"><span data-stu-id="d92ef-242">**Answer**</span></span>|<span data-ttu-id="d92ef-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d92ef-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d92ef-244">TXT</span><span class="sxs-lookup"><span data-stu-id="d92ef-244">TXT</span></span>  <br/> |<span data-ttu-id="d92ef-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d92ef-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d92ef-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d92ef-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d92ef-247">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d92ef-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d92ef-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="d92ef-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="d92ef-250">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d92ef-252">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d92ef-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d92ef-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d92ef-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d92ef-p112">まず、[このリンク](https://www.name.com/account/domain)を使って name.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="d92ef-257">[**マイドメイン**] の下で、変更するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="d92ef-259">[**詳細**] 列で、[ **DNS レコード +**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="d92ef-261">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="d92ef-262">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d92ef-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="d92ef-263">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="d92ef-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d92ef-264">**Type**</span><span class="sxs-lookup"><span data-stu-id="d92ef-264">**Type**</span></span>|<span data-ttu-id="d92ef-265">**サービス**</span><span class="sxs-lookup"><span data-stu-id="d92ef-265">**Service**</span></span>|<span data-ttu-id="d92ef-266">**加重**</span><span class="sxs-lookup"><span data-stu-id="d92ef-266">**Weight**</span></span>|<span data-ttu-id="d92ef-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d92ef-267">**TTL**</span></span>|<span data-ttu-id="d92ef-268">**優先度**</span><span class="sxs-lookup"><span data-stu-id="d92ef-268">**Prio**</span></span>|<span data-ttu-id="d92ef-269">**プロトコル**</span><span class="sxs-lookup"><span data-stu-id="d92ef-269">**Protocol**</span></span>|<span data-ttu-id="d92ef-270">**ポート**</span><span class="sxs-lookup"><span data-stu-id="d92ef-270">**Port**</span></span>|<span data-ttu-id="d92ef-271">**Target**</span><span class="sxs-lookup"><span data-stu-id="d92ef-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d92ef-272">SRV</span><span class="sxs-lookup"><span data-stu-id="d92ef-272">SRV</span></span>|<span data-ttu-id="d92ef-273">sip</span><span class="sxs-lookup"><span data-stu-id="d92ef-273">sip</span></span>|<span data-ttu-id="d92ef-274">1-d</span><span class="sxs-lookup"><span data-stu-id="d92ef-274">1</span></span>|<span data-ttu-id="d92ef-275">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-275">Use the default value (300).</span></span>|<span data-ttu-id="d92ef-276">100</span><span class="sxs-lookup"><span data-stu-id="d92ef-276">100</span></span>|<span data-ttu-id="d92ef-277">tls</span><span class="sxs-lookup"><span data-stu-id="d92ef-277">tls</span></span>|<span data-ttu-id="d92ef-278">443</span><span class="sxs-lookup"><span data-stu-id="d92ef-278">443</span></span>|<span data-ttu-id="d92ef-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="d92ef-280">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d92ef-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="d92ef-281">SRV</span><span class="sxs-lookup"><span data-stu-id="d92ef-281">SRV</span></span>|<span data-ttu-id="d92ef-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d92ef-282">sipfederationtls</span></span>|<span data-ttu-id="d92ef-283">1-d</span><span class="sxs-lookup"><span data-stu-id="d92ef-283">1</span></span>|<span data-ttu-id="d92ef-284">既定値 (300) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-284">Use the default value (300).</span></span>|<span data-ttu-id="d92ef-285">100</span><span class="sxs-lookup"><span data-stu-id="d92ef-285">100</span></span>|<span data-ttu-id="d92ef-286">tcp</span><span class="sxs-lookup"><span data-stu-id="d92ef-286">tcp</span></span>|<span data-ttu-id="d92ef-287">5061</span><span class="sxs-lookup"><span data-stu-id="d92ef-287">5061</span></span>|<span data-ttu-id="d92ef-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d92ef-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="d92ef-289">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d92ef-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="d92ef-291">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="d92ef-293">2 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-293">Add the second SRV record:</span></span>

<span data-ttu-id="d92ef-294">上の表の次の行の値を使用し、[ **Add record** ] を選択して2番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d92ef-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="d92ef-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d92ef-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
