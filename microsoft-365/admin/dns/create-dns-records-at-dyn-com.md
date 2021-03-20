---
title: Microsoft の DNS レコード Dyn.com 作成する
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法については、Microsoft Dyn.com 説明します。
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910332"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="3a5ba-103">Microsoft の DNS レコード Dyn.com 作成する</span><span class="sxs-lookup"><span data-stu-id="3a5ba-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="3a5ba-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3a5ba-105">使用している DNS ホスティング プロバイダーが Dyn.com の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="3a5ba-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3a5ba-109">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a5ba-109">Add a TXT record for verification</span></span>
<span data-ttu-id="3a5ba-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5ba-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="3a5ba-p102">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3a5ba-114">[ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3a5ba-115">ドメインの **DNS ページ** で、[基本設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3a5ba-116">[エキスパート **インターフェイスの有効化] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3a5ba-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3a5ba-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a5ba-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-119">**Host**</span></span>|<span data-ttu-id="3a5ba-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-120">**TTL**</span></span>|<span data-ttu-id="3a5ba-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-121">**Type**</span></span>|<span data-ttu-id="3a5ba-122">**データ**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a5ba-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3a5ba-124">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-124">600</span></span>  <br/> |<span data-ttu-id="3a5ba-125">TXT</span><span class="sxs-lookup"><span data-stu-id="3a5ba-125">TXT</span></span>  <br/> |<span data-ttu-id="3a5ba-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3a5ba-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3a5ba-127">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-127">**Note:** This is an example.</span></span> <span data-ttu-id="3a5ba-128">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="3a5ba-129">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3a5ba-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="3a5ba-131">[レコード **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="3a5ba-133">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3a5ba-134">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3a5ba-135">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3a5ba-136">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3a5ba-137">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3a5ba-138">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3a5ba-139">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3a5ba-p104">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3a5ba-143">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="3a5ba-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3a5ba-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5ba-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3a5ba-p105">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3a5ba-148">[ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3a5ba-149">ドメインの DNS ページで、[基本設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3a5ba-150">[エキスパート **インターフェイスの有効化] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3a5ba-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3a5ba-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a5ba-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-153">**Host**</span></span>|<span data-ttu-id="3a5ba-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-154">**TTL**</span></span>|<span data-ttu-id="3a5ba-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-155">**Type**</span></span>|<span data-ttu-id="3a5ba-156">**データ**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a5ba-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3a5ba-158">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-158">600</span></span>  <br/> |<span data-ttu-id="3a5ba-159">MX</span><span class="sxs-lookup"><span data-stu-id="3a5ba-159">MX</span></span>  <br/> |<span data-ttu-id="3a5ba-160">10  *\<domain-key\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3a5ba-161">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3a5ba-p106">**10** は MX 優先度の値です。 MX 値の先頭に追加して、スペースで値の残りの部分から区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="3a5ba-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3a5ba-164">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3a5ba-165">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3a5ba-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="3a5ba-166">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-166">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="3a5ba-168">[レコード **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="3a5ba-170">他の MX レコードがある場合は、[ **DELETE**] 列で各レコードのチェック ボックスをオンにして削除します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="3a5ba-172">**[Apply Changes]\(変更の適用\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3a5ba-174">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a5ba-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3a5ba-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5ba-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3a5ba-p108">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3a5ba-179">[ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3a5ba-180">ドメインの **DNS ページ** で、[基本設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3a5ba-181">[エキスパート **インターフェイスの有効化] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3a5ba-182">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3a5ba-183">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3a5ba-184">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a5ba-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-185">**Host**</span></span>|<span data-ttu-id="3a5ba-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-186">**TTL**</span></span>|<span data-ttu-id="3a5ba-187">**Type**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-187">**Type**</span></span>|<span data-ttu-id="3a5ba-188">**データ**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a5ba-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3a5ba-189">autodiscover</span></span>  <br/> |<span data-ttu-id="3a5ba-190">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-190">600</span></span>  <br/> |<span data-ttu-id="3a5ba-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="3a5ba-191">CNAME</span></span>  <br/> |<span data-ttu-id="3a5ba-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3a5ba-193">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3a5ba-194">sip</span><span class="sxs-lookup"><span data-stu-id="3a5ba-194">sip</span></span>  <br/> |<span data-ttu-id="3a5ba-195">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-195">600</span></span>  <br/> |<span data-ttu-id="3a5ba-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="3a5ba-196">CNAME</span></span>  <br/> |<span data-ttu-id="3a5ba-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3a5ba-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3a5ba-198">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3a5ba-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3a5ba-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3a5ba-200">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-200">600</span></span>  <br/> |<span data-ttu-id="3a5ba-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="3a5ba-201">CNAME</span></span>  <br/> |<span data-ttu-id="3a5ba-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3a5ba-203">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3a5ba-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3a5ba-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3a5ba-205">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-205">600</span></span>  <br/> |<span data-ttu-id="3a5ba-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="3a5ba-206">CNAME</span></span>  <br/> |<span data-ttu-id="3a5ba-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3a5ba-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3a5ba-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3a5ba-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3a5ba-210">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-210">600</span></span>  <br/> |<span data-ttu-id="3a5ba-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="3a5ba-211">CNAME</span></span>  <br/> |<span data-ttu-id="3a5ba-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3a5ba-213">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="3a5ba-215">[レコード **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="3a5ba-217">残りの 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="3a5ba-218">[DNS **レコードの追加**] セクションで、テーブルの次の行の値を使用してレコードを作成し、もう一度 [レコードの作成] を選択してそのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="3a5ba-219">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3a5ba-220">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a5ba-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3a5ba-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5ba-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a5ba-222">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3a5ba-223">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3a5ba-224">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3a5ba-225">代わりに、必要な Microsoft 値を現在のレコードに追加して、両方の値セットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="3a5ba-p110">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3a5ba-229">[ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3a5ba-230">ドメインの **DNS ページ** で、[基本設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3a5ba-231">[エキスパート **インターフェイスの有効化] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3a5ba-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3a5ba-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a5ba-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-234">**Host**</span></span>|<span data-ttu-id="3a5ba-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-235">**TTL**</span></span>|<span data-ttu-id="3a5ba-236">**Type**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-236">**Type**</span></span>|<span data-ttu-id="3a5ba-237">**データ**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a5ba-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="3a5ba-239">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-239">600</span></span>  <br/> |<span data-ttu-id="3a5ba-240">TXT</span><span class="sxs-lookup"><span data-stu-id="3a5ba-240">TXT</span></span>  <br/> |<span data-ttu-id="3a5ba-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3a5ba-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3a5ba-242">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="3a5ba-244">[レコード **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3a5ba-246">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3a5ba-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3a5ba-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3a5ba-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3a5ba-248">まず、[このリンク](https://account.dyn.com/dns/)を使って Dyn.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="3a5ba-249">最初にログインするように求めるメッセージが表示されます</span><span class="sxs-lookup"><span data-stu-id="3a5ba-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="3a5ba-251">[ゾーン **レベル サービス] ページ** で、編集するドメインの **[Dyn Standard DNS Service]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3a5ba-252">ドメインの **DNS ページ** で、[基本設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="3a5ba-253">[エキスパート **インターフェイスの有効化] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="3a5ba-254">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="3a5ba-255">[ **Add DNS Record**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="3a5ba-256">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="3a5ba-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3a5ba-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-257">**Host**</span></span>|<span data-ttu-id="3a5ba-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-258">**TTL**</span></span>|<span data-ttu-id="3a5ba-259">**Type**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-259">**Type**</span></span>|<span data-ttu-id="3a5ba-260">**データ**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3a5ba-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3a5ba-261">_sip._tls</span></span>|<span data-ttu-id="3a5ba-262">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-262">600</span></span>|<span data-ttu-id="3a5ba-263">SRV</span><span class="sxs-lookup"><span data-stu-id="3a5ba-263">SRV</span></span>|<span data-ttu-id="3a5ba-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3a5ba-265">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="3a5ba-266">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3a5ba-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3a5ba-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3a5ba-268">600</span><span class="sxs-lookup"><span data-stu-id="3a5ba-268">600</span></span>|<span data-ttu-id="3a5ba-269">SRV</span><span class="sxs-lookup"><span data-stu-id="3a5ba-269">SRV</span></span>|<span data-ttu-id="3a5ba-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3a5ba-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3a5ba-271">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3a5ba-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3a5ba-272">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="3a5ba-274">[レコード **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="3a5ba-276">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3a5ba-277">[DNS **レコードの追加**] セクションで、テーブルの 2 行目の値を使用してレコードを作成し、もう一度 [レコードの作成] を選択して、そのレコードを完了します。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="3a5ba-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a5ba-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
