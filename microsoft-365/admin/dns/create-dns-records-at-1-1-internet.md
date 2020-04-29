---
title: IONOS の 1&1 で DNS レコードを作成する
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを IONOS 用に 1&1 に設定する方法について説明します。
ms.openlocfilehash: a80f06287b7e4efe03804248d52b4ef43fc67b26
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919651"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="f11dc-103">IONOS の 1&1 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="f11dc-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="f11dc-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="f11dc-105">1&1 IONOS では、ドメインは MX レコードとトップレベル自動検出 CNAME レコードの両方を持つことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="f11dc-106">これにより、Microsoft の Exchange Online を構成する方法が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="f11dc-107">回避策がありますが、1&1 IONOS でサブドメインを作成した経験がある場合に**のみ**、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="f11dc-108">> このサービスの[制限](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)にかかわらず、1&1 IONOS で独自の Microsoft DNS レコードを管理する場合は、この記事の手順に従って、ドメインを確認し、電子メール、Skype For business Online などの dns レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="f11dc-109">これらのレコードを 1&1 IONOS に追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="f11dc-110">Microsoft での Web サイト向け Web ホスティングと DNS の詳細については、「[Microsoft での一般向け Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-110">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f11dc-114">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f11dc-114">Add a TXT record for verification</span></span>

