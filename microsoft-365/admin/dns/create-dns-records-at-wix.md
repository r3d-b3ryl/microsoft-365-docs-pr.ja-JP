---
title: Microsoft 用 Wix で DNS レコードを作成する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: ドメインを確認し、メール、Skype for Business Online、その他のサービス用の DNS レコードを Microsoft 用 Wix でセットアップする方法について説明します。
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814446"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="29816-103">Microsoft 用 Wix で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="29816-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="29816-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29816-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="29816-105">使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="29816-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="29816-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29816-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="29816-107">[確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="29816-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="29816-108">[MX レコードを追加して、ドメインのメールを Microsoft に送信します](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="29816-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="29816-109">[Microsoft に必要な 5 つの CNAME レコードを追加します](#add-the-five-cname-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="29816-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="29816-110">[迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="29816-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="29816-111">[Microsoft に必要な 2 つの SRV レコードを追加します](#add-the-two-srv-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="29816-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="29816-112">Wix でこれらのレコードを追加すると、使用しているドメインが、Microsoft サービスで機能するセットアップが行されます。</span><span class="sxs-lookup"><span data-stu-id="29816-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="29816-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29816-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="29816-116">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="29816-116">Add a TXT record for verification</span></span>
<span data-ttu-id="29816-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="29816-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="29816-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="29816-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29816-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="29816-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="29816-122">WIX は、サブドメインの DNS エントリをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="29816-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="29816-123">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="29816-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="29816-124">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="29816-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="29816-125">[My **Domains] ページの** **[Advanced]** メニューで **、[Edit DNS] ボタンを選** びます。</span><span class="sxs-lookup"><span data-stu-id="29816-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="29816-126">DNS **エディターの** **TXT (Text) 行で別の行を** 選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="29816-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="29816-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="29816-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="29816-128">ホスト名</span><span class="sxs-lookup"><span data-stu-id="29816-128">Host Name</span></span> <br/> | <span data-ttu-id="29816-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="29816-129">TXT Value</span></span> <br/> | <span data-ttu-id="29816-130">TTL</span><span class="sxs-lookup"><span data-stu-id="29816-130">TTL</span></span> <br/> |
   |<span data-ttu-id="29816-131">自動的に設定される</span><span class="sxs-lookup"><span data-stu-id="29816-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="29816-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="29816-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="29816-133">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="29816-133">**Note:** This is an example.</span></span> <span data-ttu-id="29816-134">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="29816-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="29816-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="29816-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="29816-136">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="29816-137">Select the **Save DNS** button at the top of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="29816-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="29816-138">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="29816-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="29816-139">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="29816-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="29816-140">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="29816-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="29816-141">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="29816-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="29816-142">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="29816-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="29816-143">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="29816-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="29816-144">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="29816-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29816-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29816-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="29816-148">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="29816-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="29816-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="29816-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="29816-150">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="29816-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="29816-151">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="29816-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="29816-152">[My **Domains] ページ** の **[Mailboxes]** 領域で **、[Configure your MX records] リンクを選** ます。</span><span class="sxs-lookup"><span data-stu-id="29816-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="29816-153">[ **お使いの** メール **プロバイダー] ドロップダウン リストから** [その他] を選びます。</span><span class="sxs-lookup"><span data-stu-id="29816-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="29816-154">Select **+ Add another**.</span><span class="sxs-lookup"><span data-stu-id="29816-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="29816-155">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="29816-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="29816-156">ホスト名</span><span class="sxs-lookup"><span data-stu-id="29816-156">Host Name</span></span> | <span data-ttu-id="29816-157">Points to </span><span class="sxs-lookup"><span data-stu-id="29816-157">Points to</span></span> | <span data-ttu-id="29816-158">Priority</span><span class="sxs-lookup"><span data-stu-id="29816-158">Priority</span></span> | <span data-ttu-id="29816-159">TTL</span><span class="sxs-lookup"><span data-stu-id="29816-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="29816-160">自動的に設定される</span><span class="sxs-lookup"><span data-stu-id="29816-160">Automatically populated</span></span> <br/> | <span data-ttu-id="29816-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="29816-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="29816-162">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="29816-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="29816-163">確認する方法</span><span class="sxs-lookup"><span data-stu-id="29816-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="29816-164">0</span><span class="sxs-lookup"><span data-stu-id="29816-164">0</span></span>  <br/> <span data-ttu-id="29816-165">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29816-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="29816-166">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-166">1 Hour</span></span>|
   
6. <span data-ttu-id="29816-167">他の MX レコードが一覧に表示されている場合は、それぞれを削除します。</span><span class="sxs-lookup"><span data-stu-id="29816-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="29816-168">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="29816-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="29816-169">確認のダイアログ ボックスで **、[OK] を選きます**。</span><span class="sxs-lookup"><span data-stu-id="29816-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="29816-170">Microsoft に必要な 5 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="29816-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="29816-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="29816-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="29816-p109">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="29816-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="29816-174">[My **Domains] ページの** **[Advanced]** メニューで **、[Edit DNS] ボタンを選** びます。</span><span class="sxs-lookup"><span data-stu-id="29816-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="29816-175">**[+Add another** in the **CNAME (Aliases)] 行で、CNAME**レコードごとに別の名前を選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="29816-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="29816-176">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="29816-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="29816-177">ホスト名</span><span class="sxs-lookup"><span data-stu-id="29816-177">Host Name</span></span> | <span data-ttu-id="29816-178">Points to </span><span class="sxs-lookup"><span data-stu-id="29816-178">Points to</span></span> | <span data-ttu-id="29816-179">TTL</span><span class="sxs-lookup"><span data-stu-id="29816-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="29816-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="29816-180">autodiscover</span></span>  <br/> |<span data-ttu-id="29816-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="29816-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="29816-182">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="29816-183">sip</span><span class="sxs-lookup"><span data-stu-id="29816-183">sip</span></span>  <br/> |<span data-ttu-id="29816-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29816-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="29816-185">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="29816-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="29816-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="29816-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29816-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="29816-188">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="29816-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="29816-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="29816-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="29816-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="29816-191">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="29816-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="29816-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="29816-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="29816-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="29816-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="29816-195">Select the **Save DNS** button at the top of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="29816-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="29816-196">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="29816-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="29816-197">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="29816-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="29816-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="29816-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="29816-199">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="29816-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="29816-200">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="29816-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="29816-201">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="29816-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="29816-202">代わりに、現在のレコードに Microsoft で必要な値を追加して、現在  *のレコードに*  両方の値を含む SPF レコードが作成されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="29816-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="29816-203">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="29816-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="29816-204">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="29816-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="29816-205">[My **Domains] ページの** **[Advanced]** メニューで **、[Edit DNS] ボタンを選** びます。</span><span class="sxs-lookup"><span data-stu-id="29816-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="29816-206">DNS **エディターの** **TXT (Text) 行で別の行を** 選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="29816-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="29816-207">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="29816-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="29816-208">ホスト名</span><span class="sxs-lookup"><span data-stu-id="29816-208">Host Name</span></span> | <span data-ttu-id="29816-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="29816-209">TXT Value</span></span> | <span data-ttu-id="29816-210">TTL</span><span class="sxs-lookup"><span data-stu-id="29816-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="29816-211">[この空白のままにする]</span><span class="sxs-lookup"><span data-stu-id="29816-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="29816-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="29816-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="29816-213">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29816-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="29816-214">TXT</span><span class="sxs-lookup"><span data-stu-id="29816-214">TXT</span></span>  <br/> | <span data-ttu-id="29816-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-215">1 Hour</span></span> |
   
5. <span data-ttu-id="29816-216">Select the **Save DNS** button at the top of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="29816-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="29816-217">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="29816-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="29816-218">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="29816-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="29816-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="29816-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="29816-220">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="29816-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="29816-221">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="29816-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="29816-222">[My **Domains] ページの** **[Advanced]** メニューで **、[Edit DNS] ボタンを選** びます。</span><span class="sxs-lookup"><span data-stu-id="29816-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="29816-223">DNS **エディターの** SRV 行に **別の行** を選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="29816-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="29816-224">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="29816-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="29816-225">サービス</span><span class="sxs-lookup"><span data-stu-id="29816-225">Service</span></span> | <span data-ttu-id="29816-226">プロトコル</span><span class="sxs-lookup"><span data-stu-id="29816-226">Protocol</span></span> | <span data-ttu-id="29816-227">名前</span><span class="sxs-lookup"><span data-stu-id="29816-227">Name</span></span> | <span data-ttu-id="29816-228">太さ</span><span class="sxs-lookup"><span data-stu-id="29816-228">Weight</span></span> | <span data-ttu-id="29816-229">ポート</span><span class="sxs-lookup"><span data-stu-id="29816-229">Port</span></span> | <span data-ttu-id="29816-230">Target</span><span class="sxs-lookup"><span data-stu-id="29816-230">Target</span></span> | <span data-ttu-id="29816-231">Priority</span><span class="sxs-lookup"><span data-stu-id="29816-231">Priority</span></span> | <span data-ttu-id="29816-232">TTL</span><span class="sxs-lookup"><span data-stu-id="29816-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="29816-233">sip</span><span class="sxs-lookup"><span data-stu-id="29816-233">sip</span></span>  |<span data-ttu-id="29816-234">tls</span><span class="sxs-lookup"><span data-stu-id="29816-234">tls</span></span>  |<span data-ttu-id="29816-235">自動的に設定される</span><span class="sxs-lookup"><span data-stu-id="29816-235">Automatically populated</span></span> |<span data-ttu-id="29816-236">1</span><span class="sxs-lookup"><span data-stu-id="29816-236">1</span></span>  |<span data-ttu-id="29816-237">443</span><span class="sxs-lookup"><span data-stu-id="29816-237">443</span></span>   |<span data-ttu-id="29816-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29816-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="29816-239">100</span><span class="sxs-lookup"><span data-stu-id="29816-239">100</span></span> |<span data-ttu-id="29816-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-240">1 Hour</span></span> |
   |<span data-ttu-id="29816-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="29816-241">sipfed</span></span>|<span data-ttu-id="29816-242">tcp</span><span class="sxs-lookup"><span data-stu-id="29816-242">tcp</span></span> |<span data-ttu-id="29816-243">自動的に設定される</span><span class="sxs-lookup"><span data-stu-id="29816-243">Automatically populated</span></span>|<span data-ttu-id="29816-244">1</span><span class="sxs-lookup"><span data-stu-id="29816-244">1</span></span> |<span data-ttu-id="29816-245">5061</span><span class="sxs-lookup"><span data-stu-id="29816-245">5061</span></span> |<span data-ttu-id="29816-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="29816-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="29816-247">100</span><span class="sxs-lookup"><span data-stu-id="29816-247">100</span></span> | <span data-ttu-id="29816-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="29816-248">1 Hour</span></span> |
   
5. <span data-ttu-id="29816-249">Select the **Save DNS** button at the top of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="29816-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="29816-250">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="29816-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29816-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29816-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
