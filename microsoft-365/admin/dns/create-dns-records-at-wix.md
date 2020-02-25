---
title: Office 365 用 Wix で DNS レコードを作成する
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: ドメインを確認し、電子メール、Skype for Business Online、および Wix for Office 365 の他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 43d2f2417153dd0c848c33736733237b1681c02c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243049"
---
# <a name="create-dns-records-at-wix-for-office-365"></a><span data-ttu-id="150d1-103">Office 365 用 Wix で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="150d1-103">Create DNS records at Wix for Office 365</span></span>

 <span data-ttu-id="150d1-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="150d1-105">使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="150d1-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="150d1-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="150d1-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="150d1-107">[確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="150d1-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="150d1-108">[MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)</span><span class="sxs-lookup"><span data-stu-id="150d1-108">[Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).</span></span>
    
- <span data-ttu-id="150d1-109">[Office 365 に必要な5つの CNAME レコードを追加](#add-the-five-cname-records-that-are-required-for-office-365)します。</span><span class="sxs-lookup"><span data-stu-id="150d1-109">[Add the five CNAME records that are required for Office 365](#add-the-five-cname-records-that-are-required-for-office-365).</span></span>
    
- <span data-ttu-id="150d1-110">[迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="150d1-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="150d1-111">[Office 365 に必要な 2 個の SRV レコードを追加する](#add-the-two-srv-records-that-are-required-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="150d1-111">[Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365).</span></span>
    
<span data-ttu-id="150d1-112">Wix でこれらのレコードを追加すると、ドメインは Office 365 サービスと連携するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="150d1-112">After you add these records at Wix, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="150d1-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="150d1-116">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="150d1-116">Add a TXT record for verification</span></span>
<span data-ttu-id="150d1-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="150d1-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="150d1-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="150d1-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="150d1-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="150d1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="150d1-122">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="150d1-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="150d1-123">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="150d1-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="150d1-124">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="150d1-125">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="150d1-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="150d1-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="150d1-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="150d1-127">**Host Name**</span></span> <br/> |<span data-ttu-id="150d1-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="150d1-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="150d1-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="150d1-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="150d1-130">自動入力</span><span class="sxs-lookup"><span data-stu-id="150d1-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="150d1-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="150d1-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="150d1-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="150d1-132">**Note:** This is an example.</span></span> <span data-ttu-id="150d1-133">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="150d1-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="150d1-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="150d1-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="150d1-136">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="150d1-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="150d1-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="150d1-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="150d1-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="150d1-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="150d1-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="150d1-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="150d1-140">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="150d1-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="150d1-141">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="150d1-142">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="150d1-143">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="150d1-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="150d1-147">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="150d1-147">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="150d1-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="150d1-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="150d1-149">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="150d1-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="150d1-150">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="150d1-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="150d1-151">**[マイドメイン**] ページの [**メールボックス**] 領域で、[ **MX レコードの構成**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="150d1-152">[**自分のメールプロバイダー** ] ドロップダウンリストから [**その他**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="150d1-153">[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="150d1-154">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="150d1-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="150d1-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="150d1-155">**Host Name**</span></span>|<span data-ttu-id="150d1-156">**ポイント先**</span><span class="sxs-lookup"><span data-stu-id="150d1-156">**Points to**</span></span>|<span data-ttu-id="150d1-157">**優先度**</span><span class="sxs-lookup"><span data-stu-id="150d1-157">**Priority**</span></span>|<span data-ttu-id="150d1-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="150d1-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="150d1-159">自動入力</span><span class="sxs-lookup"><span data-stu-id="150d1-159">Automatically populated</span></span> <br/> | <span data-ttu-id="150d1-160">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="150d1-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="150d1-161">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="150d1-161">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="150d1-162">確認する方法</span><span class="sxs-lookup"><span data-stu-id="150d1-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="150d1-163">.0</span><span class="sxs-lookup"><span data-stu-id="150d1-163">0</span></span>  <br/> <span data-ttu-id="150d1-164">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="150d1-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-165">1 Hour</span></span>|
   
6. <span data-ttu-id="150d1-166">その他の MX レコードが一覧表示されている場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="150d1-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="150d1-167">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="150d1-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="150d1-168">確認ダイアログボックスで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="150d1-169">Office 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="150d1-169">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="150d1-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="150d1-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="150d1-p109">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="150d1-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="150d1-173">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="150d1-174">CNAME レコードの DNS エディターの**cname (エイリアス)** 行で、[ **+ 追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="150d1-175">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="150d1-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="150d1-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="150d1-176">**Host Name**</span></span>|<span data-ttu-id="150d1-177">**ポイント先**</span><span class="sxs-lookup"><span data-stu-id="150d1-177">**Points to**</span></span>|<span data-ttu-id="150d1-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="150d1-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="150d1-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="150d1-179">autodiscover</span></span>  <br/> |<span data-ttu-id="150d1-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="150d1-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="150d1-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="150d1-182">sip</span><span class="sxs-lookup"><span data-stu-id="150d1-182">sip</span></span>  <br/> |<span data-ttu-id="150d1-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="150d1-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="150d1-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="150d1-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="150d1-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="150d1-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="150d1-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="150d1-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="150d1-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="150d1-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="150d1-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="150d1-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="150d1-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="150d1-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="150d1-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="150d1-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="150d1-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="150d1-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="150d1-194">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="150d1-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="150d1-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="150d1-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="150d1-196">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="150d1-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="150d1-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="150d1-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="150d1-198">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="150d1-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="150d1-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="150d1-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="150d1-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="150d1-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="150d1-201">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="150d1-201">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="150d1-202">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="150d1-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="150d1-203">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="150d1-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="150d1-204">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="150d1-205">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="150d1-206">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="150d1-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="150d1-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="150d1-207">**Host Name**</span></span>|<span data-ttu-id="150d1-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="150d1-208">**TXT Value**</span></span>|<span data-ttu-id="150d1-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="150d1-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="150d1-210">[空白のままにする]</span><span class="sxs-lookup"><span data-stu-id="150d1-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="150d1-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="150d1-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="150d1-212">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="150d1-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="150d1-213">TXT</span><span class="sxs-lookup"><span data-stu-id="150d1-213">TXT</span></span>  <br/> | <span data-ttu-id="150d1-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-214">1 Hour</span></span> |
   
5. <span data-ttu-id="150d1-215">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="150d1-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="150d1-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="150d1-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="150d1-217">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="150d1-217">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="150d1-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="150d1-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="150d1-219">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="150d1-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="150d1-220">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="150d1-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="150d1-221">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="150d1-222">DNS エディターの [ **SRV** ] 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="150d1-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="150d1-223">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="150d1-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="150d1-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="150d1-224">**Service**</span></span>|<span data-ttu-id="150d1-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="150d1-225">**Protocol**</span></span>|<span data-ttu-id="150d1-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="150d1-226">**Name**</span></span>|<span data-ttu-id="150d1-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="150d1-227">**Weight**</span></span>|<span data-ttu-id="150d1-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="150d1-228">**Port**</span></span>|<span data-ttu-id="150d1-229">**Target**</span><span class="sxs-lookup"><span data-stu-id="150d1-229">**Target**</span></span>|<span data-ttu-id="150d1-230">**Priority**</span><span class="sxs-lookup"><span data-stu-id="150d1-230">**Priority**</span></span>|<span data-ttu-id="150d1-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="150d1-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="150d1-232">sip</span><span class="sxs-lookup"><span data-stu-id="150d1-232">sip</span></span>  |<span data-ttu-id="150d1-233">tls</span><span class="sxs-lookup"><span data-stu-id="150d1-233">tls</span></span>  |<span data-ttu-id="150d1-234">自動入力</span><span class="sxs-lookup"><span data-stu-id="150d1-234">Automatically populated</span></span> |<span data-ttu-id="150d1-235">1-d</span><span class="sxs-lookup"><span data-stu-id="150d1-235">1</span></span>  |<span data-ttu-id="150d1-236">443</span><span class="sxs-lookup"><span data-stu-id="150d1-236">443</span></span>   |<span data-ttu-id="150d1-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="150d1-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="150d1-238">100</span><span class="sxs-lookup"><span data-stu-id="150d1-238">100</span></span> |<span data-ttu-id="150d1-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-239">1 Hour</span></span> |
|<span data-ttu-id="150d1-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="150d1-240">sipfed</span></span>|<span data-ttu-id="150d1-241">tcp</span><span class="sxs-lookup"><span data-stu-id="150d1-241">tcp</span></span> |<span data-ttu-id="150d1-242">自動入力</span><span class="sxs-lookup"><span data-stu-id="150d1-242">Automatically populated</span></span>|<span data-ttu-id="150d1-243">1-d</span><span class="sxs-lookup"><span data-stu-id="150d1-243">1</span></span> |<span data-ttu-id="150d1-244">5061</span><span class="sxs-lookup"><span data-stu-id="150d1-244">5061</span></span> |<span data-ttu-id="150d1-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="150d1-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="150d1-246">100</span><span class="sxs-lookup"><span data-stu-id="150d1-246">100</span></span> | <span data-ttu-id="150d1-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="150d1-247">1 Hour</span></span> |
   
5. <span data-ttu-id="150d1-248">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="150d1-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="150d1-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span><span class="sxs-lookup"><span data-stu-id="150d1-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="150d1-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150d1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

