---
title: Microsoft の Wix で DNS レコードを作成する
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
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Wix でその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 2cbc4887f276e63f09b433225e09315c227c961c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629241"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="6181f-103">Microsoft の Wix で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6181f-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="6181f-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6181f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6181f-105">使用している DNS ホスティング プロバイダーが Wix の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="6181f-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6181f-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6181f-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="6181f-107">[確認用に TXT レコードを追加する](#add-a-txt-record-for-verification)</span><span class="sxs-lookup"><span data-stu-id="6181f-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="6181f-108">[MX レコードを追加して、自分のドメインのメールが Microsoft に届くよう](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)にします。</span><span class="sxs-lookup"><span data-stu-id="6181f-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="6181f-109">[Microsoft に必要な5つの CNAME レコードを追加](#add-the-five-cname-records-that-are-required-for-microsoft)します。</span><span class="sxs-lookup"><span data-stu-id="6181f-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="6181f-110">[迷惑メールの防止に役立つ、SPF の TXT レコードを追加する](#add-a-txt-record-for-spf-to-help-prevent-email-spam)</span><span class="sxs-lookup"><span data-stu-id="6181f-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="6181f-111">[Microsoft に必要な2つの SRV レコードを追加](#add-the-two-srv-records-that-are-required-for-microsoft)します。</span><span class="sxs-lookup"><span data-stu-id="6181f-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="6181f-112">これらのレコードを Wix で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6181f-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6181f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6181f-116">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6181f-116">Add a TXT record for verification</span></span>
<span data-ttu-id="6181f-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="6181f-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="6181f-118">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6181f-118">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6181f-119">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-119">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6181f-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6181f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6181f-122">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6181f-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6181f-123">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6181f-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6181f-124">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6181f-125">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6181f-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6181f-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6181f-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6181f-127">**Host Name**</span></span> <br/> |<span data-ttu-id="6181f-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="6181f-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="6181f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6181f-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="6181f-130">自動入力</span><span class="sxs-lookup"><span data-stu-id="6181f-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="6181f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6181f-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6181f-132">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="6181f-132">**Note:** This is an example.</span></span> <span data-ttu-id="6181f-133">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6181f-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="6181f-134">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6181f-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="6181f-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="6181f-136">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6181f-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6181f-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6181f-138">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="6181f-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6181f-139">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6181f-140">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6181f-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6181f-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="6181f-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="6181f-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6181f-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6181f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6181f-147">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="6181f-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6181f-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="6181f-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="6181f-149">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6181f-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6181f-150">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6181f-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6181f-151">**[マイドメイン**] ページの [**メールボックス**] 領域で、[ **MX レコードの構成**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="6181f-152">[**自分のメールプロバイダー** ] ドロップダウンリストから [**その他**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="6181f-153">[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="6181f-154">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6181f-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6181f-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6181f-155">**Host Name**</span></span>|<span data-ttu-id="6181f-156">**ポイント先**</span><span class="sxs-lookup"><span data-stu-id="6181f-156">**Points to**</span></span>|<span data-ttu-id="6181f-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6181f-157">**Priority**</span></span>|<span data-ttu-id="6181f-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6181f-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6181f-159">自動入力</span><span class="sxs-lookup"><span data-stu-id="6181f-159">Automatically populated</span></span> <br/> | <span data-ttu-id="6181f-160">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6181f-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6181f-161">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="6181f-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="6181f-162">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6181f-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="6181f-163">.0</span><span class="sxs-lookup"><span data-stu-id="6181f-163">0</span></span>  <br/> <span data-ttu-id="6181f-164">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6181f-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83)</span></span> | <span data-ttu-id="6181f-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-165">1 Hour</span></span>|
   
6. <span data-ttu-id="6181f-166">その他の MX レコードが一覧表示されている場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="6181f-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="6181f-167">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="6181f-168">確認ダイアログボックスで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6181f-169">Microsoft に必要な5つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6181f-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6181f-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="6181f-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="6181f-p109">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6181f-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="6181f-173">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6181f-174">CNAME レコードの DNS エディターの**cname (エイリアス)** 行で、[ **+ 追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="6181f-175">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6181f-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6181f-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6181f-176">**Host Name**</span></span>|<span data-ttu-id="6181f-177">**Points to**</span><span class="sxs-lookup"><span data-stu-id="6181f-177">**Points to**</span></span>|<span data-ttu-id="6181f-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6181f-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6181f-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6181f-179">autodiscover</span></span>  <br/> |<span data-ttu-id="6181f-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6181f-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="6181f-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="6181f-182">sip</span><span class="sxs-lookup"><span data-stu-id="6181f-182">sip</span></span>  <br/> |<span data-ttu-id="6181f-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6181f-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6181f-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="6181f-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6181f-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6181f-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6181f-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="6181f-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="6181f-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6181f-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6181f-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6181f-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="6181f-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="6181f-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6181f-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6181f-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6181f-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="6181f-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="6181f-194">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6181f-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6181f-195">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6181f-196">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6181f-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6181f-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="6181f-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6181f-198">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6181f-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6181f-199">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="6181f-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6181f-200">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="6181f-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6181f-201">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="6181f-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="6181f-202">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6181f-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6181f-203">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6181f-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6181f-204">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6181f-205">DNS エディターの**TXT (テキスト)** 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6181f-206">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6181f-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6181f-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6181f-207">**Host Name**</span></span>|<span data-ttu-id="6181f-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="6181f-208">**TXT Value**</span></span>|<span data-ttu-id="6181f-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6181f-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6181f-210">[空白のままにする]</span><span class="sxs-lookup"><span data-stu-id="6181f-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="6181f-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6181f-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6181f-212">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6181f-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="6181f-213">TXT</span><span class="sxs-lookup"><span data-stu-id="6181f-213">TXT</span></span>  <br/> | <span data-ttu-id="6181f-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-214">1 Hour</span></span> |
   
5. <span data-ttu-id="6181f-215">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6181f-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6181f-216">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6181f-217">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6181f-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6181f-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="6181f-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="6181f-219">まず、[このリンク](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)を使って Wix でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6181f-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="6181f-220">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="6181f-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6181f-221">**[マイドメイン**] ページの [**詳細設定**] 領域で、[ **Edit DNS** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="6181f-222">DNS エディターの [ **SRV** ] 行で、[ **+ 他の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6181f-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="6181f-223">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6181f-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="6181f-224">**Service**</span><span class="sxs-lookup"><span data-stu-id="6181f-224">**Service**</span></span>|<span data-ttu-id="6181f-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="6181f-225">**Protocol**</span></span>|<span data-ttu-id="6181f-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="6181f-226">**Name**</span></span>|<span data-ttu-id="6181f-227">**Weight**</span><span class="sxs-lookup"><span data-stu-id="6181f-227">**Weight**</span></span>|<span data-ttu-id="6181f-228">**Port**</span><span class="sxs-lookup"><span data-stu-id="6181f-228">**Port**</span></span>|<span data-ttu-id="6181f-229">**Target**</span><span class="sxs-lookup"><span data-stu-id="6181f-229">**Target**</span></span>|<span data-ttu-id="6181f-230">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6181f-230">**Priority**</span></span>|<span data-ttu-id="6181f-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6181f-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6181f-232">sip</span><span class="sxs-lookup"><span data-stu-id="6181f-232">sip</span></span>  |<span data-ttu-id="6181f-233">tls</span><span class="sxs-lookup"><span data-stu-id="6181f-233">tls</span></span>  |<span data-ttu-id="6181f-234">自動入力</span><span class="sxs-lookup"><span data-stu-id="6181f-234">Automatically populated</span></span> |<span data-ttu-id="6181f-235">1-d</span><span class="sxs-lookup"><span data-stu-id="6181f-235">1</span></span>  |<span data-ttu-id="6181f-236">443</span><span class="sxs-lookup"><span data-stu-id="6181f-236">443</span></span>   |<span data-ttu-id="6181f-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6181f-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="6181f-238">100</span><span class="sxs-lookup"><span data-stu-id="6181f-238">100</span></span> |<span data-ttu-id="6181f-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-239">1 Hour</span></span> |
|<span data-ttu-id="6181f-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="6181f-240">sipfed</span></span>|<span data-ttu-id="6181f-241">tcp</span><span class="sxs-lookup"><span data-stu-id="6181f-241">tcp</span></span> |<span data-ttu-id="6181f-242">自動入力</span><span class="sxs-lookup"><span data-stu-id="6181f-242">Automatically populated</span></span>|<span data-ttu-id="6181f-243">1-d</span><span class="sxs-lookup"><span data-stu-id="6181f-243">1</span></span> |<span data-ttu-id="6181f-244">5061</span><span class="sxs-lookup"><span data-stu-id="6181f-244">5061</span></span> |<span data-ttu-id="6181f-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6181f-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="6181f-246">100</span><span class="sxs-lookup"><span data-stu-id="6181f-246">100</span></span> | <span data-ttu-id="6181f-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="6181f-247">1 Hour</span></span> |
   
5. <span data-ttu-id="6181f-248">DNS エディターの上部にある [ **dns の保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6181f-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="6181f-249">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="6181f-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6181f-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6181f-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

