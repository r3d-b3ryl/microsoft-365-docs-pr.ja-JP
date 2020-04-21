---
title: Microsoft の Dyn.com で DNS レコードを作成する
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: ドメインを確認し、電子メール、Skype for Business Online、および Dyn.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629589"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="99a1a-103">Microsoft の Dyn.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="99a1a-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="99a1a-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="99a1a-105">使用している DNS ホスティング プロバイダーが Dyn.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="99a1a-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="99a1a-106">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-106">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="99a1a-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="99a1a-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="99a1a-110">Add a TXT record for verification</span></span>
<span data-ttu-id="99a1a-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="99a1a-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="99a1a-p102">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="99a1a-115">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="99a1a-116">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="99a1a-117">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="99a1a-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="99a1a-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99a1a-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="99a1a-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="99a1a-120">**Host**</span></span>|<span data-ttu-id="99a1a-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="99a1a-121">**TTL**</span></span>|<span data-ttu-id="99a1a-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="99a1a-122">**Type**</span></span>|<span data-ttu-id="99a1a-123">**データ**</span><span class="sxs-lookup"><span data-stu-id="99a1a-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99a1a-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99a1a-125">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-125">600</span></span>  <br/> |<span data-ttu-id="99a1a-126">TXT</span><span class="sxs-lookup"><span data-stu-id="99a1a-126">TXT</span></span>  <br/> |<span data-ttu-id="99a1a-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="99a1a-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="99a1a-128">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="99a1a-128">**Note:** This is an example.</span></span> <span data-ttu-id="99a1a-129">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="99a1a-130">確認する方法</span><span class="sxs-lookup"><span data-stu-id="99a1a-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-検証-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="99a1a-132">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="99a1a-134">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="99a1a-135">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-135">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="99a1a-136">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-136">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="99a1a-137">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-137">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="99a1a-138">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="99a1a-139">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="99a1a-140">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="99a1a-p104">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="99a1a-144">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="99a1a-144">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="99a1a-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="99a1a-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="99a1a-p105">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="99a1a-149">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="99a1a-150">ドメインの [DNS] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="99a1a-151">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="99a1a-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="99a1a-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99a1a-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="99a1a-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="99a1a-154">**Host**</span></span>|<span data-ttu-id="99a1a-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="99a1a-155">**TTL**</span></span>|<span data-ttu-id="99a1a-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="99a1a-156">**Type**</span></span>|<span data-ttu-id="99a1a-157">**データ**</span><span class="sxs-lookup"><span data-stu-id="99a1a-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99a1a-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99a1a-159">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-159">600</span></span>  <br/> |<span data-ttu-id="99a1a-160">MX</span><span class="sxs-lookup"><span data-stu-id="99a1a-160">MX</span></span>  <br/> |<span data-ttu-id="99a1a-161">10  *\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="99a1a-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="99a1a-162">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="99a1a-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="99a1a-p106">**10** は MX 優先度の値です。 MX 値の先頭に追加して、スペースで値の残りの部分から区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="99a1a-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="99a1a-165">**注:** Microsoft アカウントから\* \<ドメインキー\> \*を取得します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="99a1a-166">確認する方法</span><span class="sxs-lookup"><span data-stu-id="99a1a-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="99a1a-167">優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="99a1a-169">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="99a1a-171">他の MX レコードがある場合は、[ **DELETE**] 列で各レコードのチェック ボックスをオンにして削除します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="99a1a-173">[**変更の適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="99a1a-175">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="99a1a-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="99a1a-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="99a1a-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="99a1a-p108">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="99a1a-180">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="99a1a-181">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="99a1a-182">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="99a1a-183">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="99a1a-184">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="99a1a-185">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="99a1a-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="99a1a-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="99a1a-186">**Host**</span></span>|<span data-ttu-id="99a1a-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="99a1a-187">**TTL**</span></span>|<span data-ttu-id="99a1a-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="99a1a-188">**Type**</span></span>|<span data-ttu-id="99a1a-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="99a1a-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99a1a-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="99a1a-190">autodiscover</span></span>  <br/> |<span data-ttu-id="99a1a-191">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-191">600</span></span>  <br/> |<span data-ttu-id="99a1a-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="99a1a-192">CNAME</span></span>  <br/> |<span data-ttu-id="99a1a-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="99a1a-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="99a1a-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="99a1a-195">sip</span><span class="sxs-lookup"><span data-stu-id="99a1a-195">sip</span></span>  <br/> |<span data-ttu-id="99a1a-196">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-196">600</span></span>  <br/> |<span data-ttu-id="99a1a-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="99a1a-197">CNAME</span></span>  <br/> |<span data-ttu-id="99a1a-198">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="99a1a-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="99a1a-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="99a1a-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="99a1a-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="99a1a-201">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-201">600</span></span>  <br/> |<span data-ttu-id="99a1a-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="99a1a-202">CNAME</span></span>  <br/> |<span data-ttu-id="99a1a-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="99a1a-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="99a1a-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="99a1a-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="99a1a-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="99a1a-206">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-206">600</span></span>  <br/> |<span data-ttu-id="99a1a-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="99a1a-207">CNAME</span></span>  <br/> |<span data-ttu-id="99a1a-208">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="99a1a-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="99a1a-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="99a1a-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="99a1a-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="99a1a-211">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-211">600</span></span>  <br/> |<span data-ttu-id="99a1a-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="99a1a-212">CNAME</span></span>  <br/> |<span data-ttu-id="99a1a-213">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="99a1a-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="99a1a-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="99a1a-216">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="99a1a-218">残りの 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="99a1a-219">[ **ADD DNS record** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="99a1a-220">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="99a1a-221">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="99a1a-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="99a1a-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="99a1a-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="99a1a-223">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="99a1a-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="99a1a-224">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="99a1a-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="99a1a-225">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="99a1a-226">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="99a1a-p110">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="99a1a-230">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="99a1a-231">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="99a1a-232">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="99a1a-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="99a1a-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="99a1a-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="99a1a-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="99a1a-235">**Host**</span></span>|<span data-ttu-id="99a1a-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="99a1a-236">**TTL**</span></span>|<span data-ttu-id="99a1a-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="99a1a-237">**Type**</span></span>|<span data-ttu-id="99a1a-238">**データ**</span><span class="sxs-lookup"><span data-stu-id="99a1a-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99a1a-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="99a1a-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="99a1a-240">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-240">600</span></span>  <br/> |<span data-ttu-id="99a1a-241">TXT</span><span class="sxs-lookup"><span data-stu-id="99a1a-241">TXT</span></span>  <br/> |<span data-ttu-id="99a1a-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="99a1a-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="99a1a-243">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99a1a-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="99a1a-245">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="99a1a-247">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="99a1a-247">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="99a1a-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="99a1a-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="99a1a-249">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99a1a-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="99a1a-250">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="99a1a-252">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="99a1a-253">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="99a1a-254">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="99a1a-255">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="99a1a-256">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="99a1a-257">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="99a1a-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="99a1a-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="99a1a-258">**Host**</span></span>|<span data-ttu-id="99a1a-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="99a1a-259">**TTL**</span></span>|<span data-ttu-id="99a1a-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="99a1a-260">**Type**</span></span>|<span data-ttu-id="99a1a-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="99a1a-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="99a1a-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="99a1a-262">_sip._tls</span></span>|<span data-ttu-id="99a1a-263">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-263">600</span></span>|<span data-ttu-id="99a1a-264">SRV</span><span class="sxs-lookup"><span data-stu-id="99a1a-264">SRV</span></span>|<span data-ttu-id="99a1a-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="99a1a-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="99a1a-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="99a1a-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="99a1a-267">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99a1a-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="99a1a-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="99a1a-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="99a1a-269">600</span><span class="sxs-lookup"><span data-stu-id="99a1a-269">600</span></span>|<span data-ttu-id="99a1a-270">SRV</span><span class="sxs-lookup"><span data-stu-id="99a1a-270">SRV</span></span>|<span data-ttu-id="99a1a-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="99a1a-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="99a1a-272">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="99a1a-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="99a1a-273">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99a1a-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="99a1a-275">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="99a1a-277">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="99a1a-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="99a1a-278">[ **ADD DNS record** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="99a1a-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="99a1a-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a1a-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
