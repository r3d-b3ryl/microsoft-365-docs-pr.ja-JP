---
title: Microsoft の Google ドメインで DNS レコードを作成する
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: ドメインを確認して、Microsoft の Google ドメインで電子メール、Lync、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 20a3ba9baefcdb26936d2d0a5fda7ed1b5db971e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629541"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="3044d-103">Microsoft の Google ドメインで DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="3044d-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="3044d-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3044d-105">使用している DNS ホスティング プロバイダーが Google Domains の場合は、この記事に記載された手順に従い、ドメインの確認を行って、メールや Lync などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="3044d-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="3044d-106">これらのレコードを Google ドメインで追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="3044d-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="3044d-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3044d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3044d-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3044d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3044d-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3044d-110">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「 [Microsoft でドメインまたは DNS レコードを追加した後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3044d-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3044d-111">Add a TXT record for verification</span></span>
<span data-ttu-id="3044d-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3044d-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3044d-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3044d-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="3044d-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="3044d-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3044d-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3044d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3044d-p104">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3044d-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="3044d-120">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="3044d-121">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="3044d-122">[**マイドメイン**] ページで、Microsoft と共に使用するドメインを見つけて、その横にある [**管理**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-122">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="3044d-123">左側のナビゲーションで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="3044d-124">[\* \* Custom resource records \* \*] セクションの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3044d-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3044d-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3044d-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3044d-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3044d-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3044d-127">**名前**</span><span class="sxs-lookup"><span data-stu-id="3044d-127">**Name**</span></span> <br/> |<span data-ttu-id="3044d-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="3044d-128">**Type**</span></span> <br/> |<span data-ttu-id="3044d-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3044d-129">**TTL**</span></span> <br/> |<span data-ttu-id="3044d-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="3044d-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3044d-131">TXT</span><span class="sxs-lookup"><span data-stu-id="3044d-131">TXT</span></span>  <br/> |<span data-ttu-id="3044d-132">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-132">1H</span></span>  <br/> |<span data-ttu-id="3044d-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3044d-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3044d-134">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="3044d-134">**Note:** This is an example.</span></span> <span data-ttu-id="3044d-135">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3044d-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3044d-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3044d-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="3044d-137">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="3044d-138">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="3044d-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3044d-139">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="3044d-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="3044d-140">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="3044d-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3044d-141">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3044d-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3044d-142">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3044d-143">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3044d-144">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3044d-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3044d-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3044d-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3044d-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3044d-147">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3044d-148">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="3044d-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3044d-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3044d-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3044d-p108">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3044d-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="3044d-153">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="3044d-154">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="3044d-155">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3044d-156">G Suite メール アカウントを持っている場合は、そのアカウントに関連付けられている MX レコードを最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3044d-156">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="3044d-157">G Suite MX レコードでは、Microsoft に必要な MX レコードを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="3044d-157">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="3044d-158">G Suite のレコードを削除しても、G Suite アカウントは削除されないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="3044d-158">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="3044d-159">G Suite の MX レコードを削除するには、次の手順のようにします。</span><span class="sxs-lookup"><span data-stu-id="3044d-159">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="3044d-160">[**統合レコード**] セクションの [ **G Suite** ] 領域で、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="3044d-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3044d-161">(You may have to scroll down.)</span></span>
    
    ![[代理レコード] セクションで、[削除] を選択します。](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="3044d-163">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-163">Select **Delete**.</span></span>
    
    ![[削除] を選択します。](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="3044d-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3044d-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3044d-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3044d-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3044d-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3044d-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3044d-168">**名前**</span><span class="sxs-lookup"><span data-stu-id="3044d-168">**Name**</span></span>|<span data-ttu-id="3044d-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="3044d-169">**Type**</span></span>|<span data-ttu-id="3044d-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3044d-170">**TTL**</span></span>|<span data-ttu-id="3044d-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="3044d-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3044d-172">MX</span><span class="sxs-lookup"><span data-stu-id="3044d-172">MX</span></span>  <br/> |<span data-ttu-id="3044d-173">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-173">1H</span></span>  <br/> |<span data-ttu-id="3044d-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3044d-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3044d-175">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3044d-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3044d-p110">**0** は MX 優先度の値です。 MX 値の先頭に追加して、値の残りの部分からスペースで区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="3044d-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="3044d-178">**注:**\<Microsoft アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="3044d-178">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="3044d-179">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3044d-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="3044d-180">優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="3044d-182">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-182">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="3044d-184">他のカスタム MX レコードがある場合は、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="3044d-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="3044d-185">MX レコードの行で [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-185">Select **Edit** in the MX record row.</span></span> 
    
    ![MX レコード行の [編集] を選択します。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="3044d-187">その他のカスタム MX レコードごとに、[**データ**] ボックスのエントリを選択し、キーボードの**delete**キーを押してそのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="3044d-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="3044d-188">各 MX レコードの [ **Data**] エントリの削除が終わるまで、この操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3044d-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="3044d-190">その他の MX レコードのそれぞれの**データ**入力を削除したら、[**保存**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3044d-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![[保存] を選択します。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3044d-192">Microsoft に必要な5つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3044d-192">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="3044d-193">開始するには、[Google Domains]https://domains.google.com/registrar)ページにアクセスして、サインインします。</span><span class="sxs-lookup"><span data-stu-id="3044d-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="3044d-194">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3044d-195">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3044d-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="3044d-196">[ **Custom resource records**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3044d-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="3044d-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3044d-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3044d-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3044d-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3044d-199">**名前**</span><span class="sxs-lookup"><span data-stu-id="3044d-199">**Name**</span></span>|<span data-ttu-id="3044d-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="3044d-200">**Type**</span></span>|<span data-ttu-id="3044d-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3044d-201">**TTL**</span></span>|<span data-ttu-id="3044d-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="3044d-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3044d-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3044d-203">autodiscover</span></span>  <br/> |<span data-ttu-id="3044d-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="3044d-204">CNAME</span></span>  <br/> |<span data-ttu-id="3044d-205">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-205">1H</span></span>  <br/> |<span data-ttu-id="3044d-206">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3044d-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3044d-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3044d-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3044d-208">sip</span><span class="sxs-lookup"><span data-stu-id="3044d-208">sip</span></span>  <br/> |<span data-ttu-id="3044d-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="3044d-209">CNAME</span></span>  <br/> |<span data-ttu-id="3044d-210">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-210">1H</span></span>  <br/> |<span data-ttu-id="3044d-211">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3044d-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3044d-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3044d-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3044d-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3044d-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3044d-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="3044d-214">CNAME</span></span>  <br/> |<span data-ttu-id="3044d-215">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-215">1H</span></span>  <br/> |<span data-ttu-id="3044d-216">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="3044d-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3044d-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3044d-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3044d-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3044d-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3044d-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="3044d-219">CNAME</span></span>  <br/> |<span data-ttu-id="3044d-220">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-220">1H</span></span>  <br/> |<span data-ttu-id="3044d-221">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="3044d-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3044d-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="3044d-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3044d-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3044d-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3044d-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="3044d-224">CNAME</span></span>  <br/> |<span data-ttu-id="3044d-225">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-225">1H</span></span>  <br/> |<span data-ttu-id="3044d-226">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3044d-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3044d-227">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3044d-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="3044d-229">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-229">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="3044d-231">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3044d-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="3044d-232">[ **Custom resource records** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="3044d-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="3044d-233">必要な CNAME レコードをすべて作成するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3044d-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3044d-234">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3044d-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3044d-235">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3044d-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3044d-236">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3044d-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3044d-237">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3044d-237">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3044d-238">代わりに、値のセットを含む1つの SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="3044d-238">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="3044d-239">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3044d-239">Need examples?</span></span> <span data-ttu-id="3044d-240">これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)確認します。</span><span class="sxs-lookup"><span data-stu-id="3044d-240">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="3044d-241">SPF レコードを確認するには、[SPF の検証ツール](../setup/domains-faq.md)を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3044d-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="3044d-p113">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3044d-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="3044d-245">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="3044d-246">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="3044d-247">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="3044d-248">[ **Custom resource records** ] セクションの [TXT record] 行で、[ **Edit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="3044d-p114">Google Domains では TXT レコードが 1 つのセットとして格納されており、このセットには複数のレコードを入れることができます。既に他の TXT レコードが 1 つ以上あるときは (たとえば、ドメインの検証に使用した TXT レコード)、新しい TXT レコードをそのレコード セットに追加する必要があります。追加の TXT レコードを別の行として入力しようとすると、「 **Duplicate record**」というエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="3044d-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT レコード行の [編集] を選択します。](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="3044d-253">**(+)** コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-253">Select the **(+)** control.</span></span> 
    
    ![プラスコントロールを選択する](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="3044d-255">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3044d-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="3044d-256">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="3044d-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="3044d-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="3044d-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="3044d-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3044d-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="3044d-259">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3044d-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="3044d-261">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-261">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3044d-263">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3044d-263">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3044d-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3044d-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3044d-p115">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3044d-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="3044d-268">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="3044d-269">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="3044d-270">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="3044d-271">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3044d-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="3044d-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3044d-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3044d-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="3044d-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="3044d-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3044d-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3044d-275">**名前**</span><span class="sxs-lookup"><span data-stu-id="3044d-275">**Name**</span></span>|<span data-ttu-id="3044d-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="3044d-276">**Type**</span></span>|<span data-ttu-id="3044d-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3044d-277">**TTL**</span></span>|<span data-ttu-id="3044d-278">**Data**</span><span class="sxs-lookup"><span data-stu-id="3044d-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3044d-279">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="3044d-279">_sip._tls</span></span>|<span data-ttu-id="3044d-280">SRV</span><span class="sxs-lookup"><span data-stu-id="3044d-280">SRV</span></span>|<span data-ttu-id="3044d-281">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-281">1H</span></span>|<span data-ttu-id="3044d-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3044d-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3044d-283">**この値は、ピリオド (.) で終了する必要があります。\*\*\*\*注:** このエントリをコピーして貼り付けることをお勧めします。この場合、すべてのスペースが正しい状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="3044d-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3044d-284">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="3044d-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3044d-285">SRV</span><span class="sxs-lookup"><span data-stu-id="3044d-285">SRV</span></span>|<span data-ttu-id="3044d-286">1H</span><span class="sxs-lookup"><span data-stu-id="3044d-286">1H</span></span>|<span data-ttu-id="3044d-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3044d-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3044d-288">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="3044d-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="3044d-289">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3044d-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="3044d-291">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3044d-291">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="3044d-293">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3044d-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="3044d-294">[ **Custom resource records** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="3044d-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="3044d-295">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="3044d-295">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="3044d-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="3044d-296">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="3044d-297">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3044d-297">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
