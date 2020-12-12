---
title: Bluehost で Microsoft 用の DNS レコードを作成する
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Bluehost for Microsoft でドメインを確認し、メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: a9de709b0981c3e74eec1a3ea0e0452d068c5ad4
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658149"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="acc59-103">Bluehost で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="acc59-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="acc59-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="acc59-105">使用している DNS ホスティング プロバイダーが Bluehost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="acc59-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="acc59-106">これらのレコードを Bluehost で追加すると、ドメインは Microsoft サービスで動作する設定になります。</span><span class="sxs-lookup"><span data-stu-id="acc59-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="acc59-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="acc59-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="acc59-110">Add a TXT record for verification</span></span>
<span data-ttu-id="acc59-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="acc59-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="acc59-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="acc59-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="acc59-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="acc59-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="acc59-116">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="acc59-116">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="acc59-117">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="acc59-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="acc59-118">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="acc59-118">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="acc59-119">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="acc59-119">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="acc59-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor row,*\* select Manage DNS **records**.</span><span class="sxs-lookup"><span data-stu-id="acc59-120">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="acc59-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="acc59-121">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="acc59-122">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="acc59-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="acc59-123">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="acc59-123">**Host Record**</span></span> <br/> |<span data-ttu-id="acc59-124">**TTL**</span><span class="sxs-lookup"><span data-stu-id="acc59-124">**TTL**</span></span> <br/> |<span data-ttu-id="acc59-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="acc59-125">**Type**</span></span> <br/> |<span data-ttu-id="acc59-126">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="acc59-126">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="acc59-127">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-127">14400</span></span>  <br/> |<span data-ttu-id="acc59-128">TXT</span><span class="sxs-lookup"><span data-stu-id="acc59-128">TXT</span></span>  <br/> |<span data-ttu-id="acc59-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="acc59-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="acc59-130">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="acc59-130">**Note:** This is an example.</span></span> <span data-ttu-id="acc59-131">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="acc59-132">確認する方法</span><span class="sxs-lookup"><span data-stu-id="acc59-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="acc59-133">レコードの **追加を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-133">Select **add record**.</span></span>
    
