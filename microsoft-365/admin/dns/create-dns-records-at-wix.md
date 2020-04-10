---
title: Office 365 用 Wix で DNS レコードを作成する
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: ドメインを確認し、電子メール、Skype for Business Online、および Wix for Office 365 の他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211064"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="2052e-103">Office 365 用 Wix で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="2052e-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="2052e-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2052e-105">使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="2052e-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2052e-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2052e-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="2052e-107">[確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="2052e-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="2052e-108">[MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="2052e-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="2052e-109">[Office 365 に必要な5つの CNAME レコードを追加](#add-the-five-cname-records-that-are-required-for-office-365)します。</span><span class="sxs-lookup"><span data-stu-id="2052e-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="2052e-110">[迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="2052e-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="2052e-111">[Office 365 に必要な 2 個の SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="2052e-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="2052e-112">Wix でこれらのレコードを追加すると、ドメインは Office 365 サービスと連携するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="2052e-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="2052e-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2052e-116">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="2052e-116">Add a TXT record for verification</span></span>
<span data-ttu-id="2052e-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="2052e-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="2052e-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="2052e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2052e-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="2052e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2052e-122">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2052e-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2052e-123">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="2052e-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2052e-124">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2052e-125">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2052e-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="2052e-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2052e-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2052e-127">**Host Name**</span></span> <br/> |<span data-ttu-id="2052e-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="2052e-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="2052e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2052e-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="2052e-130">自動入力</span><span class="sxs-lookup"><span data-stu-id="2052e-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="2052e-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2052e-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2052e-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="2052e-132">**Note:** This is an example.</span></span> <span data-ttu-id="2052e-133">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="2052e-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="2052e-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="2052e-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="2052e-136">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2052e-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2052e-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="2052e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2052e-138">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="2052e-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="2052e-139">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="2052e-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2052e-140">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2052e-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2052e-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="2052e-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="2052e-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2052e-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="2052e-147">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="2052e-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="2052e-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="2052e-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="2052e-149">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2052e-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2052e-150">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="2052e-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2052e-151">**[マイドメイン**] ページの [**メールボックス**] 領域で、[ **MX レコードの構成**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="2052e-152">[**自分のメールプロバイダー** ] ドロップダウンリストから [**その他**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="2052e-153">[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="2052e-154">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2052e-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2052e-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2052e-155">**Host Name**</span></span>|<span data-ttu-id="2052e-156">**ポイント先**</span><span class="sxs-lookup"><span data-stu-id="2052e-156">**Points to**</span></span>|<span data-ttu-id="2052e-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2052e-157">**Priority**</span></span>|<span data-ttu-id="2052e-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2052e-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2052e-159">自動入力</span><span class="sxs-lookup"><span data-stu-id="2052e-159">Automatically populated</span></span> <br/> | <span data-ttu-id="2052e-160">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2052e-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2052e-161">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="2052e-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="2052e-162">確認する方法</span><span class="sxs-lookup"><span data-stu-id="2052e-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="2052e-163">.0</span><span class="sxs-lookup"><span data-stu-id="2052e-163">0</span></span>  <br/> <span data-ttu-id="2052e-164">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="2052e-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-165">1 Hour</span></span>|
   
6. <span data-ttu-id="2052e-166">その他の MX レコードが一覧表示されている場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="2052e-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="2052e-167">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="2052e-168">確認ダイアログボックスで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="2052e-169">Office 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2052e-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="2052e-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="2052e-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="2052e-p109">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="2052e-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="2052e-173">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2052e-174">CNAME レコードの DNS エディターの**cname (エイリアス)** 行で、[ **+ 追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="2052e-175">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2052e-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2052e-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2052e-176">**Host Name**</span></span>|<span data-ttu-id="2052e-177">**Points to**</span><span class="sxs-lookup"><span data-stu-id="2052e-177">**Points to**</span></span>|<span data-ttu-id="2052e-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2052e-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2052e-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2052e-179">autodiscover</span></span>  <br/> |<span data-ttu-id="2052e-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2052e-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="2052e-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2052e-182">sip</span><span class="sxs-lookup"><span data-stu-id="2052e-182">sip</span></span>  <br/> |<span data-ttu-id="2052e-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2052e-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2052e-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="2052e-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2052e-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2052e-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2052e-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="2052e-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="2052e-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2052e-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2052e-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2052e-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="2052e-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="2052e-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2052e-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2052e-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2052e-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="2052e-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="2052e-194">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2052e-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2052e-195">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="2052e-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2052e-196">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="2052e-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2052e-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="2052e-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2052e-198">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2052e-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2052e-199">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2052e-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2052e-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2052e-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="2052e-201">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="2052e-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="2052e-202">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2052e-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2052e-203">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="2052e-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2052e-204">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2052e-205">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2052e-206">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2052e-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2052e-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="2052e-207">**Host Name**</span></span>|<span data-ttu-id="2052e-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="2052e-208">**TXT Value**</span></span>|<span data-ttu-id="2052e-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2052e-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2052e-210">[空白のままにする]</span><span class="sxs-lookup"><span data-stu-id="2052e-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="2052e-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2052e-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2052e-212">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2052e-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="2052e-213">TXT</span><span class="sxs-lookup"><span data-stu-id="2052e-213">TXT</span></span>  <br/> | <span data-ttu-id="2052e-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-214">1 Hour</span></span> |
   
5. <span data-ttu-id="2052e-215">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2052e-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2052e-216">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="2052e-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2052e-217">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="2052e-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="2052e-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="2052e-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="2052e-219">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2052e-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="2052e-220">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="2052e-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="2052e-221">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="2052e-222">DNS エディターの [ **SRV** ] 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2052e-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="2052e-223">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2052e-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="2052e-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="2052e-224">**Service**</span></span>|<span data-ttu-id="2052e-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="2052e-225">**Protocol**</span></span>|<span data-ttu-id="2052e-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="2052e-226">**Name**</span></span>|<span data-ttu-id="2052e-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="2052e-227">**Weight**</span></span>|<span data-ttu-id="2052e-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="2052e-228">**Port**</span></span>|<span data-ttu-id="2052e-229">**Target**</span><span class="sxs-lookup"><span data-stu-id="2052e-229">**Target**</span></span>|<span data-ttu-id="2052e-230">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2052e-230">**Priority**</span></span>|<span data-ttu-id="2052e-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2052e-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2052e-232">sip</span><span class="sxs-lookup"><span data-stu-id="2052e-232">sip</span></span>  |<span data-ttu-id="2052e-233">tls</span><span class="sxs-lookup"><span data-stu-id="2052e-233">tls</span></span>  |<span data-ttu-id="2052e-234">自動入力</span><span class="sxs-lookup"><span data-stu-id="2052e-234">Automatically populated</span></span> |<span data-ttu-id="2052e-235">1-d</span><span class="sxs-lookup"><span data-stu-id="2052e-235">1</span></span>  |<span data-ttu-id="2052e-236">443</span><span class="sxs-lookup"><span data-stu-id="2052e-236">443</span></span>   |<span data-ttu-id="2052e-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2052e-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="2052e-238">100</span><span class="sxs-lookup"><span data-stu-id="2052e-238">100</span></span> |<span data-ttu-id="2052e-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-239">1 Hour</span></span> |
|<span data-ttu-id="2052e-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="2052e-240">sipfed</span></span>|<span data-ttu-id="2052e-241">tcp</span><span class="sxs-lookup"><span data-stu-id="2052e-241">tcp</span></span> |<span data-ttu-id="2052e-242">自動入力</span><span class="sxs-lookup"><span data-stu-id="2052e-242">Automatically populated</span></span>|<span data-ttu-id="2052e-243">1-d</span><span class="sxs-lookup"><span data-stu-id="2052e-243">1</span></span> |<span data-ttu-id="2052e-244">5061</span><span class="sxs-lookup"><span data-stu-id="2052e-244">5061</span></span> |<span data-ttu-id="2052e-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2052e-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="2052e-246">100</span><span class="sxs-lookup"><span data-stu-id="2052e-246">100</span></span> | <span data-ttu-id="2052e-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2052e-247">1 Hour</span></span> |
   
5. <span data-ttu-id="2052e-248">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2052e-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="2052e-249">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="2052e-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2052e-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2052e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

