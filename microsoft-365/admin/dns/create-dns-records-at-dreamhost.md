---
title: Dreamhost で Office 365 用の DNS レコードを作成する
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: ドメインを確認し、電子メール、Skype for Business Online、および Dreamhost for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f3f52e97fefece72dd96d9370e75e24fc4cebedf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248883"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a><span data-ttu-id="7b6a2-103">Dreamhost で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="7b6a2-103">Create DNS records at Dreamhost for Office 365</span></span>

 <span data-ttu-id="7b6a2-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7b6a2-105">使用している DNS ホスティング プロバイダーが DreamHost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Lync などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-105">If DreamHost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
 
<span data-ttu-id="7b6a2-106">これらのレコードを DreamHost で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-106">After you add these records at DreamHost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="7b6a2-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b6a2-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7b6a2-111">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7b6a2-111">Add a TXT record for verification</span></span>
<span data-ttu-id="7b6a2-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6a2-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7b6a2-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b6a2-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7b6a2-p104">まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p104">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7b6a2-120">[**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-120">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7b6a2-122">[ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-122">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7b6a2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-124">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7b6a2-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7b6a2-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7b6a2-127">**名前**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-127">**Name**</span></span>|<span data-ttu-id="7b6a2-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-128">**Type**</span></span>|<span data-ttu-id="7b6a2-129">**値**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-129">**Value**</span></span>|<span data-ttu-id="7b6a2-130">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-130">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6a2-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7b6a2-132">TXT</span><span class="sxs-lookup"><span data-stu-id="7b6a2-132">TXT</span></span>  <br/> |<span data-ttu-id="7b6a2-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7b6a2-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7b6a2-p105">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="7b6a2-137">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-137">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-検証-1-1](../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. <span data-ttu-id="7b6a2-139">[**今すぐレコードを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-139">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Verify-1-2](../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. <span data-ttu-id="7b6a2-141">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7b6a2-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="7b6a2-143">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7b6a2-144">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7b6a2-145">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="7b6a2-146">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="7b6a2-147">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="7b6a2-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="7b6a2-151">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="7b6a2-151">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="7b6a2-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6a2-152"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="7b6a2-153">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-153">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7b6a2-p107">まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p107">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7b6a2-157">[**ダッシュボード**] ページで、[**メール**] を選択してから、[**カスタム MX**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-157">On the **Dashboard** page, select **Mail**, and then **Custom MX**.</span></span>
    
    ![Dreamhost-BP-Configure-2-1](../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. <span data-ttu-id="7b6a2-159">[**メール配信の管理**] セクションの [**操作**] 列で、編集するドメインの [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-159">In the **Manage Mail Delivery** section, in the **Actions** column, select **Edit** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-2-2](../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. <span data-ttu-id="7b6a2-161">[ **Custom MX Record**] セクションにある新規レコードのボックスに、次の表から次の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-161">In the **Custom MX Record** section, in the boxes for the new record, type or copy and paste the following values from the following table.</span></span> 
    
    <span data-ttu-id="7b6a2-162">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-162">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7b6a2-163">(MX レコードが他にもある場合は、それらのレコードが削除されるようにマーク付けします。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-163">(If there are any other existing MX records, mark those records to be deleted.)</span></span>
    
    |<span data-ttu-id="7b6a2-164">**MX レコード (必須)**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-164">**MX Record (required)**</span></span>|
    |:-----|
    |<span data-ttu-id="7b6a2-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-165">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7b6a2-166">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-166">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7b6a2-p108">0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  </span><span class="sxs-lookup"><span data-stu-id="7b6a2-p108">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="7b6a2-169">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="7b6a2-170">確認する方法</span><span class="sxs-lookup"><span data-stu-id="7b6a2-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-2-3](../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. <span data-ttu-id="7b6a2-172">[**今すぐカスタム MX レコードを使用するように、このドメインを変更する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-172">Select **Change this domain to use custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-4](../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. <span data-ttu-id="7b6a2-174">他の MX レコードが既にある場合は、エントリを選択し、キーボードの **Delete** キーを押して、各レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-174">If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Dreamhost-BP-Configure-2-5](../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. <span data-ttu-id="7b6a2-176">レコードを削除した場合は、[**今すぐカスタム MX レコードを更新**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-176">If you have deleted any records, select **Update your custom MX records now!**</span></span>
    
    ![Dreamhost-BP-Configure-2-6](../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="7b6a2-178">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7b6a2-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="7b6a2-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6a2-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="7b6a2-180">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-180">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7b6a2-p110">まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p110">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7b6a2-184">[**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-184">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7b6a2-186">[ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-186">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7b6a2-188">[ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-188">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7b6a2-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-189">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7b6a2-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7b6a2-191">**名前**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-191">**Name**</span></span>|<span data-ttu-id="7b6a2-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-192">**Type**</span></span>|<span data-ttu-id="7b6a2-193">**値**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-193">**Value**</span></span>|<span data-ttu-id="7b6a2-194">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-194">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6a2-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7b6a2-195">autodiscover</span></span>  <br/> |<span data-ttu-id="7b6a2-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="7b6a2-196">CNAME</span></span>  <br/> |<span data-ttu-id="7b6a2-197">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-197">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7b6a2-198">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-199">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-199">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7b6a2-200">sip</span><span class="sxs-lookup"><span data-stu-id="7b6a2-200">sip</span></span>  <br/> |<span data-ttu-id="7b6a2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="7b6a2-201">CNAME</span></span>  <br/> |<span data-ttu-id="7b6a2-202">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-202">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6a2-203">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-203">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-204">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-204">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7b6a2-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7b6a2-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7b6a2-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="7b6a2-206">CNAME</span></span>  <br/> |<span data-ttu-id="7b6a2-207">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-207">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6a2-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-209">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-209">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7b6a2-210">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7b6a2-210">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7b6a2-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="7b6a2-211">CNAME</span></span>  <br/> |<span data-ttu-id="7b6a2-212">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-212">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7b6a2-213">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-213">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-214">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-214">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7b6a2-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7b6a2-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7b6a2-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="7b6a2-216">CNAME</span></span>  <br/> |<span data-ttu-id="7b6a2-217">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-217">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7b6a2-218">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-219">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-219">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-3-1](../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. <span data-ttu-id="7b6a2-221">[**今すぐレコードを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-221">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-3-2](../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. <span data-ttu-id="7b6a2-223">上記の2つの手順と、表の他の5つの行の値を使用して、残りの5つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-223">Using the preceding two steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7b6a2-224">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7b6a2-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7b6a2-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6a2-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b6a2-226">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7b6a2-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7b6a2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b6a2-228">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="7b6a2-229">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-229">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="7b6a2-230">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-230">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7b6a2-p112">まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p112">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7b6a2-234">[**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-234">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7b6a2-236">[ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-236">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7b6a2-238">[ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-238">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7b6a2-239">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-239">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7b6a2-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7b6a2-241">**名前**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-241">**Name**</span></span>|<span data-ttu-id="7b6a2-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-242">**Type**</span></span>|<span data-ttu-id="7b6a2-243">**値**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-243">**Value**</span></span>|<span data-ttu-id="7b6a2-244">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-244">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6a2-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7b6a2-246">TXT</span><span class="sxs-lookup"><span data-stu-id="7b6a2-246">TXT</span></span>  <br/> |<span data-ttu-id="7b6a2-247">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7b6a2-247">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7b6a2-248">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-248">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7b6a2-249">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-249">(This field is optional.)</span></span>  <br/> |
   
   ![Dreamhost-4-1](../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. <span data-ttu-id="7b6a2-251">[**今すぐレコードを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-251">Select **Add Record Now!**</span></span>
    
    ![Dreamhost-BP-Configure-4-2](../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. <span data-ttu-id="7b6a2-253">上の 2 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-253">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="7b6a2-254">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="7b6a2-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="7b6a2-255"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6a2-255"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="7b6a2-256">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-256">Follow the steps below.</span></span>
  
1. <span data-ttu-id="7b6a2-p113">まず、[このリンク](https://panel.dreamhost.com/)を使って DreamHost でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p113">To get started, go to your domains page at DreamHost by using [this link](https://panel.dreamhost.com/). You'll be prompted to Sign in.</span></span>
    
    ![Dreamhost-BP-Configure-1-1](../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. <span data-ttu-id="7b6a2-260">[**ダッシュボード**] ページで、[ **domains**] を選択してから、**ドメインを管理**します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-260">On the **Dashboard** page, select **Domains**, and then **Manage Domains**.</span></span>
    
    ![Dreamhost-BP-Configure-1-2](../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. <span data-ttu-id="7b6a2-262">[ドメインの**管理**] ページの [**ドメイン**] セクションで、編集するドメインの [ **DNS** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-262">On the **Manage Domains** page, in the **Domain** section, select **DNS** for the domain that you want to edit.</span></span> 
    
    ![Dreamhost-BP-Configure-1-3](../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. <span data-ttu-id="7b6a2-264">[ **Add a custom DNS record**] セクションにある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-264">In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7b6a2-265">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-265">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7b6a2-266">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-266">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7b6a2-267">**名前**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-267">**Name**</span></span>|<span data-ttu-id="7b6a2-268">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-268">**Type**</span></span>|<span data-ttu-id="7b6a2-269">**値**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-269">**Value**</span></span>|<span data-ttu-id="7b6a2-270">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-270">**Comment**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6a2-271">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="7b6a2-271">_sip._tls</span></span>  <br/> |<span data-ttu-id="7b6a2-272">SRV</span><span class="sxs-lookup"><span data-stu-id="7b6a2-272">SRV</span></span>  <br/> |<span data-ttu-id="7b6a2-273">100 1 443</span><span class="sxs-lookup"><span data-stu-id="7b6a2-273">100 1 443</span></span>  <br/> <span data-ttu-id="7b6a2-274">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-274">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6a2-275">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-275">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-276">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-276">(This field is optional.)</span></span>  <br/> |
    |<span data-ttu-id="7b6a2-277">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="7b6a2-277">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="7b6a2-278">SRV</span><span class="sxs-lookup"><span data-stu-id="7b6a2-278">SRV</span></span>  <br/> |<span data-ttu-id="7b6a2-279">100 1 5061</span><span class="sxs-lookup"><span data-stu-id="7b6a2-279">100 1 5061</span></span>  <br/> <span data-ttu-id="7b6a2-280">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-280">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6a2-281">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="7b6a2-281">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6a2-282">(このフィールドは省略可能です。)</span><span class="sxs-lookup"><span data-stu-id="7b6a2-282">(This field is optional.)</span></span>  <br/> |
   
    ![Dreamhost-5-1](../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. <span data-ttu-id="7b6a2-284">[ **Add Record Now!**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-284">Select **Add Record Now!**.</span></span>
    
    ![Dreamhost-BP-Configure-5-2](../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. <span data-ttu-id="7b6a2-286">上の 2 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-286">Using the preceding two steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="7b6a2-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b6a2-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
