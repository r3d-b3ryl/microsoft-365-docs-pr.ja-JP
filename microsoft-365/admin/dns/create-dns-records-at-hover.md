---
title: Microsoft のホバー時に DNS レコードを作成する
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: ドメインを確認し、メール、Skype for Business Online、および Microsoft のホバー時に他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629517"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="9a893-103">Microsoft のホバー時に DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9a893-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="9a893-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9a893-105">使用している DNS ホスティング プロバイダーが Hover の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="9a893-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="9a893-106">これらのレコードを Hover で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9a893-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="9a893-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9a893-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9a893-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9a893-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9a893-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9a893-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9a893-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a893-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="9a893-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="9a893-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a893-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="9a893-117">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9a893-p104">まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="9a893-121">[**ドメインの管理**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="9a893-123">[ **DNS** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-123">Select the **DNS** tab.</span></span> 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="9a893-125">[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-125">Select **Add New**.</span></span>
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="9a893-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9a893-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9a893-128">ホスト名</span><span class="sxs-lookup"><span data-stu-id="9a893-128">Hostname</span></span>  <br/> |<span data-ttu-id="9a893-129">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="9a893-129">Record Type</span></span>  <br/> |<span data-ttu-id="9a893-130">値</span><span class="sxs-lookup"><span data-stu-id="9a893-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="9a893-131">TXT</span><span class="sxs-lookup"><span data-stu-id="9a893-131">TXT</span></span>  <br/> |<span data-ttu-id="9a893-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9a893-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9a893-133">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9a893-133">**Note:** This is an example.</span></span> <span data-ttu-id="9a893-134">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a893-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9a893-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9a893-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="9a893-137">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-137">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="9a893-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9a893-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9a893-140">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft 365 に戻り、Microsoft 365 にレコードを検索するよう要求します。</span><span class="sxs-lookup"><span data-stu-id="9a893-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="9a893-141">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="9a893-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9a893-142">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9a893-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9a893-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9a893-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9a893-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9a893-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9a893-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9a893-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9a893-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9a893-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="9a893-151">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9a893-p107">まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="9a893-155">[**ドメインの管理**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="9a893-157">[ **DNS** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-157">Select the **DNS** tab.</span></span> 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="9a893-159">[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-159">Select **Add New**.</span></span>
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="9a893-161">新しいレコードのボックスで、[ **Record Type**] に [ **MX**] を選び、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9a893-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9a893-162">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="9a893-162">**Hostname**</span></span>|<span data-ttu-id="9a893-163">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="9a893-163">**Record Type**</span></span>|<span data-ttu-id="9a893-164">**優先度**</span><span class="sxs-lookup"><span data-stu-id="9a893-164">**Priority**</span></span>|<span data-ttu-id="9a893-165">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9a893-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9a893-166">MX</span><span class="sxs-lookup"><span data-stu-id="9a893-166">MX</span></span>  <br/> |<span data-ttu-id="9a893-167">.0</span><span class="sxs-lookup"><span data-stu-id="9a893-167">0</span></span>  <br/> <span data-ttu-id="9a893-168">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="9a893-169">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9a893-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9a893-170">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a893-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="9a893-171">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9a893-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="9a893-173">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-173">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="9a893-175">これ以外の MX レコードがある場合は、次の 2 段階のプロセスに従って、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="9a893-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="9a893-176">最初に、削除するレコードにマウスポインターて、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![マウスをポイントし、[削除] を選択します。](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="9a893-178">次に、[**はい]** を選択して各削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="9a893-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![[はい] を選択して削除を確認する](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="9a893-180">この手順の最初に追加した MX レコード以外の MX レコードをすべて削除するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9a893-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9a893-181">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9a893-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9a893-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9a893-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="9a893-183">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9a893-p109">まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="9a893-187">[**ドメインの管理**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="9a893-189">[ **DNS** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-189">Select the **DNS** tab.</span></span> 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="9a893-191">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9a893-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="9a893-192">[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-192">Select **Add New**.</span></span>
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="9a893-194">新しいレコードの空のボックスで、[ **Record Type**] に [ **CNAME**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9a893-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="9a893-195">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="9a893-195">**Hostname**</span></span>|<span data-ttu-id="9a893-196">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="9a893-196">**Record Type**</span></span>|<span data-ttu-id="9a893-197">**ターゲット ホスト**</span><span class="sxs-lookup"><span data-stu-id="9a893-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9a893-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9a893-198">autodiscover</span></span>  <br/> |<span data-ttu-id="9a893-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a893-199">CNAME</span></span>  <br/> |<span data-ttu-id="9a893-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9a893-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9a893-201">sip</span><span class="sxs-lookup"><span data-stu-id="9a893-201">sip</span></span>  <br/> |<span data-ttu-id="9a893-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a893-202">CNAME</span></span>  <br/> |<span data-ttu-id="9a893-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a893-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a893-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9a893-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9a893-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a893-205">CNAME</span></span>  <br/> |<span data-ttu-id="9a893-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a893-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a893-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9a893-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9a893-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a893-208">CNAME</span></span>  <br/> |<span data-ttu-id="9a893-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9a893-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="9a893-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9a893-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9a893-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="9a893-211">CNAME</span></span>  <br/> |<span data-ttu-id="9a893-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9a893-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="9a893-214">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-214">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="9a893-216">上の 3 つの手順に従って、表の残りの 5 行の値を使って、残りの 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="9a893-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9a893-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9a893-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9a893-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9a893-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a893-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9a893-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9a893-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9a893-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9a893-221">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9a893-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9a893-222">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a893-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="9a893-223">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9a893-p111">まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="9a893-227">[**ドメインの管理**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="9a893-229">[ **DNS** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-229">Select the **DNS** tab.</span></span> 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="9a893-231">[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-231">Select **Add New**.</span></span>
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="9a893-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9a893-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9a893-234">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9a893-234">**Hostname**</span></span>|<span data-ttu-id="9a893-235">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="9a893-235">**Record Type**</span></span>|<span data-ttu-id="9a893-236">**値**</span><span class="sxs-lookup"><span data-stu-id="9a893-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9a893-237">TXT</span><span class="sxs-lookup"><span data-stu-id="9a893-237">TXT</span></span>  <br/> |<span data-ttu-id="9a893-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9a893-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="9a893-239">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a893-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="9a893-241">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-241">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9a893-243">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9a893-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9a893-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9a893-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="9a893-245">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="9a893-p112">まず、[このリンク](https://www.hover.com/domains)を使って Hover でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9a893-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![サインイン](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="9a893-249">[**ドメインの管理**] で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![ドメインの選択](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="9a893-251">[ **DNS** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-251">Select the **DNS** tab.</span></span> 
    
    ![[DNS] タブを選択します。](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="9a893-253">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9a893-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9a893-254">[ **Add New**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-254">Select **Add New**.</span></span>
    
    ![[Add New] を選択します。](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="9a893-256">新しいレコードの空のボックスで、[ **Record Type**] に [ **SRV**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9a893-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="9a893-257">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="9a893-257">**Hostname**</span></span>|<span data-ttu-id="9a893-258">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="9a893-258">**Record Type**</span></span>|<span data-ttu-id="9a893-259">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9a893-259">**Priority**</span></span>|<span data-ttu-id="9a893-260">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9a893-260">**Weight**</span></span>|<span data-ttu-id="9a893-261">**Port**</span><span class="sxs-lookup"><span data-stu-id="9a893-261">**Port**</span></span>|<span data-ttu-id="9a893-262">**対象**</span><span class="sxs-lookup"><span data-stu-id="9a893-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9a893-263">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="9a893-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="9a893-264">SRV</span><span class="sxs-lookup"><span data-stu-id="9a893-264">SRV</span></span>  <br/> |<span data-ttu-id="9a893-265">100</span><span class="sxs-lookup"><span data-stu-id="9a893-265">100</span></span>  <br/> |<span data-ttu-id="9a893-266">1-d</span><span class="sxs-lookup"><span data-stu-id="9a893-266">1</span></span>  <br/> |<span data-ttu-id="9a893-267">443</span><span class="sxs-lookup"><span data-stu-id="9a893-267">443</span></span>  <br/> |<span data-ttu-id="9a893-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a893-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9a893-269">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="9a893-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9a893-270">SRV</span><span class="sxs-lookup"><span data-stu-id="9a893-270">SRV</span></span>  <br/> |<span data-ttu-id="9a893-271">100</span><span class="sxs-lookup"><span data-stu-id="9a893-271">100</span></span>  <br/> |<span data-ttu-id="9a893-272">1-d</span><span class="sxs-lookup"><span data-stu-id="9a893-272">1</span></span>  <br/> |<span data-ttu-id="9a893-273">5061</span><span class="sxs-lookup"><span data-stu-id="9a893-273">5061</span></span>  <br/> |<span data-ttu-id="9a893-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9a893-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![DNS の値を入力するか、コピーして貼り付けます。](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="9a893-276">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a893-276">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="9a893-278">上の 3 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9a893-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9a893-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a893-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