6. <span data-ttu-id="acc59-134">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="acc59-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="acc59-135">ドメイン レジストラーのサイトでレコードを追加した後、Microsoft に戻り、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="acc59-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="acc59-136">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="acc59-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="acc59-137">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="acc59-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="acc59-138">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="acc59-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="acc59-139">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc59-139">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="acc59-140">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc59-140">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="acc59-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="acc59-144">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="acc59-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="acc59-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="acc59-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="acc59-146">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="acc59-146">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="acc59-147">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="acc59-147">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="acc59-148">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="acc59-148">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="acc59-149">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="acc59-149">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="acc59-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor row,*\* select Manage DNS **records**.</span><span class="sxs-lookup"><span data-stu-id="acc59-150">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="acc59-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="acc59-151">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="acc59-152">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="acc59-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="acc59-153">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="acc59-153">**Host Record**</span></span>|<span data-ttu-id="acc59-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="acc59-154">**TTL**</span></span>|<span data-ttu-id="acc59-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="acc59-155">**Type**</span></span>|<span data-ttu-id="acc59-156">**Points To**</span><span class="sxs-lookup"><span data-stu-id="acc59-156">**Points To**</span></span>|<span data-ttu-id="acc59-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="acc59-157">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="acc59-158">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-158">14400</span></span>  <br/> |<span data-ttu-id="acc59-159">MX</span><span class="sxs-lookup"><span data-stu-id="acc59-159">MX</span></span>  <br/> | <span data-ttu-id="acc59-160">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="acc59-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="acc59-161">**注: Microsoft アカウントから** 取得\<*domain-key*\> します。</span><span class="sxs-lookup"><span data-stu-id="acc59-161">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="acc59-162">確認する方法</span><span class="sxs-lookup"><span data-stu-id="acc59-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="acc59-163">0</span><span class="sxs-lookup"><span data-stu-id="acc59-163">0</span></span>  <br/> <span data-ttu-id="acc59-164">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![ドロップダウン リストから [種類] を選択する](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="acc59-166">レコードの **追加を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-166">Select **add record**.</span></span>
    
    ![[Add Record] (レコードの追加) を選択](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="acc59-168">その他の MX レコードが [ **MX (Mail Exchanger)** ] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="acc59-168">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="acc59-169">その他の MX レコードの 1 つで、[削除] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="acc59-169">For one of the other MX records, select **Delete.**</span></span>
    
    ![追加の MX レコードごとに [削除] を選択する](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="acc59-171">確認ダイアログ ボックスで **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-171">In the confirmation dialog box, select **OK**.</span></span>
    
    ![[OK] を選択します。](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="acc59-173">同じ手順に従って、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="acc59-173">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="acc59-174">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="acc59-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="acc59-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="acc59-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="acc59-176">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="acc59-176">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="acc59-177">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="acc59-177">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="acc59-178">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="acc59-178">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="acc59-179">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="acc59-179">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="acc59-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor row,*\* select Manage DNS **records**.</span><span class="sxs-lookup"><span data-stu-id="acc59-180">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="acc59-181">**[A (ホスト)** レコード] セクションで、自動検出レコードの行を検索し、その行の **[** 削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="acc59-181">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="acc59-182">Microsoft で必要な **自動検出レコード** を追加する前に、既存の **自動** 検出レコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc59-182">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="acc59-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="acc59-183">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![[削除] を選択する](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="acc59-185">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acc59-185">Select **OK**.</span></span>
    
    ![[OK] を選択します。](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="acc59-187">6 つの CNAME レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="acc59-187">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="acc59-188">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="acc59-188">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="acc59-189">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="acc59-189">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="acc59-190">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="acc59-190">**Host Record**</span></span>|<span data-ttu-id="acc59-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="acc59-191">**TTL**</span></span>|<span data-ttu-id="acc59-192">**Type**</span><span class="sxs-lookup"><span data-stu-id="acc59-192">**Type**</span></span>|<span data-ttu-id="acc59-193">**Points To**</span><span class="sxs-lookup"><span data-stu-id="acc59-193">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="acc59-194">autodiscover</span><span class="sxs-lookup"><span data-stu-id="acc59-194">autodiscover</span></span>  <br/> |<span data-ttu-id="acc59-195">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-195">14400</span></span>  <br/> |<span data-ttu-id="acc59-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="acc59-196">CNAME</span></span>  <br/> |<span data-ttu-id="acc59-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="acc59-197">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="acc59-198">sip</span><span class="sxs-lookup"><span data-stu-id="acc59-198">sip</span></span>  <br/> |<span data-ttu-id="acc59-199">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-199">14400</span></span>  <br/> |<span data-ttu-id="acc59-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="acc59-200">CNAME</span></span>  <br/> |<span data-ttu-id="acc59-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="acc59-201">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="acc59-202">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="acc59-202">lyncdiscover</span></span>  <br/> |<span data-ttu-id="acc59-203">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-203">14400</span></span>  <br/> |<span data-ttu-id="acc59-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="acc59-204">CNAME</span></span>  <br/> |<span data-ttu-id="acc59-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="acc59-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="acc59-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="acc59-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="acc59-207">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-207">14400</span></span>  <br/> |<span data-ttu-id="acc59-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="acc59-208">CNAME</span></span>  <br/> |<span data-ttu-id="acc59-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="acc59-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="acc59-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="acc59-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="acc59-211">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-211">14400</span></span>  <br/> |<span data-ttu-id="acc59-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="acc59-212">CNAME</span></span>  <br/> |<span data-ttu-id="acc59-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="acc59-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![最初の CNAME レコードを作成する](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="acc59-215">レコードの **追加を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-215">Select **add record**.</span></span>
    
    ![[Add Record] (レコードの追加) を選択](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="acc59-217">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="acc59-217">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="acc59-218">引き続き **[DNS** レコードの追加] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [レコードの追加] を選択してそのレコードを完成します。</span><span class="sxs-lookup"><span data-stu-id="acc59-218">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="acc59-219">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="acc59-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="acc59-220">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="acc59-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="acc59-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="acc59-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="acc59-222">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="acc59-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="acc59-223">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="acc59-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="acc59-224">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="acc59-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="acc59-225">代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="acc59-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="acc59-226">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="acc59-226">Need examples?</span></span> <span data-ttu-id="acc59-227">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-227">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="acc59-228">SPF レコードを検証するには、次の[SPF 検証ツールのいずれかを使用できます](../setup/domains-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="acc59-228">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="acc59-229">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="acc59-229">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="acc59-230">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="acc59-230">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="acc59-231">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="acc59-231">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="acc59-232">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="acc59-232">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="acc59-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor row,*\* select Manage DNS **records**.</span><span class="sxs-lookup"><span data-stu-id="acc59-233">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="acc59-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="acc59-234">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="acc59-235">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="acc59-235">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="acc59-236">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="acc59-236">**Host Record**</span></span>|<span data-ttu-id="acc59-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="acc59-237">**TTL**</span></span>|<span data-ttu-id="acc59-238">**Type**</span><span class="sxs-lookup"><span data-stu-id="acc59-238">**Type**</span></span>|<span data-ttu-id="acc59-239">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="acc59-239">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="acc59-240">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-240">14400</span></span>  <br/> |<span data-ttu-id="acc59-241">TXT</span><span class="sxs-lookup"><span data-stu-id="acc59-241">TXT</span></span>  <br/> |<span data-ttu-id="acc59-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="acc59-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="acc59-243">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="acc59-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![TXT 値をコピーする](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="acc59-245">レコードの **追加を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-245">Select **add record**.</span></span>
    
    ![[Add Record] (レコードの追加) を選択](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="acc59-247">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="acc59-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="acc59-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="acc59-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="acc59-249">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="acc59-249">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="acc59-250">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="acc59-250">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="acc59-251">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="acc59-251">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="acc59-252">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="acc59-252">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="acc59-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor row,*\* select Manage DNS **records**.</span><span class="sxs-lookup"><span data-stu-id="acc59-253">In the **_domain_name_*_ area, on the _\* DNS Zone Editor*\* row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="acc59-254">2 つの SRV レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="acc59-254">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="acc59-255">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="acc59-255">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="acc59-256">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="acc59-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="acc59-257">**Service**</span><span class="sxs-lookup"><span data-stu-id="acc59-257">**Service**</span></span>|<span data-ttu-id="acc59-258">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="acc59-258">**Protocol**</span></span>|<span data-ttu-id="acc59-259">**Host**</span><span class="sxs-lookup"><span data-stu-id="acc59-259">**Host**</span></span>|<span data-ttu-id="acc59-260">**TTL**</span><span class="sxs-lookup"><span data-stu-id="acc59-260">**TTL**</span></span>|<span data-ttu-id="acc59-261">**Type**</span><span class="sxs-lookup"><span data-stu-id="acc59-261">**Type**</span></span>|<span data-ttu-id="acc59-262">**Priority**</span><span class="sxs-lookup"><span data-stu-id="acc59-262">**Priority**</span></span>|<span data-ttu-id="acc59-263">**Weight**</span><span class="sxs-lookup"><span data-stu-id="acc59-263">**Weight**</span></span>|<span data-ttu-id="acc59-264">**Port**</span><span class="sxs-lookup"><span data-stu-id="acc59-264">**Port**</span></span>|<span data-ttu-id="acc59-265">**Points To**</span><span class="sxs-lookup"><span data-stu-id="acc59-265">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="acc59-266">_sip</span><span class="sxs-lookup"><span data-stu-id="acc59-266">_sip</span></span>  <br/> |<span data-ttu-id="acc59-267">_tls</span><span class="sxs-lookup"><span data-stu-id="acc59-267">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="acc59-268">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-268">14400</span></span>  <br/> |<span data-ttu-id="acc59-269">SRV</span><span class="sxs-lookup"><span data-stu-id="acc59-269">SRV</span></span>  <br/> |<span data-ttu-id="acc59-270">100</span><span class="sxs-lookup"><span data-stu-id="acc59-270">100</span></span>  <br/> |<span data-ttu-id="acc59-271">1 </span><span class="sxs-lookup"><span data-stu-id="acc59-271">1</span></span>  <br/> |<span data-ttu-id="acc59-272">443</span><span class="sxs-lookup"><span data-stu-id="acc59-272">443</span></span>  <br/> |<span data-ttu-id="acc59-273">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="acc59-273">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="acc59-274">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="acc59-274">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="acc59-275">_tcp</span><span class="sxs-lookup"><span data-stu-id="acc59-275">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="acc59-276">14400</span><span class="sxs-lookup"><span data-stu-id="acc59-276">14400</span></span>  <br/> |<span data-ttu-id="acc59-277">SRV</span><span class="sxs-lookup"><span data-stu-id="acc59-277">SRV</span></span>  <br/> |<span data-ttu-id="acc59-278">100</span><span class="sxs-lookup"><span data-stu-id="acc59-278">100</span></span>  <br/> |<span data-ttu-id="acc59-279">1 </span><span class="sxs-lookup"><span data-stu-id="acc59-279">1</span></span>  <br/> |<span data-ttu-id="acc59-280">5061</span><span class="sxs-lookup"><span data-stu-id="acc59-280">5061</span></span>  <br/> |<span data-ttu-id="acc59-281">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="acc59-281">sipfed.online.lync.com</span></span>  <br/> |
   
    ![新しいレコードの値をコピーする](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="acc59-283">レコードの **追加を選択します**。</span><span class="sxs-lookup"><span data-stu-id="acc59-283">Select **add record**.</span></span>
    
    ![[Add Record] (レコードの追加) を選択](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="acc59-285">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="acc59-285">Add the other SRV record.</span></span>
    
    <span data-ttu-id="acc59-286">引き続き **[DNS** レコードの追加] セクションで、表の他の行の値を使用してレコードを作成し、もう一度 [レコードの追加] を選択してそのレコードを完成します。</span><span class="sxs-lookup"><span data-stu-id="acc59-286">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="acc59-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc59-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