<span data-ttu-id="f11dc-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="f11dc-119">次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f11dc-120">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="f11dc-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="f11dc-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="f11dc-122">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="f11dc-123">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="f11dc-124">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="f11dc-125">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="f11dc-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f11dc-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f11dc-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="f11dc-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="f11dc-128">**Type**</span></span> <br/> |<span data-ttu-id="f11dc-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="f11dc-129">**Prefix**</span></span> <br/> |<span data-ttu-id="f11dc-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="f11dc-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="f11dc-131">TXT</span><span class="sxs-lookup"><span data-stu-id="f11dc-131">TXT</span></span>  <br/> |<span data-ttu-id="f11dc-132">(このフィールドは空白のままにしておきます)</span><span class="sxs-lookup"><span data-stu-id="f11dc-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="f11dc-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f11dc-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f11dc-134">注: これは例です。</span><span class="sxs-lookup"><span data-stu-id="f11dc-134">NOTE: This is an example.</span></span> <span data-ttu-id="f11dc-135">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f11dc-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f11dc-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="f11dc-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="f11dc-138">[**保存**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="f11dc-139">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="f11dc-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f11dc-141">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="f11dc-142">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="f11dc-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f11dc-143">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f11dc-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f11dc-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f11dc-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f11dc-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f11dc-150">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="f11dc-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f11dc-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f11dc-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f11dc-152">次の手順を実行するか、[ビデオ (3 分 22 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-153">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="f11dc-154">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="f11dc-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="f11dc-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="f11dc-156">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="f11dc-157">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="f11dc-158">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="f11dc-159">[ **Mx Records** ] セクションの [ **MAIL エクスチェンジャー (MX Record)** ] 領域で、[**その他のメールサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-159">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="f11dc-160">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="f11dc-161">![1&amp;1-BP-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-161">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="f11dc-162">既に他の MX レコードがある場合は、それぞれのレコードを選び、キーボードの **Delete** キーを押して、レコードを削除します</span><span class="sxs-lookup"><span data-stu-id="f11dc-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="f11dc-163">(登録されている MX レコードがない場合は、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="f11dc-164">![1&amp;1-BP-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-164">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="f11dc-165">[ **MX 1**] レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="f11dc-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="f11dc-166">**MX 1**</span></span>|<span data-ttu-id="f11dc-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f11dc-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="f11dc-168">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="f11dc-169">注: Microsoft アカウント\<からドメインキー\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-169">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="f11dc-170">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f11dc-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f11dc-171">10  </span><span class="sxs-lookup"><span data-stu-id="f11dc-171">10</span></span>  <br/> <span data-ttu-id="f11dc-172">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1および 1-構成2および3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="f11dc-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-174">Select **Save**.</span></span><br/><span data-ttu-id="f11dc-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="f11dc-176">![1&amp;1-BP-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-176">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="f11dc-177">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="f11dc-178">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-178">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f11dc-179">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f11dc-179">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f11dc-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f11dc-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f11dc-181">1&1 IONOS には、Microsoft メールサービスに必要な CNAME レコードと共に MX レコードを使用できるようにするための回避策が必要です。</span><span class="sxs-lookup"><span data-stu-id="f11dc-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="f11dc-182">この回避策では、1&1 IONOS にサブドメインのセットを作成し、それらを CNAME レコードに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f11dc-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f11dc-183">この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="f11dc-184">この解決策は、サブドメインの作成に IONOS 1&1 で既に経験している場合にのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="f11dc-185">基本的な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="f11dc-185">Basic CNAME records</span></span>

<span data-ttu-id="f11dc-186">次の手順を実行するか、[ビデオ (3 分 57 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-187">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="f11dc-188">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="f11dc-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="f11dc-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="f11dc-190">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="f11dc-191">[**ドメインセンター** ] ページで、更新するドメインを見つけ、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="f11dc-192">![1&amp;1-BP-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-192">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="f11dc-193">次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します</span><span class="sxs-lookup"><span data-stu-id="f11dc-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="f11dc-194">(1&1 IONOS でサポートされる最上位の CNAME レコードは1つだけなので、Microsoft はいくつかの CNAME レコードを必要とします)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="f11dc-195">最初に、Autodiscover サブドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="f11dc-196">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="f11dc-p113">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="f11dc-200">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-200">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f11dc-202">autodiscover</span></span>  <br/> |<span data-ttu-id="f11dc-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="f11dc-205">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="f11dc-206">![1&amp;1-BP-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-206">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="f11dc-207">[**サブドメインの概要**] セクションで、作成したばかりの**自動検出**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="f11dc-208">![1&amp;1-BP-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-208">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="f11dc-209">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="f11dc-210">![1&amp;1-BP-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-210">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="f11dc-211">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="f11dc-212">![1&amp;1-BP-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-212">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="f11dc-213">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="f11dc-214">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-214">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f11dc-216">autodiscover</span></span>  <br/> |<span data-ttu-id="f11dc-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="f11dc-219">免責事項の [ **I am aware**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="f11dc-220">![1&amp;1-BP-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-220">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="f11dc-221">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-221">Select **Save**.</span></span><br/><span data-ttu-id="f11dc-222">![1&amp;1-BP-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-222">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="f11dc-223">追加の CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="f11dc-223">Additional CNAME records</span></span>

<span data-ttu-id="f11dc-p114">以降の手順に従って追加の CNAME レコードを作成すると、Skype for Business Online サービスが有効になります。 手順は、前に 2 つの CNAME レコードを作成したときの手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="f11dc-226">3 つ目のサブドメイン (Lyncdiscover) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="f11dc-227">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="f11dc-p115">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="f11dc-230">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-230">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f11dc-232">lyncdiscover</span></span>   |<span data-ttu-id="f11dc-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="f11dc-234">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="f11dc-235">[**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="f11dc-236">[**サブドメインの概要**] セクションで、作成したばかりの**lyncdiscover**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="f11dc-237">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="f11dc-238">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-238">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="f11dc-239">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="f11dc-240">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-240">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f11dc-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f11dc-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="f11dc-244">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="f11dc-245">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="f11dc-246">4 つ目のサブドメイン (SIP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="f11dc-247">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="f11dc-p116">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="f11dc-250">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-250">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-252">sip</span><span class="sxs-lookup"><span data-stu-id="f11dc-252">sip</span></span>  <br/> |<span data-ttu-id="f11dc-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="f11dc-254">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="f11dc-255">[**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="f11dc-256">[**サブドメインの概要**] セクションで、作成したばかりの**sip**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="f11dc-257">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="f11dc-258">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-258">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="f11dc-259">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="f11dc-260">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-260">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="f11dc-262">sip</span><span class="sxs-lookup"><span data-stu-id="f11dc-262">sip</span></span>  <br/> |<span data-ttu-id="f11dc-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="f11dc-264">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="f11dc-265">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="f11dc-266">MDM に必要な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="f11dc-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f11dc-267">手順は、他の 4 個の CNAME レコードの場合と同じですが、次の表の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="f11dc-268">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="f11dc-268">**Create Subdomain**</span></span>|<span data-ttu-id="f11dc-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f11dc-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f11dc-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f11dc-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f11dc-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f11dc-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="f11dc-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f11dc-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f11dc-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f11dc-274">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f11dc-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f11dc-275">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f11dc-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f11dc-276">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f11dc-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f11dc-277">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-277">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f11dc-278">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-278">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="f11dc-279">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-279">Need examples?</span></span> <span data-ttu-id="f11dc-280">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-280">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="f11dc-281">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="f11dc-282">次の手順を実行するか、[ビデオ (5 分 9 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-283">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="f11dc-284">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="f11dc-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="f11dc-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="f11dc-286">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="f11dc-287">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** (**v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="f11dc-288">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="f11dc-289">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="f11dc-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="f11dc-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f11dc-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="f11dc-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="f11dc-293">**型**</span><span class="sxs-lookup"><span data-stu-id="f11dc-293">**Type**</span></span>|<span data-ttu-id="f11dc-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="f11dc-294">**Prefix**</span></span>|<span data-ttu-id="f11dc-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="f11dc-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f11dc-296">TXT</span><span class="sxs-lookup"><span data-stu-id="f11dc-296">TXT</span></span>  <br/> |<span data-ttu-id="f11dc-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f11dc-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f11dc-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f11dc-299">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT レコード](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="f11dc-301">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-301">Select **Save**.</span></span><br/><span data-ttu-id="f11dc-302">![レコードを追加する](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-302">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="f11dc-303">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-303">Select **Save**.</span></span><br/><span data-ttu-id="f11dc-304">![レコードを保存する](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-304">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="f11dc-305">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="f11dc-306">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-306">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f11dc-307">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f11dc-307">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="f11dc-308">次の手順を実行するか、[ビデオ (5 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f11dc-309">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="f11dc-310">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f11dc-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="f11dc-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="f11dc-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="f11dc-312">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="f11dc-313">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="f11dc-314">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="f11dc-315">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="f11dc-316">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="f11dc-317">[ **Add Record**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="f11dc-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="f11dc-318">(ドロップダウンリストから [ **Type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="f11dc-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f11dc-319">**Type**</span><span class="sxs-lookup"><span data-stu-id="f11dc-319">**Type**</span></span>|<span data-ttu-id="f11dc-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="f11dc-320">**Service**</span></span>|<span data-ttu-id="f11dc-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f11dc-321">**Protocol**</span></span>|<span data-ttu-id="f11dc-322">**Name**</span><span class="sxs-lookup"><span data-stu-id="f11dc-322">**Name**</span></span>|<span data-ttu-id="f11dc-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="f11dc-323">**Host**</span></span>|<span data-ttu-id="f11dc-324">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f11dc-324">**Priority**</span></span>|<span data-ttu-id="f11dc-325">**Weight**</span><span class="sxs-lookup"><span data-stu-id="f11dc-325">**Weight**</span></span>|<span data-ttu-id="f11dc-326">**Port**</span><span class="sxs-lookup"><span data-stu-id="f11dc-326">**Port**</span></span>|<span data-ttu-id="f11dc-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f11dc-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f11dc-328">SRV</span><span class="sxs-lookup"><span data-stu-id="f11dc-328">SRV</span></span>  <br/> |<span data-ttu-id="f11dc-329">sip</span><span class="sxs-lookup"><span data-stu-id="f11dc-329">sip</span></span>  <br/> |<span data-ttu-id="f11dc-330">tls</span><span class="sxs-lookup"><span data-stu-id="f11dc-330">tls</span></span>  <br/> |<span data-ttu-id="f11dc-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="f11dc-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f11dc-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f11dc-333">100</span><span class="sxs-lookup"><span data-stu-id="f11dc-333">100</span></span>  <br/> |<span data-ttu-id="f11dc-334">1-d</span><span class="sxs-lookup"><span data-stu-id="f11dc-334">1</span></span>  <br/> |<span data-ttu-id="f11dc-335">443</span><span class="sxs-lookup"><span data-stu-id="f11dc-335">443</span></span>  <br/> |<span data-ttu-id="f11dc-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="f11dc-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="f11dc-337">SRV</span><span class="sxs-lookup"><span data-stu-id="f11dc-337">SRV</span></span>  <br/> |<span data-ttu-id="f11dc-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f11dc-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="f11dc-339">tcp</span><span class="sxs-lookup"><span data-stu-id="f11dc-339">tcp</span></span>  <br/> |<span data-ttu-id="f11dc-340">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="f11dc-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="f11dc-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f11dc-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="f11dc-342">100</span><span class="sxs-lookup"><span data-stu-id="f11dc-342">100</span></span>  <br/> |<span data-ttu-id="f11dc-343">1-d</span><span class="sxs-lookup"><span data-stu-id="f11dc-343">1</span></span>  <br/> |<span data-ttu-id="f11dc-344">5061</span><span class="sxs-lookup"><span data-stu-id="f11dc-344">5061</span></span>  <br/> |<span data-ttu-id="f11dc-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="f11dc-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="f11dc-347">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-347">Select **Save**.</span></span> <br/><span data-ttu-id="f11dc-348">![1&amp;1-BP-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-348">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="f11dc-349">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-349">Select **Save**.</span></span> <br/><span data-ttu-id="f11dc-350">![1&amp;1-BP-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-350">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="f11dc-351">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="f11dc-352">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="f11dc-352">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="f11dc-353">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="f11dc-354">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f11dc-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="f11dc-355">[ **Add Record** ] 領域で、表の他の行の値を使用してレコードを作成し、[**追加**]、[**保存**]、および **[はい]** を再度選択してレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="f11dc-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="f11dc-p120">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f11dc-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
