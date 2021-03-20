---
title: Microsoft の Freenom で DNS レコードを作成する
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: ドメインを確認し、メール、Skype for Business Online、および Freenom for Microsoft の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910356"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a><span data-ttu-id="1de73-103">Microsoft の Freenom で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="1de73-103">Create DNS records at Freenom for Microsoft</span></span>

<span data-ttu-id="1de73-104">探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.yml) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1de73-104">[Check the Domains FAQ ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1de73-105">Freenom Web サイトは SRV レコードをサポートしません。つまり、Skype for Business Online と一部Outlook Web App機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="1de73-105">The Freenom website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="1de73-106">使用する Microsoft の計画に関係なく、サービスに重大な制限があり、別の DNS ホスティング プロバイダーに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="1de73-106">No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="1de73-107">サービスの制限にもかかわらず、Freenom で独自の Microsoft DNS レコードを管理する場合は、この記事の手順に従ってドメインを確認し、電子メールや他のサービスの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="1de73-107">If despite the service limitations, you choose to manage your own Microsoft DNS records at Freenom, follow the steps in this article to verify your domain and set up DNS records for email and other services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="1de73-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de73-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1de73-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="1de73-111">Add a TXT record for verification</span></span>
<span data-ttu-id="1de73-112"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="1de73-112"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="1de73-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="1de73-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1de73-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1de73-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1de73-117">開始するには、このリンクを使用して Freenom の [ドメイン] ページ [に移動します](https://my.freenom.com/)。</span><span class="sxs-lookup"><span data-stu-id="1de73-117">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1de73-118">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="1de73-118">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1de73-120">[サービス **] を** 選択し、[自分の **ドメイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-120">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1de73-122">編集するドメインの場合は、[ドメインの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-122">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1de73-124">**[Freenom DNS の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-124">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. <span data-ttu-id="1de73-126">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1de73-126">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. <span data-ttu-id="1de73-128">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1de73-128">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="1de73-129">**名前**</span><span class="sxs-lookup"><span data-stu-id="1de73-129">**Name**</span></span>|<span data-ttu-id="1de73-130">**Type**</span><span class="sxs-lookup"><span data-stu-id="1de73-130">**Type**</span></span>|<span data-ttu-id="1de73-131">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1de73-131">**TTL**</span></span>|<span data-ttu-id="1de73-132">**Target**</span><span class="sxs-lookup"><span data-stu-id="1de73-132">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de73-133">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="1de73-133">(leave blank)</span></span>  <br/> |<span data-ttu-id="1de73-134">TXT</span><span class="sxs-lookup"><span data-stu-id="1de73-134">TXT</span></span>  <br/> |<span data-ttu-id="1de73-135">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-135">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-136">MS=msXXXXXXXX</span><span class="sxs-lookup"><span data-stu-id="1de73-136">MS=msXXXXXXXX</span></span>  <br/> <span data-ttu-id="1de73-137">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="1de73-137">**Note:** This is an example.</span></span> <span data-ttu-id="1de73-138">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="1de73-138">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1de73-139">確認する方法</span><span class="sxs-lookup"><span data-stu-id="1de73-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. <span data-ttu-id="1de73-141">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-141">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. <span data-ttu-id="1de73-143">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="1de73-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1de73-144">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="1de73-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1de73-145">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="1de73-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1de73-146">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="1de73-146">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1de73-147">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="1de73-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1de73-148">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1de73-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1de73-149">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1de73-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1de73-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de73-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1de73-153">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="1de73-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1de73-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="1de73-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="1de73-155">開始するには、このリンクを使用して Freenom の [ドメイン] ページ [に移動します](https://my.freenom.com/)。</span><span class="sxs-lookup"><span data-stu-id="1de73-155">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1de73-156">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="1de73-156">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1de73-158">[サービス **] を** 選択し、[自分の **ドメイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-158">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1de73-160">編集するドメインの場合は、[ドメインの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-160">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1de73-162">ドメインの名前を既定の Freenom ネーム サーバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="1de73-162">Set the name serves for your domain to the default Freenom name servers.</span></span> <span data-ttu-id="1de73-163">[ **管理ツール] を** 選択し、[ネームサーバー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-163">Select **Management Tools**, and then select **Nameservers**.</span></span>
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. <span data-ttu-id="1de73-165">[既定の **ネーム サーバーを使用する] が** 選択されている場合は、[ネーム サーバーの変更] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-165">Make sure **Use default nameservers** is selected, and then select **Change Nameservers**.</span></span>
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. <span data-ttu-id="1de73-167">**[Freenom DNS の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-167">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. <span data-ttu-id="1de73-169">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **MX** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1de73-169">Under **Add Record**, in the **Type** column, choose **MX** from the menu.</span></span> 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. <span data-ttu-id="1de73-171">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1de73-171">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="1de73-172">**名前**</span><span class="sxs-lookup"><span data-stu-id="1de73-172">**Name**</span></span>|<span data-ttu-id="1de73-173">**Type**</span><span class="sxs-lookup"><span data-stu-id="1de73-173">**Type**</span></span>|<span data-ttu-id="1de73-174">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1de73-174">**TTL**</span></span>|<span data-ttu-id="1de73-175">**Target**</span><span class="sxs-lookup"><span data-stu-id="1de73-175">**Target**</span></span>|<span data-ttu-id="1de73-176">**Priority**</span><span class="sxs-lookup"><span data-stu-id="1de73-176">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de73-177">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="1de73-177">(leave blank)</span></span>  <br/> |<span data-ttu-id="1de73-178">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="1de73-178">MX (Mail Exchanger)</span></span>  <br/> |<span data-ttu-id="1de73-179">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-179">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-180">\<domain-key\>.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1de73-180">\<domain-key\>.mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1de73-181">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1de73-181">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="1de73-182">確認する方法</span><span class="sxs-lookup"><span data-stu-id="1de73-182">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="1de73-183">10  </span><span class="sxs-lookup"><span data-stu-id="1de73-183">10</span></span>  <br/> <span data-ttu-id="1de73-184">優先度の詳細については、「[What is MX priority?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de73-184">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. <span data-ttu-id="1de73-186">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-186">Select **Save Changes**.</span></span>
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. <span data-ttu-id="1de73-188">その他の MX レコードがある場合は、すべて削除します。</span><span class="sxs-lookup"><span data-stu-id="1de73-188">If there are any other MX records, delete them all.</span></span> <span data-ttu-id="1de73-189">各レコードについて、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-189">For each record, select **Delete**.</span></span> <span data-ttu-id="1de73-190">メッセージ 「本当 **にこのエントリを削除しますか」** というメッセージが表示されたら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-190">When the message **Do you really want to remove this entry?** appears, select **OK**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1de73-191">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="1de73-191">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1de73-192"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="1de73-192"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="1de73-193">開始するには、このリンクを使用して Freenom の [ドメイン] ページ [に移動します](https://my.freenom.com/)。</span><span class="sxs-lookup"><span data-stu-id="1de73-193">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1de73-194">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="1de73-194">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1de73-196">[サービス **] を** 選択し、[自分の **ドメイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-196">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1de73-198">編集するドメインの場合は、[ドメインの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-198">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1de73-200">**[Freenom DNS の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-200">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. <span data-ttu-id="1de73-202">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **CNAME** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1de73-202">Under **Add Record**, in the **Type** column, choose **CNAME** from the menu.</span></span> 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. <span data-ttu-id="1de73-p113">最初の CNAME レコードを作成します。新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1de73-p113">Create the first CNAME record. In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    |<span data-ttu-id="1de73-206">**Name**</span><span class="sxs-lookup"><span data-stu-id="1de73-206">**Name**</span></span>|<span data-ttu-id="1de73-207">**Record type**</span><span class="sxs-lookup"><span data-stu-id="1de73-207">**Record type**</span></span>|<span data-ttu-id="1de73-208">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1de73-208">**TTL**</span></span>|<span data-ttu-id="1de73-209">**Target**</span><span class="sxs-lookup"><span data-stu-id="1de73-209">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de73-210">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1de73-210">autodiscover</span></span>  <br/> |<span data-ttu-id="1de73-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="1de73-211">CNAME</span></span>  <br/> |<span data-ttu-id="1de73-212">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-212">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1de73-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="1de73-214">sip</span><span class="sxs-lookup"><span data-stu-id="1de73-214">sip</span></span>  <br/> |<span data-ttu-id="1de73-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="1de73-215">CNAME</span></span>  <br/> |<span data-ttu-id="1de73-216">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-216">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1de73-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1de73-218">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1de73-218">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1de73-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="1de73-219">CNAME</span></span>  <br/> |<span data-ttu-id="1de73-220">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-220">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-221">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1de73-221">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="1de73-222">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1de73-222">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1de73-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="1de73-223">CNAME</span></span>  <br/> |<span data-ttu-id="1de73-224">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-224">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-225">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1de73-225">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="1de73-226">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1de73-226">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1de73-227">CNAME</span><span class="sxs-lookup"><span data-stu-id="1de73-227">CNAME</span></span>  <br/> |<span data-ttu-id="1de73-228">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-228">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-229">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1de73-229">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. <span data-ttu-id="1de73-231">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-231">Select **Save Changes**.</span></span>
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. <span data-ttu-id="1de73-233">前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1de73-233">Repeat the previous steps to create the other five CNAME records.</span></span> 
    
    <span data-ttu-id="1de73-234">レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1de73-234">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1de73-235">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="1de73-235">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1de73-236"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="1de73-236"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1de73-237">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1de73-237">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1de73-238">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1de73-238">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1de73-239">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="1de73-239">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1de73-240">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1de73-240">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

1. <span data-ttu-id="1de73-241">開始するには、このリンクを使用して Freenom の [ドメイン] ページ [に移動します](https://my.freenom.com/)。</span><span class="sxs-lookup"><span data-stu-id="1de73-241">To get started, go to your domains page in Freenom by using [this link](https://my.freenom.com/).</span></span> <span data-ttu-id="1de73-242">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="1de73-242">You'll be prompted to log in.</span></span>
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. <span data-ttu-id="1de73-244">[サービス **] を** 選択し、[自分の **ドメイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-244">Select **Services**, and then select **My Domains**.</span></span>
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. <span data-ttu-id="1de73-246">編集するドメインの場合は、[ドメインの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-246">For the domain that you want to edit, select **Manage Domain**.</span></span>
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. <span data-ttu-id="1de73-248">**[Freenom DNS の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-248">Select **Manage Freenom DNS**.</span></span>
    
    ![Freenom select Manage Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. <span data-ttu-id="1de73-250">[ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1de73-250">Under **Add Record**, in the **Type** column, choose **TXT** from the menu.</span></span> 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. <span data-ttu-id="1de73-252">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1de73-252">In the boxes for the new record, type or copy and paste the following values.</span></span> 
    
    |<span data-ttu-id="1de73-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="1de73-253">**Name**</span></span>|<span data-ttu-id="1de73-254">**Record type**</span><span class="sxs-lookup"><span data-stu-id="1de73-254">**Record type**</span></span>|<span data-ttu-id="1de73-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1de73-255">**TTL**</span></span>|<span data-ttu-id="1de73-256">**Target**</span><span class="sxs-lookup"><span data-stu-id="1de73-256">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1de73-257">(空白のまま)</span><span class="sxs-lookup"><span data-stu-id="1de73-257">(leave blank)</span></span>  <br/> |<span data-ttu-id="1de73-258">TXT</span><span class="sxs-lookup"><span data-stu-id="1de73-258">TXT</span></span>  <br/> |<span data-ttu-id="1de73-259">3600 (秒)</span><span class="sxs-lookup"><span data-stu-id="1de73-259">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="1de73-260">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1de73-260">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="1de73-261">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1de73-261">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. <span data-ttu-id="1de73-263">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1de73-263">Select **Save Changes**.</span></span>
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
