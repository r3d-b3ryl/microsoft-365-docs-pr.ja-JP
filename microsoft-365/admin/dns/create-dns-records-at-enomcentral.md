---
title: Office 365 用 eNomCentral で DNS レコードを作成する
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Office 365 の eNomCentral で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: c4cd12667ebf945aa2f354ccfa0bad1688dc9863
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241122"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a><span data-ttu-id="f3535-103">Office 365 用 eNomCentral で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="f3535-103">Create DNS records at eNomCentral for Office 365</span></span>

 <span data-ttu-id="f3535-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f3535-105">使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3535-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f3535-106">eNomCentral でこれらのレコードを追加すると、ドメインは Office 365 サービスと連携するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="f3535-106">After you add these records at eNomCentral, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f3535-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f3535-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f3535-111">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f3535-111">Add a TXT record for verification</span></span>
<span data-ttu-id="f3535-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f3535-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f3535-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3535-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="f3535-117">次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-117">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f3535-p104">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f3535-121">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-121">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f3535-123">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-123">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-検証-1-1](../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="f3535-125">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f3535-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f3535-126">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3535-126">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="f3535-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f3535-127">**Host Name**</span></span> <br/> |<span data-ttu-id="f3535-128">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f3535-128">**Record Type**</span></span> <br/> |<span data-ttu-id="f3535-129">**Address**</span><span class="sxs-lookup"><span data-stu-id="f3535-129">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="f3535-130">TXT</span><span class="sxs-lookup"><span data-stu-id="f3535-130">TXT</span></span>  <br/> |<span data-ttu-id="f3535-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f3535-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f3535-p105">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f3535-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![eNom-BP-検証-1-2](../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="f3535-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-136">Select **save**.</span></span>
    
    ![eNom-BP-検証-1-3](../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="f3535-138">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="f3535-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f3535-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="f3535-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f3535-140">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="f3535-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f3535-141">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3535-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f3535-142">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f3535-143">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f3535-144">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f3535-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f3535-148">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="f3535-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f3535-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f3535-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f3535-150">次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-150">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f3535-p107">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f3535-154">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-154">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f3535-156">[ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-156">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-1-3](../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="f3535-158">[ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-158">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-1-4](../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="f3535-160">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="f3535-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f3535-161">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f3535-161">**Host Name**</span></span>|<span data-ttu-id="f3535-162">**Address**</span><span class="sxs-lookup"><span data-stu-id="f3535-162">**Address**</span></span>|<span data-ttu-id="f3535-163">**Pref**</span><span class="sxs-lookup"><span data-stu-id="f3535-163">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="f3535-164">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f3535-164">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f3535-165">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f3535-165">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f3535-166">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="f3535-166">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="f3535-167">確認する方法</span><span class="sxs-lookup"><span data-stu-id="f3535-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f3535-168">10 </span><span class="sxs-lookup"><span data-stu-id="f3535-168">10</span></span>  <br/> <span data-ttu-id="f3535-169">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-2-1](../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="f3535-171">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-171">Select **save**.</span></span>
    
    ![eNom-BP-2-2](../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="f3535-173">他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-173">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-2-3](../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="f3535-175">[**削除] チェック**ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f3535-175">Select **delete checked**.</span></span>
    
    ![eNom-BP-2-4](../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f3535-177">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f3535-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f3535-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f3535-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f3535-179">次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-179">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f3535-p109">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f3535-183">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-183">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f3535-185">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-185">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f3535-187">[**新しい行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-187">Select **new row**.</span></span>
    
    ![eNom-BP-3-1](../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="f3535-189">6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f3535-189">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |<span data-ttu-id="f3535-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f3535-190">**Host Name**</span></span>|<span data-ttu-id="f3535-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f3535-191">**Record Type**</span></span>|<span data-ttu-id="f3535-192">**アドレス**</span><span class="sxs-lookup"><span data-stu-id="f3535-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f3535-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f3535-193">autodiscover</span></span>  <br/> |<span data-ttu-id="f3535-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f3535-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f3535-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f3535-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f3535-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f3535-197">sip</span><span class="sxs-lookup"><span data-stu-id="f3535-197">sip</span></span>  <br/> |<span data-ttu-id="f3535-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f3535-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f3535-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f3535-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f3535-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f3535-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f3535-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f3535-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f3535-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f3535-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f3535-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="f3535-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f3535-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f3535-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f3535-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f3535-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f3535-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="f3535-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="f3535-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f3535-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f3535-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f3535-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f3535-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="f3535-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="f3535-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="f3535-212">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f3535-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-3-2](../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="f3535-214">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-214">Select **save**.</span></span>
    
    ![eNom-BP-3-3](../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f3535-216">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f3535-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f3535-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f3535-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3535-218">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="f3535-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f3535-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="f3535-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f3535-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3535-220">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f3535-221">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="f3535-221">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="f3535-222">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-222">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f3535-p111">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f3535-226">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f3535-228">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f3535-230">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f3535-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f3535-231">(Choose the **Record Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="f3535-231">(Choose the **Record Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f3535-232">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="f3535-232">**Host Name**</span></span>|<span data-ttu-id="f3535-233">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f3535-233">**Record Type**</span></span>|<span data-ttu-id="f3535-234">**Address**</span><span class="sxs-lookup"><span data-stu-id="f3535-234">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f3535-235">TXT</span><span class="sxs-lookup"><span data-stu-id="f3535-235">TXT</span></span>  <br/> |<span data-ttu-id="f3535-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f3535-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="f3535-237">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3535-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-4-1](../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="f3535-239">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-239">Select **save**.</span></span>
    
    ![eNom-BP-4-2](../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f3535-241">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f3535-241">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f3535-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f3535-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f3535-243">次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-243">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="f3535-p112">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="f3535-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="f3535-247">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="f3535-249">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f3535-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="f3535-251">**新しい行**の右側で、[ **SRV レコードまたは SPF レコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-5-1](../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="f3535-253">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f3535-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f3535-254">**Service**</span><span class="sxs-lookup"><span data-stu-id="f3535-254">**Service**</span></span>|<span data-ttu-id="f3535-255">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f3535-255">**Protocol**</span></span>|<span data-ttu-id="f3535-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f3535-256">**Priority**</span></span>|<span data-ttu-id="f3535-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="f3535-257">**Weight**</span></span>|<span data-ttu-id="f3535-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="f3535-258">**Port**</span></span>|<span data-ttu-id="f3535-259">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="f3535-259">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f3535-260">_sip</span><span class="sxs-lookup"><span data-stu-id="f3535-260">_sip</span></span>  <br/> |<span data-ttu-id="f3535-261">_tls</span><span class="sxs-lookup"><span data-stu-id="f3535-261">_tls</span></span>  <br/> |<span data-ttu-id="f3535-262">100</span><span class="sxs-lookup"><span data-stu-id="f3535-262">100</span></span>  <br/> |<span data-ttu-id="f3535-263">1-d</span><span class="sxs-lookup"><span data-stu-id="f3535-263">1</span></span>  <br/> |<span data-ttu-id="f3535-264">443</span><span class="sxs-lookup"><span data-stu-id="f3535-264">443</span></span>  <br/> |<span data-ttu-id="f3535-265">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f3535-266">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f3535-266">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f3535-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f3535-267">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f3535-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="f3535-268">_tcp</span></span>  <br/> |<span data-ttu-id="f3535-269">100</span><span class="sxs-lookup"><span data-stu-id="f3535-269">100</span></span>  <br/> |<span data-ttu-id="f3535-270">1-d</span><span class="sxs-lookup"><span data-stu-id="f3535-270">1</span></span>  <br/> |<span data-ttu-id="f3535-271">5061</span><span class="sxs-lookup"><span data-stu-id="f3535-271">5061</span></span>  <br/> |<span data-ttu-id="f3535-272">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="f3535-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="f3535-273">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="f3535-273">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-5-2](../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="f3535-275">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3535-275">Select **save**</span></span>
    
    ![eNom-BP-5-3](../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="f3535-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3535-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

