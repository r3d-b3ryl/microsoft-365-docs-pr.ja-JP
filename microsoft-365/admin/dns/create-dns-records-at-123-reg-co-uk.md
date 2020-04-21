---
title: Microsoft の123-reg.co.uk で DNS レコードを作成する
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: ドメインを確認し、電子メール、Skype for Business Online、および123-reg.co.uk のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629745"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="c792f-103">Microsoft の123-reg.co.uk で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="c792f-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="c792f-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c792f-105">使用している DNS ホスティング プロバイダーが 123-reg.co.uk の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="c792f-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c792f-106">これらのレコードを123-reg.co.uk で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="c792f-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="c792f-107">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c792f-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c792f-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c792f-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c792f-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c792f-110">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c792f-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c792f-111">Add a TXT record for verification</span></span>
<span data-ttu-id="c792f-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c792f-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c792f-113">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c792f-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="c792f-114">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="c792f-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c792f-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c792f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c792f-117">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c792f-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="c792f-118">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c792f-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c792f-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="c792f-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c792f-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c792f-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="c792f-121">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="c792f-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c792f-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c792f-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c792f-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="c792f-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="c792f-124">**Hostname**</span></span> <br/> |<span data-ttu-id="c792f-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="c792f-125">**Type**</span></span> <br/> |<span data-ttu-id="c792f-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="c792f-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="c792f-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="c792f-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="c792f-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c792f-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c792f-129">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="c792f-129">**Note:** This is an example.</span></span> <span data-ttu-id="c792f-130">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c792f-130">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c792f-131">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c792f-131">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="c792f-132">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="c792f-133">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="c792f-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c792f-134">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="c792f-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="c792f-135">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="c792f-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c792f-136">Microsoft 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**設定** \> ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="c792f-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c792f-137">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c792f-138">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c792f-139">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c792f-140">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c792f-140">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c792f-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c792f-141">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c792f-142">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-142">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c792f-143">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c792f-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c792f-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c792f-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c792f-p107">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c792f-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c792f-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="c792f-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c792f-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c792f-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="c792f-149">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="c792f-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c792f-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c792f-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c792f-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c792f-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="c792f-152">**Hostname**</span></span>|<span data-ttu-id="c792f-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="c792f-153">**Type**</span></span>|<span data-ttu-id="c792f-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c792f-154">**Priority**</span></span>|<span data-ttu-id="c792f-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="c792f-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c792f-156">MX</span><span class="sxs-lookup"><span data-stu-id="c792f-156">MX</span></span>  <br/> |<span data-ttu-id="c792f-157">1-d</span><span class="sxs-lookup"><span data-stu-id="c792f-157">1</span></span>  <br/> <span data-ttu-id="c792f-158">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="c792f-159">*\<ドメインキー\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="c792f-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c792f-160">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c792f-161">**注:** Microsoft アカウント\<からドメインキー\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="c792f-161">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="c792f-162">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c792f-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルの値をコピーして貼り付ける](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="c792f-164">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-164">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="c792f-166">その他の MX レコードがある場合は、そのレコードの **削除 (ごみ箱)** アイコンを選んでそれぞれ削除します。</span><span class="sxs-lookup"><span data-stu-id="c792f-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![[削除] (ごみ箱アイコン) を選択します。](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c792f-168">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c792f-168">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c792f-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c792f-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c792f-p109">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c792f-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c792f-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="c792f-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c792f-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c792f-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="c792f-174">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="c792f-175">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c792f-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="c792f-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c792f-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c792f-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c792f-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c792f-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="c792f-178">**Hostname**</span></span>|<span data-ttu-id="c792f-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="c792f-179">**Type**</span></span>|<span data-ttu-id="c792f-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="c792f-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="c792f-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c792f-181">autodiscover</span></span>  <br/> |<span data-ttu-id="c792f-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="c792f-182">CNAME</span></span>  <br/> |<span data-ttu-id="c792f-183">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c792f-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c792f-184">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="c792f-185">sip</span><span class="sxs-lookup"><span data-stu-id="c792f-185">sip</span></span>  <br/> |<span data-ttu-id="c792f-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="c792f-186">CNAME</span></span>  <br/> |<span data-ttu-id="c792f-187">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c792f-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c792f-188">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="c792f-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c792f-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c792f-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="c792f-190">CNAME</span></span>  <br/> |<span data-ttu-id="c792f-191">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c792f-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c792f-192">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="c792f-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c792f-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c792f-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="c792f-194">CNAME</span></span>  <br/> |<span data-ttu-id="c792f-195">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c792f-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c792f-196">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c792f-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="c792f-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c792f-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c792f-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="c792f-198">CNAME</span></span>  <br/> |<span data-ttu-id="c792f-199">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c792f-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c792f-200">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c792f-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="c792f-202">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-202">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="c792f-204">他の 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c792f-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="c792f-205">[ **ADVANCED DNS** ] セクションで、表の次の行の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="c792f-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="c792f-206">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c792f-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c792f-207">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c792f-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c792f-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c792f-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c792f-209">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c792f-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c792f-210">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c792f-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c792f-211">自分のドメインに対して既に SPF レコードがある場合は、Microsfot 用の新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c792f-211">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="c792f-212">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c792f-212">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="c792f-213">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c792f-213">Need examples?</span></span> <span data-ttu-id="c792f-214">これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)確認します。</span><span class="sxs-lookup"><span data-stu-id="c792f-214">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="c792f-215">SPF レコードを確認するには、[SPF の検証ツール](../setup/domains-faq.md)を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c792f-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="c792f-216">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c792f-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="c792f-217">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c792f-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c792f-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="c792f-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c792f-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c792f-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="c792f-220">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="c792f-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c792f-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c792f-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c792f-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c792f-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="c792f-223">**Hostname**</span></span>|<span data-ttu-id="c792f-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="c792f-224">**Type**</span></span>|<span data-ttu-id="c792f-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="c792f-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c792f-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="c792f-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="c792f-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c792f-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c792f-228">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c792f-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="c792f-230">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-230">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c792f-232">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c792f-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c792f-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c792f-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c792f-p112">まず、[このリンク](https://www.123-reg.co.uk/secure/cpanel/domain/overview)を使って 123-reg.co.uk でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c792f-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c792f-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="c792f-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="c792f-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="c792f-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="c792f-238">[ **Dns の管理**] ページで、[ **Advanced dns** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="c792f-239">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c792f-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="c792f-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c792f-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c792f-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c792f-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c792f-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="c792f-242">Hostname</span></span>|<span data-ttu-id="c792f-243">Type</span><span class="sxs-lookup"><span data-stu-id="c792f-243">Type</span></span>|<span data-ttu-id="c792f-244">Priority</span><span class="sxs-lookup"><span data-stu-id="c792f-244">Priority</span></span>|<span data-ttu-id="c792f-245">TTL</span><span class="sxs-lookup"><span data-stu-id="c792f-245">TTL</span></span>|<span data-ttu-id="c792f-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="c792f-246">Destination SRV</span></span>|
    |<span data-ttu-id="c792f-247">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="c792f-247">_sip._tls</span></span>|<span data-ttu-id="c792f-248">SRV</span><span class="sxs-lookup"><span data-stu-id="c792f-248">SRV</span></span>|<span data-ttu-id="c792f-249">100</span><span class="sxs-lookup"><span data-stu-id="c792f-249">100</span></span>|<span data-ttu-id="c792f-250">3600</span><span class="sxs-lookup"><span data-stu-id="c792f-250">3600</span></span>|<span data-ttu-id="c792f-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c792f-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="c792f-252">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="c792f-253">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c792f-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="c792f-254">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="c792f-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="c792f-255">SRV</span><span class="sxs-lookup"><span data-stu-id="c792f-255">SRV</span></span>|<span data-ttu-id="c792f-256">100</span><span class="sxs-lookup"><span data-stu-id="c792f-256">100</span></span>|<span data-ttu-id="c792f-257">3600</span><span class="sxs-lookup"><span data-stu-id="c792f-257">3600</span></span>|<span data-ttu-id="c792f-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="c792f-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="c792f-259">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c792f-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="c792f-260">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c792f-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="c792f-262">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c792f-262">Select **Add**.</span></span>
    
    ![[追加] を選択します。](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="c792f-264">他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c792f-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="c792f-265">[ **ADVANCED DNS** ] セクションで、表の2行目の値を使用してレコードを作成し、もう一度 [ **Add** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="c792f-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c792f-266">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c792f-266">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c792f-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c792f-267">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c792f-268">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c792f-268">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
