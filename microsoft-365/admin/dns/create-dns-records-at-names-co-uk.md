---
title: Microsoft の Names.co.uk で DNS レコードを作成する
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: ドメインを確認し、電子メール、Skype for Business Online、および Names.co.uk のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 91c328877d583f415ffd2b8312ff1dc899a05bcc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939169"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="9f967-103">Microsoft の Names.co.uk で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9f967-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="9f967-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9f967-105">使用している DNS ホスティング プロバイダーが Names.co.uk の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="9f967-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="9f967-106">これらのレコードを Names.co.uk で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9f967-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="9f967-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9f967-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9f967-110">Add a TXT record for verification</span></span>
<span data-ttu-id="9f967-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9f967-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9f967-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f967-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9f967-p104">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="9f967-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9f967-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9f967-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="9f967-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9f967-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9f967-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9f967-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="9f967-124">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="9f967-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="9f967-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="9f967-126">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9f967-126">**Host name**</span></span>|<span data-ttu-id="9f967-127">**種類**</span><span class="sxs-lookup"><span data-stu-id="9f967-127">**Type**</span></span>|<span data-ttu-id="9f967-128">**結果**</span><span class="sxs-lookup"><span data-stu-id="9f967-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9f967-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="9f967-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9f967-130">TXT</span><span class="sxs-lookup"><span data-stu-id="9f967-130">TXT</span></span>  <br/> |<span data-ttu-id="9f967-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9f967-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9f967-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9f967-132">**Note:** This is an example.</span></span> <span data-ttu-id="9f967-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9f967-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9f967-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-検証-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="9f967-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-136">Select **Save**.</span></span>
    
    <span data-ttu-id="9f967-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-検証-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="9f967-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9f967-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9f967-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9f967-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9f967-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9f967-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9f967-142">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9f967-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9f967-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9f967-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9f967-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9f967-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9f967-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9f967-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9f967-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9f967-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9f967-p107">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="9f967-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9f967-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9f967-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="9f967-157">[ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9f967-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9f967-158">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9f967-159">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9f967-159">**Host name**</span></span>|<span data-ttu-id="9f967-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9f967-160">**Priority**</span></span>|<span data-ttu-id="9f967-161">**結果**</span><span class="sxs-lookup"><span data-stu-id="9f967-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9f967-162">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="9f967-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9f967-163">1-d</span><span class="sxs-lookup"><span data-stu-id="9f967-163">1</span></span>  <br/> <span data-ttu-id="9f967-164">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="9f967-165">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9f967-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9f967-166">> [!NOTE]>、Microsoft アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f967-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="9f967-167">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9f967-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="9f967-169">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-169">Select **Save**.</span></span>
    
    <span data-ttu-id="9f967-170">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="9f967-172">他の MX レコードがリストにある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="9f967-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="9f967-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-174">Select **Save**.</span></span>
    
    <span data-ttu-id="9f967-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9f967-177">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9f967-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9f967-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9f967-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9f967-p109">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="9f967-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9f967-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9f967-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="9f967-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9f967-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9f967-186">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9f967-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="9f967-187">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="9f967-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="9f967-188">(下へスクロールしなければならないことがあります)。</span><span class="sxs-lookup"><span data-stu-id="9f967-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9f967-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="9f967-189">**Host Name**</span></span>|<span data-ttu-id="9f967-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="9f967-190">**Type**</span></span>|<span data-ttu-id="9f967-191">**Result**</span><span class="sxs-lookup"><span data-stu-id="9f967-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9f967-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9f967-192">autodiscover</span></span>  <br/> |<span data-ttu-id="9f967-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="9f967-193">CNAME</span></span>  <br/> |<span data-ttu-id="9f967-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9f967-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9f967-195">sip</span><span class="sxs-lookup"><span data-stu-id="9f967-195">sip</span></span>  <br/> |<span data-ttu-id="9f967-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="9f967-196">CNAME</span></span>  <br/> |<span data-ttu-id="9f967-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9f967-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9f967-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9f967-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9f967-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9f967-199">CNAME</span></span>  <br/> |<span data-ttu-id="9f967-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9f967-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9f967-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9f967-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9f967-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="9f967-202">CNAME</span></span>  <br/> |<span data-ttu-id="9f967-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9f967-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9f967-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9f967-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9f967-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="9f967-205">CNAME</span></span>  <br/> |<span data-ttu-id="9f967-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9f967-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="9f967-208">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9f967-210">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9f967-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9f967-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9f967-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f967-212">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f967-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9f967-213">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9f967-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9f967-214">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9f967-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9f967-215">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9f967-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="9f967-p111">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="9f967-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9f967-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9f967-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="9f967-222">[**アカウントの DNS ゾーン**] ページの [**ドメイン名**] 列で、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="9f967-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9f967-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9f967-225">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="9f967-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="9f967-226">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="9f967-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="9f967-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9f967-228">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9f967-228">**Host name**</span></span>|<span data-ttu-id="9f967-229">**種類**</span><span class="sxs-lookup"><span data-stu-id="9f967-229">**Type**</span></span>|<span data-ttu-id="9f967-230">**結果**</span><span class="sxs-lookup"><span data-stu-id="9f967-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9f967-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="9f967-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9f967-232">TXT</span><span class="sxs-lookup"><span data-stu-id="9f967-232">TXT</span></span>  <br/> |<span data-ttu-id="9f967-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9f967-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9f967-234">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f967-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="9f967-236">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-236">Select **Save**.</span></span>
    
    <span data-ttu-id="9f967-237">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9f967-239">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9f967-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9f967-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9f967-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9f967-p112">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9f967-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="9f967-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="9f967-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9f967-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9f967-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="9f967-247">[ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9f967-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9f967-248">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="9f967-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9f967-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="9f967-249">**Name**</span></span>|<span data-ttu-id="9f967-250">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9f967-250">**Priority**</span></span>|<span data-ttu-id="9f967-251">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9f967-251">**Weight**</span></span>|<span data-ttu-id="9f967-252">**Port**</span><span class="sxs-lookup"><span data-stu-id="9f967-252">**Port**</span></span>|<span data-ttu-id="9f967-253">**結果**</span><span class="sxs-lookup"><span data-stu-id="9f967-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9f967-254">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="9f967-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="9f967-255">100</span><span class="sxs-lookup"><span data-stu-id="9f967-255">100</span></span>  <br/> |<span data-ttu-id="9f967-256">1-d</span><span class="sxs-lookup"><span data-stu-id="9f967-256">1</span></span>  <br/> |<span data-ttu-id="9f967-257">443</span><span class="sxs-lookup"><span data-stu-id="9f967-257">443</span></span>  <br/> |<span data-ttu-id="9f967-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9f967-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9f967-259">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="9f967-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9f967-260">100</span><span class="sxs-lookup"><span data-stu-id="9f967-260">100</span></span>  <br/> |<span data-ttu-id="9f967-261">1-d</span><span class="sxs-lookup"><span data-stu-id="9f967-261">1</span></span>  <br/> |<span data-ttu-id="9f967-262">5061</span><span class="sxs-lookup"><span data-stu-id="9f967-262">5061</span></span>  <br/> |<span data-ttu-id="9f967-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9f967-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="9f967-265">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f967-265">Select **Save**.</span></span>
    
    <span data-ttu-id="9f967-266">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="9f967-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="9f967-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f967-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
