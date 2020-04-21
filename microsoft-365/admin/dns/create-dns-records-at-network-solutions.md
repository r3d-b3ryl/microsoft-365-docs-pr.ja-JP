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
ms.openlocfilehash: e7ce1dd633aa916643f3dcbf7900fa7831608e78
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629301"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="b00ae-103">Microsoft のネットワークソリューションで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="b00ae-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="b00ae-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b00ae-105">使用している DNS ホスティング プロバイダーが Network Solutions の場合は、この記事に示す手順に従い、ドメインを確認して、メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b00ae-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b00ae-106">These are the main records to add.</span></span> <span data-ttu-id="b00ae-107">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="b00ae-108">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="b00ae-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="b00ae-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b00ae-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b00ae-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="b00ae-112">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b00ae-113">これらのレコードをネットワークソリューションで追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="b00ae-114">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b00ae-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b00ae-118">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-118">Add a TXT record for verification</span></span>
<span data-ttu-id="b00ae-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b00ae-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b00ae-120">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b00ae-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b00ae-121">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b00ae-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b00ae-124">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b00ae-125">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="b00ae-126">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b00ae-127">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b00ae-129">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b00ae-131">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-131">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b00ae-133">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b00ae-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-134">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b00ae-136">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="b00ae-138">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="b00ae-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="b00ae-139">**Host**</span></span>|<span data-ttu-id="b00ae-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b00ae-140">**TTL**</span></span>|<span data-ttu-id="b00ae-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="b00ae-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="b00ae-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="b00ae-143">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-143">3600</span></span>  <br/> |<span data-ttu-id="b00ae-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b00ae-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b00ae-145">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="b00ae-145">**Note:** This is an example.</span></span> <span data-ttu-id="b00ae-146">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-146">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="b00ae-147">確認する方法</span><span class="sxs-lookup"><span data-stu-id="b00ae-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="b00ae-149">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-149">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="b00ae-151">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-151">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="b00ae-153">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b00ae-154">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b00ae-155">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="b00ae-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b00ae-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b00ae-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b00ae-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b00ae-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b00ae-163">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="b00ae-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b00ae-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b00ae-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b00ae-165">次の手順を実行するか、[ビデオ (3 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b00ae-166">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="b00ae-167">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b00ae-168">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b00ae-170">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b00ae-172">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-172">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b00ae-174">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b00ae-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-175">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b00ae-177">[ **Mail Servers (Mx records)** ] セクションまで下にスクロールし、[ **Edit MX records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![[MX レコードの編集] を選択します。](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="b00ae-179">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b00ae-180">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b00ae-180">**Priority**</span></span>|<span data-ttu-id="b00ae-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b00ae-181">**TTL**</span></span>|<span data-ttu-id="b00ae-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="b00ae-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b00ae-183">10 </span><span class="sxs-lookup"><span data-stu-id="b00ae-183">10</span></span>  <br/> <span data-ttu-id="b00ae-184">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="b00ae-185">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-185">3600</span></span>  <br/> | <span data-ttu-id="b00ae-186">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b00ae-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b00ae-187">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b00ae-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="b00ae-188">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-188">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="b00ae-189">確認する方法</span><span class="sxs-lookup"><span data-stu-id="b00ae-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="b00ae-191">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-191">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="b00ae-193">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-193">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="b00ae-195">他の MX レコードがある場合は、レコードごとに [ **Delete**] を選んで他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="b00ae-197">すべてが選択されたら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-197">When they are all selected, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="b00ae-199">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-199">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b00ae-201">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-201">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b00ae-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b00ae-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b00ae-203">次の手順を実行するか、[ビデオ (4 分 43 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b00ae-204">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="b00ae-205">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b00ae-206">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b00ae-208">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b00ae-210">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-210">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b00ae-212">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b00ae-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-213">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b00ae-215">[ **Host alias (Cname records)** ] セクションまでスクロールし、[ **Edit CNAME records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![[ホストエイリアス] の下の [CNAME レコードの編集] を選択します。](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="b00ae-217">4 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b00ae-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b00ae-218">**Alias**</span></span>|<span data-ttu-id="b00ae-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b00ae-219">**TTL**</span></span>|<span data-ttu-id="b00ae-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="b00ae-220">**Refers to Host Name**</span></span>|<span data-ttu-id="b00ae-221">**Other Host          ([ **Other Host**] オプション ボタンを選びます)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b00ae-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b00ae-222">autodiscover</span></span>  <br/> |<span data-ttu-id="b00ae-223">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-223">3600</span></span>  <br/> |<span data-ttu-id="b00ae-224">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="b00ae-224">(No setting)</span></span>  <br/> |<span data-ttu-id="b00ae-225">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="b00ae-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="b00ae-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b00ae-227">sip</span><span class="sxs-lookup"><span data-stu-id="b00ae-227">sip</span></span>  <br/> |<span data-ttu-id="b00ae-228">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-228">3600</span></span>  <br/> |<span data-ttu-id="b00ae-229">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="b00ae-229">(No setting)</span></span>  <br/> |<span data-ttu-id="b00ae-230">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b00ae-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b00ae-231">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b00ae-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b00ae-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b00ae-233">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-233">3600</span></span>  <br/> |<span data-ttu-id="b00ae-234">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="b00ae-234">(No setting)</span></span>  <br/> |<span data-ttu-id="b00ae-235">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b00ae-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b00ae-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b00ae-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b00ae-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b00ae-238">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-238">3600</span></span>  <br/> |<span data-ttu-id="b00ae-239">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="b00ae-239">(No setting)</span></span>  <br/> |<span data-ttu-id="b00ae-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b00ae-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="b00ae-241">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b00ae-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b00ae-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b00ae-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b00ae-243">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-243">3600</span></span>  <br/> |<span data-ttu-id="b00ae-244">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="b00ae-244">(No setting)</span></span>  <br/> |<span data-ttu-id="b00ae-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b00ae-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="b00ae-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![新しいレコードの値を入力するか貼り付けます。](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="b00ae-248">必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="b00ae-250">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-250">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b00ae-252">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b00ae-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b00ae-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b00ae-254">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b00ae-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b00ae-255">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="b00ae-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b00ae-256">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-256">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b00ae-257">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-257">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="b00ae-258">次の手順を実行するか、[ビデオ (5 分 35 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b00ae-259">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="b00ae-260">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b00ae-261">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b00ae-263">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b00ae-265">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-265">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b00ae-267">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b00ae-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-268">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b00ae-270">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[テキスト] の下の [TXT レコードの編集] を選択する](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="b00ae-272">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="b00ae-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="b00ae-273">**Host**</span></span>|<span data-ttu-id="b00ae-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b00ae-274">**TTL**</span></span>|<span data-ttu-id="b00ae-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="b00ae-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="b00ae-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="b00ae-277">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-277">3600</span></span>  <br/> |<span data-ttu-id="b00ae-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b00ae-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b00ae-279">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="b00ae-281">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-281">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="b00ae-283">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-283">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b00ae-285">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="b00ae-285">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b00ae-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b00ae-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="b00ae-287">次の手順を実行するか、[ビデオ (6 分 18 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="b00ae-p113">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b00ae-290">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="b00ae-292">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b00ae-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="b00ae-294">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-294">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="b00ae-296">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="b00ae-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="b00ae-297">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="b00ae-299">[**サービス (Srv records)** ] セクションまでスクロールし、[ **Edit SRV records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![[サービス] の [SRV レコードの編集] を選択します。](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="b00ae-301">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="b00ae-302">[ **Service**] と [ **Protocol**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="b00ae-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="b00ae-303">**Service**</span></span>|<span data-ttu-id="b00ae-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="b00ae-304">**Protocol**</span></span>|<span data-ttu-id="b00ae-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b00ae-305">**TTL**</span></span>|<span data-ttu-id="b00ae-306">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b00ae-306">**Priority**</span></span>|<span data-ttu-id="b00ae-307">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b00ae-307">**Weight**</span></span>|<span data-ttu-id="b00ae-308">**Port**</span><span class="sxs-lookup"><span data-stu-id="b00ae-308">**Port**</span></span>|<span data-ttu-id="b00ae-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="b00ae-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b00ae-310">_sip</span><span class="sxs-lookup"><span data-stu-id="b00ae-310">_sip</span></span>  <br/> |<span data-ttu-id="b00ae-311">_tls</span><span class="sxs-lookup"><span data-stu-id="b00ae-311">_tls</span></span>  <br/> |<span data-ttu-id="b00ae-312">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-312">3600</span></span>  <br/> |<span data-ttu-id="b00ae-313">100</span><span class="sxs-lookup"><span data-stu-id="b00ae-313">100</span></span>  <br/> |<span data-ttu-id="b00ae-314">1-d</span><span class="sxs-lookup"><span data-stu-id="b00ae-314">1</span></span>  <br/> |<span data-ttu-id="b00ae-315">443</span><span class="sxs-lookup"><span data-stu-id="b00ae-315">443</span></span>  <br/> |<span data-ttu-id="b00ae-316">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b00ae-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="b00ae-317">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="b00ae-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="b00ae-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b00ae-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b00ae-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="b00ae-319">_tcp</span></span>  <br/> |<span data-ttu-id="b00ae-320">3600</span><span class="sxs-lookup"><span data-stu-id="b00ae-320">3600</span></span>  <br/> |<span data-ttu-id="b00ae-321">100</span><span class="sxs-lookup"><span data-stu-id="b00ae-321">100</span></span>  <br/> |<span data-ttu-id="b00ae-322">1-d</span><span class="sxs-lookup"><span data-stu-id="b00ae-322">1</span></span>  <br/> |<span data-ttu-id="b00ae-323">5061</span><span class="sxs-lookup"><span data-stu-id="b00ae-323">5061</span></span>  <br/> |<span data-ttu-id="b00ae-324">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="b00ae-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="b00ae-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="b00ae-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="b00ae-327">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b00ae-327">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="b00ae-329">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b00ae-329">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="b00ae-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b00ae-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
