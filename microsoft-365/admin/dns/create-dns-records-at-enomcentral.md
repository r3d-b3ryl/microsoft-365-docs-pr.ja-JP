---
title: Microsoft の eNomCentral で DNS レコードを作成する
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の eNomCentral のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 2a1d32f0152b0c8a38b1a9e1c3fc46237708480d
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919495"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="3faed-103">Microsoft の eNomCentral で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="3faed-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="3faed-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3faed-105">使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="3faed-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3faed-106">これらのレコードを eNomCentral で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="3faed-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3faed-107">Microsoft での Web サイト向け Web ホスティングと DNS の詳細については、「[Microsoft での一般向け Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3faed-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3faed-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3faed-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3faed-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3faed-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3faed-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3faed-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="3faed-117">次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3faed-p104">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="3faed-121">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="3faed-123">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-検証-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="3faed-125">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3faed-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3faed-126">\(ドロップダウンリストから [ **Record Type** ] の値を選択します。\)</span><span class="sxs-lookup"><span data-stu-id="3faed-126">\(Choose the **Record Type** value from the drop-down list.\)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="3faed-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3faed-127">**Host Name**</span></span> <br/> |<span data-ttu-id="3faed-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="3faed-128">**Record Type**</span></span> <br/> |<span data-ttu-id="3faed-129">**Address**</span><span class="sxs-lookup"><span data-stu-id="3faed-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3faed-130">TXT</span><span class="sxs-lookup"><span data-stu-id="3faed-130">TXT</span></span>  <br/> |<span data-ttu-id="3faed-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3faed-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3faed-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="3faed-132">**Note:** This is an example.</span></span> <span data-ttu-id="3faed-133">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3faed-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3faed-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-検証-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="3faed-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-136">Select **save**.</span></span>
    
    ![eNom-BP-検証-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="3faed-138">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="3faed-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3faed-139">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="3faed-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="3faed-140">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="3faed-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3faed-141">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3faed-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3faed-142">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3faed-143">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3faed-144">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3faed-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3faed-148">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="3faed-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3faed-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3faed-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3faed-150">次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3faed-p107">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="3faed-154">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="3faed-156">[ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="3faed-158">[ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="3faed-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3faed-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3faed-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3faed-161">**Host Name**</span></span>|<span data-ttu-id="3faed-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="3faed-162">**Address**</span></span>|<span data-ttu-id="3faed-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="3faed-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="3faed-164">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3faed-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3faed-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3faed-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3faed-166">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="3faed-166">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3faed-167">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3faed-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3faed-168">10  </span><span class="sxs-lookup"><span data-stu-id="3faed-168">10</span></span>  <br/> <span data-ttu-id="3faed-169">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="3faed-171">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-171">Select **save**.</span></span>
    
    ![eNom-BP-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="3faed-173">他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="3faed-175">[**削除] チェック**ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3faed-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3faed-177">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3faed-177">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="3faed-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3faed-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3faed-179">次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3faed-p109">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="3faed-183">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="3faed-185">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="3faed-187">[**新しい行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-187">Select **new row**.</span></span>
    
    ![eNom-BP-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="3faed-189">6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3faed-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="3faed-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3faed-190">**Host Name**</span></span>|<span data-ttu-id="3faed-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="3faed-191">**Record Type**</span></span>|<span data-ttu-id="3faed-192">**アドレス**</span><span class="sxs-lookup"><span data-stu-id="3faed-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3faed-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3faed-193">autodiscover</span></span>  <br/> |<span data-ttu-id="3faed-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3faed-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3faed-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3faed-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3faed-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3faed-197">sip</span><span class="sxs-lookup"><span data-stu-id="3faed-197">sip</span></span>  <br/> |<span data-ttu-id="3faed-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3faed-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3faed-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3faed-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3faed-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3faed-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3faed-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3faed-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3faed-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3faed-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3faed-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3faed-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3faed-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3faed-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3faed-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3faed-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3faed-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="3faed-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3faed-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3faed-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3faed-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3faed-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3faed-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3faed-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3faed-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3faed-212">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3faed-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="3faed-214">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-214">Select **save**.</span></span>
    
    ![eNom-BP-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3faed-216">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3faed-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3faed-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3faed-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3faed-218">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3faed-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3faed-219">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3faed-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3faed-220">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3faed-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3faed-221">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="3faed-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="3faed-222">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3faed-p111">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="3faed-226">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="3faed-228">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="3faed-230">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3faed-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3faed-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3faed-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3faed-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="3faed-232">**Host Name**</span></span>|<span data-ttu-id="3faed-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="3faed-233">**Record Type**</span></span>|<span data-ttu-id="3faed-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="3faed-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3faed-235">TXT</span><span class="sxs-lookup"><span data-stu-id="3faed-235">TXT</span></span>  <br/> |<span data-ttu-id="3faed-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3faed-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="3faed-237">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3faed-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="3faed-239">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-239">Select **save**.</span></span>
    
    ![eNom-BP-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3faed-241">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3faed-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3faed-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3faed-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3faed-243">次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="3faed-p112">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3faed-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="3faed-247">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="3faed-249">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3faed-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="3faed-251">**新しい行**の右側で、[ **SRV レコードまたは SPF レコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="3faed-253">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3faed-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="3faed-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="3faed-254">**Service**</span></span>|<span data-ttu-id="3faed-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="3faed-255">**Protocol**</span></span>|<span data-ttu-id="3faed-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3faed-256">**Priority**</span></span>|<span data-ttu-id="3faed-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="3faed-257">**Weight**</span></span>|<span data-ttu-id="3faed-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="3faed-258">**Port**</span></span>|<span data-ttu-id="3faed-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="3faed-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3faed-260">_sip</span><span class="sxs-lookup"><span data-stu-id="3faed-260">_sip</span></span>  <br/> |<span data-ttu-id="3faed-261">_tls</span><span class="sxs-lookup"><span data-stu-id="3faed-261">_tls</span></span>  <br/> |<span data-ttu-id="3faed-262">100</span><span class="sxs-lookup"><span data-stu-id="3faed-262">100</span></span>  <br/> |<span data-ttu-id="3faed-263">1-d</span><span class="sxs-lookup"><span data-stu-id="3faed-263">1</span></span>  <br/> |<span data-ttu-id="3faed-264">443</span><span class="sxs-lookup"><span data-stu-id="3faed-264">443</span></span>  <br/> |<span data-ttu-id="3faed-265">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3faed-266">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3faed-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3faed-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3faed-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3faed-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="3faed-268">_tcp</span></span>  <br/> |<span data-ttu-id="3faed-269">100</span><span class="sxs-lookup"><span data-stu-id="3faed-269">100</span></span>  <br/> |<span data-ttu-id="3faed-270">1-d</span><span class="sxs-lookup"><span data-stu-id="3faed-270">1</span></span>  <br/> |<span data-ttu-id="3faed-271">5061</span><span class="sxs-lookup"><span data-stu-id="3faed-271">5061</span></span>  <br/> |<span data-ttu-id="3faed-272">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3faed-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="3faed-273">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3faed-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="3faed-275">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3faed-275">Select **save**</span></span>
    
    ![eNom-BP-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="3faed-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3faed-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

