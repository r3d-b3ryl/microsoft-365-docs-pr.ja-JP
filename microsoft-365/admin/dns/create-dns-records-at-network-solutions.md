---
title: Microsoft のネットワーク ソリューションで DNS レコードを作成する
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Microsoft のネットワーク ソリューションで、ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: f25e21037695c99489adc9038bf70629a103ec7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910140"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="27963-103">Microsoft のネットワーク ソリューションで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="27963-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="27963-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="27963-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="27963-105">使用している DNS ホスティング プロバイダーが Network Solutions の場合は、この記事に示す手順に従い、ドメインを確認して、メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="27963-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="27963-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27963-106">These are the main records to add.</span></span> <span data-ttu-id="27963-107">次の手順を実行するか、[ビデオを参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="27963-108">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="27963-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="27963-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="27963-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="27963-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="27963-112">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="27963-113">ネットワーク ソリューションでこれらのレコードを追加すると、Microsoft サービスを使用するためにドメインがセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="27963-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="27963-p102">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27963-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="27963-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-117">Add a TXT record for verification</span></span>
<span data-ttu-id="27963-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="27963-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="27963-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="27963-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27963-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="27963-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="27963-123">次の手順を実行するか、[ビデオ (47 秒から開始) を参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="27963-p105">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="27963-p105">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27963-126">[ログイン] ボタンを **選択する前** に、[ログイン先:] ドロップダウン リストで [自分のドメイン名の管理 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="27963-128">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27963-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="27963-130">[DNS **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-130">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="27963-132">[高度 **な DNS レコードの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="27963-133">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="27963-133">(You may have to scroll down.)</span></span>
    
    ![[高度な DNS レコードの管理] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="27963-135">[テキスト **(TXT レコード)] セクションまで** 下にスクロールし、[TXT レコードの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[TXT レコードの編集] を選択する](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="27963-137">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="27963-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="27963-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="27963-138">**Host**</span></span>|<span data-ttu-id="27963-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27963-139">**TTL**</span></span>|<span data-ttu-id="27963-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="27963-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="27963-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="27963-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="27963-142">3600</span><span class="sxs-lookup"><span data-stu-id="27963-142">3600</span></span>  <br/> |<span data-ttu-id="27963-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="27963-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="27963-144">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="27963-144">**Note:** This is an example.</span></span> <span data-ttu-id="27963-145">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="27963-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="27963-146">確認する方法</span><span class="sxs-lookup"><span data-stu-id="27963-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![新しいレコードのボックスに値を入力または貼り付ける](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="27963-148">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-148">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="27963-150">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-150">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="27963-152">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="27963-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="27963-153">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="27963-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="27963-154">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="27963-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="27963-155">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="27963-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="27963-156">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="27963-157">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="27963-158">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="27963-p107">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27963-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="27963-162">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="27963-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="27963-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="27963-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="27963-164">次の手順を実行するか、[ビデオ (3 分 51 秒から開始) を参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="27963-p108">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="27963-p108">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27963-167">[ログイン] ボタンを **選択する前** に、[ログイン先:] ドロップダウン リストで [自分のドメイン名の管理 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="27963-169">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27963-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="27963-171">[DNS **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-171">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="27963-173">[高度 **な DNS レコードの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="27963-174">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="27963-174">(You may have to scroll down.)</span></span>
    
    ![[高度な DNS レコードの管理] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="27963-176">[メール サーバー **(MX レコード)] セクションまで** 下にスクロールし、[MX レコードの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![[MX レコードの編集] を選択する](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="27963-178">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="27963-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="27963-179">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="27963-179">**Priority**</span></span>|<span data-ttu-id="27963-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27963-180">**TTL**</span></span>|<span data-ttu-id="27963-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="27963-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="27963-182">10  </span><span class="sxs-lookup"><span data-stu-id="27963-182">10</span></span>  <br/> <span data-ttu-id="27963-183">優先度の詳細については、「[MX 優先度とは何か](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27963-183">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="27963-184">3600</span><span class="sxs-lookup"><span data-stu-id="27963-184">3600</span></span>  <br/> | <span data-ttu-id="27963-185">*\<domain-key\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="27963-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="27963-186">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="27963-187">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="27963-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="27963-188">確認する方法</span><span class="sxs-lookup"><span data-stu-id="27963-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![新しいレコードのボックスに値を入力または貼り付ける](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="27963-190">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-190">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="27963-192">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-192">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="27963-194">他の MX レコードがある場合は、レコードごとに [ **Delete**] を選んで他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="27963-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="27963-196">すべて選択されている場合は、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-196">When they are all selected, select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="27963-198">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-198">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="27963-200">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="27963-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="27963-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="27963-202">次の手順を実行するか、[ビデオ (4 分 43 秒から開始) を参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="27963-p110">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="27963-p110">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27963-205">[ログイン] ボタンを **選択する前** に、[ログイン先:] ドロップダウン リストで [自分のドメイン名の管理 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="27963-207">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27963-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="27963-209">[DNS **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-209">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="27963-211">[高度 **な DNS レコードの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="27963-212">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="27963-212">(You may have to scroll down.)</span></span>
    
    ![[高度な DNS レコードの管理] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="27963-214">[ホスト エイリアス **(CNAME レコード)] セクション** まで下にスクロールし、[CNAME レコードの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![[ホスト エイリアス] で [CNAME レコードの編集] を選択します。](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="27963-216">4 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="27963-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="27963-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="27963-217">**Alias**</span></span>|<span data-ttu-id="27963-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27963-218">**TTL**</span></span>|<span data-ttu-id="27963-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="27963-219">**Refers to Host Name**</span></span>|<span data-ttu-id="27963-220">**Other Host          ([ **Other Host**] オプション ボタンを選びます)**</span><span class="sxs-lookup"><span data-stu-id="27963-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27963-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="27963-221">autodiscover</span></span>  <br/> |<span data-ttu-id="27963-222">3600</span><span class="sxs-lookup"><span data-stu-id="27963-222">3600</span></span>  <br/> |<span data-ttu-id="27963-223">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="27963-223">(No setting)</span></span>  <br/> |<span data-ttu-id="27963-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="27963-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="27963-225">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27963-226">sip</span><span class="sxs-lookup"><span data-stu-id="27963-226">sip</span></span>  <br/> |<span data-ttu-id="27963-227">3600</span><span class="sxs-lookup"><span data-stu-id="27963-227">3600</span></span>  <br/> |<span data-ttu-id="27963-228">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="27963-228">(No setting)</span></span>  <br/> |<span data-ttu-id="27963-229">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="27963-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="27963-230">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27963-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="27963-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="27963-232">3600</span><span class="sxs-lookup"><span data-stu-id="27963-232">3600</span></span>  <br/> |<span data-ttu-id="27963-233">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="27963-233">(No setting)</span></span>  <br/> |<span data-ttu-id="27963-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="27963-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="27963-235">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27963-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="27963-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="27963-237">3600</span><span class="sxs-lookup"><span data-stu-id="27963-237">3600</span></span>  <br/> |<span data-ttu-id="27963-238">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="27963-238">(No setting)</span></span>  <br/> |<span data-ttu-id="27963-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="27963-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="27963-240">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27963-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="27963-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="27963-242">3600</span><span class="sxs-lookup"><span data-stu-id="27963-242">3600</span></span>  <br/> |<span data-ttu-id="27963-243">(設定しない)</span><span class="sxs-lookup"><span data-stu-id="27963-243">(No setting)</span></span>  <br/> |<span data-ttu-id="27963-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="27963-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="27963-245">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![新しいレコードの値を入力または貼り付ける](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="27963-247">必要なすべての CNAME レコードを追加した場合は、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="27963-249">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-249">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="27963-251">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="27963-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="27963-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="27963-253">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="27963-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="27963-254">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="27963-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="27963-255">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="27963-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="27963-256">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="27963-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="27963-257">次の手順を実行するか、[ビデオ (5 分 35 秒から開始) を参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="27963-p112">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="27963-p112">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27963-260">[ログイン] ボタンを **選択する前** に、[ログイン先:] ドロップダウン リストで [自分のドメイン名の管理 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="27963-262">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27963-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="27963-264">[DNS **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-264">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="27963-266">[高度 **な DNS レコードの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="27963-267">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="27963-267">(You may have to scroll down.)</span></span>
    
    ![[高度な DNS レコードの管理] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="27963-269">[テキスト **(TXT レコード)] セクションまで** 下にスクロールし、[TXT レコードの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![[テキスト] で [TXT レコードの編集] を選択します。](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="27963-271">新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="27963-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="27963-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="27963-272">**Host**</span></span>|<span data-ttu-id="27963-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27963-273">**TTL**</span></span>|<span data-ttu-id="27963-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="27963-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="27963-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="27963-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="27963-276">3600</span><span class="sxs-lookup"><span data-stu-id="27963-276">3600</span></span>  <br/> |<span data-ttu-id="27963-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="27963-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="27963-278">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27963-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![新しいレコードの値を入力または貼り付ける](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="27963-280">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-280">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="27963-282">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-282">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="27963-284">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="27963-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="27963-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="27963-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="27963-286">次の手順を実行するか、[ビデオ (6 分 18 秒から開始) を参照](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099)してください。</span><span class="sxs-lookup"><span data-stu-id="27963-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="27963-p113">まず、[このリンク](https://www.networksolutions.com/manage-it)を使って Network Solutions でドメイン ページにアクセスします。ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="27963-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27963-289">[ログイン] ボタンを **選択する前** に、[ログイン先:] ドロップダウン リストで [自分のドメイン名の管理 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27963-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![[Manage My Domain Names] を選択して、Network Solutions にログインします](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="27963-291">変更するドメインの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="27963-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![自分のドメインのチェック ボックスを選択します](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="27963-293">[DNS **の編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-293">Select **Edit DNS**.</span></span>
    
    ![[DNS の編集] を選択します。](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="27963-295">[高度 **な DNS レコードの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="27963-296">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="27963-296">(You may have to scroll down.)</span></span>
    
    ![[高度な DNS レコードの管理] を選択します。](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="27963-298">[サービス **(SRV レコード)] セクションまで下にスクロールし、[SRV** レコードの編集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![[サービス] で [SRV レコードの編集] を選択します。](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="27963-300">2 つの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="27963-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="27963-301">[ **Service**] と [ **Protocol**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="27963-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="27963-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="27963-302">**Service**</span></span>|<span data-ttu-id="27963-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="27963-303">**Protocol**</span></span>|<span data-ttu-id="27963-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27963-304">**TTL**</span></span>|<span data-ttu-id="27963-305">**Priority**</span><span class="sxs-lookup"><span data-stu-id="27963-305">**Priority**</span></span>|<span data-ttu-id="27963-306">**Weight**</span><span class="sxs-lookup"><span data-stu-id="27963-306">**Weight**</span></span>|<span data-ttu-id="27963-307">**Port**</span><span class="sxs-lookup"><span data-stu-id="27963-307">**Port**</span></span>|<span data-ttu-id="27963-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="27963-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27963-309">_sip</span><span class="sxs-lookup"><span data-stu-id="27963-309">_sip</span></span>  <br/> |<span data-ttu-id="27963-310">_tls</span><span class="sxs-lookup"><span data-stu-id="27963-310">_tls</span></span>  <br/> |<span data-ttu-id="27963-311">3600</span><span class="sxs-lookup"><span data-stu-id="27963-311">3600</span></span>  <br/> |<span data-ttu-id="27963-312">100</span><span class="sxs-lookup"><span data-stu-id="27963-312">100</span></span>  <br/> |<span data-ttu-id="27963-313">1</span><span class="sxs-lookup"><span data-stu-id="27963-313">1</span></span>  <br/> |<span data-ttu-id="27963-314">443</span><span class="sxs-lookup"><span data-stu-id="27963-314">443</span></span>  <br/> |<span data-ttu-id="27963-315">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="27963-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="27963-316">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27963-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="27963-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="27963-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="27963-318">_tcp</span></span>  <br/> |<span data-ttu-id="27963-319">3600</span><span class="sxs-lookup"><span data-stu-id="27963-319">3600</span></span>  <br/> |<span data-ttu-id="27963-320">100</span><span class="sxs-lookup"><span data-stu-id="27963-320">100</span></span>  <br/> |<span data-ttu-id="27963-321">1</span><span class="sxs-lookup"><span data-stu-id="27963-321">1</span></span>  <br/> |<span data-ttu-id="27963-322">5061</span><span class="sxs-lookup"><span data-stu-id="27963-322">5061</span></span>  <br/> |<span data-ttu-id="27963-323">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="27963-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="27963-324">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="27963-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![新しいレコードの値を入力または貼り付ける](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="27963-326">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-326">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="27963-328">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27963-328">Select **Save Changes**.</span></span>
    
    ![[変更の保存] を選択します。](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="27963-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27963-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
