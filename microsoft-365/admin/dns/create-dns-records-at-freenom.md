---
title: Freenom で Office 365 用の DNS レコードを作成する
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: ドメインを確認し、電子メール、Skype for Business Online、および Office 365 用の Freenom の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 16348eb03a6507e15d31d5c183bd91125d0236f6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350668"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a><span data-ttu-id="de6a6-103">Freenom で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="de6a6-103">Create DNS records at Freenom for Office 365</span></span>

<span data-ttu-id="de6a6-104">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="de6a6-p101">Freenom の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、かなりのサービスの制限事項があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p101">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="de6a6-107">サービスの制限があっても、Freenom で Office 365 の DNS レコードを管理する場合は、この記事に示す手順に従って、ドメインを確認し、メールや他のサービスの DNS レコードを設定してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-107">If despite the service limitations, you choose to manage your own Office 365 DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
<span data-ttu-id="de6a6-108">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="de6a6-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de6a6-112">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de6a6-112">Add a TXT record for verification</span></span>
<span data-ttu-id="de6a6-113"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="de6a6-113"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="de6a6-p103">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de6a6-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="de6a6-118">まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-118">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="de6a6-119">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-119">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="de6a6-121">[**サービス**] を選択し、[**マイドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-121">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="de6a6-123">編集するドメインの場合は、[ドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-123">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="de6a6-125">[ **Manage Freenom DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-125">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="de6a6-127">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-127">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="de6a6-129">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-129">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="de6a6-130">**名前**</span><span class="sxs-lookup"><span data-stu-id="de6a6-130">**Name**</span></span>|<span data-ttu-id="de6a6-131">**Type**</span><span class="sxs-lookup"><span data-stu-id="de6a6-131">**Type**</span></span>|<span data-ttu-id="de6a6-132">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de6a6-132">**TTL**</span></span>|<span data-ttu-id="de6a6-133">**Target**</span><span class="sxs-lookup"><span data-stu-id="de6a6-133">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de6a6-134">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="de6a6-134">(leave blank)</span></span>  <br/> |<span data-ttu-id="de6a6-135">TXT</span><span class="sxs-lookup"><span data-stu-id="de6a6-135">TXT</span></span>  <br/> |<span data-ttu-id="de6a6-136">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-136">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-137">MS = msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="de6a6-137">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="de6a6-p106">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="de6a6-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="de6a6-142">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-142">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="de6a6-144">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-144">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de6a6-145">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="de6a6-146">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="de6a6-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de6a6-147">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="de6a6-148">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="de6a6-149">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="de6a6-150">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="de6a6-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="de6a6-154">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="de6a6-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="de6a6-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="de6a6-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="de6a6-156">まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-156">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="de6a6-157">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-157">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="de6a6-159">[**サービス**] を選択し、[**マイドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-159">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="de6a6-161">編集するドメインの場合は、[ドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-161">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="de6a6-163">ドメインの名前機能を既定の Freenom ネームサーバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-163">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="de6a6-164">[**管理ツール**] を選択し、[**ネーム**サーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-164">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="de6a6-166">[既定のネームサーバーを**使用する**] が選択されていることを確認し、[ネームサーバーの**変更**] を選択します</span><span class="sxs-lookup"><span data-stu-id="de6a6-166">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="de6a6-168">[ **Manage Freenom DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-168">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Freenom DNS の管理](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="de6a6-170">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **MX** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-170">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="de6a6-172">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-172">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="de6a6-173">**名前**</span><span class="sxs-lookup"><span data-stu-id="de6a6-173">**Name**</span></span>|<span data-ttu-id="de6a6-174">**Type**</span><span class="sxs-lookup"><span data-stu-id="de6a6-174">**Type**</span></span>|<span data-ttu-id="de6a6-175">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de6a6-175">**TTL**</span></span>|<span data-ttu-id="de6a6-176">**Target**</span><span class="sxs-lookup"><span data-stu-id="de6a6-176">**Target**</span></span>|<span data-ttu-id="de6a6-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="de6a6-177">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de6a6-178">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="de6a6-178">(leave blank)</span></span>  <br/> |<span data-ttu-id="de6a6-179">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="de6a6-179">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="de6a6-180">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-180">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-181">\<ドメインキー\>. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de6a6-181">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="de6a6-182">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-182">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="de6a6-183">確認する方法</span><span class="sxs-lookup"><span data-stu-id="de6a6-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="de6a6-184">10 </span><span class="sxs-lookup"><span data-stu-id="de6a6-184">10</span></span>  <br/> <span data-ttu-id="de6a6-185">優先度の詳細については、「[What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6a6-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="de6a6-187">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-187">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="de6a6-189">その他の MX レコードがある場合は、すべてを削除します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-189">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="de6a6-190">レコードごとに [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-190">For each record, select **Delete**.</span></span> <span data-ttu-id="de6a6-191">メッセージを**本当に削除したい場合は**、[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-191">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="de6a6-192">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de6a6-192">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="de6a6-193"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="de6a6-193"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="de6a6-194">まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-194">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="de6a6-195">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-195">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="de6a6-197">[**サービス**] を選択し、[**マイドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-197">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="de6a6-199">編集するドメインの場合は、[ドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-199">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="de6a6-201">[ **Manage Freenom DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-201">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Freenom DNS の管理](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="de6a6-203">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **CNAME** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-203">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="de6a6-p113">最初の CNAME レコードを作成します。新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="de6a6-207">**Name**</span><span class="sxs-lookup"><span data-stu-id="de6a6-207">**Name**</span></span>|<span data-ttu-id="de6a6-208">**Record type**</span><span class="sxs-lookup"><span data-stu-id="de6a6-208">**Record type**</span></span>|<span data-ttu-id="de6a6-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de6a6-209">**TTL**</span></span>|<span data-ttu-id="de6a6-210">**Target**</span><span class="sxs-lookup"><span data-stu-id="de6a6-210">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de6a6-211">autodiscover</span><span class="sxs-lookup"><span data-stu-id="de6a6-211">autodiscover</span></span>  <br/> |<span data-ttu-id="de6a6-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="de6a6-212">CNAME</span></span>  <br/> |<span data-ttu-id="de6a6-213">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-214">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="de6a6-214">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="de6a6-215">sip</span><span class="sxs-lookup"><span data-stu-id="de6a6-215">sip</span></span>  <br/> |<span data-ttu-id="de6a6-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="de6a6-216">CNAME</span></span>  <br/> |<span data-ttu-id="de6a6-217">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de6a6-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de6a6-219">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="de6a6-219">lyncdiscover</span></span>  <br/> |<span data-ttu-id="de6a6-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="de6a6-220">CNAME</span></span>  <br/> |<span data-ttu-id="de6a6-221">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-221">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-222">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="de6a6-222">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="de6a6-223">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="de6a6-223">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="de6a6-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="de6a6-224">CNAME</span></span>  <br/> |<span data-ttu-id="de6a6-225">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-225">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-226">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="de6a6-226">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="de6a6-227">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="de6a6-227">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="de6a6-228">CNAME</span><span class="sxs-lookup"><span data-stu-id="de6a6-228">CNAME</span></span>  <br/> |<span data-ttu-id="de6a6-229">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-229">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-230">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="de6a6-230">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="de6a6-232">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-232">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="de6a6-234">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-234">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="de6a6-235">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-235">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="de6a6-236">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de6a6-236">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="de6a6-237"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="de6a6-237"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="de6a6-238">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="de6a6-238">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="de6a6-239">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="de6a6-239">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="de6a6-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="de6a6-240">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="de6a6-241">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-241">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="de6a6-242">まず、[このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-242">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="de6a6-243">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-243">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="de6a6-245">[**サービス**] を選択し、[**マイドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-245">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="de6a6-247">編集するドメインの場合は、[ドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-247">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="de6a6-249">[ **Manage Freenom DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de6a6-249">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Freenom DNS の管理](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="de6a6-251">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-251">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="de6a6-253">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-253">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="de6a6-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="de6a6-254">**Name**</span></span>|<span data-ttu-id="de6a6-255">**Record type**</span><span class="sxs-lookup"><span data-stu-id="de6a6-255">**Record type**</span></span>|<span data-ttu-id="de6a6-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de6a6-256">**TTL**</span></span>|<span data-ttu-id="de6a6-257">**Target**</span><span class="sxs-lookup"><span data-stu-id="de6a6-257">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="de6a6-258">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="de6a6-258">(leave blank)</span></span>  <br/> |<span data-ttu-id="de6a6-259">TXT</span><span class="sxs-lookup"><span data-stu-id="de6a6-259">TXT</span></span>  <br/> |<span data-ttu-id="de6a6-260">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="de6a6-260">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="de6a6-261">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="de6a6-261">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="de6a6-262">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de6a6-262">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="de6a6-264">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de6a6-264">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

