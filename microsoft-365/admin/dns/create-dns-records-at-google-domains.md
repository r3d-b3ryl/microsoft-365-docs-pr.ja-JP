---
title: Google Domains で Microsoft 用の DNS レコードを作成する
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: ドメインを確認し、メール、Lync、その他のサービスに対する DNS レコードを Microsoft 用の Google ドメインでセットアップする方法について説明します。
ms.openlocfilehash: 417fe89bd408eba4d3b14ecb3e38af6beed196cf
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646093"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="af0f7-103">Google Domains で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="af0f7-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="af0f7-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="af0f7-105">使用している DNS ホスティング プロバイダーが Google Domains の場合は、この記事に記載された手順に従い、ドメインの確認を行って、メールや Lync などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="af0f7-106">これらのレコードを Google Domains で追加すると、使用しているドメインが、Microsoft のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="af0f7-107">通常は DNS の変更が反映されるまで約 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="af0f7-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="af0f7-108">ただし、インターネットの DNS システム全体を更新するための変更を行った場合、それ以上の時間がかかる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="af0f7-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="af0f7-109">DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Microsoft でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="af0f7-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="af0f7-110">Add a TXT record for verification</span></span>
<span data-ttu-id="af0f7-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="af0f7-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="af0f7-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af0f7-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="af0f7-p104">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="af0f7-119">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="af0f7-120">ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="af0f7-121">[**My Domains**] ページで、Microsoft で使用するドメインを見つけ、その横にある [**管理**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="af0f7-122">左側のナビゲーションで、[**DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="af0f7-123">[**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="af0f7-124">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="af0f7-125">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af0f7-126">**名前**</span><span class="sxs-lookup"><span data-stu-id="af0f7-126">**Name**</span></span> <br/> |<span data-ttu-id="af0f7-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="af0f7-127">**Type**</span></span> <br/> |<span data-ttu-id="af0f7-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="af0f7-128">**TTL**</span></span> <br/> |<span data-ttu-id="af0f7-129">**データ**</span><span class="sxs-lookup"><span data-stu-id="af0f7-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="af0f7-130">TXT</span><span class="sxs-lookup"><span data-stu-id="af0f7-130">TXT</span></span>  <br/> |<span data-ttu-id="af0f7-131">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-131">1H</span></span>  <br/> |<span data-ttu-id="af0f7-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="af0f7-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="af0f7-133">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="af0f7-133">**Note:** This is an example.</span></span> <span data-ttu-id="af0f7-134">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="af0f7-135">確認する方法</span><span class="sxs-lookup"><span data-stu-id="af0f7-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="af0f7-136">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="af0f7-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="af0f7-138">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="af0f7-139">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="af0f7-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="af0f7-140">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="af0f7-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="af0f7-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="af0f7-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af0f7-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="af0f7-147">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="af0f7-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="af0f7-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="af0f7-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="af0f7-p108">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="af0f7-152">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="af0f7-153">ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="af0f7-154">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af0f7-155">G Suite メール アカウントを持っている場合は、そのアカウントに関連付けられている MX レコードを最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af0f7-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="af0f7-156">G Suite の MX レコードがあると、Microsoft に必要な MX レコードなど、他の MX レコードを追加できません。</span><span class="sxs-lookup"><span data-stu-id="af0f7-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="af0f7-157">G Suite のレコードを削除しても、G Suite アカウントは削除されないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="af0f7-158">G Suite の MX レコードを削除するには、次の手順のようにします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="af0f7-159">最初に、[**統合的な記録**] セクションの [**G Suite**] 領域で、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="af0f7-160">(下へスクロールすることが必要な場合があります)。</span><span class="sxs-lookup"><span data-stu-id="af0f7-160">(You may have to scroll down.)</span></span>
    
    ![[統合的な記録] セクションで [削除] をクリックする](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="af0f7-162">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-162">Select **Delete**.</span></span>
    
    ![[削除] を選択する](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="af0f7-164">[**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="af0f7-165">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="af0f7-166">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="af0f7-167">**名前**</span><span class="sxs-lookup"><span data-stu-id="af0f7-167">**Name**</span></span>|<span data-ttu-id="af0f7-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="af0f7-168">**Type**</span></span>|<span data-ttu-id="af0f7-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="af0f7-169">**TTL**</span></span>|<span data-ttu-id="af0f7-170">**データ**</span><span class="sxs-lookup"><span data-stu-id="af0f7-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="af0f7-171">MX</span><span class="sxs-lookup"><span data-stu-id="af0f7-171">MX</span></span>  <br/> |<span data-ttu-id="af0f7-172">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-172">1H</span></span>  <br/> |<span data-ttu-id="af0f7-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="af0f7-174">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="af0f7-p110">**0** は MX 優先度の値です。 MX 値の先頭に追加して、値の残りの部分からスペースで区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="af0f7-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="af0f7-177">**注: Microsoft アカウントから**取得\<*domain-key*\> します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="af0f7-178">確認する方法</span><span class="sxs-lookup"><span data-stu-id="af0f7-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="af0f7-179">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="af0f7-181">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-181">Select **Add**.</span></span>
    
    ![[追加] を選択する](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="af0f7-183">他のカスタム MX レコードがある場合は、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="af0f7-184">MX レコード行の **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-184">Select **Edit** in the MX record row.</span></span> 
    
    ![MX レコード行の [編集] を選択します。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="af0f7-186">他のカスタム MX レコードごとに、[**データ**] ボックスのエントリを選び、キーボードの **Delete** キーを押して、そのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="af0f7-187">各 MX レコードの [**Data**] エントリの削除が終わるまで、この操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="af0f7-189">他の各 MX レコードの [**データ**] エントリを削除したら、[**保存**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![[保存] を選択します。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="af0f7-191">Microsoft に必要な 5 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="af0f7-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="af0f7-192">はじめに、[Google Domains ページ] (https://domains.google.com/registrar)) にアクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="af0f7-193">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="af0f7-194">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="af0f7-195">[**Custom resource records**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="af0f7-196">(下へスクロールすることが必要な場合があります)。</span><span class="sxs-lookup"><span data-stu-id="af0f7-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="af0f7-197">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="af0f7-198">**名前**</span><span class="sxs-lookup"><span data-stu-id="af0f7-198">**Name**</span></span>|<span data-ttu-id="af0f7-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="af0f7-199">**Type**</span></span>|<span data-ttu-id="af0f7-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="af0f7-200">**TTL**</span></span>|<span data-ttu-id="af0f7-201">**データ**</span><span class="sxs-lookup"><span data-stu-id="af0f7-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af0f7-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="af0f7-202">autodiscover</span></span>  <br/> |<span data-ttu-id="af0f7-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="af0f7-203">CNAME</span></span>  <br/> |<span data-ttu-id="af0f7-204">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-204">1H</span></span>  <br/> |<span data-ttu-id="af0f7-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="af0f7-206">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af0f7-207">sip</span><span class="sxs-lookup"><span data-stu-id="af0f7-207">sip</span></span>  <br/> |<span data-ttu-id="af0f7-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="af0f7-208">CNAME</span></span>  <br/> |<span data-ttu-id="af0f7-209">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-209">1H</span></span>  <br/> |<span data-ttu-id="af0f7-210">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="af0f7-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af0f7-211">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af0f7-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="af0f7-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="af0f7-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="af0f7-213">CNAME</span></span>  <br/> |<span data-ttu-id="af0f7-214">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-214">1H</span></span>  <br/> |<span data-ttu-id="af0f7-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="af0f7-216">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af0f7-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="af0f7-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="af0f7-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="af0f7-218">CNAME</span></span>  <br/> |<span data-ttu-id="af0f7-219">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-219">1H</span></span>  <br/> |<span data-ttu-id="af0f7-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="af0f7-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="af0f7-221">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="af0f7-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="af0f7-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="af0f7-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="af0f7-223">CNAME</span></span>  <br/> |<span data-ttu-id="af0f7-224">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-224">1H</span></span>  <br/> |<span data-ttu-id="af0f7-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="af0f7-226">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="af0f7-228">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-228">Select **Add**.</span></span>
    
    ![[追加] を選択する](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="af0f7-230">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="af0f7-231">[**カスタム リソース レコード**] セクションで、表の次の行の値を使用してレコードを作成して、もう一度 [**追加**] を選んでレコードの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="af0f7-232">必要な CNAME レコードをすべて作成するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="af0f7-233">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="af0f7-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af0f7-234">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="af0f7-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="af0f7-235">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="af0f7-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="af0f7-236">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="af0f7-237">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="af0f7-238">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-238">Need examples?</span></span> <span data-ttu-id="af0f7-239">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="af0f7-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="af0f7-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="af0f7-p113">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="af0f7-244">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="af0f7-245">ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="af0f7-246">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="af0f7-247">[**カスタム リソース レコード**] セクションの TXT レコードの行の [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="af0f7-p114">Google Domains では TXT レコードが 1 つのセットとして格納されており、このセットには複数のレコードを入れることができます。既に他の TXT レコードが 1 つ以上あるときは (たとえば、ドメインの検証に使用した TXT レコード)、新しい TXT レコードをそのレコード セットに追加する必要があります。追加の TXT レコードを別の行として入力しようとすると、「**Duplicate record**」というエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT レコード行の [編集] を選択します。](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="af0f7-252">[**+**] コントロールを選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-252">Select the **(+)** control.</span></span> 
    
    ![プラス コントロールを選択します。](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="af0f7-254">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="af0f7-255">(下へスクロールすることが必要な場合があります)。</span><span class="sxs-lookup"><span data-stu-id="af0f7-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="af0f7-256">**データ**</span><span class="sxs-lookup"><span data-stu-id="af0f7-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="af0f7-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="af0f7-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="af0f7-258">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="af0f7-260">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-260">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="af0f7-262">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="af0f7-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="af0f7-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="af0f7-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="af0f7-p115">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="af0f7-267">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="af0f7-268">ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="af0f7-269">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="af0f7-270">最初の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="af0f7-271">[**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="af0f7-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="af0f7-272">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="af0f7-273">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="af0f7-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="af0f7-274">**名前**</span><span class="sxs-lookup"><span data-stu-id="af0f7-274">**Name**</span></span>|<span data-ttu-id="af0f7-275">**Type**</span><span class="sxs-lookup"><span data-stu-id="af0f7-275">**Type**</span></span>|<span data-ttu-id="af0f7-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="af0f7-276">**TTL**</span></span>|<span data-ttu-id="af0f7-277">**データ**</span><span class="sxs-lookup"><span data-stu-id="af0f7-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="af0f7-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="af0f7-278">_sip._tls</span></span>|<span data-ttu-id="af0f7-279">SRV</span><span class="sxs-lookup"><span data-stu-id="af0f7-279">SRV</span></span>|<span data-ttu-id="af0f7-280">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-280">1H</span></span>|<span data-ttu-id="af0f7-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="af0f7-282">**この値は、末尾がピリオド (.) でなければなりません** **注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="af0f7-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="af0f7-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="af0f7-284">SRV</span><span class="sxs-lookup"><span data-stu-id="af0f7-284">SRV</span></span>|<span data-ttu-id="af0f7-285">1H</span><span class="sxs-lookup"><span data-stu-id="af0f7-285">1H</span></span>|<span data-ttu-id="af0f7-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="af0f7-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="af0f7-287">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="af0f7-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="af0f7-288">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af0f7-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![[カスタム リソース レコード] セクションに値を入力するか貼り付けます](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="af0f7-290">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-290">Select **Add**.</span></span>
    
    ![[追加] を選択する](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="af0f7-292">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="af0f7-293">[**カスタムカスタム リソース レコード**] セクションで、表の 2 行目の値を使用してレコードを作成して、もう一度 [**追加**] を選んでレコードの作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="af0f7-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="af0f7-p118">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af0f7-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
