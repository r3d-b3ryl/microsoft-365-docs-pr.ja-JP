---
title: Names.co.uk で Office 365 用の DNS レコードを作成する
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: ドメインを確認し、電子メール、Skype for Business Online、および Names.co.uk for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: d27cd22b0047cf58def01533a486c7641f50148e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42348138"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="97824-103">Names.co.uk で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="97824-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="97824-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="97824-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="97824-105">使用している DNS ホスティング プロバイダーが Names.co.uk の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="97824-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="97824-106">これらのレコードを Names.co.uk で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="97824-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="97824-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97824-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="97824-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97824-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="97824-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="97824-111">Add a TXT record for verification</span></span>
<span data-ttu-id="97824-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="97824-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="97824-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="97824-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97824-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="97824-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="97824-p104">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97824-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="97824-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="97824-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="97824-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="97824-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="97824-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="97824-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="97824-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="97824-125">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="97824-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="97824-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="97824-127">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="97824-127">**Host name**</span></span>|<span data-ttu-id="97824-128">**種類**</span><span class="sxs-lookup"><span data-stu-id="97824-128">**Type**</span></span>|<span data-ttu-id="97824-129">**結果**</span><span class="sxs-lookup"><span data-stu-id="97824-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="97824-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="97824-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="97824-131">TXT</span><span class="sxs-lookup"><span data-stu-id="97824-131">TXT</span></span>  <br/> |<span data-ttu-id="97824-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="97824-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="97824-p105">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="97824-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
       
    ![NamesUK-BP-検証-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="97824-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-137">Select **Save**.</span></span>
    
    <span data-ttu-id="97824-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-検証-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="97824-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="97824-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="97824-141">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="97824-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="97824-142">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="97824-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="97824-143">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="97824-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="97824-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="97824-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="97824-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="97824-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97824-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="97824-150">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="97824-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="97824-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="97824-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="97824-p107">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97824-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="97824-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="97824-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="97824-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="97824-158">[ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="97824-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="97824-159">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="97824-160">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="97824-160">**Host name**</span></span>|<span data-ttu-id="97824-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="97824-161">**Priority**</span></span>|<span data-ttu-id="97824-162">**結果**</span><span class="sxs-lookup"><span data-stu-id="97824-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="97824-163">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="97824-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="97824-164">1-d</span><span class="sxs-lookup"><span data-stu-id="97824-164">1</span></span>  <br/> <span data-ttu-id="97824-165">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97824-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="97824-166">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="97824-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="97824-167">> [!NOTE]> Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="97824-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="97824-168">確認する方法</span><span class="sxs-lookup"><span data-stu-id="97824-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="97824-170">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-170">Select **Save**.</span></span>
    
    <span data-ttu-id="97824-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="97824-173">他の MX レコードがリストにある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="97824-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="97824-175">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-175">Select **Save**.</span></span>
    
    <span data-ttu-id="97824-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="97824-178">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="97824-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="97824-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="97824-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="97824-p109">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97824-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="97824-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="97824-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="97824-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="97824-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="97824-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="97824-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="97824-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="97824-188">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="97824-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="97824-189">(下へスクロールしなければならないことがあります)。</span><span class="sxs-lookup"><span data-stu-id="97824-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="97824-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="97824-190">**Host Name**</span></span>|<span data-ttu-id="97824-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="97824-191">**Type**</span></span>|<span data-ttu-id="97824-192">**Result**</span><span class="sxs-lookup"><span data-stu-id="97824-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="97824-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="97824-193">autodiscover</span></span>  <br/> |<span data-ttu-id="97824-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="97824-194">CNAME</span></span>  <br/> |<span data-ttu-id="97824-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="97824-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="97824-196">sip</span><span class="sxs-lookup"><span data-stu-id="97824-196">sip</span></span>  <br/> |<span data-ttu-id="97824-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="97824-197">CNAME</span></span>  <br/> |<span data-ttu-id="97824-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="97824-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="97824-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="97824-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="97824-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="97824-200">CNAME</span></span>  <br/> |<span data-ttu-id="97824-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="97824-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="97824-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="97824-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="97824-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="97824-203">CNAME</span></span>  <br/> |<span data-ttu-id="97824-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="97824-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="97824-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="97824-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="97824-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="97824-206">CNAME</span></span>  <br/> |<span data-ttu-id="97824-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="97824-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="97824-209">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="97824-211">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="97824-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="97824-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="97824-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="97824-213">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="97824-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="97824-214">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="97824-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="97824-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="97824-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="97824-216">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="97824-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="97824-p111">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97824-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="97824-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="97824-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="97824-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="97824-223">[**アカウントの DNS ゾーン**] ページの [**ドメイン名**] 列で、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="97824-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="97824-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="97824-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="97824-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="97824-227">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="97824-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="97824-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="97824-229">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="97824-229">**Host name**</span></span>|<span data-ttu-id="97824-230">**種類**</span><span class="sxs-lookup"><span data-stu-id="97824-230">**Type**</span></span>|<span data-ttu-id="97824-231">**結果**</span><span class="sxs-lookup"><span data-stu-id="97824-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="97824-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="97824-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="97824-233">TXT</span><span class="sxs-lookup"><span data-stu-id="97824-233">TXT</span></span>  <br/> |<span data-ttu-id="97824-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="97824-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="97824-235">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97824-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="97824-237">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-237">Select **Save**.</span></span>
    
    <span data-ttu-id="97824-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="97824-240">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="97824-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="97824-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="97824-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="97824-p112">まず、[このリンク](https://account.names.co.uk/dashboard#/)を使って Names.co.uk でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97824-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="97824-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="97824-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="97824-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="97824-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="97824-248">[ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="97824-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="97824-249">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="97824-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="97824-250">**Name**</span><span class="sxs-lookup"><span data-stu-id="97824-250">**Name**</span></span>|<span data-ttu-id="97824-251">**Priority**</span><span class="sxs-lookup"><span data-stu-id="97824-251">**Priority**</span></span>|<span data-ttu-id="97824-252">**Weight**</span><span class="sxs-lookup"><span data-stu-id="97824-252">**Weight**</span></span>|<span data-ttu-id="97824-253">**Port**</span><span class="sxs-lookup"><span data-stu-id="97824-253">**Port**</span></span>|<span data-ttu-id="97824-254">**結果**</span><span class="sxs-lookup"><span data-stu-id="97824-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="97824-255">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="97824-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="97824-256">100</span><span class="sxs-lookup"><span data-stu-id="97824-256">100</span></span>  <br/> |<span data-ttu-id="97824-257">1-d</span><span class="sxs-lookup"><span data-stu-id="97824-257">1</span></span>  <br/> |<span data-ttu-id="97824-258">443</span><span class="sxs-lookup"><span data-stu-id="97824-258">443</span></span>  <br/> |<span data-ttu-id="97824-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="97824-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="97824-260">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="97824-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="97824-261">100</span><span class="sxs-lookup"><span data-stu-id="97824-261">100</span></span>  <br/> |<span data-ttu-id="97824-262">1-d</span><span class="sxs-lookup"><span data-stu-id="97824-262">1</span></span>  <br/> |<span data-ttu-id="97824-263">5061</span><span class="sxs-lookup"><span data-stu-id="97824-263">5061</span></span>  <br/> |<span data-ttu-id="97824-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="97824-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="97824-266">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97824-266">Select **Save**.</span></span>
    
    <span data-ttu-id="97824-267">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="97824-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="97824-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97824-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
