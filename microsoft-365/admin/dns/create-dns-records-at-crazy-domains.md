---
title: Microsoft 用の変わったドメインで DNS レコードを作成する
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の他のドメインにある他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: db8979d303e4749a2a04870d277b68e5aec2e52f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629697"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="dc37b-103">Microsoft 用の変わったドメインで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="dc37b-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="dc37b-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dc37b-105">使用している DNS ホスティング プロバイダーが Crazy Domains の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dc37b-106">これらのレコードを、変わったドメインで追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="dc37b-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc37b-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dc37b-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="dc37b-111">Add a TXT record for verification</span></span>
<span data-ttu-id="dc37b-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dc37b-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dc37b-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc37b-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="dc37b-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc37b-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dc37b-p104">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="dc37b-120">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="dc37b-122">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="dc37b-124">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="dc37b-126">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="dc37b-128">[ **Add Record**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-検証-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="dc37b-130">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-130">Select **Add**.</span></span>
    
    ![CrazyDomains-検証-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="dc37b-132">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dc37b-133">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="dc37b-133">**Sub Domain**</span></span>|<span data-ttu-id="dc37b-134">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="dc37b-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="dc37b-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="dc37b-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc37b-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dc37b-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dc37b-137">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="dc37b-137">**Note:** This is an example.</span></span> <span data-ttu-id="dc37b-138">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="dc37b-139">確認する方法</span><span class="sxs-lookup"><span data-stu-id="dc37b-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-検証-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="dc37b-141">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-141">Select **Update**.</span></span>
    
    ![CrazyDomains-検証-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="dc37b-143">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dc37b-144">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="dc37b-145">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dc37b-146">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="dc37b-147">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dc37b-148">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dc37b-149">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dc37b-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dc37b-153">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="dc37b-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dc37b-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dc37b-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="dc37b-p107">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="dc37b-158">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="dc37b-160">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="dc37b-162">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="dc37b-164">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="dc37b-166">[ **Add Record:**] ボックスの一覧から [ **MX Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="dc37b-168">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-168">Select **Add**.</span></span>
    
    ![CrazyDomains-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="dc37b-170">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="dc37b-171">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="dc37b-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dc37b-172">**メール送信先ゾーン**</span><span class="sxs-lookup"><span data-stu-id="dc37b-172">**Mail For Zone**</span></span>|<span data-ttu-id="dc37b-173">**優先度**</span><span class="sxs-lookup"><span data-stu-id="dc37b-173">**Priority**</span></span>|<span data-ttu-id="dc37b-174">**割り当て先サーバー**</span><span class="sxs-lookup"><span data-stu-id="dc37b-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="dc37b-175">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="dc37b-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc37b-176">1-d</span><span class="sxs-lookup"><span data-stu-id="dc37b-176">1</span></span>  <br/> <span data-ttu-id="dc37b-177">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="dc37b-178">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dc37b-179">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-179">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="dc37b-180">確認する方法</span><span class="sxs-lookup"><span data-stu-id="dc37b-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="dc37b-182">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-182">Select **Update**.</span></span>
    
    ![CrazyDomains-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="dc37b-184">その他の MX レコードが [ **Mx Record** ] セクションに表示されている場合は、いずれかのレコードに対して [**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="dc37b-186">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="dc37b-188">[**更新**] を選択して、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="dc37b-190">この手順の前半で追加した MX レコードだけを残し、同じ手順で、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dc37b-191">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="dc37b-191">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="dc37b-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dc37b-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="dc37b-p109">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="dc37b-196">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="dc37b-198">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="dc37b-200">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="dc37b-202">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="dc37b-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="dc37b-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="dc37b-206">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-206">Select **Add**.</span></span>
    
    ![CrazyDomains-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="dc37b-208">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="dc37b-209">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="dc37b-210">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="dc37b-210">**Sub Domain**</span></span>|<span data-ttu-id="dc37b-211">**エイリアス**</span><span class="sxs-lookup"><span data-stu-id="dc37b-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="dc37b-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dc37b-212">autodiscover</span></span>  <br/> |<span data-ttu-id="dc37b-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="dc37b-214">sip</span><span class="sxs-lookup"><span data-stu-id="dc37b-214">sip</span></span>  <br/> |<span data-ttu-id="dc37b-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc37b-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dc37b-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dc37b-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc37b-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dc37b-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dc37b-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dc37b-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="dc37b-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dc37b-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dc37b-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="dc37b-223">[ **ADD CNAME Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="dc37b-225">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="dc37b-226">新規レコードのボックスに、表の次の行の値を使用し、[ **ADD CNAME record**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="dc37b-227">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="dc37b-228">[**更新**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dc37b-230">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="dc37b-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dc37b-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dc37b-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc37b-232">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc37b-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dc37b-233">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="dc37b-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dc37b-234">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-234">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dc37b-235">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-235">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="dc37b-p111">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="dc37b-239">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="dc37b-241">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="dc37b-243">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="dc37b-245">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="dc37b-247">[ **Add Record:**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="dc37b-249">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-249">Select **Add**.</span></span>
    
    ![CrazyDomains-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="dc37b-251">新規レコードのボックスに、次の表の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="dc37b-252">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="dc37b-252">**Sub Domain**</span></span>|<span data-ttu-id="dc37b-253">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="dc37b-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="dc37b-254">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="dc37b-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="dc37b-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dc37b-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="dc37b-256">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc37b-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="dc37b-258">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-258">Select **Update**.</span></span>
    
    ![CrazyDomains-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dc37b-260">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="dc37b-260">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dc37b-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dc37b-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="dc37b-p112">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="dc37b-265">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="dc37b-267">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="dc37b-269">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="dc37b-271">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="dc37b-273">[ **Add Record:**] ボックスの一覧から [ **SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="dc37b-275">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-275">Select **Add**.</span></span>
    
    ![CrazyDomains-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="dc37b-277">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="dc37b-278">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="dc37b-279">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="dc37b-279">**Record Type**</span></span>|<span data-ttu-id="dc37b-280">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="dc37b-280">**Sub Domain**</span></span>|<span data-ttu-id="dc37b-281">**Priority**</span><span class="sxs-lookup"><span data-stu-id="dc37b-281">**Priority**</span></span>|<span data-ttu-id="dc37b-282">**Weight**</span><span class="sxs-lookup"><span data-stu-id="dc37b-282">**Weight**</span></span>|<span data-ttu-id="dc37b-283">**Port**</span><span class="sxs-lookup"><span data-stu-id="dc37b-283">**Port**</span></span>|<span data-ttu-id="dc37b-284">**対象**</span><span class="sxs-lookup"><span data-stu-id="dc37b-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dc37b-285">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="dc37b-285">SRV Record</span></span>  <br/> |<span data-ttu-id="dc37b-286">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="dc37b-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="dc37b-287">100</span><span class="sxs-lookup"><span data-stu-id="dc37b-287">100</span></span>  <br/> |<span data-ttu-id="dc37b-288">1-d</span><span class="sxs-lookup"><span data-stu-id="dc37b-288">1</span></span>  <br/> |<span data-ttu-id="dc37b-289">443</span><span class="sxs-lookup"><span data-stu-id="dc37b-289">443</span></span>  <br/> |<span data-ttu-id="dc37b-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="dc37b-291">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="dc37b-291">SRV Record</span></span>  <br/> |<span data-ttu-id="dc37b-292">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="dc37b-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="dc37b-293">100</span><span class="sxs-lookup"><span data-stu-id="dc37b-293">100</span></span>  <br/> |<span data-ttu-id="dc37b-294">1-d</span><span class="sxs-lookup"><span data-stu-id="dc37b-294">1</span></span>  <br/> |<span data-ttu-id="dc37b-295">5061</span><span class="sxs-lookup"><span data-stu-id="dc37b-295">5061</span></span>  <br/> |<span data-ttu-id="dc37b-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dc37b-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="dc37b-298">[ **ADD SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dc37b-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="dc37b-300">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="dc37b-301">新規レコードのボックスで、次の表の 2 行目の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="dc37b-302">[**更新**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="dc37b-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="dc37b-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc37b-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
