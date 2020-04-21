---
title: Microsoft にとって簡単に DNS レコードを Dnsで作成する
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: ドメインを確認し、電子メール、Skype for Business Online、および Dnsat の他のサービスの DNS レコードを Microsoft にとって簡単にセットアップする方法について説明します。
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629685"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="cb5ac-103">Microsoft にとって簡単に DNS レコードを Dnsで作成する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="cb5ac-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cb5ac-105">使用している DNS ホスティング プロバイダーが DNSMadeEasy の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cb5ac-106">これらのレコードを Dnsで追加すると、ドメインは Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="cb5ac-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb5ac-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cb5ac-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cb5ac-110">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cb5ac-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cb5ac-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cb5ac-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cb5ac-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="cb5ac-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb5ac-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cb5ac-117">Dnsが簡単なアカウントの場合、追加したドメインは別のドメインレジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="cb5ac-118">Dns は簡単にドメイン登録サービスを提供しません。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="cb5ac-119">Dnsて簡単にログインし、DNS レコードを作成することで、所有権を十分に証明できます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="cb5ac-120">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="cb5ac-121">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cb5ac-122">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="cb5ac-123">[管理された**DNS** ] ページの [ **TXT Records** ] 領域で**+**、() コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="cb5ac-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="cb5ac-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb5ac-126">**名前**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-126">**Name**</span></span> <br/> |<span data-ttu-id="cb5ac-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-127">**Value**</span></span> <br/> |<span data-ttu-id="cb5ac-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="cb5ac-129">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb5ac-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cb5ac-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cb5ac-131">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-131">**Note:** This is an example.</span></span> <span data-ttu-id="cb5ac-132">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="cb5ac-133">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cb5ac-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cb5ac-134">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="cb5ac-135">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="cb5ac-136">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cb5ac-137">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cb5ac-138">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cb5ac-139">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cb5ac-140">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cb5ac-141">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cb5ac-142">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cb5ac-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cb5ac-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cb5ac-145">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cb5ac-146">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cb5ac-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cb5ac-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cb5ac-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cb5ac-p108">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cb5ac-150">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="cb5ac-151">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![Dnsの簡単な設定-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="cb5ac-153">[管理された**DNS** ] ページの [ **MX Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="cb5ac-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-154">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="cb5ac-156">[ **Add MX Records**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cb5ac-157">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="cb5ac-158">**名前**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-158">**Name**</span></span>|<span data-ttu-id="cb5ac-159">**サーバー**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-159">**Server**</span></span>|<span data-ttu-id="cb5ac-160">**MX レベル**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-160">**MX Level**</span></span>|<span data-ttu-id="cb5ac-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb5ac-162">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="cb5ac-163">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cb5ac-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cb5ac-164">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cb5ac-165">**注:**\<Microsoft アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-165">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="cb5ac-166">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cb5ac-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cb5ac-167">10 </span><span class="sxs-lookup"><span data-stu-id="cb5ac-167">10</span></span>  <br/> <span data-ttu-id="cb5ac-168">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="cb5ac-169">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-169">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="cb5ac-171">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-171">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="cb5ac-173">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、1 つずつ選択してそれらを全部削除します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![Dnsの簡単な設定-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="cb5ac-175">すべてのレコードが選択されたら、[**選択した**ものを削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![Dnsの簡単な設定-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="cb5ac-177">[ **MX レコードの削除**] ダイアログボックスで、[**削除**] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![Dnsの簡単な設定-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb5ac-179">Microsoft に必要な5つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cb5ac-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cb5ac-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="cb5ac-p110">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cb5ac-183">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="cb5ac-184">[管理された**DNS** ] ページの [ **CNAME Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="cb5ac-185">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-185">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="cb5ac-187">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="cb5ac-188">[ **Add CNAME Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="cb5ac-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-189">**Name**</span></span>|<span data-ttu-id="cb5ac-190">**Alias to (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-190">**Alias to**</span></span>|<span data-ttu-id="cb5ac-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb5ac-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cb5ac-192">autodiscover</span></span>  <br/> |<span data-ttu-id="cb5ac-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cb5ac-194">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-195">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-195">1800</span></span>  <br/> |
    |<span data-ttu-id="cb5ac-196">sip</span><span class="sxs-lookup"><span data-stu-id="cb5ac-196">sip</span></span>  <br/> |<span data-ttu-id="cb5ac-197">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb5ac-198">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-199">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-199">1800</span></span>  <br/> |
    |<span data-ttu-id="cb5ac-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cb5ac-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cb5ac-201">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb5ac-202">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-203">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-203">1800</span></span>  <br/> |
    |<span data-ttu-id="cb5ac-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cb5ac-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cb5ac-205">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cb5ac-206">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-207">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-207">1800</span></span>  <br/> |
    |<span data-ttu-id="cb5ac-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cb5ac-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cb5ac-209">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cb5ac-210">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-211">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-211">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="cb5ac-213">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-213">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="cb5ac-215">他の4つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="cb5ac-216">[ **CNAME Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="cb5ac-217">この手順を繰り返し、5つの CNAME レコードをすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cb5ac-218">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cb5ac-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cb5ac-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb5ac-220">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cb5ac-221">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cb5ac-222">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-222">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cb5ac-223">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-223">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="cb5ac-224">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-224">Need examples?</span></span> <span data-ttu-id="cb5ac-225">これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)確認します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-225">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="cb5ac-226">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="cb5ac-227">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="cb5ac-228">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cb5ac-229">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="cb5ac-230">[管理された**DNS** ] ページの [ **TXT Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="cb5ac-231">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-231">(You may have to scroll down.)</span></span>
    
    ![Dnsの簡単な設定-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="cb5ac-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="cb5ac-234">**名前**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-234">**Name**</span></span>|<span data-ttu-id="cb5ac-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-235">**Value**</span></span>|<span data-ttu-id="cb5ac-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="cb5ac-237">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cb5ac-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cb5ac-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cb5ac-239">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cb5ac-240">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-240">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="cb5ac-242">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-242">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cb5ac-244">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cb5ac-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cb5ac-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cb5ac-p113">まず、[このリンク](https://cp.dnsmadeeasy.com/)を使って DNSMadeEasy でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="cb5ac-248">[**管理コンソール**] ページの [**最近更新さ**れたドメイン] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="cb5ac-249">[管理された**DNS** ] ページの [ **SRV Records** ] 領域で、 **(+)** コントロール ([**新規追加**]) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="cb5ac-250">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="cb5ac-250">(You may have to scroll down)</span></span>
    
    ![Dnsの簡単な設定-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="cb5ac-252">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="cb5ac-253">[ **Add SRV Records**] 領域にある新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="cb5ac-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-254">**Name**</span></span>|<span data-ttu-id="cb5ac-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-255">**Priority**</span></span>|<span data-ttu-id="cb5ac-256">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-256">**Weight**</span></span>|<span data-ttu-id="cb5ac-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-257">**Port**</span></span>|<span data-ttu-id="cb5ac-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-258">**Host**</span></span>|<span data-ttu-id="cb5ac-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cb5ac-260">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="cb5ac-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="cb5ac-261">100</span><span class="sxs-lookup"><span data-stu-id="cb5ac-261">100</span></span>  <br/> |<span data-ttu-id="cb5ac-262">1-d</span><span class="sxs-lookup"><span data-stu-id="cb5ac-262">1</span></span>  <br/> |<span data-ttu-id="cb5ac-263">443</span><span class="sxs-lookup"><span data-stu-id="cb5ac-263">443</span></span>  <br/> |<span data-ttu-id="cb5ac-264">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb5ac-265">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-266">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-266">1800</span></span>  <br/> |
    |<span data-ttu-id="cb5ac-267">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="cb5ac-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="cb5ac-268">100</span><span class="sxs-lookup"><span data-stu-id="cb5ac-268">100</span></span>  <br/> |<span data-ttu-id="cb5ac-269">1-d</span><span class="sxs-lookup"><span data-stu-id="cb5ac-269">1</span></span>  <br/> |<span data-ttu-id="cb5ac-270">5061</span><span class="sxs-lookup"><span data-stu-id="cb5ac-270">5061</span></span>  <br/> |<span data-ttu-id="cb5ac-271">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="cb5ac-272">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cb5ac-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cb5ac-273">1800</span><span class="sxs-lookup"><span data-stu-id="cb5ac-273">1800</span></span>  <br/> |
   
    ![Dnsの簡単な設定-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="cb5ac-275">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-275">Select **Submit**.</span></span>
    
    ![Dnsの簡単な設定-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="cb5ac-277">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cb5ac-278">[ **SRV Records** ] セクションで、 **(+)** コントロール ([**新規追加**]) を選択し、表の次の行の値を使用してレコードを作成し、[ **Submit** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cb5ac-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cb5ac-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cb5ac-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cb5ac-281">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

