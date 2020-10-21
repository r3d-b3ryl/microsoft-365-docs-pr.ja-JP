---
title: IONOS の 1&1 で DNS レコードを作成する
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを IONOS 用に 1&1 に設定する方法について説明します。
ms.openlocfilehash: b88fa4f14104f60f22857bb9cfdc9e6366d2c303
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646393"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="77c7d-103">IONOS の 1&1 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="77c7d-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="77c7d-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="77c7d-105">1&1 IONOS では、ドメインは MX レコードとトップレベル自動検出 CNAME レコードの両方を持つことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="77c7d-106">これにより、Microsoft の Exchange Online を構成する方法が制限されます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="77c7d-107">回避策がありますが、1&1 IONOS でサブドメインを作成した経験がある場合に **のみ** 、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="77c7d-108">> このサービスの [制限](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) にかかわらず、1&1 IONOS で独自の Microsoft DNS レコードを管理する場合は、この記事の手順に従って、ドメインを確認し、電子メール、Skype For business Online などの dns レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="77c7d-109">これらのレコードを 1&1 IONOS に追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="77c7d-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="77c7d-113">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="77c7d-113">Add a TXT record for verification</span></span>

<span data-ttu-id="77c7d-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77c7d-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="77c7d-118">次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="77c7d-119">まず、 [このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="77c7d-120">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="77c7d-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="77c7d-121">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="77c7d-122">[ **ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="77c7d-123">[ **ドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="77c7d-124">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="77c7d-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="77c7d-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="77c7d-126">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="77c7d-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="77c7d-127">**Type**</span></span> <br/> |<span data-ttu-id="77c7d-128">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="77c7d-128">**Prefix**</span></span> <br/> |<span data-ttu-id="77c7d-129">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="77c7d-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="77c7d-130">TXT</span><span class="sxs-lookup"><span data-stu-id="77c7d-130">TXT</span></span>  <br/> |<span data-ttu-id="77c7d-131">(このフィールドは空白のままにしておきます)</span><span class="sxs-lookup"><span data-stu-id="77c7d-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="77c7d-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="77c7d-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="77c7d-133">注: これは例です。</span><span class="sxs-lookup"><span data-stu-id="77c7d-133">NOTE: This is an example.</span></span> <span data-ttu-id="77c7d-134">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="77c7d-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="77c7d-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="77c7d-136">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="77c7d-137">[ **保存** ] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="77c7d-138">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="77c7d-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="77c7d-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="77c7d-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="77c7d-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="77c7d-142">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="77c7d-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="77c7d-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="77c7d-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="77c7d-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="77c7d-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="77c7d-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="77c7d-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="77c7d-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="77c7d-151">次の手順を実行するか、[ビデオ (3 分 22 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77c7d-152">1und1.de に登録した場合は、 [ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="77c7d-153">まず、 [このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="77c7d-154">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="77c7d-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="77c7d-155">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="77c7d-156">[ **ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="77c7d-157">[ **ドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="77c7d-158">[ **Mx Records** ] セクションの [ **MAIL エクスチェンジャー (MX Record)** ] 領域で、[ **その他のメールサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="77c7d-159">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="77c7d-160">![1 &amp; 1-BP-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="77c7d-161">既に他の MX レコードがある場合は、それぞれのレコードを選び、キーボードの **Delete** キーを押して、レコードを削除します</span><span class="sxs-lookup"><span data-stu-id="77c7d-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="77c7d-162">(登録されている MX レコードがない場合は、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="77c7d-163">![1 &amp; 1-BP-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="77c7d-164">[ **MX 1**] レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="77c7d-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="77c7d-165">**MX 1**</span></span>|<span data-ttu-id="77c7d-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="77c7d-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="77c7d-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="77c7d-168">注: \<domain-key\> Microsoft アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="77c7d-169">確認する方法</span><span class="sxs-lookup"><span data-stu-id="77c7d-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="77c7d-170">10  </span><span class="sxs-lookup"><span data-stu-id="77c7d-170">10</span></span>  <br/> <span data-ttu-id="77c7d-171">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1および 1-構成2および3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="77c7d-173">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-173">Select **Save**.</span></span><br/><span data-ttu-id="77c7d-174">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="77c7d-175">![1 &amp; 1-BP-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="77c7d-176">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="77c7d-177">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="77c7d-178">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="77c7d-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="77c7d-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="77c7d-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="77c7d-180">1&1 IONOS には、Microsoft メールサービスに必要な CNAME レコードと共に MX レコードを使用できるようにするための回避策が必要です。</span><span class="sxs-lookup"><span data-stu-id="77c7d-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="77c7d-181">この回避策では、1&1 IONOS にサブドメインのセットを作成し、それらを CNAME レコードに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c7d-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77c7d-182">この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="77c7d-183">この解決策は、サブドメインの作成に IONOS 1&1 で既に経験している場合にのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="77c7d-184">基本的な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="77c7d-184">Basic CNAME records</span></span>

<span data-ttu-id="77c7d-185">次の手順を実行するか、[ビデオ (3 分 57 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77c7d-186">1und1.de に登録した場合は、 [ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="77c7d-187">まず、 [このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="77c7d-188">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="77c7d-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="77c7d-189">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="77c7d-190">[ **ドメインセンター** ] ページで、更新するドメインを見つけ、[サブドメインの **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="77c7d-191">![1 &amp; 1-BP-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="77c7d-192">次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します</span><span class="sxs-lookup"><span data-stu-id="77c7d-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="77c7d-193">(1&1 IONOS でサポートされる最上位の CNAME レコードは1つだけなので、Microsoft はいくつかの CNAME レコードを必要とします)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="77c7d-194">最初に、Autodiscover サブドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="77c7d-195">[ **サブドメインの概要** ] セクションで、[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="77c7d-p113">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="77c7d-199">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-199">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="77c7d-201">autodiscover</span></span>  <br/> |<span data-ttu-id="77c7d-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-202">autodiscover.outlook.com</span></span>   | 

    ![1 &amp; 1-BP-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="77c7d-204">[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="77c7d-205">![1 &amp; 1-BP-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="77c7d-206">[ **サブドメインの概要** ] セクションで、作成したばかりの **自動検出** サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="77c7d-207">![1 &amp; 1-BP-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="77c7d-208">[ **サブドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="77c7d-209">![1 &amp; 1-BP-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="77c7d-210">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="77c7d-211">![1 &amp; 1-BP-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="77c7d-212">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="77c7d-213">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-213">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="77c7d-215">autodiscover</span></span>  <br/> |<span data-ttu-id="77c7d-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-216">autodiscover.outlook.com</span></span>   |

    ![1 &amp; 1-BP-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="77c7d-218">免責事項の [ **I am aware**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="77c7d-219">![1 &amp; 1-BP-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="77c7d-220">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-220">Select **Save**.</span></span><br/><span data-ttu-id="77c7d-221">![1 &amp; 1-BP-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="77c7d-222">追加の CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="77c7d-222">Additional CNAME records</span></span>

<span data-ttu-id="77c7d-p114">以降の手順に従って追加の CNAME レコードを作成すると、Skype for Business Online サービスが有効になります。 手順は、前に 2 つの CNAME レコードを作成したときの手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="77c7d-225">3 つ目のサブドメイン (Lyncdiscover) を作成します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="77c7d-226">[ **サブドメインの概要** ] セクションで、[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="77c7d-p115">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="77c7d-229">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-229">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="77c7d-231">lyncdiscover</span></span>   |<span data-ttu-id="77c7d-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="77c7d-233">[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="77c7d-234">[ **ドメインセンター** ] ページで、[サブドメインの **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="77c7d-235">[ **サブドメインの概要** ] セクションで、作成したばかりの **lyncdiscover** サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="77c7d-236">[ **サブドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="77c7d-237">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="77c7d-238">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="77c7d-239">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-239">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="77c7d-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="77c7d-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="77c7d-243">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="77c7d-244">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="77c7d-245">4 つ目のサブドメイン (SIP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="77c7d-246">[ **サブドメインの概要** ] セクションで、[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="77c7d-p116">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="77c7d-249">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-249">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-251">sip</span><span class="sxs-lookup"><span data-stu-id="77c7d-251">sip</span></span>  <br/> |<span data-ttu-id="77c7d-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="77c7d-253">[ **サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="77c7d-254">[ **ドメインセンター** ] ページで、[サブドメインの **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="77c7d-255">[ **サブドメインの概要** ] セクションで、作成したばかりの **sip** サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="77c7d-256">[ **サブドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="77c7d-257">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="77c7d-258">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="77c7d-259">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-259">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="77c7d-261">sip</span><span class="sxs-lookup"><span data-stu-id="77c7d-261">sip</span></span>  <br/> |<span data-ttu-id="77c7d-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="77c7d-263">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="77c7d-264">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="77c7d-265">MDM に必要な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="77c7d-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77c7d-266">手順は、他の 4 個の CNAME レコードの場合と同じですが、次の表の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="77c7d-267">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="77c7d-267">**Create Subdomain**</span></span>|<span data-ttu-id="77c7d-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="77c7d-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77c7d-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="77c7d-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="77c7d-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="77c7d-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="77c7d-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="77c7d-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="77c7d-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="77c7d-273">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="77c7d-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77c7d-274">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="77c7d-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="77c7d-275">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="77c7d-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="77c7d-276">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="77c7d-277">代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="77c7d-278">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-278">Need examples?</span></span> <span data-ttu-id="77c7d-279">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="77c7d-280">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="77c7d-281">次の手順を実行するか、[ビデオ (5 分 9 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77c7d-282">1und1.de に登録した場合は、 [ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="77c7d-283">まず、 [このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="77c7d-284">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="77c7d-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="77c7d-285">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="77c7d-286">[ **ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** (**v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="77c7d-287">[ **ドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="77c7d-288">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="77c7d-289">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="77c7d-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="77c7d-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="77c7d-291">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="77c7d-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="77c7d-292">**Type**</span></span>|<span data-ttu-id="77c7d-293">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="77c7d-293">**Prefix**</span></span>|<span data-ttu-id="77c7d-294">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="77c7d-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="77c7d-295">TXT</span><span class="sxs-lookup"><span data-stu-id="77c7d-295">TXT</span></span>  <br/> |<span data-ttu-id="77c7d-296">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="77c7d-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="77c7d-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="77c7d-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="77c7d-298">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT レコード](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="77c7d-300">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-300">Select **Save**.</span></span><br/><span data-ttu-id="77c7d-301">![レコードを追加する](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="77c7d-302">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-302">Select **Save**.</span></span><br/><span data-ttu-id="77c7d-303">![レコードを保存する](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="77c7d-304">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="77c7d-305">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="77c7d-306">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="77c7d-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="77c7d-307">次の手順を実行するか、[ビデオ (5 分 51 秒から開始) を参照](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="77c7d-308">1und1.de に登録した場合は、 [ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="77c7d-309">まず、 [このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="77c7d-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="77c7d-310">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="77c7d-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="77c7d-311">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="77c7d-312">[ **ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="77c7d-313">[ **ドメインの設定** ] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="77c7d-314">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="77c7d-315">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="77c7d-316">[ **Add Record**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="77c7d-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="77c7d-317">(ドロップダウンリストから [ **Type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="77c7d-318">**Type**</span><span class="sxs-lookup"><span data-stu-id="77c7d-318">**Type**</span></span>|<span data-ttu-id="77c7d-319">**Service**</span><span class="sxs-lookup"><span data-stu-id="77c7d-319">**Service**</span></span>|<span data-ttu-id="77c7d-320">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="77c7d-320">**Protocol**</span></span>|<span data-ttu-id="77c7d-321">**Name**</span><span class="sxs-lookup"><span data-stu-id="77c7d-321">**Name**</span></span>|<span data-ttu-id="77c7d-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="77c7d-322">**Host**</span></span>|<span data-ttu-id="77c7d-323">**Priority**</span><span class="sxs-lookup"><span data-stu-id="77c7d-323">**Priority**</span></span>|<span data-ttu-id="77c7d-324">**Weight**</span><span class="sxs-lookup"><span data-stu-id="77c7d-324">**Weight**</span></span>|<span data-ttu-id="77c7d-325">**Port**</span><span class="sxs-lookup"><span data-stu-id="77c7d-325">**Port**</span></span>|<span data-ttu-id="77c7d-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="77c7d-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="77c7d-327">SRV</span><span class="sxs-lookup"><span data-stu-id="77c7d-327">SRV</span></span>  <br/> |<span data-ttu-id="77c7d-328">sip</span><span class="sxs-lookup"><span data-stu-id="77c7d-328">sip</span></span>  <br/> |<span data-ttu-id="77c7d-329">tls</span><span class="sxs-lookup"><span data-stu-id="77c7d-329">tls</span></span>  <br/> |<span data-ttu-id="77c7d-330">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="77c7d-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="77c7d-332">100</span><span class="sxs-lookup"><span data-stu-id="77c7d-332">100</span></span>  <br/> |<span data-ttu-id="77c7d-333">1-d</span><span class="sxs-lookup"><span data-stu-id="77c7d-333">1</span></span>  <br/> |<span data-ttu-id="77c7d-334">443</span><span class="sxs-lookup"><span data-stu-id="77c7d-334">443</span></span>  <br/> |<span data-ttu-id="77c7d-335">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="77c7d-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="77c7d-336">SRV</span><span class="sxs-lookup"><span data-stu-id="77c7d-336">SRV</span></span>  <br/> |<span data-ttu-id="77c7d-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="77c7d-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="77c7d-338">tcp</span><span class="sxs-lookup"><span data-stu-id="77c7d-338">tcp</span></span>  <br/> |<span data-ttu-id="77c7d-339">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="77c7d-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="77c7d-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="77c7d-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="77c7d-341">100</span><span class="sxs-lookup"><span data-stu-id="77c7d-341">100</span></span>  <br/> |<span data-ttu-id="77c7d-342">1-d</span><span class="sxs-lookup"><span data-stu-id="77c7d-342">1</span></span>  <br/> |<span data-ttu-id="77c7d-343">5061</span><span class="sxs-lookup"><span data-stu-id="77c7d-343">5061</span></span>  <br/> |<span data-ttu-id="77c7d-344">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="77c7d-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1 &amp; 1-BP-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="77c7d-346">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-346">Select **Save**.</span></span> <br/><span data-ttu-id="77c7d-347">![1 &amp; 1-BP-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="77c7d-348">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-348">Select **Save**.</span></span> <br/><span data-ttu-id="77c7d-349">![1 &amp; 1-BP-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="77c7d-350">[ **EDIT DNS Settings** ] ダイアログボックスで、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="77c7d-351">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="77c7d-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="77c7d-352">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="77c7d-353">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="77c7d-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="77c7d-354">[ **Add Record** ] 領域で、表の他の行の値を使用してレコードを作成し、[ **追加**]、[ **保存**]、および **[はい]** を再度選択してレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="77c7d-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="77c7d-p120">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c7d-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
