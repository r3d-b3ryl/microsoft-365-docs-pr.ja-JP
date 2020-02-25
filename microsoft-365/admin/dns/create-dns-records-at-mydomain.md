---
title: MyDomain で Office 365 用の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: ドメインを確認し、メール、Skype for Business Online、その他のサービスに対する DNS レコードを Office 365 用の My Domain でセットアップする方法について説明します。
ms.openlocfilehash: 5a935ea456175f6d63926c9aa33280c4ec113abd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249371"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="9b9a1-103">Office 365 用の MyDomain で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9b9a1-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="9b9a1-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="9b9a1-p101">MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="9b9a1-107">サービスの制限事項があっても MyDomain で自分の Office 365 DNS レコードを管理する場合は、この記事に示す手順に従って、メールや Skype for Business Online などの DNS レコードを設定してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="9b9a1-108">これらのレコードを MyDomain で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9b9a1-109">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b9a1-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9b9a1-113">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b9a1-113">Add a TXT record for verification</span></span>
<span data-ttu-id="9b9a1-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9b9a1-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9b9a1-p103">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b9a1-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9b9a1-p105">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9b9a1-121">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9b9a1-122">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9b9a1-123">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9b9a1-124">[**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="9b9a1-125">[**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="9b9a1-126">**Content**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="9b9a1-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9b9a1-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9b9a1-128">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-128">**Note:** This is an example.</span></span> <span data-ttu-id="9b9a1-129">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="9b9a1-130">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9b9a1-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="9b9a1-131">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="9b9a1-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9b9a1-133">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9b9a1-134">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9b9a1-135">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9b9a1-136">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9b9a1-137">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9b9a1-138">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b9a1-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9b9a1-142">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9b9a1-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9b9a1-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9b9a1-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9b9a1-144">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-144">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="9b9a1-145">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9b9a1-146">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9b9a1-147">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9b9a1-148">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9b9a1-149">[**変更**] ドロップダウン リストから、[**MX レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="9b9a1-151">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9b9a1-152">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-152">**Priority**</span></span>|<span data-ttu-id="9b9a1-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-153">**Host**</span></span>|<span data-ttu-id="9b9a1-154">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9b9a1-155">0</span><span class="sxs-lookup"><span data-stu-id="9b9a1-155">0</span></span>  <br/> <span data-ttu-id="9b9a1-156">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="9b9a1-157">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b9a1-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9b9a1-158">**注:** Office 365 アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="9b9a1-159"> > [確認する方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9b9a1-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="9b9a1-161">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="9b9a1-163">MX レコードが他にもある場合は、各レコードの [**アクション**] 列にある [**削除**] を選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="9b9a1-165">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9b9a1-167">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b9a1-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9b9a1-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9b9a1-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9b9a1-169">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-169">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="9b9a1-170">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-170">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9b9a1-171">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9b9a1-172">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9b9a1-173">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9b9a1-174">[**変更**] ドロップダウン リストから、[**CNAME エイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="9b9a1-176">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="9b9a1-177">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9b9a1-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-178">**Host**</span></span>|<span data-ttu-id="9b9a1-179">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9b9a1-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9b9a1-180">autodiscover</span></span>  <br/> |<span data-ttu-id="9b9a1-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b9a1-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9b9a1-182">sip</span><span class="sxs-lookup"><span data-stu-id="9b9a1-182">sip</span></span>  <br/> |<span data-ttu-id="9b9a1-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b9a1-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b9a1-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9b9a1-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9b9a1-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b9a1-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9b9a1-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9b9a1-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9b9a1-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9b9a1-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9b9a1-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9b9a1-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9b9a1-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b9a1-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="9b9a1-191">[**追加**] を選択し、最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="9b9a1-193">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="9b9a1-194">上の表の 2 行目の値を使用し、[**追加**] を選択して 2 番目のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="9b9a1-195">同様に、表の 3 行目、4 行目、5 行目、6 行目の値を使用して、残りのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9b9a1-196">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b9a1-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9b9a1-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9b9a1-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b9a1-198">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9b9a1-199">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9b9a1-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b9a1-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9b9a1-201">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="9b9a1-202">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-202">Need examples?</span></span> <span data-ttu-id="9b9a1-203">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="9b9a1-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9b9a1-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9b9a1-205">まず、[このリンク](https://www.mydomain.com/controlpanel)を使って MyDomain でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-205">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="9b9a1-206">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-206">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="9b9a1-207">[**お気に入り**] セクションで、[**Domain Central**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="9b9a1-208">[**ドメイン**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="9b9a1-209">[**概要**] 行で、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="9b9a1-210">[**変更**] ドロップダウン リストから、[**TXT/SPF レコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="9b9a1-212">[**Content**] の新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="9b9a1-213">**Content**</span><span class="sxs-lookup"><span data-stu-id="9b9a1-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="9b9a1-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9b9a1-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9b9a1-215">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="9b9a1-217">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9b9a1-219">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9b9a1-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9b9a1-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9b9a1-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="9b9a1-p113">MyDomain の Web サイトでは、SRV レコードはサポートされません。つまり、Skype for Business Online と Outlook Web App のいくつかの機能は動作しません。どの Office 365 プランでも、MyDomain で DNS レコードを管理する場合は、[かなりのサービスの制限事項](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)があり、別の DNS ホスティング プロバイダーへの切り替えを考えることもあります。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9b9a1-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b9a1-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
