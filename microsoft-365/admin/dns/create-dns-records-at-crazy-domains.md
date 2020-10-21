---
title: Microsoft 用の変わったドメインで DNS レコードを作成する
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の他のドメインにある他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: cf65173873affdc66e4e6d03764a3d6c842b7642
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646225"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="85fc9-103">Microsoft 用の変わったドメインで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="85fc9-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="85fc9-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="85fc9-105">使用している DNS ホスティング プロバイダーが Crazy Domains の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="85fc9-106">これらのレコードを、変わったドメインで追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="85fc9-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="85fc9-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="85fc9-110">Add a TXT record for verification</span></span>
<span data-ttu-id="85fc9-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="85fc9-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="85fc9-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85fc9-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="85fc9-p104">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="85fc9-119">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="85fc9-121">[ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="85fc9-123">[ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="85fc9-125">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="85fc9-127">[ **Add Record**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-検証-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="85fc9-129">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-129">Select **Add**.</span></span>
    
    ![CrazyDomains-検証-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="85fc9-131">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="85fc9-132">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="85fc9-132">**Sub Domain**</span></span>|<span data-ttu-id="85fc9-133">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="85fc9-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="85fc9-134">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="85fc9-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85fc9-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="85fc9-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="85fc9-136">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="85fc9-136">**Note:** This is an example.</span></span> <span data-ttu-id="85fc9-137">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="85fc9-138">確認する方法</span><span class="sxs-lookup"><span data-stu-id="85fc9-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-検証-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="85fc9-140">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-140">Select **Update**.</span></span>
    
    ![CrazyDomains-検証-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="85fc9-142">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="85fc9-143">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="85fc9-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="85fc9-144">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="85fc9-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="85fc9-145">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="85fc9-146">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="85fc9-147">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="85fc9-148">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="85fc9-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="85fc9-152">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="85fc9-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="85fc9-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="85fc9-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="85fc9-p107">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="85fc9-157">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="85fc9-159">[ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="85fc9-161">[ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="85fc9-163">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="85fc9-165">[ **Add Record:**] ボックスの一覧から [ **MX Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="85fc9-167">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-167">Select **Add**.</span></span>
    
    ![CrazyDomains-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="85fc9-169">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="85fc9-170">(ドロップダウンリストから **優先度** の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="85fc9-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="85fc9-171">**メール送信先ゾーン**</span><span class="sxs-lookup"><span data-stu-id="85fc9-171">**Mail For Zone**</span></span>|<span data-ttu-id="85fc9-172">**優先度**</span><span class="sxs-lookup"><span data-stu-id="85fc9-172">**Priority**</span></span>|<span data-ttu-id="85fc9-173">**割り当て先サーバー**</span><span class="sxs-lookup"><span data-stu-id="85fc9-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="85fc9-174">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="85fc9-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85fc9-175">1-d</span><span class="sxs-lookup"><span data-stu-id="85fc9-175">1</span></span>  <br/> <span data-ttu-id="85fc9-176">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-176">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="85fc9-177">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="85fc9-178">\**注:\*\*\*\<domain-key\>* Microsoft アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="85fc9-179">確認する方法</span><span class="sxs-lookup"><span data-stu-id="85fc9-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="85fc9-181">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-181">Select **Update**.</span></span>
    
    ![CrazyDomains-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="85fc9-183">その他の MX レコードが [ **Mx Record** ] セクションに表示されている場合は、いずれかのレコードに対して [ **変更** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="85fc9-185">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="85fc9-187">[ **更新** ] を選択して、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="85fc9-189">この手順の前半で追加した MX レコードだけを残し、同じ手順で、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="85fc9-190">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="85fc9-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="85fc9-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="85fc9-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="85fc9-p109">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="85fc9-195">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="85fc9-197">[ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="85fc9-199">[ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="85fc9-201">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="85fc9-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="85fc9-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="85fc9-205">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-205">Select **Add**.</span></span>
    
    ![CrazyDomains-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="85fc9-207">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="85fc9-208">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="85fc9-209">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="85fc9-209">**Sub Domain**</span></span>|<span data-ttu-id="85fc9-210">**エイリアス**</span><span class="sxs-lookup"><span data-stu-id="85fc9-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="85fc9-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="85fc9-211">autodiscover</span></span>  <br/> |<span data-ttu-id="85fc9-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="85fc9-213">sip</span><span class="sxs-lookup"><span data-stu-id="85fc9-213">sip</span></span>  <br/> |<span data-ttu-id="85fc9-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="85fc9-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="85fc9-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="85fc9-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="85fc9-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="85fc9-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="85fc9-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="85fc9-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="85fc9-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="85fc9-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="85fc9-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="85fc9-222">[ **ADD CNAME Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="85fc9-224">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="85fc9-225">新規レコードのボックスに、表の次の行の値を使用し、[ **ADD CNAME record**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="85fc9-226">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="85fc9-227">[ **更新** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="85fc9-229">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="85fc9-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="85fc9-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="85fc9-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="85fc9-231">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="85fc9-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="85fc9-232">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="85fc9-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="85fc9-233">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="85fc9-234">代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="85fc9-p111">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="85fc9-238">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="85fc9-240">[ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="85fc9-242">[ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="85fc9-244">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="85fc9-246">[ **Add Record:**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="85fc9-248">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-248">Select **Add**.</span></span>
    
    ![CrazyDomains-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="85fc9-250">新規レコードのボックスに、次の表の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="85fc9-251">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="85fc9-251">**Sub Domain**</span></span>|<span data-ttu-id="85fc9-252">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="85fc9-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="85fc9-253">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="85fc9-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="85fc9-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="85fc9-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="85fc9-255">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85fc9-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="85fc9-257">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-257">Select **Update**.</span></span>
    
    ![CrazyDomains-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="85fc9-259">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="85fc9-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="85fc9-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="85fc9-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="85fc9-p112">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="85fc9-264">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="85fc9-266">[ **ドメイン名** ] ページの [ **ドメイン** ] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="85fc9-268">[ **DNS 設定** ] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="85fc9-270">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="85fc9-272">[ **Add Record:**] ボックスの一覧から [ **SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="85fc9-274">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-274">Select **Add**.</span></span>
    
    ![CrazyDomains-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="85fc9-276">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="85fc9-277">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="85fc9-278">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="85fc9-278">**Record Type**</span></span>|<span data-ttu-id="85fc9-279">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="85fc9-279">**Sub Domain**</span></span>|<span data-ttu-id="85fc9-280">**Priority**</span><span class="sxs-lookup"><span data-stu-id="85fc9-280">**Priority**</span></span>|<span data-ttu-id="85fc9-281">**Weight**</span><span class="sxs-lookup"><span data-stu-id="85fc9-281">**Weight**</span></span>|<span data-ttu-id="85fc9-282">**Port**</span><span class="sxs-lookup"><span data-stu-id="85fc9-282">**Port**</span></span>|<span data-ttu-id="85fc9-283">**対象**</span><span class="sxs-lookup"><span data-stu-id="85fc9-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="85fc9-284">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="85fc9-284">SRV Record</span></span>  <br/> |<span data-ttu-id="85fc9-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="85fc9-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="85fc9-286">100</span><span class="sxs-lookup"><span data-stu-id="85fc9-286">100</span></span>  <br/> |<span data-ttu-id="85fc9-287">1-d</span><span class="sxs-lookup"><span data-stu-id="85fc9-287">1</span></span>  <br/> |<span data-ttu-id="85fc9-288">443</span><span class="sxs-lookup"><span data-stu-id="85fc9-288">443</span></span>  <br/> |<span data-ttu-id="85fc9-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="85fc9-290">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="85fc9-290">SRV Record</span></span>  <br/> |<span data-ttu-id="85fc9-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="85fc9-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="85fc9-292">100</span><span class="sxs-lookup"><span data-stu-id="85fc9-292">100</span></span>  <br/> |<span data-ttu-id="85fc9-293">1-d</span><span class="sxs-lookup"><span data-stu-id="85fc9-293">1</span></span>  <br/> |<span data-ttu-id="85fc9-294">5061</span><span class="sxs-lookup"><span data-stu-id="85fc9-294">5061</span></span>  <br/> |<span data-ttu-id="85fc9-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="85fc9-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="85fc9-297">[ **ADD SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="85fc9-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="85fc9-299">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="85fc9-300">新規レコードのボックスで、次の表の 2 行目の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="85fc9-301">[ **更新** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="85fc9-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="85fc9-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fc9-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
