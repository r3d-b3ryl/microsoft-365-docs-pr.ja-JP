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
ms.openlocfilehash: b43261c601b953eef7f98170f04b51d8dcf97d8d
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939273"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="badf8-103">Microsoft の eNomCentral で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="badf8-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="badf8-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="badf8-105">使用している DNS ホスティング プロバイダーが eNomCentral の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="badf8-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="badf8-106">これらのレコードを eNomCentral で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="badf8-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="badf8-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="badf8-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="badf8-110">Add a TXT record for verification</span></span>
<span data-ttu-id="badf8-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="badf8-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="badf8-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="badf8-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="badf8-116">次の手順を実行するか、[ビデオ (46 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-116">Follow the steps below or [watch the video (start at 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="badf8-p104">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="badf8-120">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="badf8-122">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-検証-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. <span data-ttu-id="badf8-124">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="badf8-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="badf8-125">ドロップダウンリストから [ **Record Type** ] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-125">Choose the **Record Type** value from the drop-down list.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="badf8-126">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="badf8-126">**Host Name**</span></span> <br/> |<span data-ttu-id="badf8-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="badf8-127">**Record Type**</span></span> <br/> |<span data-ttu-id="badf8-128">**Address**</span><span class="sxs-lookup"><span data-stu-id="badf8-128">**Address**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="badf8-129">TXT</span><span class="sxs-lookup"><span data-stu-id="badf8-129">TXT</span></span>  <br/> |<span data-ttu-id="badf8-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="badf8-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="badf8-131">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="badf8-131">**Note:** This is an example.</span></span> <span data-ttu-id="badf8-132">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="badf8-133">確認する方法</span><span class="sxs-lookup"><span data-stu-id="badf8-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![eNom-BP-検証-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. <span data-ttu-id="badf8-135">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-135">Select **save**.</span></span>
    
    ![eNom-BP-検証-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. <span data-ttu-id="badf8-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="badf8-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="badf8-138">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="badf8-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="badf8-139">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="badf8-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="badf8-140">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="badf8-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="badf8-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="badf8-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="badf8-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="badf8-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="badf8-147">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="badf8-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="badf8-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="badf8-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="badf8-149">次の手順を実行するか、[ビデオ (3 分 40 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-149">Follow the steps below or [watch the video (start at 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="badf8-p107">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="badf8-153">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="badf8-155">[ **Manage Domain**] ボックスの一覧で、[ **Email Settings**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>
    
    ![eNom-BP-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. <span data-ttu-id="badf8-157">[ **Service Selection**] ボックスで、[ **User (MX)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>
    
    ![eNom-BP-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. <span data-ttu-id="badf8-159">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="badf8-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="badf8-160">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="badf8-160">**Host Name**</span></span>|<span data-ttu-id="badf8-161">**Address**</span><span class="sxs-lookup"><span data-stu-id="badf8-161">**Address**</span></span>|<span data-ttu-id="badf8-162">**Pref**</span><span class="sxs-lookup"><span data-stu-id="badf8-162">**Pref**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> | <span data-ttu-id="badf8-163">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="badf8-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="badf8-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="badf8-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="badf8-165">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="badf8-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="badf8-166">確認する方法</span><span class="sxs-lookup"><span data-stu-id="badf8-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="badf8-167">10  </span><span class="sxs-lookup"><span data-stu-id="badf8-167">10</span></span>  <br/> <span data-ttu-id="badf8-168">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
       
   ![eNom-BP-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. <span data-ttu-id="badf8-170">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-170">Select **save**.</span></span>
    
    ![eNom-BP-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. <span data-ttu-id="badf8-172">他の既存の MX レコードがある場合は、そのレコードのチェック ボックスをオンにして選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>
    
    ![eNom-BP-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. <span data-ttu-id="badf8-174">[**削除] チェック**ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="badf8-174">Select **delete checked**.</span></span>
    
    ![eNom-BP-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="badf8-176">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="badf8-176">Add the CNAME records that are required for Microsoft</span></span> 
<span data-ttu-id="badf8-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="badf8-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="badf8-178">次の手順を実行するか、[ビデオ (4 分 24 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-178">Follow the steps below or [watch the video (start at 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="badf8-p109">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="badf8-182">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="badf8-184">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="badf8-186">[**新しい行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-186">Select **new row**.</span></span>
    
    ![eNom-BP-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. <span data-ttu-id="badf8-188">6 つの新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="badf8-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>
    
<span data-ttu-id="badf8-189">ドロップダウンリストから [ **Record Type** ] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-189">Choose the **Record Type** value from the drop-down list.</span></span>
        
    |<span data-ttu-id="badf8-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="badf8-190">**Host Name**</span></span>|<span data-ttu-id="badf8-191">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="badf8-191">**Record Type**</span></span>|<span data-ttu-id="badf8-192">**アドレス**</span><span class="sxs-lookup"><span data-stu-id="badf8-192">**Address**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="badf8-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="badf8-193">autodiscover</span></span>  <br/> |<span data-ttu-id="badf8-194">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="badf8-194">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="badf8-195">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="badf8-196">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="badf8-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="badf8-197">sip</span><span class="sxs-lookup"><span data-stu-id="badf8-197">sip</span></span>  <br/> |<span data-ttu-id="badf8-198">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="badf8-198">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="badf8-199">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="badf8-200">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="badf8-200">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="badf8-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="badf8-201">lyncdiscover</span></span>  <br/> |<span data-ttu-id="badf8-202">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="badf8-202">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="badf8-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="badf8-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="badf8-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="badf8-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="badf8-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="badf8-206">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="badf8-206">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="badf8-207">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="badf8-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="badf8-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="badf8-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="badf8-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="badf8-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="badf8-210">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="badf8-210">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="badf8-211">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="badf8-212">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="badf8-212">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. <span data-ttu-id="badf8-213">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-213">Select **save**.</span></span>
    
    ![eNom-BP-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="badf8-215">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="badf8-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="badf8-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="badf8-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="badf8-217">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="badf8-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="badf8-218">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="badf8-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="badf8-219">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="badf8-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="badf8-220">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="badf8-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
<span data-ttu-id="badf8-221">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-221">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="badf8-p111">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="badf8-225">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-225">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="badf8-227">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-227">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="badf8-229">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="badf8-229">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
<span data-ttu-id="badf8-230">ドロップダウンリストから [ **Record Type** ] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-230">Choose the **Record Type** value from the drop-down list.</span></span>
    
    |<span data-ttu-id="badf8-231">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="badf8-231">**Host Name**</span></span>|<span data-ttu-id="badf8-232">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="badf8-232">**Record Type**</span></span>|<span data-ttu-id="badf8-233">**Address**</span><span class="sxs-lookup"><span data-stu-id="badf8-233">**Address**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="badf8-234">TXT</span><span class="sxs-lookup"><span data-stu-id="badf8-234">TXT</span></span>  <br/> |<span data-ttu-id="badf8-235">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="badf8-235">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="badf8-236">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="badf8-236">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![eNom-BP-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. <span data-ttu-id="badf8-238">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-238">Select **save**.</span></span>
    
    ![eNom-BP-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="badf8-240">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="badf8-240">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="badf8-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="badf8-241"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="badf8-242">次の手順を実行するか、[ビデオ (5 分 50 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-242">Follow the steps below or [watch the video (start at 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="badf8-p112">まず、[このリンク](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)を使って eNom Central でドメイン ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="badf8-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>
    
    ![eNom-BP-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. <span data-ttu-id="badf8-246">[ **My domains**] の下で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-246">Under **my domains**, select the name of the domain that you want to edit.</span></span>
    
    ![eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. <span data-ttu-id="badf8-248">[ **Manage Domain**] ボックスの一覧で、[ **Host Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="badf8-248">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>
    
    ![eNom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. <span data-ttu-id="badf8-250">**新しい行**の右側で、[ **SRV レコードまたは SPF レコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-250">To the right of **new row**, select **add SRV or SPF record**.</span></span>
    
    ![eNom-BP-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. <span data-ttu-id="badf8-252">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="badf8-252">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="badf8-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="badf8-253">**Service**</span></span>|<span data-ttu-id="badf8-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="badf8-254">**Protocol**</span></span>|<span data-ttu-id="badf8-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="badf8-255">**Priority**</span></span>|<span data-ttu-id="badf8-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="badf8-256">**Weight**</span></span>|<span data-ttu-id="badf8-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="badf8-257">**Port**</span></span>|<span data-ttu-id="badf8-258">**Target          (Hostname)**</span><span class="sxs-lookup"><span data-stu-id="badf8-258">**Target          (Hostname)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="badf8-259">_sip</span><span class="sxs-lookup"><span data-stu-id="badf8-259">_sip</span></span>  <br/> |<span data-ttu-id="badf8-260">_tls</span><span class="sxs-lookup"><span data-stu-id="badf8-260">_tls</span></span>  <br/> |<span data-ttu-id="badf8-261">100</span><span class="sxs-lookup"><span data-stu-id="badf8-261">100</span></span>  <br/> |<span data-ttu-id="badf8-262">1-d</span><span class="sxs-lookup"><span data-stu-id="badf8-262">1</span></span>  <br/> |<span data-ttu-id="badf8-263">443</span><span class="sxs-lookup"><span data-stu-id="badf8-263">443</span></span>  <br/> |<span data-ttu-id="badf8-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="badf8-265">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="badf8-265">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="badf8-266">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="badf8-266">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="badf8-267">_tcp</span><span class="sxs-lookup"><span data-stu-id="badf8-267">_tcp</span></span>  <br/> |<span data-ttu-id="badf8-268">100</span><span class="sxs-lookup"><span data-stu-id="badf8-268">100</span></span>  <br/> |<span data-ttu-id="badf8-269">1-d</span><span class="sxs-lookup"><span data-stu-id="badf8-269">1</span></span>  <br/> |<span data-ttu-id="badf8-270">5061</span><span class="sxs-lookup"><span data-stu-id="badf8-270">5061</span></span>  <br/> |<span data-ttu-id="badf8-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="badf8-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="badf8-272">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="badf8-272">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![eNom-BP-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. <span data-ttu-id="badf8-274">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="badf8-274">Select **save**</span></span>
    
    ![eNom-BP-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  <span data-ttu-id="badf8-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="badf8-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

