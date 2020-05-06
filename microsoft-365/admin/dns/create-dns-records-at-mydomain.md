---
title: Microsoft 用の MyDomain で DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: ドメインを確認し、メール、Skype for Business Online、その他のサービスに対する DNS レコードを Microsoft 用の My Domain でセットアップする方法について説明します。
ms.openlocfilehash: cc12729e10e651abc2eaa109c47c2a5fbfe5ea1e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048977"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="9e507-103">Microsoft 用の MyDomain で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9e507-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="9e507-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="9e507-p101">MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Microsoft プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。</span><span class="sxs-lookup"><span data-stu-id="9e507-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="9e507-107">サービスの制限事項があっても MyDomain で自分の Microsoft DNS レコードを管理する場合は、この記事に示す手順に従って、メールや Skype for Business Online などの DNS レコードを設定してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="9e507-108">これらのレコードを MyDomain で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e507-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="9e507-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e507-112">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e507-112">Add a TXT record for verification</span></span>
<span data-ttu-id="9e507-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9e507-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9e507-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e507-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9e507-p105">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9e507-120">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9e507-121">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9e507-122">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9e507-123">[**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="9e507-124">[**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e507-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="9e507-125">**Content**</span><span class="sxs-lookup"><span data-stu-id="9e507-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="9e507-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e507-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e507-127">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9e507-127">**Note:** This is an example.</span></span> <span data-ttu-id="9e507-128">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9e507-129">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9e507-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="9e507-130">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="9e507-131">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9e507-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e507-132">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9e507-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9e507-133">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9e507-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e507-134">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e507-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9e507-135">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9e507-136">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9e507-137">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e507-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9e507-141">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9e507-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9e507-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9e507-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9e507-p108">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9e507-145">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9e507-146">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9e507-147">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9e507-148">[**変更**] ドロップダウン リストから、[**MX レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="9e507-150">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e507-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9e507-151">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="9e507-151">**Priority**</span></span>|<span data-ttu-id="9e507-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="9e507-152">**Host**</span></span>|<span data-ttu-id="9e507-153">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="9e507-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e507-154">0</span><span class="sxs-lookup"><span data-stu-id="9e507-154">0</span></span>  <br/> <span data-ttu-id="9e507-155">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="9e507-156">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e507-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9e507-157">**注:** Microsoft アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e507-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="9e507-158"> > [確認する方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9e507-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="9e507-160">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="9e507-162">MX レコードが他にもある場合は、各レコードの [**アクション**] 列にある [**削除**] を選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="9e507-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="9e507-164">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e507-166">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e507-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9e507-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9e507-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9e507-p110">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9e507-170">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9e507-171">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9e507-172">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9e507-173">[**変更**] ドロップダウン リストから、[**CNAME エイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="9e507-175">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e507-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="9e507-176">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e507-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9e507-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="9e507-177">**Host**</span></span>|<span data-ttu-id="9e507-178">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="9e507-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e507-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9e507-179">autodiscover</span></span>  <br/> |<span data-ttu-id="9e507-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e507-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9e507-181">sip</span><span class="sxs-lookup"><span data-stu-id="9e507-181">sip</span></span>  <br/> |<span data-ttu-id="9e507-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e507-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9e507-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e507-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e507-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e507-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9e507-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e507-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e507-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9e507-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9e507-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e507-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e507-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e507-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="9e507-190">[**追加**] を選択し、最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e507-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="9e507-192">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e507-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="9e507-193">上の表の 2 行目の値を使用し、[**追加**] を選択して 2 番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e507-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="9e507-194">同様に、表の 3 行目、4 行目、5 行目、6 行目の値を使用して、残りのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e507-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e507-195">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e507-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9e507-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9e507-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e507-197">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e507-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e507-198">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9e507-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e507-199">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9e507-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9e507-200">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="9e507-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="9e507-201">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e507-201">Need examples?</span></span> <span data-ttu-id="9e507-202">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="9e507-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9e507-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9e507-p112">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e507-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9e507-206">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9e507-207">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9e507-208">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9e507-209">[**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="9e507-211">[**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e507-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="9e507-212">**Content**</span><span class="sxs-lookup"><span data-stu-id="9e507-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="9e507-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e507-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e507-214">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e507-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="9e507-216">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e507-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e507-218">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e507-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9e507-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9e507-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="9e507-p113">MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Microsoft プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。</span><span class="sxs-lookup"><span data-stu-id="9e507-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9e507-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e507-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
