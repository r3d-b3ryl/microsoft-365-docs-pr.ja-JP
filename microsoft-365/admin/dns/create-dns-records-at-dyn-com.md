---
title: Dyn.com で Office 365 用の DNS レコードを作成する
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: ドメインを確認し、電子メール、Skype for Business Online、および Dyn.com for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349348"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="bef6c-103">Dyn.com で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="bef6c-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="bef6c-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bef6c-105">使用している DNS ホスティング プロバイダーが Dyn.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="bef6c-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="bef6c-106">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="bef6c-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bef6c-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bef6c-110">Add a TXT record for verification</span></span>
<span data-ttu-id="bef6c-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bef6c-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="bef6c-p102">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="bef6c-115">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bef6c-116">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="bef6c-117">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="bef6c-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bef6c-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bef6c-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bef6c-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="bef6c-120">**Host**</span></span>|<span data-ttu-id="bef6c-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bef6c-121">**TTL**</span></span>|<span data-ttu-id="bef6c-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="bef6c-122">**Type**</span></span>|<span data-ttu-id="bef6c-123">**データ**</span><span class="sxs-lookup"><span data-stu-id="bef6c-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bef6c-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="bef6c-125">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-125">600</span></span>  <br/> |<span data-ttu-id="bef6c-126">TXT</span><span class="sxs-lookup"><span data-stu-id="bef6c-126">TXT</span></span>  <br/> |<span data-ttu-id="bef6c-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bef6c-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bef6c-p103">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="bef6c-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Dyn-検証-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="bef6c-132">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="bef6c-134">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bef6c-135">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="bef6c-136">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="bef6c-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bef6c-137">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="bef6c-138">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="bef6c-139">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="bef6c-140">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bef6c-p104">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="bef6c-144">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="bef6c-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="bef6c-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bef6c-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="bef6c-p105">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="bef6c-149">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bef6c-150">ドメインの [DNS] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="bef6c-151">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="bef6c-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bef6c-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bef6c-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bef6c-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="bef6c-154">**Host**</span></span>|<span data-ttu-id="bef6c-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bef6c-155">**TTL**</span></span>|<span data-ttu-id="bef6c-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="bef6c-156">**Type**</span></span>|<span data-ttu-id="bef6c-157">**データ**</span><span class="sxs-lookup"><span data-stu-id="bef6c-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bef6c-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="bef6c-159">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-159">600</span></span>  <br/> |<span data-ttu-id="bef6c-160">MX</span><span class="sxs-lookup"><span data-stu-id="bef6c-160">MX</span></span>  <br/> |<span data-ttu-id="bef6c-161">10  *\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="bef6c-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="bef6c-162">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="bef6c-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="bef6c-p106">**10** は MX 優先度の値です。 MX 値の先頭に追加して、スペースで値の残りの部分から区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="bef6c-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="bef6c-165">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="bef6c-166">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bef6c-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="bef6c-167">優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="bef6c-169">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="bef6c-171">他の MX レコードがある場合は、[ **DELETE**] 列で各レコードのチェック ボックスをオンにして削除します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="bef6c-173">[**変更の適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="bef6c-175">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bef6c-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="bef6c-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bef6c-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="bef6c-p108">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="bef6c-180">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bef6c-181">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="bef6c-182">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="bef6c-183">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="bef6c-184">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="bef6c-185">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="bef6c-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bef6c-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="bef6c-186">**Host**</span></span>|<span data-ttu-id="bef6c-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bef6c-187">**TTL**</span></span>|<span data-ttu-id="bef6c-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="bef6c-188">**Type**</span></span>|<span data-ttu-id="bef6c-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="bef6c-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bef6c-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bef6c-190">autodiscover</span></span>  <br/> |<span data-ttu-id="bef6c-191">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-191">600</span></span>  <br/> |<span data-ttu-id="bef6c-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="bef6c-192">CNAME</span></span>  <br/> |<span data-ttu-id="bef6c-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="bef6c-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="bef6c-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bef6c-195">sip</span><span class="sxs-lookup"><span data-stu-id="bef6c-195">sip</span></span>  <br/> |<span data-ttu-id="bef6c-196">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-196">600</span></span>  <br/> |<span data-ttu-id="bef6c-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="bef6c-197">CNAME</span></span>  <br/> |<span data-ttu-id="bef6c-198">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="bef6c-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bef6c-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bef6c-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bef6c-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bef6c-201">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-201">600</span></span>  <br/> |<span data-ttu-id="bef6c-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="bef6c-202">CNAME</span></span>  <br/> |<span data-ttu-id="bef6c-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="bef6c-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="bef6c-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bef6c-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bef6c-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bef6c-206">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-206">600</span></span>  <br/> |<span data-ttu-id="bef6c-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="bef6c-207">CNAME</span></span>  <br/> |<span data-ttu-id="bef6c-208">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="bef6c-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="bef6c-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="bef6c-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bef6c-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bef6c-211">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-211">600</span></span>  <br/> |<span data-ttu-id="bef6c-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="bef6c-212">CNAME</span></span>  <br/> |<span data-ttu-id="bef6c-213">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="bef6c-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="bef6c-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="bef6c-216">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="bef6c-218">残りの 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="bef6c-219">[ **ADD DNS record** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="bef6c-220">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bef6c-221">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bef6c-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bef6c-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bef6c-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bef6c-223">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bef6c-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bef6c-224">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bef6c-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bef6c-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="bef6c-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="bef6c-226">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="bef6c-p110">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="bef6c-230">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bef6c-231">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="bef6c-232">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="bef6c-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bef6c-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="bef6c-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bef6c-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="bef6c-235">**Host**</span></span>|<span data-ttu-id="bef6c-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bef6c-236">**TTL**</span></span>|<span data-ttu-id="bef6c-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="bef6c-237">**Type**</span></span>|<span data-ttu-id="bef6c-238">**データ**</span><span class="sxs-lookup"><span data-stu-id="bef6c-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bef6c-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="bef6c-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="bef6c-240">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-240">600</span></span>  <br/> |<span data-ttu-id="bef6c-241">TXT</span><span class="sxs-lookup"><span data-stu-id="bef6c-241">TXT</span></span>  <br/> |<span data-ttu-id="bef6c-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bef6c-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bef6c-243">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="bef6c-245">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="bef6c-247">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bef6c-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="bef6c-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bef6c-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="bef6c-249">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="bef6c-250">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="bef6c-252">[ **Zone Level Services** ] ページで、編集するドメインの [ **Dyn Standard DNS Service** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="bef6c-253">ドメインの [ **DNS** ] ページで、[**プレファレンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="bef6c-254">[**エキスパートインターフェイスを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="bef6c-255">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="bef6c-256">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="bef6c-257">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="bef6c-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bef6c-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="bef6c-258">**Host**</span></span>|<span data-ttu-id="bef6c-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bef6c-259">**TTL**</span></span>|<span data-ttu-id="bef6c-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="bef6c-260">**Type**</span></span>|<span data-ttu-id="bef6c-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="bef6c-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bef6c-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="bef6c-262">_sip._tls</span></span>|<span data-ttu-id="bef6c-263">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-263">600</span></span>|<span data-ttu-id="bef6c-264">SRV</span><span class="sxs-lookup"><span data-stu-id="bef6c-264">SRV</span></span>|<span data-ttu-id="bef6c-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bef6c-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="bef6c-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="bef6c-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="bef6c-267">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="bef6c-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="bef6c-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="bef6c-269">600</span><span class="sxs-lookup"><span data-stu-id="bef6c-269">600</span></span>|<span data-ttu-id="bef6c-270">SRV</span><span class="sxs-lookup"><span data-stu-id="bef6c-270">SRV</span></span>|<span data-ttu-id="bef6c-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bef6c-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="bef6c-272">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="bef6c-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="bef6c-273">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bef6c-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="bef6c-275">[ **Create Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="bef6c-277">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bef6c-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="bef6c-278">[ **ADD DNS record** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **create record** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="bef6c-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="bef6c-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bef6c-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
