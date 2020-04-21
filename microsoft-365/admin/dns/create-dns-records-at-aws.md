---
title: Microsoft の Amazon Web サービス (AWS) で DNS レコードを作成する
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: ドメインを確認し、電子メール、Skype for Business Online、および Amazon Web Services (AWS) for Microsoft のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 086a5d7210d2c722aeda701dc62a699ca0eaec87
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629733"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="d1b6c-103">Microsoft の Amazon Web サービス (AWS) で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="d1b6c-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="d1b6c-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d1b6c-105">DNS ホスティングプロバイダーが AWS の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype Online for Business などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="d1b6c-106">これらのレコードを AWS で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d1b6c-107">Microsfot を使用した web サイトのホストと DNS の詳細については、「 [Microsoft でパブリック web サイトを使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1b6c-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1b6c-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1b6c-110">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d1b6c-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d1b6c-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d1b6c-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d1b6c-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d1b6c-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d1b6c-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1b6c-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d1b6c-117">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d1b6c-118">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d1b6c-119">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d1b6c-120">[\* \* Hosted Zones \* \*] ページの [ **Domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d1b6c-121">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d1b6c-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d1b6c-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d1b6c-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d1b6c-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1b6c-126">**名前**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-126">**Name**</span></span> <br/> |<span data-ttu-id="d1b6c-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-127">**Type**</span></span> <br/> |<span data-ttu-id="d1b6c-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-128">**Alias**</span></span> <br/> |<span data-ttu-id="d1b6c-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="d1b6c-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-130">**Value**</span></span> <br/> |<span data-ttu-id="d1b6c-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="d1b6c-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d1b6c-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d1b6c-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="d1b6c-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="d1b6c-134">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-134">No</span></span>  <br/> |<span data-ttu-id="d1b6c-135">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-135">300</span></span>  <br/> |<span data-ttu-id="d1b6c-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d1b6c-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="d1b6c-137">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-137">**Note:** This is an example.</span></span> <span data-ttu-id="d1b6c-138">Microsoft 365 の表に記載されている、特定の**宛先またはポイントを**使用して、ここでのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="d1b6c-139">確認する方法</span><span class="sxs-lookup"><span data-stu-id="d1b6c-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d1b6c-140">単純</span><span class="sxs-lookup"><span data-stu-id="d1b6c-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="d1b6c-141">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="d1b6c-142">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d1b6c-143">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="d1b6c-144">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d1b6c-145">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d1b6c-146">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d1b6c-147">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d1b6c-148">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1b6c-149">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-149">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1b6c-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-150">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1b6c-151">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-151">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="d1b6c-152">MX レコードを追加して、自分のドメインのメールが Microsoft 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="d1b6c-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="d1b6c-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d1b6c-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d1b6c-p108">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d1b6c-156">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d1b6c-157">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d1b6c-158">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d1b6c-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d1b6c-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="d1b6c-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d1b6c-161">**名前**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-161">**Name**</span></span>|<span data-ttu-id="d1b6c-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-162">**Type**</span></span>|<span data-ttu-id="d1b6c-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-163">**Alias**</span></span>|<span data-ttu-id="d1b6c-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="d1b6c-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-165">**Value**</span></span>|<span data-ttu-id="d1b6c-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1b6c-167">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="d1b6c-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d1b6c-168">MX - Mail Exchange</span><span class="sxs-lookup"><span data-stu-id="d1b6c-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="d1b6c-169">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-169">No</span></span>  <br/> |<span data-ttu-id="d1b6c-170">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-170">300</span></span>  <br/> |<span data-ttu-id="d1b6c-171">0  *\<ドメイン キー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d1b6c-p109">0 は、MX 優先度の値です。 この値を MX 値の先頭に追加して、スペースで他の値から分離します。  </span><span class="sxs-lookup"><span data-stu-id="d1b6c-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="d1b6c-174">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d1b6c-175">**注:**\<Microsoft 365 アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="d1b6c-176">確認する方法</span><span class="sxs-lookup"><span data-stu-id="d1b6c-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="d1b6c-177">単純</span><span class="sxs-lookup"><span data-stu-id="d1b6c-177">Simple</span></span>  <br/> |
       
    ![AWS-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="d1b6c-179">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="d1b6c-181">他の MX レコードがある場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d1b6c-182">AWS は、複数のレコードが含まれる可能性のあるセットとして MX レコードを格納します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="d1b6c-183">[**レコードセットを削除**する] を選択し**ない**でください。これにより、追加した MX レコードを含むすべての MX レコードが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="d1b6c-184">代わりに、次の手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="d1b6c-185">最初に、MX レコードセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="d1b6c-187">次に、[ **Edit Record Set**] 領域で、[ **Value**] ボックスのエントリを選んで、キーボードの **Delete** キーを押し、使われなくなった MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="d1b6c-189">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d1b6c-191">Microsoft 365 に必要な5つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="d1b6c-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d1b6c-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d1b6c-p112">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d1b6c-195">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d1b6c-196">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d1b6c-197">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d1b6c-198">1 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d1b6c-199">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d1b6c-200">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d1b6c-201">**名前**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-201">**Name**</span></span>|<span data-ttu-id="d1b6c-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-202">**Type**</span></span>|<span data-ttu-id="d1b6c-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-203">**Alias**</span></span>|<span data-ttu-id="d1b6c-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="d1b6c-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-205">**Value**</span></span>|<span data-ttu-id="d1b6c-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1b6c-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d1b6c-207">autodiscover</span></span>  <br/> |<span data-ttu-id="d1b6c-208">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="d1b6c-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d1b6c-209">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-209">No</span></span>  <br/> |<span data-ttu-id="d1b6c-210">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-210">300</span></span>  <br/> |<span data-ttu-id="d1b6c-211">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d1b6c-212">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d1b6c-213">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="d1b6c-214">sip</span><span class="sxs-lookup"><span data-stu-id="d1b6c-214">sip</span></span>  <br/> |<span data-ttu-id="d1b6c-215">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="d1b6c-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d1b6c-216">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-216">No</span></span>  <br/> |<span data-ttu-id="d1b6c-217">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-217">300</span></span>  <br/> |<span data-ttu-id="d1b6c-218">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d1b6c-219">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d1b6c-220">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="d1b6c-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d1b6c-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d1b6c-222">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="d1b6c-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d1b6c-223">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-223">No</span></span>  <br/> |<span data-ttu-id="d1b6c-224">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-224">300</span></span>  <br/> |<span data-ttu-id="d1b6c-225">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d1b6c-226">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d1b6c-227">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="d1b6c-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d1b6c-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d1b6c-229">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="d1b6c-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d1b6c-230">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-230">No</span></span>  <br/> |<span data-ttu-id="d1b6c-231">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-231">300</span></span>  <br/> |<span data-ttu-id="d1b6c-232">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d1b6c-233">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d1b6c-234">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="d1b6c-235">EnterpriseEnrollment</span><span class="sxs-lookup"><span data-stu-id="d1b6c-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d1b6c-236">CNAME - 正規名</span><span class="sxs-lookup"><span data-stu-id="d1b6c-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="d1b6c-237">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-237">No</span></span>  <br/> |<span data-ttu-id="d1b6c-238">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-238">300</span></span>  <br/> |<span data-ttu-id="d1b6c-239">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d1b6c-240">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="d1b6c-241">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-241">Simple</span></span>  <br/> |
   
    ![AWS-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="d1b6c-243">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="d1b6c-245">残りの 4 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="d1b6c-246">[ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="d1b6c-247">この手順を繰り返し、5つの CNAME レコードをすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d1b6c-248">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="d1b6c-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d1b6c-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d1b6c-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b6c-250">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d1b6c-251">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d1b6c-252">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d1b6c-253">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="d1b6c-254">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-254">Need examples?</span></span> <span data-ttu-id="d1b6c-255">これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)確認します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="d1b6c-256">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d1b6c-257">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="d1b6c-258">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d1b6c-259">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d1b6c-260">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d1b6c-261">**TXT**レコードセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="d1b6c-p115">[ **レコード セットの編集**] 領域で、既存のレコード用の [ **Value:**] ボックス内にある現在のエントリの最後で、キーボードの Enter キーを押して新規の行を作成します。次に、その行 (既存の値の下) に、次のテーブルの値を入力、またはコピーして貼り付けます (表の下のイラストに例があります)。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="d1b6c-265">**Value:**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="d1b6c-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d1b6c-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d1b6c-p116">(画面の手順で必要になる引用符は自動的に補完されます。手動で入力する必要はありません。)  </span><span class="sxs-lookup"><span data-stu-id="d1b6c-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="d1b6c-269">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="d1b6c-271">[ **Save Record Set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="d1b6c-273">Microsoft 365 に必要な2つの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="d1b6c-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d1b6c-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d1b6c-p117">まず、[このリンク](https://console.aws.amazon.com/route53/home)を使って AWS でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="d1b6c-277">[**リソース**] ページで、[ **Hosted Zones**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="d1b6c-278">[ **Hosted Zones** ] ページの [ **domain Name** ] 列で、編集するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d1b6c-279">[ **Create Record Set**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="d1b6c-280">1 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="d1b6c-281">[ **Create Record Set**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d1b6c-282">[ **Type**] と [ **Routing Policy**] の値をドロップダウン リストから選びます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d1b6c-283">**名前**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-283">**Name**</span></span>|<span data-ttu-id="d1b6c-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-284">**Type**</span></span>|<span data-ttu-id="d1b6c-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-285">**Alias**</span></span>|<span data-ttu-id="d1b6c-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="d1b6c-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-287">**Value**</span></span>|<span data-ttu-id="d1b6c-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d1b6c-289">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="d1b6c-289">_sip._tls</span></span>|<span data-ttu-id="d1b6c-290">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="d1b6c-290">SRV - Service locator</span></span>|<span data-ttu-id="d1b6c-291">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-291">No</span></span>|<span data-ttu-id="d1b6c-292">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-292">300</span></span>|<span data-ttu-id="d1b6c-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d1b6c-294">**この値は、ピリオド (.) で終了する必要があります。**></span><span class="sxs-lookup"><span data-stu-id="d1b6c-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="d1b6c-295">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d1b6c-296">Simple</span><span class="sxs-lookup"><span data-stu-id="d1b6c-296">Simple</span></span>|
    |<span data-ttu-id="d1b6c-297">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="d1b6c-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d1b6c-298">SRV - サービス ロケータ</span><span class="sxs-lookup"><span data-stu-id="d1b6c-298">SRV - Service locator</span></span>|<span data-ttu-id="d1b6c-299">No</span><span class="sxs-lookup"><span data-stu-id="d1b6c-299">No</span></span>|<span data-ttu-id="d1b6c-300">300</span><span class="sxs-lookup"><span data-stu-id="d1b6c-300">300</span></span>|<span data-ttu-id="d1b6c-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d1b6c-302">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="d1b6c-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="d1b6c-303">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="d1b6c-304">単純</span><span class="sxs-lookup"><span data-stu-id="d1b6c-304">Simple</span></span>|
   
    ![AWS-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="d1b6c-306">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="d1b6c-308">他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="d1b6c-309">[ **Hosted Zones** ] ページで、[ **create record Set**] を選択し、表の次の行の値を使用してレコードを作成して、もう一度 [ **create** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d1b6c-310">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-310">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="d1b6c-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d1b6c-311">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="d1b6c-312">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b6c-312">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
