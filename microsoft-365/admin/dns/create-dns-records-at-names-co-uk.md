---
title: Microsoft の DNS レコード Names.co.uk 作成する
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法については、Microsoft Names.co.uk 説明します。
ms.openlocfilehash: ddd7286d983a0f180c9aefdbf5218eb9765c8669
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910044"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="01f62-103">Microsoft の DNS レコード Names.co.uk 作成する</span><span class="sxs-lookup"><span data-stu-id="01f62-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="01f62-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="01f62-105">使用している DNS ホスティング プロバイダーが Names.co.uk の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="01f62-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="01f62-106">これらのレコードを追加すると、Names.co.uk Microsoft サービスを使用するためにドメインが設定されます。</span><span class="sxs-lookup"><span data-stu-id="01f62-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="01f62-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="01f62-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="01f62-110">Add a TXT record for verification</span></span>
<span data-ttu-id="01f62-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="01f62-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="01f62-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01f62-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="01f62-p104">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01f62-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01f62-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01f62-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01f62-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01f62-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01f62-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01f62-123">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="01f62-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01f62-124">(行を追加する必要がある場合は **、[A/CNAME RECORDS (+)** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01f62-125">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="01f62-126">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="01f62-126">**Host name**</span></span>|<span data-ttu-id="01f62-127">**種類**</span><span class="sxs-lookup"><span data-stu-id="01f62-127">**Type**</span></span>|<span data-ttu-id="01f62-128">**結果**</span><span class="sxs-lookup"><span data-stu-id="01f62-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01f62-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="01f62-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01f62-130">TXT</span><span class="sxs-lookup"><span data-stu-id="01f62-130">TXT</span></span>  <br/> |<span data-ttu-id="01f62-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="01f62-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="01f62-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="01f62-132">**Note:** This is an example.</span></span> <span data-ttu-id="01f62-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="01f62-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="01f62-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="01f62-136">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-136">Select **Save**.</span></span>
    
    <span data-ttu-id="01f62-137">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="01f62-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="01f62-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="01f62-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="01f62-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="01f62-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="01f62-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="01f62-142">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="01f62-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="01f62-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="01f62-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="01f62-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="01f62-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="01f62-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="01f62-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="01f62-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="01f62-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="01f62-p107">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01f62-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01f62-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01f62-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01f62-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01f62-157">[ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="01f62-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01f62-158">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01f62-159">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="01f62-159">**Host name**</span></span>|<span data-ttu-id="01f62-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="01f62-160">**Priority**</span></span>|<span data-ttu-id="01f62-161">**Result**</span><span class="sxs-lookup"><span data-stu-id="01f62-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01f62-162">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="01f62-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01f62-163">1</span><span class="sxs-lookup"><span data-stu-id="01f62-163">1</span></span>  <br/> <span data-ttu-id="01f62-164">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-164">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="01f62-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01f62-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="01f62-166">> [!NOTE]> Microsoft アカウント  *\<domain-key\>*  から取得します。</span><span class="sxs-lookup"><span data-stu-id="01f62-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="01f62-167">確認する方法</span><span class="sxs-lookup"><span data-stu-id="01f62-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="01f62-169">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-169">Select **Save**.</span></span>
    
    <span data-ttu-id="01f62-170">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="01f62-172">他の MX レコードがリストにある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="01f62-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="01f62-174">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-174">Select **Save**.</span></span>
    
    <span data-ttu-id="01f62-175">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="01f62-177">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="01f62-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="01f62-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="01f62-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="01f62-p109">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01f62-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01f62-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01f62-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01f62-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01f62-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01f62-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01f62-186">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="01f62-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01f62-187">(行を追加する必要がある場合は **、[A/CNAME RECORDS (+)** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01f62-188">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01f62-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="01f62-189">**Host Name**</span></span>|<span data-ttu-id="01f62-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="01f62-190">**Type**</span></span>|<span data-ttu-id="01f62-191">**Result**</span><span class="sxs-lookup"><span data-stu-id="01f62-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01f62-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="01f62-192">autodiscover</span></span>  <br/> |<span data-ttu-id="01f62-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="01f62-193">CNAME</span></span>  <br/> |<span data-ttu-id="01f62-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="01f62-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="01f62-195">sip</span><span class="sxs-lookup"><span data-stu-id="01f62-195">sip</span></span>  <br/> |<span data-ttu-id="01f62-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="01f62-196">CNAME</span></span>  <br/> |<span data-ttu-id="01f62-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01f62-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01f62-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="01f62-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="01f62-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="01f62-199">CNAME</span></span>  <br/> |<span data-ttu-id="01f62-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01f62-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01f62-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="01f62-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="01f62-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="01f62-202">CNAME</span></span>  <br/> |<span data-ttu-id="01f62-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="01f62-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="01f62-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="01f62-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="01f62-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="01f62-205">CNAME</span></span>  <br/> |<span data-ttu-id="01f62-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01f62-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="01f62-208">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="01f62-210">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="01f62-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="01f62-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="01f62-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="01f62-212">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="01f62-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="01f62-213">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="01f62-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="01f62-214">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="01f62-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="01f62-215">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="01f62-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="01f62-p111">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01f62-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01f62-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01f62-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01f62-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01f62-222">[アカウント **の DNS ゾーン]** ページの [ドメイン名] **列で、** 更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="01f62-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="01f62-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01f62-225">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="01f62-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="01f62-226">(行を追加する必要がある場合は **、[A/CNAME RECORDS (+)** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="01f62-227">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01f62-228">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="01f62-228">**Host name**</span></span>|<span data-ttu-id="01f62-229">**種類**</span><span class="sxs-lookup"><span data-stu-id="01f62-229">**Type**</span></span>|<span data-ttu-id="01f62-230">**結果**</span><span class="sxs-lookup"><span data-stu-id="01f62-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="01f62-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="01f62-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="01f62-232">TXT</span><span class="sxs-lookup"><span data-stu-id="01f62-232">TXT</span></span>  <br/> |<span data-ttu-id="01f62-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="01f62-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="01f62-234">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01f62-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="01f62-236">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-236">Select **Save**.</span></span>
    
    <span data-ttu-id="01f62-237">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="01f62-239">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="01f62-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="01f62-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="01f62-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="01f62-p112">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="01f62-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="01f62-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="01f62-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="01f62-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="01f62-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="01f62-247">[ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="01f62-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="01f62-248">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="01f62-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="01f62-249">**Name**</span></span>|<span data-ttu-id="01f62-250">**Priority**</span><span class="sxs-lookup"><span data-stu-id="01f62-250">**Priority**</span></span>|<span data-ttu-id="01f62-251">**Weight**</span><span class="sxs-lookup"><span data-stu-id="01f62-251">**Weight**</span></span>|<span data-ttu-id="01f62-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="01f62-252">**Port**</span></span>|<span data-ttu-id="01f62-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="01f62-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="01f62-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="01f62-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="01f62-255">100</span><span class="sxs-lookup"><span data-stu-id="01f62-255">100</span></span>  <br/> |<span data-ttu-id="01f62-256">1</span><span class="sxs-lookup"><span data-stu-id="01f62-256">1</span></span>  <br/> |<span data-ttu-id="01f62-257">443</span><span class="sxs-lookup"><span data-stu-id="01f62-257">443</span></span>  <br/> |<span data-ttu-id="01f62-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01f62-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="01f62-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="01f62-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="01f62-260">100</span><span class="sxs-lookup"><span data-stu-id="01f62-260">100</span></span>  <br/> |<span data-ttu-id="01f62-261">1</span><span class="sxs-lookup"><span data-stu-id="01f62-261">1</span></span>  <br/> |<span data-ttu-id="01f62-262">5061</span><span class="sxs-lookup"><span data-stu-id="01f62-262">5061</span></span>  <br/> |<span data-ttu-id="01f62-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="01f62-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="01f62-265">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01f62-265">Select **Save**.</span></span>
    
    <span data-ttu-id="01f62-266">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="01f62-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="01f62-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f62-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
