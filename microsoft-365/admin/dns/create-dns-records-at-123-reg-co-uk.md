---
title: Microsoft の123-reg.co.uk で DNS レコードを作成する
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: ドメインを確認し、電子メール、Skype for Business Online、および123-reg.co.uk のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 0c9a6a144a38398e7664f7f2bb317a96b627b640
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049133"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="0cda7-103">Microsoft の123-reg.co.uk で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="0cda7-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="0cda7-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0cda7-105">使用している DNS ホスティング プロバイダーが 123-reg.co.uk の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0cda7-106">これらのレコードを123-reg.co.uk で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="0cda7-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0cda7-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0cda7-110">Add a TXT record for verification</span></span>
<span data-ttu-id="0cda7-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0cda7-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0cda7-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cda7-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0cda7-116">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0cda7-116">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0cda7-117">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0cda7-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="0cda7-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0cda7-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="0cda7-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0cda7-120">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0cda7-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0cda7-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0cda7-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0cda7-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="0cda7-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0cda7-123">**Hostname**</span></span> <br/> |<span data-ttu-id="0cda7-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="0cda7-124">**Type**</span></span> <br/> |<span data-ttu-id="0cda7-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0cda7-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0cda7-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0cda7-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0cda7-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0cda7-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0cda7-128">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="0cda7-128">**Note:** This is an example.</span></span> <span data-ttu-id="0cda7-129">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="0cda7-130">確認する方法</span><span class="sxs-lookup"><span data-stu-id="0cda7-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="0cda7-131">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="0cda7-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0cda7-133">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="0cda7-134">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="0cda7-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0cda7-135">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0cda7-136">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0cda7-137">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0cda7-138">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0cda7-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0cda7-142">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="0cda7-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0cda7-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0cda7-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0cda7-p107">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0cda7-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="0cda7-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0cda7-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="0cda7-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0cda7-148">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0cda7-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0cda7-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0cda7-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0cda7-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0cda7-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0cda7-151">**Hostname**</span></span>|<span data-ttu-id="0cda7-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="0cda7-152">**Type**</span></span>|<span data-ttu-id="0cda7-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0cda7-153">**Priority**</span></span>|<span data-ttu-id="0cda7-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="0cda7-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0cda7-155">MX</span><span class="sxs-lookup"><span data-stu-id="0cda7-155">MX</span></span>  <br/> |<span data-ttu-id="0cda7-156">1-d</span><span class="sxs-lookup"><span data-stu-id="0cda7-156">1</span></span>  <br/> <span data-ttu-id="0cda7-157">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="0cda7-158">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0cda7-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="0cda7-159">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="0cda7-160">**注:** Microsoft アカウントから自分の\<ドメイン キー\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="0cda7-161">確認する方法</span><span class="sxs-lookup"><span data-stu-id="0cda7-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルの値をコピーして貼り付ける](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="0cda7-163">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-163">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="0cda7-165">その他の MX レコードがある場合は、そのレコードの **削除 (ごみ箱)** アイコンを選んでそれぞれ削除します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![[削除] (ごみ箱アイコン) を選択します。](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0cda7-167">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0cda7-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0cda7-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0cda7-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0cda7-p109">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0cda7-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="0cda7-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0cda7-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="0cda7-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0cda7-173">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0cda7-174">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="0cda7-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0cda7-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0cda7-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0cda7-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0cda7-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0cda7-177">**Hostname**</span></span>|<span data-ttu-id="0cda7-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="0cda7-178">**Type**</span></span>|<span data-ttu-id="0cda7-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="0cda7-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="0cda7-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0cda7-180">autodiscover</span></span>  <br/> |<span data-ttu-id="0cda7-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="0cda7-181">CNAME</span></span>  <br/> |<span data-ttu-id="0cda7-182">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="0cda7-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="0cda7-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cda7-184">sip</span><span class="sxs-lookup"><span data-stu-id="0cda7-184">sip</span></span>  <br/> |<span data-ttu-id="0cda7-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="0cda7-185">CNAME</span></span>  <br/> |<span data-ttu-id="0cda7-186">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0cda7-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cda7-187">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cda7-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0cda7-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0cda7-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="0cda7-189">CNAME</span></span>  <br/> |<span data-ttu-id="0cda7-190">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="0cda7-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="0cda7-191">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cda7-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0cda7-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0cda7-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="0cda7-193">CNAME</span></span>  <br/> |<span data-ttu-id="0cda7-194">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="0cda7-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="0cda7-195">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="0cda7-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="0cda7-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0cda7-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0cda7-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="0cda7-197">CNAME</span></span>  <br/> |<span data-ttu-id="0cda7-198">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="0cda7-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="0cda7-199">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="0cda7-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="0cda7-201">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-201">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="0cda7-203">他の 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="0cda7-204">[ **ADVANCED DNS** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="0cda7-205">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0cda7-206">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0cda7-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0cda7-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0cda7-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cda7-208">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0cda7-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0cda7-209">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0cda7-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0cda7-210">自分のドメインに対して既に SPF レコードがある場合は、Microsfot 用の新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="0cda7-211">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0cda7-212">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-212">Need examples?</span></span> <span data-ttu-id="0cda7-213">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="0cda7-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="0cda7-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="0cda7-215">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0cda7-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="0cda7-216">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0cda7-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="0cda7-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0cda7-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="0cda7-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0cda7-219">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0cda7-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0cda7-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0cda7-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0cda7-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0cda7-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="0cda7-222">**Hostname**</span></span>|<span data-ttu-id="0cda7-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="0cda7-223">**Type**</span></span>|<span data-ttu-id="0cda7-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="0cda7-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0cda7-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="0cda7-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="0cda7-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0cda7-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0cda7-227">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cda7-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="0cda7-229">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-229">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0cda7-231">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="0cda7-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0cda7-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0cda7-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0cda7-p112">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0cda7-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="0cda7-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="0cda7-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="0cda7-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="0cda7-237">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="0cda7-238">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="0cda7-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0cda7-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0cda7-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0cda7-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0cda7-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="0cda7-241">Hostname</span></span>|<span data-ttu-id="0cda7-242">Type</span><span class="sxs-lookup"><span data-stu-id="0cda7-242">Type</span></span>|<span data-ttu-id="0cda7-243">Priority</span><span class="sxs-lookup"><span data-stu-id="0cda7-243">Priority</span></span>|<span data-ttu-id="0cda7-244">TTL</span><span class="sxs-lookup"><span data-stu-id="0cda7-244">TTL</span></span>|<span data-ttu-id="0cda7-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="0cda7-245">Destination SRV</span></span>|
    |<span data-ttu-id="0cda7-246">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="0cda7-246">_sip._tls</span></span>|<span data-ttu-id="0cda7-247">SRV</span><span class="sxs-lookup"><span data-stu-id="0cda7-247">SRV</span></span>|<span data-ttu-id="0cda7-248">100</span><span class="sxs-lookup"><span data-stu-id="0cda7-248">100</span></span>|<span data-ttu-id="0cda7-249">3600</span><span class="sxs-lookup"><span data-stu-id="0cda7-249">3600</span></span>|<span data-ttu-id="0cda7-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cda7-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="0cda7-251">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="0cda7-252">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cda7-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="0cda7-253">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="0cda7-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0cda7-254">SRV</span><span class="sxs-lookup"><span data-stu-id="0cda7-254">SRV</span></span>|<span data-ttu-id="0cda7-255">100</span><span class="sxs-lookup"><span data-stu-id="0cda7-255">100</span></span>|<span data-ttu-id="0cda7-256">3600</span><span class="sxs-lookup"><span data-stu-id="0cda7-256">3600</span></span>|<span data-ttu-id="0cda7-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0cda7-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="0cda7-258">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="0cda7-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="0cda7-259">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cda7-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="0cda7-261">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-261">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="0cda7-263">他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cda7-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="0cda7-264">[ **ADVANCED DNS** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="0cda7-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0cda7-p115">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cda7-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
