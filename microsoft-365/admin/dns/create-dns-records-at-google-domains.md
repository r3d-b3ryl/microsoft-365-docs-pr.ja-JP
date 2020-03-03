---
title: Google Domains で Office 365 用の DNS レコードを作成する
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: ドメインを確認して、Office 365 用の Google Domains で電子メール、Lync、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 5b72753dfdf44fa15cd0dffaa4baf61e843cf532
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349698"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="cc04e-103">Google Domains で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="cc04e-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="cc04e-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cc04e-105">使用している DNS ホスティング プロバイダーが Google Domains の場合は、この記事に記載された手順に従い、ドメインの確認を行って、メールや Lync などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="cc04e-106">これらのレコードを Google Domains で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="cc04e-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc04e-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cc04e-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cc04e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cc04e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cc04e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cc04e-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc04e-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cc04e-p104">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cc04e-120">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cc04e-121">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="cc04e-122">[**マイドメイン**] ページで、Office 365 で使用するドメインを見つけて、その横にある [**管理**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="cc04e-123">左側のナビゲーションで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="cc04e-124">[\* \* Custom resource records \* \*] セクションの新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cc04e-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cc04e-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc04e-127">**名前**</span><span class="sxs-lookup"><span data-stu-id="cc04e-127">**Name**</span></span> <br/> |<span data-ttu-id="cc04e-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc04e-128">**Type**</span></span> <br/> |<span data-ttu-id="cc04e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc04e-129">**TTL**</span></span> <br/> |<span data-ttu-id="cc04e-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="cc04e-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="cc04e-131">TXT</span><span class="sxs-lookup"><span data-stu-id="cc04e-131">TXT</span></span>  <br/> |<span data-ttu-id="cc04e-132">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-132">1H</span></span>  <br/> |<span data-ttu-id="cc04e-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cc04e-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cc04e-134">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="cc04e-134">**Note:** This is an example.</span></span> <span data-ttu-id="cc04e-135">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="cc04e-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cc04e-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="cc04e-137">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="cc04e-138">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cc04e-139">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="cc04e-140">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="cc04e-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cc04e-141">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cc04e-142">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cc04e-143">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cc04e-144">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cc04e-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="cc04e-148">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cc04e-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="cc04e-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cc04e-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cc04e-p108">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cc04e-153">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cc04e-154">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="cc04e-155">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cc04e-p109">G Suite メール アカウントを持っている場合は、そのアカウントに関連付けられている MX レコードを最初に削除する必要があります。G Suite の MX レコードがあると、Office 365 に必要な MX レコードなど、他の MX レコードを追加できません。G Suite のレコードを削除しても、G Suite アカウントは削除されないことにご注意ください。G Suite の MX レコードを削除するには、次の手順のようにします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="cc04e-160">[**統合レコード**] セクションの [ **G Suite** ] 領域で、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="cc04e-161">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-161">(You may have to scroll down.)</span></span>
    
    ![[代理レコード] セクションで、[削除] を選択します。](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="cc04e-163">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-163">Select **Delete**.</span></span>
    
    ![[削除] を選択します。](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="cc04e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cc04e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cc04e-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cc04e-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cc04e-168">**名前**</span><span class="sxs-lookup"><span data-stu-id="cc04e-168">**Name**</span></span>|<span data-ttu-id="cc04e-169">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc04e-169">**Type**</span></span>|<span data-ttu-id="cc04e-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc04e-170">**TTL**</span></span>|<span data-ttu-id="cc04e-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="cc04e-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cc04e-172">MX</span><span class="sxs-lookup"><span data-stu-id="cc04e-172">MX</span></span>  <br/> |<span data-ttu-id="cc04e-173">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-173">1H</span></span>  <br/> |<span data-ttu-id="cc04e-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cc04e-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cc04e-175">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cc04e-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cc04e-p110">**0** は MX 優先度の値です。 MX 値の先頭に追加して、値の残りの部分からスペースで区切ってください。  </span><span class="sxs-lookup"><span data-stu-id="cc04e-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cc04e-178">**注:** Office 365 アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="cc04e-179">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cc04e-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="cc04e-180">優先度の詳細については、「[MX 優先度とは何ですか?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="cc04e-182">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-182">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="cc04e-184">他のカスタム MX レコードがある場合は、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="cc04e-185">MX レコードの行で [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-185">Select **Edit** in the MX record row.</span></span> 
    
    ![MX レコード行の [編集] を選択します。](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="cc04e-187">その他のカスタム MX レコードごとに、[**データ**] ボックスのエントリを選択し、キーボードの**delete**キーを押してそのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="cc04e-188">各 MX レコードの [ **Data**] エントリの削除が終わるまで、この操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="cc04e-190">その他の MX レコードのそれぞれの**データ**入力を削除したら、[**保存**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![[保存] を選択します。](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="cc04e-192">Office 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="cc04e-193">開始するには、[Google Domains]https://domains.google.com/registrar)ページにアクセスして、サインインします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="cc04e-194">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cc04e-195">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="cc04e-196">[ **Custom resource records**] セクションにある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="cc04e-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cc04e-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cc04e-199">**名前**</span><span class="sxs-lookup"><span data-stu-id="cc04e-199">**Name**</span></span>|<span data-ttu-id="cc04e-200">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc04e-200">**Type**</span></span>|<span data-ttu-id="cc04e-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc04e-201">**TTL**</span></span>|<span data-ttu-id="cc04e-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="cc04e-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc04e-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cc04e-203">autodiscover</span></span>  <br/> |<span data-ttu-id="cc04e-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc04e-204">CNAME</span></span>  <br/> |<span data-ttu-id="cc04e-205">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-205">1H</span></span>  <br/> |<span data-ttu-id="cc04e-206">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cc04e-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cc04e-207">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cc04e-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cc04e-208">sip</span><span class="sxs-lookup"><span data-stu-id="cc04e-208">sip</span></span>  <br/> |<span data-ttu-id="cc04e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc04e-209">CNAME</span></span>  <br/> |<span data-ttu-id="cc04e-210">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-210">1H</span></span>  <br/> |<span data-ttu-id="cc04e-211">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cc04e-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cc04e-212">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cc04e-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cc04e-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cc04e-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cc04e-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc04e-214">CNAME</span></span>  <br/> |<span data-ttu-id="cc04e-215">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-215">1H</span></span>  <br/> |<span data-ttu-id="cc04e-216">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cc04e-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cc04e-217">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cc04e-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cc04e-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cc04e-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cc04e-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc04e-219">CNAME</span></span>  <br/> |<span data-ttu-id="cc04e-220">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-220">1H</span></span>  <br/> |<span data-ttu-id="cc04e-221">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="cc04e-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cc04e-222">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cc04e-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cc04e-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cc04e-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cc04e-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="cc04e-224">CNAME</span></span>  <br/> |<span data-ttu-id="cc04e-225">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-225">1H</span></span>  <br/> |<span data-ttu-id="cc04e-226">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="cc04e-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cc04e-227">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cc04e-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="cc04e-229">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-229">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="cc04e-231">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="cc04e-232">[ **Custom resource records** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="cc04e-233">必要な CNAME レコードをすべて作成するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cc04e-234">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cc04e-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc04e-235">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc04e-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cc04e-236">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cc04e-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cc04e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc04e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="cc04e-238">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="cc04e-239">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-239">Need examples?</span></span> <span data-ttu-id="cc04e-240">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="cc04e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="cc04e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="cc04e-p113">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="cc04e-245">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="cc04e-246">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="cc04e-247">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="cc04e-248">[ **Custom resource records** ] セクションの [TXT record] 行で、[ **Edit**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="cc04e-p114">Google Domains では TXT レコードが 1 つのセットとして格納されており、このセットには複数のレコードを入れることができます。既に他の TXT レコードが 1 つ以上あるときは (たとえば、ドメインの検証に使用した TXT レコード)、新しい TXT レコードをそのレコード セットに追加する必要があります。追加の TXT レコードを別の行として入力しようとすると、「 **Duplicate record**」というエラー メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![TXT レコード行の [編集] を選択します。](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="cc04e-253">**(+)** コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-253">Select the **(+)** control.</span></span> 
    
    ![プラスコントロールを選択する](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="cc04e-255">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cc04e-256">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cc04e-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cc04e-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="cc04e-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="cc04e-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cc04e-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="cc04e-259">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="cc04e-261">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-261">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="cc04e-263">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cc04e-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="cc04e-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cc04e-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cc04e-p115">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="cc04e-268">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="cc04e-269">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="cc04e-270">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="cc04e-271">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="cc04e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cc04e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cc04e-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="cc04e-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="cc04e-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cc04e-275">**名前**</span><span class="sxs-lookup"><span data-stu-id="cc04e-275">**Name**</span></span>|<span data-ttu-id="cc04e-276">**Type**</span><span class="sxs-lookup"><span data-stu-id="cc04e-276">**Type**</span></span>|<span data-ttu-id="cc04e-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cc04e-277">**TTL**</span></span>|<span data-ttu-id="cc04e-278">**Data**</span><span class="sxs-lookup"><span data-stu-id="cc04e-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cc04e-279">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cc04e-279">_sip._tls</span></span>|<span data-ttu-id="cc04e-280">SRV</span><span class="sxs-lookup"><span data-stu-id="cc04e-280">SRV</span></span>|<span data-ttu-id="cc04e-281">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-281">1H</span></span>|<span data-ttu-id="cc04e-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cc04e-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="cc04e-283">**この値は、ピリオド (.) で終了する必要があります。\*\*\*\*注:** このエントリをコピーして貼り付けることをお勧めします。この場合、すべてのスペースが正しい状態に保たれます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="cc04e-284">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cc04e-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="cc04e-285">SRV</span><span class="sxs-lookup"><span data-stu-id="cc04e-285">SRV</span></span>|<span data-ttu-id="cc04e-286">1H</span><span class="sxs-lookup"><span data-stu-id="cc04e-286">1H</span></span>|<span data-ttu-id="cc04e-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cc04e-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="cc04e-288">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cc04e-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="cc04e-289">スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc04e-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![[Custom resource records] セクションに値を入力するか貼り付けます。](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="cc04e-291">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-291">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="cc04e-293">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc04e-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cc04e-294">[ **Custom resource records** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cc04e-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cc04e-p118">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc04e-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
