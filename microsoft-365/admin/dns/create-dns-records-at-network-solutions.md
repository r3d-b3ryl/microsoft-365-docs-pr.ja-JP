---
title: Network Solutions で Office 365 用の DNS レコードを作成する
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
description: Office 365 のネットワークソリューションで、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211124"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="513bc-103">Network Solutions で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="513bc-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="513bc-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="513bc-105">使用している DNS ホスティング プロバイダーが Network Solutions の場合は、この記事に示す手順に従い、ドメインを確認して、メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="513bc-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="513bc-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="513bc-106">These are the main records to add.</span></span> <span data-ttu-id="513bc-107">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="513bc-108">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="513bc-109">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="513bc-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="513bc-110">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="513bc-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="513bc-112">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="513bc-113">これらのレコードを Network Solutions で追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="513bc-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="513bc-114">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="513bc-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="513bc-118">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-118">Add a TXT record for verification</span></span>
<span data-ttu-id="513bc-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="513bc-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="513bc-p103">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="513bc-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="513bc-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="513bc-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="513bc-124">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="513bc-125">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="513bc-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="513bc-126">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="513bc-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="513bc-127">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="513bc-129">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="513bc-131">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-131">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="513bc-133">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="513bc-134">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="513bc-134">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="513bc-136">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="513bc-138">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="513bc-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="513bc-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="513bc-139">**Host**</span></span>|<span data-ttu-id="513bc-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="513bc-140">**TTL**</span></span>|<span data-ttu-id="513bc-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="513bc-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="513bc-142">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="513bc-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="513bc-143">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-143">3600</span></span>  <br/> |<span data-ttu-id="513bc-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="513bc-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="513bc-145">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="513bc-145">**Note:** This is an example.</span></span> <span data-ttu-id="513bc-146">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="513bc-147">確認する方法</span><span class="sxs-lookup"><span data-stu-id="513bc-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="513bc-149">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-149">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="513bc-151">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-151">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="513bc-153">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="513bc-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="513bc-154">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="513bc-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="513bc-155">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="513bc-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="513bc-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="513bc-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="513bc-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="513bc-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="513bc-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="513bc-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="513bc-163">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="513bc-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="513bc-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="513bc-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="513bc-165">次の手順を実行するか、[ビデオ (3 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="513bc-166">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="513bc-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="513bc-167">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="513bc-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="513bc-168">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="513bc-170">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="513bc-172">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-172">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="513bc-174">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="513bc-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="513bc-175">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="513bc-177">[ **Mail Servers (Mx records)** ] セクションまで下にスクロールし、[ **Edit MX records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![[MX レコードの編集] を選択します。](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="513bc-179">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="513bc-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="513bc-180">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="513bc-180">**Priority**</span></span>|<span data-ttu-id="513bc-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="513bc-181">**TTL**</span></span>|<span data-ttu-id="513bc-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="513bc-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="513bc-183">10 </span><span class="sxs-lookup"><span data-stu-id="513bc-183">10</span></span>  <br/> <span data-ttu-id="513bc-184">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="513bc-185">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-185">3600</span></span>  <br/> | <span data-ttu-id="513bc-186">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="513bc-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="513bc-187">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="513bc-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="513bc-188">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="513bc-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="513bc-189">確認する方法</span><span class="sxs-lookup"><span data-stu-id="513bc-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![新しいレコードのボックスに値を入力するか貼り付けます。](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="513bc-191">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-191">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="513bc-193">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-193">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="513bc-195">他の MX レコードがある場合は、レコードごとに [ **Delete**] を選んで他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="513bc-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="513bc-197">すべてが選択されたら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-197">When they are all selected, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="513bc-199">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-199">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="513bc-201">Office 365 に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="513bc-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="513bc-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="513bc-203">次の手順を実行するか、[ビデオ (4 分 43 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="513bc-204">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="513bc-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="513bc-205">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="513bc-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="513bc-206">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="513bc-208">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="513bc-210">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-210">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="513bc-212">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="513bc-213">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="513bc-213">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="513bc-215">[ **Host alias (Cname records)** ] セクションまでスクロールし、[ **Edit CNAME records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![[ホストエイリアス] の下の [CNAME レコードの編集] を選択します。](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="513bc-217">4 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="513bc-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="513bc-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="513bc-218">**Alias**</span></span>|<span data-ttu-id="513bc-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="513bc-219">**TTL**</span></span>|<span data-ttu-id="513bc-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="513bc-220">**Refers to Host Name**</span></span>|<span data-ttu-id="513bc-221">**Other Host          ([ **Other Host**] オプション ボタンを選びます)**</span><span class="sxs-lookup"><span data-stu-id="513bc-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="513bc-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="513bc-222">autodiscover</span></span>  <br/> |<span data-ttu-id="513bc-223">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-223">3600</span></span>  <br/> |<span data-ttu-id="513bc-224">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="513bc-224">(No setting)</span></span>  <br/> |<span data-ttu-id="513bc-225">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="513bc-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="513bc-226">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="513bc-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="513bc-227">sip</span><span class="sxs-lookup"><span data-stu-id="513bc-227">sip</span></span>  <br/> |<span data-ttu-id="513bc-228">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-228">3600</span></span>  <br/> |<span data-ttu-id="513bc-229">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="513bc-229">(No setting)</span></span>  <br/> |<span data-ttu-id="513bc-230">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="513bc-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="513bc-231">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="513bc-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="513bc-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="513bc-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="513bc-233">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-233">3600</span></span>  <br/> |<span data-ttu-id="513bc-234">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="513bc-234">(No setting)</span></span>  <br/> |<span data-ttu-id="513bc-235">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="513bc-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="513bc-236">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="513bc-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="513bc-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="513bc-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="513bc-238">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-238">3600</span></span>  <br/> |<span data-ttu-id="513bc-239">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="513bc-239">(No setting)</span></span>  <br/> |<span data-ttu-id="513bc-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="513bc-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="513bc-241">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="513bc-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="513bc-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="513bc-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="513bc-243">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-243">3600</span></span>  <br/> |<span data-ttu-id="513bc-244">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="513bc-244">(No setting)</span></span>  <br/> |<span data-ttu-id="513bc-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="513bc-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="513bc-246">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="513bc-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![新しいレコードの値を入力するか貼り付けます。](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="513bc-248">必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="513bc-250">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-250">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="513bc-252">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="513bc-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="513bc-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="513bc-254">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="513bc-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="513bc-255">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="513bc-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="513bc-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="513bc-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="513bc-257">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="513bc-258">次の手順を実行するか、[ビデオ (5 分 35 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="513bc-259">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="513bc-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="513bc-260">ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="513bc-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="513bc-261">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="513bc-263">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="513bc-265">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-265">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="513bc-267">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="513bc-268">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="513bc-268">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="513bc-270">[**テキスト (Txt レコード)** ] セクションまでスクロールしてから、[ **Txt レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[テキスト] の下の [TXT レコードの編集] を選択する](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="513bc-272">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="513bc-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="513bc-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="513bc-273">**Host**</span></span>|<span data-ttu-id="513bc-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="513bc-274">**TTL**</span></span>|<span data-ttu-id="513bc-275">**Text**</span><span class="sxs-lookup"><span data-stu-id="513bc-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="513bc-276">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="513bc-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="513bc-277">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-277">3600</span></span>  <br/> |<span data-ttu-id="513bc-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="513bc-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="513bc-279">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="513bc-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="513bc-281">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-281">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="513bc-283">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-283">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="513bc-285">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="513bc-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="513bc-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="513bc-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="513bc-287">次の手順を実行するか、[ビデオ (6 分 18 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="513bc-p113">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="513bc-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="513bc-290">[**ログイン**] ボタンを選択する前に、[ **Log in to** ] ドロップダウンリストで [ **Manage My Domain Names** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="513bc-292">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="513bc-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="513bc-294">[ **EDIT DNS**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-294">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="513bc-296">[ **Manage ADVANCED DNS Records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="513bc-297">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="513bc-297">(You may have to scroll down.)</span></span>
    
    ![[Manage Advanced DNS Records] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="513bc-299">[**サービス (Srv records)** ] セクションまでスクロールし、[ **Edit SRV records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![[サービス] の [SRV レコードの編集] を選択します。](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="513bc-301">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="513bc-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="513bc-302">[ **Service**] と [ **Protocol**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="513bc-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="513bc-303">**Service**</span></span>|<span data-ttu-id="513bc-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="513bc-304">**Protocol**</span></span>|<span data-ttu-id="513bc-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="513bc-305">**TTL**</span></span>|<span data-ttu-id="513bc-306">**Priority**</span><span class="sxs-lookup"><span data-stu-id="513bc-306">**Priority**</span></span>|<span data-ttu-id="513bc-307">**Weight**</span><span class="sxs-lookup"><span data-stu-id="513bc-307">**Weight**</span></span>|<span data-ttu-id="513bc-308">**Port**</span><span class="sxs-lookup"><span data-stu-id="513bc-308">**Port**</span></span>|<span data-ttu-id="513bc-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="513bc-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="513bc-310">_sip</span><span class="sxs-lookup"><span data-stu-id="513bc-310">_sip</span></span>  <br/> |<span data-ttu-id="513bc-311">_tls</span><span class="sxs-lookup"><span data-stu-id="513bc-311">_tls</span></span>  <br/> |<span data-ttu-id="513bc-312">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-312">3600</span></span>  <br/> |<span data-ttu-id="513bc-313">100</span><span class="sxs-lookup"><span data-stu-id="513bc-313">100</span></span>  <br/> |<span data-ttu-id="513bc-314">1-d</span><span class="sxs-lookup"><span data-stu-id="513bc-314">1</span></span>  <br/> |<span data-ttu-id="513bc-315">443</span><span class="sxs-lookup"><span data-stu-id="513bc-315">443</span></span>  <br/> |<span data-ttu-id="513bc-316">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="513bc-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="513bc-317">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="513bc-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="513bc-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="513bc-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="513bc-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="513bc-319">_tcp</span></span>  <br/> |<span data-ttu-id="513bc-320">3600</span><span class="sxs-lookup"><span data-stu-id="513bc-320">3600</span></span>  <br/> |<span data-ttu-id="513bc-321">100</span><span class="sxs-lookup"><span data-stu-id="513bc-321">100</span></span>  <br/> |<span data-ttu-id="513bc-322">1-d</span><span class="sxs-lookup"><span data-stu-id="513bc-322">1</span></span>  <br/> |<span data-ttu-id="513bc-323">5061</span><span class="sxs-lookup"><span data-stu-id="513bc-323">5061</span></span>  <br/> |<span data-ttu-id="513bc-324">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="513bc-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="513bc-325">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="513bc-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![新しいレコードの値を入力するか貼り付けます。](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="513bc-327">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="513bc-327">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="513bc-329">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="513bc-329">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択する](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="513bc-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513bc-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
