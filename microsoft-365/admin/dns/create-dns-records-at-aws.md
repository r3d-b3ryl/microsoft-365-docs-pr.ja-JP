---
title: Amazon Web Services (AWS) for Office 365 で DNS レコードを作成する
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Office 365 の Amazon Web Services (AWS) で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: baba7bb7275303604d241166f4dc1d2af77b3f17
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351478"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="ae8da-103">Amazon Web Services (AWS) for Office 365 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="ae8da-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="ae8da-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ae8da-105">DNS ホスティングプロバイダーが AWS の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype Online for Business などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="ae8da-106">これらのレコードを AWS で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="ae8da-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae8da-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ae8da-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="ae8da-111">Add a TXT record for verification</span></span>
<span data-ttu-id="ae8da-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ae8da-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ae8da-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae8da-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ae8da-117">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="ae8da-118">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ae8da-119">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ae8da-120">[\* \* Hosted Zones \* \*] ページの [ **Domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ae8da-121">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ae8da-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ae8da-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae8da-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="ae8da-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ae8da-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="ae8da-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae8da-126">**名前**</span><span class="sxs-lookup"><span data-stu-id="ae8da-126">**Name**</span></span> <br/> |<span data-ttu-id="ae8da-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae8da-127">**Type**</span></span> <br/> |<span data-ttu-id="ae8da-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ae8da-128">**Alias**</span></span> <br/> |<span data-ttu-id="ae8da-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="ae8da-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="ae8da-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae8da-130">**Value**</span></span> <br/> |<span data-ttu-id="ae8da-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="ae8da-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="ae8da-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="ae8da-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ae8da-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="ae8da-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="ae8da-134">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-134">No</span></span>  <br/> |<span data-ttu-id="ae8da-135">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-135">300</span></span>  <br/> |<span data-ttu-id="ae8da-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ae8da-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="ae8da-137">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="ae8da-137">**Note:** This is an example.</span></span> <span data-ttu-id="ae8da-138">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="ae8da-139">確認する方法</span><span class="sxs-lookup"><span data-stu-id="ae8da-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ae8da-140">単純</span><span class="sxs-lookup"><span data-stu-id="ae8da-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="ae8da-141">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="ae8da-142">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ae8da-143">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ae8da-144">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="ae8da-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ae8da-145">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ae8da-146">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ae8da-147">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ae8da-148">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae8da-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="ae8da-152">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="ae8da-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="ae8da-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ae8da-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ae8da-p108">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ae8da-156">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ae8da-157">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ae8da-158">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ae8da-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ae8da-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ae8da-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="ae8da-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ae8da-161">**名前**</span><span class="sxs-lookup"><span data-stu-id="ae8da-161">**Name**</span></span>|<span data-ttu-id="ae8da-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae8da-162">**Type**</span></span>|<span data-ttu-id="ae8da-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ae8da-163">**Alias**</span></span>|<span data-ttu-id="ae8da-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="ae8da-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="ae8da-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae8da-165">**Value**</span></span>|<span data-ttu-id="ae8da-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="ae8da-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae8da-167">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="ae8da-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="ae8da-168">MX - Mail Exchange</span><span class="sxs-lookup"><span data-stu-id="ae8da-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="ae8da-169">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-169">No</span></span>  <br/> |<span data-ttu-id="ae8da-170">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-170">300</span></span>  <br/> |<span data-ttu-id="ae8da-171">0  *\<ドメイン キー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ae8da-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ae8da-p109">0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  </span><span class="sxs-lookup"><span data-stu-id="ae8da-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="ae8da-174">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="ae8da-175">**注:** Office 365 アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="ae8da-176">確認する方法</span><span class="sxs-lookup"><span data-stu-id="ae8da-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ae8da-177">単純</span><span class="sxs-lookup"><span data-stu-id="ae8da-177">Simple</span></span>  <br/> |
       
    ![AWS-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="ae8da-179">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="ae8da-181">他の MX レコードがある場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae8da-182">AWS は、複数のレコードが含まれる可能性のあるセットとして MX レコードを格納します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="ae8da-183">[**レコードセットを削除**する] を選択し**ない**でください。これにより、追加した MX レコードを含むすべての MX レコードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="ae8da-184">代わりに、次の手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="ae8da-185">最初に、MX レコードセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="ae8da-187">次に、[ **Edit Record Set**] 領域で、[ **Value**] ボックスのエントリを選んで、キーボードの **Delete** キーを押し、使われなくなった MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="ae8da-189">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="ae8da-191">Office 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="ae8da-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ae8da-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ae8da-p112">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ae8da-195">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ae8da-196">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ae8da-197">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ae8da-198">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="ae8da-199">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ae8da-200">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ae8da-201">**名前**</span><span class="sxs-lookup"><span data-stu-id="ae8da-201">**Name**</span></span>|<span data-ttu-id="ae8da-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae8da-202">**Type**</span></span>|<span data-ttu-id="ae8da-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ae8da-203">**Alias**</span></span>|<span data-ttu-id="ae8da-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="ae8da-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="ae8da-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae8da-205">**Value**</span></span>|<span data-ttu-id="ae8da-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="ae8da-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae8da-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ae8da-207">autodiscover</span></span>  <br/> |<span data-ttu-id="ae8da-208">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="ae8da-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ae8da-209">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-209">No</span></span>  <br/> |<span data-ttu-id="ae8da-210">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-210">300</span></span>  <br/> |<span data-ttu-id="ae8da-211">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ae8da-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="ae8da-212">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ae8da-213">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="ae8da-214">sip</span><span class="sxs-lookup"><span data-stu-id="ae8da-214">sip</span></span>  <br/> |<span data-ttu-id="ae8da-215">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="ae8da-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ae8da-216">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-216">No</span></span>  <br/> |<span data-ttu-id="ae8da-217">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-217">300</span></span>  <br/> |<span data-ttu-id="ae8da-218">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ae8da-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ae8da-219">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ae8da-220">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="ae8da-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ae8da-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ae8da-222">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="ae8da-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ae8da-223">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-223">No</span></span>  <br/> |<span data-ttu-id="ae8da-224">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-224">300</span></span>  <br/> |<span data-ttu-id="ae8da-225">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="ae8da-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ae8da-226">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ae8da-227">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="ae8da-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ae8da-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ae8da-229">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="ae8da-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ae8da-230">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-230">No</span></span>  <br/> |<span data-ttu-id="ae8da-231">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-231">300</span></span>  <br/> |<span data-ttu-id="ae8da-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="ae8da-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="ae8da-233">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ae8da-234">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="ae8da-235">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="ae8da-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ae8da-236">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="ae8da-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="ae8da-237">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-237">No</span></span>  <br/> |<span data-ttu-id="ae8da-238">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-238">300</span></span>  <br/> |<span data-ttu-id="ae8da-239">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ae8da-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="ae8da-240">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ae8da-241">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-241">Simple</span></span>  <br/> |
   
    ![AWS-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="ae8da-243">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="ae8da-245">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="ae8da-246">[ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="ae8da-247">この手順を繰り返し、5つの CNAME レコードをすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ae8da-248">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="ae8da-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ae8da-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ae8da-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae8da-250">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae8da-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ae8da-251">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ae8da-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ae8da-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae8da-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="ae8da-253">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ae8da-254">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-254">Need examples?</span></span> <span data-ttu-id="ae8da-255">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ae8da-256">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="ae8da-257">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="ae8da-258">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ae8da-259">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ae8da-260">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ae8da-261">**TXT**レコードセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="ae8da-p115">[ **レコード セットの編集**] 領域で、既存のレコード用の [ **Value:**] ボックス内にある現在のエントリの最後で、キーボードの Enter キーを押して新規の行を作成します。次に、その行 (既存の値の下) に、次のテーブルの値を入力、またはコピーして貼り付けます (表の下のイラストに例があります)。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="ae8da-265">**Value:**</span><span class="sxs-lookup"><span data-stu-id="ae8da-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="ae8da-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ae8da-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ae8da-p116">(画面の手順で必要になる引用符は自動的に補完されます。手動で入力する必要はありません。)  </span><span class="sxs-lookup"><span data-stu-id="ae8da-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="ae8da-269">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="ae8da-271">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="ae8da-273">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="ae8da-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="ae8da-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ae8da-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ae8da-p117">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ae8da-277">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="ae8da-278">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="ae8da-279">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="ae8da-280">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="ae8da-281">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ae8da-282">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="ae8da-283">**名前**</span><span class="sxs-lookup"><span data-stu-id="ae8da-283">**Name**</span></span>|<span data-ttu-id="ae8da-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="ae8da-284">**Type**</span></span>|<span data-ttu-id="ae8da-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="ae8da-285">**Alias**</span></span>|<span data-ttu-id="ae8da-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="ae8da-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="ae8da-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="ae8da-287">**Value**</span></span>|<span data-ttu-id="ae8da-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="ae8da-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae8da-289">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="ae8da-289">_sip._tls</span></span>|<span data-ttu-id="ae8da-290">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="ae8da-290">SRV - Service locator</span></span>|<span data-ttu-id="ae8da-291">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-291">No</span></span>|<span data-ttu-id="ae8da-292">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-292">300</span></span>|<span data-ttu-id="ae8da-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ae8da-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="ae8da-294">**この値は、ピリオド (.) で終了する必要があります。**></span><span class="sxs-lookup"><span data-stu-id="ae8da-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="ae8da-295">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="ae8da-296">Simple</span><span class="sxs-lookup"><span data-stu-id="ae8da-296">Simple</span></span>|
    |<span data-ttu-id="ae8da-297">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="ae8da-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ae8da-298">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="ae8da-298">SRV - Service locator</span></span>|<span data-ttu-id="ae8da-299">No</span><span class="sxs-lookup"><span data-stu-id="ae8da-299">No</span></span>|<span data-ttu-id="ae8da-300">300</span><span class="sxs-lookup"><span data-stu-id="ae8da-300">300</span></span>|<span data-ttu-id="ae8da-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ae8da-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="ae8da-302">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="ae8da-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="ae8da-303">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae8da-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="ae8da-304">単純</span><span class="sxs-lookup"><span data-stu-id="ae8da-304">Simple</span></span>|
   
    ![AWS-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="ae8da-306">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="ae8da-308">他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae8da-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="ae8da-309">[ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="ae8da-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ae8da-p120">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae8da-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
