---
title: Microsoft の Register365 で DNS レコードを作成する
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: ドメインを確認し、電子メール、Skype for Business Online、および Register365 のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629265"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="cb12e-103">Microsoft の Register365 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="cb12e-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="cb12e-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cb12e-105">使用している DNS ホスティング プロバイダーが Register365 の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="cb12e-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="cb12e-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb12e-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="cb12e-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="cb12e-108">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cb12e-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="cb12e-109">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="cb12e-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="cb12e-111">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="cb12e-112">これらのレコードを Microsoft で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="cb12e-113">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-113">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="cb12e-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cb12e-117">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-117">Add a TXT record for verification</span></span>
<span data-ttu-id="cb12e-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cb12e-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cb12e-119">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb12e-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="cb12e-120">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb12e-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cb12e-p104">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="cb12e-126">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="cb12e-127">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-127">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="cb12e-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb12e-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb12e-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="cb12e-131">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="cb12e-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="cb12e-132">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb12e-133">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="cb12e-133">**Host name**</span></span>|<span data-ttu-id="cb12e-134">**種類**</span><span class="sxs-lookup"><span data-stu-id="cb12e-134">**Type**</span></span>|<span data-ttu-id="cb12e-135">**結果**</span><span class="sxs-lookup"><span data-stu-id="cb12e-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb12e-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb12e-137">TXT</span><span class="sxs-lookup"><span data-stu-id="cb12e-137">TXT</span></span>  <br/> |<span data-ttu-id="cb12e-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cb12e-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cb12e-139">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="cb12e-139">**Note:** This is an example.</span></span> <span data-ttu-id="cb12e-140">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="cb12e-141">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cb12e-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="cb12e-143">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-143">Select **Save**.</span></span>
    
    <span data-ttu-id="cb12e-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-144">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="cb12e-146">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cb12e-147">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cb12e-148">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cb12e-149">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cb12e-150">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cb12e-151">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cb12e-152">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cb12e-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cb12e-156">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cb12e-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cb12e-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cb12e-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cb12e-p107">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="cb12e-161">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="cb12e-162">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-162">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="cb12e-164">[ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb12e-165">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb12e-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb12e-166">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="cb12e-166">**Host name**</span></span>|<span data-ttu-id="cb12e-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cb12e-167">**Priority**</span></span>|<span data-ttu-id="cb12e-168">**結果**</span><span class="sxs-lookup"><span data-stu-id="cb12e-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb12e-169">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="cb12e-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb12e-170">1-d</span><span class="sxs-lookup"><span data-stu-id="cb12e-170">1</span></span>  <br/> <span data-ttu-id="cb12e-171">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="cb12e-172">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cb12e-173">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-173">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="cb12e-174">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cb12e-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="cb12e-176">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-176">Select **Save**.</span></span>
    
    <span data-ttu-id="cb12e-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-177">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="cb12e-179">他の MX レコードがある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="cb12e-181">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-181">Select **Save**.</span></span>
    
    <span data-ttu-id="cb12e-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-182">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb12e-184">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-184">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cb12e-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cb12e-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="cb12e-p109">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="cb12e-189">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="cb12e-190">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-190">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="cb12e-192">[ **Add/Modify DNS Zone**] ページの [ **A, CNAME, AAAA, TXT and NS records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb12e-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="cb12e-194">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="cb12e-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="cb12e-195">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb12e-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb12e-196">\*\*\*\*Host name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb12e-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="cb12e-197">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb12e-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="cb12e-198">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cb12e-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb12e-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cb12e-199">autodiscover</span></span>  <br/> |<span data-ttu-id="cb12e-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb12e-200">CNAME</span></span>  <br/> |<span data-ttu-id="cb12e-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="cb12e-202">sip</span><span class="sxs-lookup"><span data-stu-id="cb12e-202">sip</span></span>  <br/> |<span data-ttu-id="cb12e-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb12e-203">CNAME</span></span>  <br/> |<span data-ttu-id="cb12e-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cb12e-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cb12e-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cb12e-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb12e-206">CNAME</span></span>  <br/> |<span data-ttu-id="cb12e-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cb12e-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cb12e-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cb12e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb12e-209">CNAME</span></span>  <br/> |<span data-ttu-id="cb12e-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cb12e-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="cb12e-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cb12e-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cb12e-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb12e-212">CNAME</span></span>  <br/> |<span data-ttu-id="cb12e-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="cb12e-215">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-215">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cb12e-217">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cb12e-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cb12e-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb12e-219">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb12e-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cb12e-220">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cb12e-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cb12e-221">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cb12e-222">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="cb12e-p111">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="cb12e-226">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="cb12e-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-227">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="cb12e-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb12e-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb12e-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="cb12e-231">(行を追加する必要がある場合は、[ **a/CNAME レコードの追加] (+)** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="cb12e-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="cb12e-232">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb12e-233">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="cb12e-233">**Host name**</span></span>|<span data-ttu-id="cb12e-234">**種類**</span><span class="sxs-lookup"><span data-stu-id="cb12e-234">**Type**</span></span>|<span data-ttu-id="cb12e-235">**結果**</span><span class="sxs-lookup"><span data-stu-id="cb12e-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb12e-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb12e-237">TXT</span><span class="sxs-lookup"><span data-stu-id="cb12e-237">TXT</span></span>  <br/> |<span data-ttu-id="cb12e-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cb12e-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="cb12e-239">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb12e-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="cb12e-241">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-241">Select **Save**.</span></span>
    
    <span data-ttu-id="cb12e-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-242">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb12e-244">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb12e-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cb12e-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cb12e-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cb12e-p112">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="cb12e-249">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="cb12e-250">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-250">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="cb12e-252">[ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb12e-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb12e-253">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb12e-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb12e-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="cb12e-254">**Name**</span></span>|<span data-ttu-id="cb12e-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cb12e-255">**Priority**</span></span>|<span data-ttu-id="cb12e-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cb12e-256">**Weight**</span></span>|<span data-ttu-id="cb12e-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="cb12e-257">**Port**</span></span>|<span data-ttu-id="cb12e-258">**Result**</span><span class="sxs-lookup"><span data-stu-id="cb12e-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb12e-259">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cb12e-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="cb12e-260">100</span><span class="sxs-lookup"><span data-stu-id="cb12e-260">100</span></span>  <br/> |<span data-ttu-id="cb12e-261">1-d</span><span class="sxs-lookup"><span data-stu-id="cb12e-261">1</span></span>  <br/> |<span data-ttu-id="cb12e-262">443</span><span class="sxs-lookup"><span data-stu-id="cb12e-262">443</span></span>  <br/> |<span data-ttu-id="cb12e-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cb12e-264">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cb12e-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cb12e-265">100</span><span class="sxs-lookup"><span data-stu-id="cb12e-265">100</span></span>  <br/> |<span data-ttu-id="cb12e-266">1-d</span><span class="sxs-lookup"><span data-stu-id="cb12e-266">1</span></span>  <br/> |<span data-ttu-id="cb12e-267">5061</span><span class="sxs-lookup"><span data-stu-id="cb12e-267">5061</span></span>  <br/> |<span data-ttu-id="cb12e-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cb12e-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![[サービスレコード] セクションに値を入力する](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="cb12e-270">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb12e-270">Select **Save**.</span></span>
    
    <span data-ttu-id="cb12e-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb12e-271">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="cb12e-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb12e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
