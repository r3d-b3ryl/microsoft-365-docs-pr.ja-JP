---
title: Microsoft のネットワークソリューションで DNS レコードを作成する
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft のネットワークソリューションでその他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: fb5fd2d2bcb263a62306617d728f08b07bb6da34
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048929"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="02f24-103">Microsoft のネットワークソリューションで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="02f24-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="02f24-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="02f24-105">使用している DNS ホスティング プロバイダーが Network Solutions の場合は、この記事に示す手順に従い、ドメインを確認して、メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="02f24-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="02f24-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02f24-106">These are the main records to add.</span></span> <span data-ttu-id="02f24-107">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="02f24-108">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="02f24-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="02f24-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="02f24-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="02f24-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="02f24-112">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="02f24-113">これらのレコードをネットワークソリューションで追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="02f24-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="02f24-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="02f24-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-117">Add a TXT record for verification</span></span>
<span data-ttu-id="02f24-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="02f24-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="02f24-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="02f24-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02f24-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="02f24-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="02f24-123">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="02f24-124">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="02f24-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="02f24-125">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="02f24-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02f24-126">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="02f24-128">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f24-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="02f24-130">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-130">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="02f24-132">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="02f24-133">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="02f24-133">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="02f24-135">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="02f24-137">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="02f24-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="02f24-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="02f24-138">**Host**</span></span>|<span data-ttu-id="02f24-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02f24-139">**TTL**</span></span>|<span data-ttu-id="02f24-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="02f24-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="02f24-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="02f24-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="02f24-142">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-142">3600</span></span>  <br/> |<span data-ttu-id="02f24-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="02f24-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="02f24-144">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="02f24-144">**Note:** This is an example.</span></span> <span data-ttu-id="02f24-145">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="02f24-146">確認する方法</span><span class="sxs-lookup"><span data-stu-id="02f24-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="02f24-148">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-148">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="02f24-150">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-150">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="02f24-152">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="02f24-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="02f24-153">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="02f24-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="02f24-154">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="02f24-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="02f24-155">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="02f24-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="02f24-156">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="02f24-157">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="02f24-158">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="02f24-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="02f24-162">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="02f24-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="02f24-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="02f24-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="02f24-164">次の手順を実行するか、[ビデオ (3 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="02f24-165">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="02f24-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="02f24-166">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="02f24-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02f24-167">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="02f24-169">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f24-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="02f24-171">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-171">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="02f24-173">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="02f24-174">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="02f24-174">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="02f24-176">[ **Mail Servers (Mx records)** ] セクションまで下にスクロールし、[ **Edit MX records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![[MX レコードの編集] を選択します。](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="02f24-178">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="02f24-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="02f24-179">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="02f24-179">**Priority**</span></span>|<span data-ttu-id="02f24-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02f24-180">**TTL**</span></span>|<span data-ttu-id="02f24-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="02f24-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="02f24-182">10  </span><span class="sxs-lookup"><span data-stu-id="02f24-182">10</span></span>  <br/> <span data-ttu-id="02f24-183">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="02f24-184">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-184">3600</span></span>  <br/> | <span data-ttu-id="02f24-185">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="02f24-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="02f24-186">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="02f24-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="02f24-187">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f24-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="02f24-188">確認する方法</span><span class="sxs-lookup"><span data-stu-id="02f24-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="02f24-190">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-190">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="02f24-192">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-192">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="02f24-194">他の MX レコードがある場合は、レコードごとに [ **Delete**] を選んで他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="02f24-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="02f24-196">すべてが選択されたら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-196">When they are all selected, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="02f24-198">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-198">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="02f24-200">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="02f24-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="02f24-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="02f24-202">次の手順を実行するか、[ビデオ (4 分 43 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="02f24-203">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="02f24-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="02f24-204">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="02f24-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02f24-205">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="02f24-207">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f24-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="02f24-209">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-209">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="02f24-211">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="02f24-212">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="02f24-212">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="02f24-214">[ **Host alias (Cname records)** ] セクションまでスクロールし、[ **Edit CNAME records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![[ホストエイリアス] の下の [CNAME レコードの編集] を選択します。](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="02f24-216">4 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="02f24-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="02f24-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="02f24-217">**Alias**</span></span>|<span data-ttu-id="02f24-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02f24-218">**TTL**</span></span>|<span data-ttu-id="02f24-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="02f24-219">**Refers to Host Name**</span></span>|<span data-ttu-id="02f24-220">**Other Host          ([ **Other Host**] オプション ボタンを選びます)**</span><span class="sxs-lookup"><span data-stu-id="02f24-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02f24-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="02f24-221">autodiscover</span></span>  <br/> |<span data-ttu-id="02f24-222">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-222">3600</span></span>  <br/> |<span data-ttu-id="02f24-223">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="02f24-223">(No setting)</span></span>  <br/> |<span data-ttu-id="02f24-224">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="02f24-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="02f24-225">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="02f24-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="02f24-226">sip</span><span class="sxs-lookup"><span data-stu-id="02f24-226">sip</span></span>  <br/> |<span data-ttu-id="02f24-227">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-227">3600</span></span>  <br/> |<span data-ttu-id="02f24-228">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="02f24-228">(No setting)</span></span>  <br/> |<span data-ttu-id="02f24-229">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="02f24-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="02f24-230">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="02f24-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="02f24-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="02f24-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="02f24-232">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-232">3600</span></span>  <br/> |<span data-ttu-id="02f24-233">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="02f24-233">(No setting)</span></span>  <br/> |<span data-ttu-id="02f24-234">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="02f24-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="02f24-235">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="02f24-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="02f24-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="02f24-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="02f24-237">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-237">3600</span></span>  <br/> |<span data-ttu-id="02f24-238">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="02f24-238">(No setting)</span></span>  <br/> |<span data-ttu-id="02f24-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="02f24-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="02f24-240">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="02f24-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="02f24-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="02f24-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="02f24-242">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-242">3600</span></span>  <br/> |<span data-ttu-id="02f24-243">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="02f24-243">(No setting)</span></span>  <br/> |<span data-ttu-id="02f24-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02f24-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="02f24-245">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="02f24-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![新しいレコードの値を入力するか貼り付けます。](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="02f24-247">必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="02f24-249">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-249">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="02f24-251">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="02f24-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="02f24-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="02f24-253">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f24-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="02f24-254">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="02f24-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="02f24-255">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="02f24-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="02f24-256">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="02f24-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="02f24-257">次の手順を実行するか、[ビデオ (5 分 35 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="02f24-258">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="02f24-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="02f24-259">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="02f24-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02f24-260">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="02f24-262">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f24-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="02f24-264">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-264">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="02f24-266">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="02f24-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="02f24-267">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="02f24-269">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[テキスト] の下の [TXT レコードの編集] を選択する](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="02f24-271">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="02f24-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="02f24-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="02f24-272">**Host**</span></span>|<span data-ttu-id="02f24-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02f24-273">**TTL**</span></span>|<span data-ttu-id="02f24-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="02f24-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="02f24-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="02f24-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="02f24-276">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-276">3600</span></span>  <br/> |<span data-ttu-id="02f24-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="02f24-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="02f24-278">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02f24-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="02f24-280">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-280">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="02f24-282">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-282">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="02f24-284">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="02f24-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="02f24-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="02f24-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="02f24-286">次の手順を実行するか、[ビデオ (6 分 18 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="02f24-p113">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="02f24-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02f24-289">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="02f24-291">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="02f24-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="02f24-293">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-293">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="02f24-295">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="02f24-296">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="02f24-296">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="02f24-298">[**サービス (Srv records)** ] セクションまでスクロールし、[ **Edit SRV records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![[サービス] の [SRV レコードの編集] を選択します。](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="02f24-300">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="02f24-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="02f24-301">[ **Service**] と [ **Protocol**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="02f24-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="02f24-302">**Service**</span></span>|<span data-ttu-id="02f24-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="02f24-303">**Protocol**</span></span>|<span data-ttu-id="02f24-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02f24-304">**TTL**</span></span>|<span data-ttu-id="02f24-305">**Priority**</span><span class="sxs-lookup"><span data-stu-id="02f24-305">**Priority**</span></span>|<span data-ttu-id="02f24-306">**Weight**</span><span class="sxs-lookup"><span data-stu-id="02f24-306">**Weight**</span></span>|<span data-ttu-id="02f24-307">**Port**</span><span class="sxs-lookup"><span data-stu-id="02f24-307">**Port**</span></span>|<span data-ttu-id="02f24-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="02f24-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02f24-309">_sip</span><span class="sxs-lookup"><span data-stu-id="02f24-309">_sip</span></span>  <br/> |<span data-ttu-id="02f24-310">_tls</span><span class="sxs-lookup"><span data-stu-id="02f24-310">_tls</span></span>  <br/> |<span data-ttu-id="02f24-311">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-311">3600</span></span>  <br/> |<span data-ttu-id="02f24-312">100</span><span class="sxs-lookup"><span data-stu-id="02f24-312">100</span></span>  <br/> |<span data-ttu-id="02f24-313">1-d</span><span class="sxs-lookup"><span data-stu-id="02f24-313">1</span></span>  <br/> |<span data-ttu-id="02f24-314">443</span><span class="sxs-lookup"><span data-stu-id="02f24-314">443</span></span>  <br/> |<span data-ttu-id="02f24-315">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="02f24-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="02f24-316">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="02f24-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="02f24-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="02f24-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="02f24-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="02f24-318">_tcp</span></span>  <br/> |<span data-ttu-id="02f24-319">3600</span><span class="sxs-lookup"><span data-stu-id="02f24-319">3600</span></span>  <br/> |<span data-ttu-id="02f24-320">100</span><span class="sxs-lookup"><span data-stu-id="02f24-320">100</span></span>  <br/> |<span data-ttu-id="02f24-321">1-d</span><span class="sxs-lookup"><span data-stu-id="02f24-321">1</span></span>  <br/> |<span data-ttu-id="02f24-322">5061</span><span class="sxs-lookup"><span data-stu-id="02f24-322">5061</span></span>  <br/> |<span data-ttu-id="02f24-323">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="02f24-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="02f24-324">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="02f24-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="02f24-326">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02f24-326">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="02f24-328">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="02f24-328">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="02f24-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f24-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
