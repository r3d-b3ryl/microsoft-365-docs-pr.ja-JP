---
title: Microsoft の Hostgator で DNS レコードを作成する
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Hostgator にあるその他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 9ac14d516dff6e84dd0fb06a6632376d475689fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629529"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="cdd68-103">Microsoft の Hostgator で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="cdd68-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="cdd68-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cdd68-105">使用している DNS ホスティング プロバイダーが Hostgator の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cdd68-106">この記事に記載されている他の手順のいずれかを使用して DNS レコードを追加する前に、最初の procedurebelow を実行して、[ドメインをホスティングアカウントにする](#point-your-domain-to-your-hosting-account)必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="cdd68-107">Hostgator でこれらの変更をすべて行った後、ドメインは Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="cdd68-108">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-108">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdd68-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdd68-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdd68-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdd68-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdd68-111">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="cdd68-112">ドメインがホスティング アカウントを指すようにする</span><span class="sxs-lookup"><span data-stu-id="cdd68-112">Point your domain to your hosting account</span></span>
<span data-ttu-id="cdd68-113"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-113"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-114">この手順どおりに行ってから、この記事のその他の手順どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-114">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="cdd68-115">この手順に従って、ドメインとホスティング アカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-115">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="cdd68-p102">まず、[このリンク](https://portal.hostgator.com/)を使って Hostgator でドメイン管理ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="cdd68-118">左側の [ **Domains** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-118">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="cdd68-119">[**ドメインの管理**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-119">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="cdd68-120">左側の [ポップアップ] メニューで、[**ネームサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-120">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="cdd68-121">自分のドメインの [**ネームサーバー** ] ページで、[**自動的にこのドメインをホスティングアカウントにポイントする**] ドロップダウンリストで、ドメインに関連付けられているホスティングアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-121">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="cdd68-122">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-122">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cdd68-123">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd68-123">Add a TXT record for verification</span></span>
<span data-ttu-id="cdd68-124"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-124"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-125">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-125">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="cdd68-126">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-126">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="cdd68-127">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-127">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cdd68-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cdd68-130">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-130">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="cdd68-131">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="cdd68-131">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="cdd68-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="cdd68-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="cdd68-133">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-133">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="cdd68-134">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-134">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdd68-135">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-135">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="cdd68-136">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-136">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="cdd68-137">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-137">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="cdd68-138">[**ゾーン編集の詳細**] ページの [ **Add a record** ] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-138">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cdd68-139">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="cdd68-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdd68-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="cdd68-140">**Name**</span></span> <br/> |<span data-ttu-id="cdd68-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdd68-141">**TTL**</span></span> <br/> |<span data-ttu-id="cdd68-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="cdd68-142">**Type**</span></span> <br/> |<span data-ttu-id="cdd68-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="cdd68-143">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="cdd68-144">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-144">Use your  *domain_name*.</span></span> <span data-ttu-id="cdd68-145">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="cdd68-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-146">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="cdd68-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-147">1-d</span><span class="sxs-lookup"><span data-stu-id="cdd68-147">1</span></span>  <br/> |<span data-ttu-id="cdd68-148">TXT</span><span class="sxs-lookup"><span data-stu-id="cdd68-148">TXT</span></span>  <br/> |<span data-ttu-id="cdd68-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cdd68-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cdd68-150">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="cdd68-150">**Note:** This is an example.</span></span> <span data-ttu-id="cdd68-151">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="cdd68-152">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cdd68-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="cdd68-153">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="cdd68-154">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cdd68-155">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cdd68-156">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cdd68-157">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cdd68-158">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cdd68-159">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cdd68-160">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cdd68-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdd68-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdd68-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdd68-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdd68-163">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cdd68-164">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cdd68-164">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cdd68-165"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-165"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-166">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-166">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="cdd68-p111">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="cdd68-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="cdd68-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="cdd68-170">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-170">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="cdd68-171">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-171">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdd68-172">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-172">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="cdd68-173">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-173">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="cdd68-174">[**コントロールパネル**] ページの [**電子メール**] 領域で、[ **MX Entry**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-174">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="cdd68-175">[ **Email Routing**] 領域で、[ **Remote Mail Exchanger**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-175">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="cdd68-176">[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-176">Select **Change**.</span></span>
  
5. <span data-ttu-id="cdd68-177">[**新しいレコードの追加**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-177">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="cdd68-178">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cdd68-178">**Priority**</span></span>|<span data-ttu-id="cdd68-179">**Destination**</span><span class="sxs-lookup"><span data-stu-id="cdd68-179">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cdd68-180">.0</span><span class="sxs-lookup"><span data-stu-id="cdd68-180">0</span></span>  <br/> <span data-ttu-id="cdd68-181">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-181">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="cdd68-182">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-182">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cdd68-183">**注:**\< Microsoft アカウントから*ドメインキー* \>を取得します。  </span><span class="sxs-lookup"><span data-stu-id="cdd68-183">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="cdd68-184">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cdd68-184">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="cdd68-185">[ **Add New Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-185">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="cdd68-186">その他の MX レコードが [ **MX Records**] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-186">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cdd68-187">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd68-187">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cdd68-188"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-188"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-189">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-189">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="cdd68-p115">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="cdd68-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="cdd68-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="cdd68-193">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-193">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="cdd68-194">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-194">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdd68-195">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-195">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="cdd68-196">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-196">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="cdd68-197">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-197">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="cdd68-198">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-198">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="cdd68-199">[ **Advanced Zone Editor** ] ページの [ **Add a record** ] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-199">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cdd68-200">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="cdd68-200">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdd68-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="cdd68-201">**Name**</span></span>|<span data-ttu-id="cdd68-202">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdd68-202">**TTL**</span></span>|<span data-ttu-id="cdd68-203">**Type**</span><span class="sxs-lookup"><span data-stu-id="cdd68-203">**Type**</span></span>|<span data-ttu-id="cdd68-204">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="cdd68-204">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdd68-205">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="cdd68-205">autodiscover.</span></span> <span data-ttu-id="cdd68-206">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-206">*domain_name*.</span></span> <span data-ttu-id="cdd68-207">(たとえば、autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="cdd68-207">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-209">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-209">3600</span></span>  <br/> |<span data-ttu-id="cdd68-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdd68-210">CNAME</span></span>  <br/> |<span data-ttu-id="cdd68-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-211">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="cdd68-212">sip.</span><span class="sxs-lookup"><span data-stu-id="cdd68-212">sip.</span></span> <span data-ttu-id="cdd68-213">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-213">*domain_name*.</span></span> <span data-ttu-id="cdd68-214">(たとえば、sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="cdd68-214">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-215">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-215">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-216">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-216">3600</span></span>  <br/> |<span data-ttu-id="cdd68-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdd68-217">CNAME</span></span>  <br/> |<span data-ttu-id="cdd68-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cdd68-219">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="cdd68-219">lyncdiscover.</span></span> <span data-ttu-id="cdd68-220">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-220">*domain_name*.</span></span> <span data-ttu-id="cdd68-221">(たとえば、lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="cdd68-221">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-222">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-222">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-223">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-223">3600</span></span>  <br/> |<span data-ttu-id="cdd68-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdd68-224">CNAME</span></span>  <br/> |<span data-ttu-id="cdd68-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-225">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cdd68-226">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="cdd68-226">enterpriseregistration.</span></span> <span data-ttu-id="cdd68-227">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-227">*domain_name*.</span></span> <span data-ttu-id="cdd68-228">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="cdd68-228">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-229">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-229">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-230">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-230">3600</span></span>  <br/> |<span data-ttu-id="cdd68-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdd68-231">CNAME</span></span>  <br/> |<span data-ttu-id="cdd68-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cdd68-232">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="cdd68-233">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="cdd68-233">enterpriseenrollment.</span></span> <span data-ttu-id="cdd68-234">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-234">*domain_name*.</span></span> <span data-ttu-id="cdd68-235">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="cdd68-235">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-236">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-236">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-237">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-237">3600</span></span>  <br/> |<span data-ttu-id="cdd68-238">CNAME</span><span class="sxs-lookup"><span data-stu-id="cdd68-238">CNAME</span></span>  <br/> |<span data-ttu-id="cdd68-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-239">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="cdd68-240">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-240">Select **Add Record**.</span></span>

5. <span data-ttu-id="cdd68-241">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-241">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="cdd68-242">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-242">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="cdd68-243">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-243">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cdd68-244">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd68-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cdd68-245"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-245"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-246">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdd68-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cdd68-247">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cdd68-248">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-248">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cdd68-249">代わりに、値のセットを含む1つの SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-249">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="cdd68-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-250">Need examples?</span></span> <span data-ttu-id="cdd68-251">これらの[外部ドメインネームシステムレコードを Microsoft に対して](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords)確認します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-251">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="cdd68-252">SPF レコードを確認するには、[SPF の検証ツール](../setup/domains-faq.md)を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cdd68-253">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-253">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="cdd68-p124">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="cdd68-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="cdd68-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="cdd68-257">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-257">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="cdd68-258">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-258">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdd68-259">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-259">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="cdd68-260">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-260">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="cdd68-261">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-261">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="cdd68-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cdd68-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cdd68-263">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="cdd68-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdd68-264">**Name**</span><span class="sxs-lookup"><span data-stu-id="cdd68-264">**Name**</span></span>|<span data-ttu-id="cdd68-265">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdd68-265">**TTL**</span></span>|<span data-ttu-id="cdd68-266">**Type**</span><span class="sxs-lookup"><span data-stu-id="cdd68-266">**Type**</span></span>|<span data-ttu-id="cdd68-267">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="cdd68-267">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdd68-268">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-268">Use your  *domain_name*.</span></span> <span data-ttu-id="cdd68-269">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="cdd68-269">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-270">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-270">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-271">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-271">3600</span></span>  <br/> |<span data-ttu-id="cdd68-272">TXT</span><span class="sxs-lookup"><span data-stu-id="cdd68-272">TXT</span></span>  <br/> |<span data-ttu-id="cdd68-273">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cdd68-273">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cdd68-274">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cdd68-274">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="cdd68-275">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-275">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cdd68-276">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cdd68-276">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cdd68-277"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cdd68-277"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdd68-278">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-278">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="cdd68-p128">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="cdd68-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="cdd68-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="cdd68-282">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-282">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="cdd68-283">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cdd68-283">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cdd68-284">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="cdd68-284">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="cdd68-285">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-285">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="cdd68-286">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-286">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="cdd68-287">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-287">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="cdd68-288">[ **Advanced DNS Zone Editor**] ページの [ **Add a Record**] 領域で、新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-288">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="cdd68-289">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="cdd68-289">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cdd68-290">**Name**</span><span class="sxs-lookup"><span data-stu-id="cdd68-290">**Name**</span></span>|<span data-ttu-id="cdd68-291">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdd68-291">**TTL**</span></span>|<span data-ttu-id="cdd68-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="cdd68-292">**Type**</span></span>|<span data-ttu-id="cdd68-293">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cdd68-293">**Priority**</span></span>|<span data-ttu-id="cdd68-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cdd68-294">**Weight**</span></span>|<span data-ttu-id="cdd68-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="cdd68-295">**Port**</span></span>|<span data-ttu-id="cdd68-296">**対象**</span><span class="sxs-lookup"><span data-stu-id="cdd68-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdd68-297">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="cdd68-297">_sip._tls.</span></span> <span data-ttu-id="cdd68-298">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-298">*domain_name*.</span></span> <span data-ttu-id="cdd68-299">(たとえば、_sip. _tls] など)。</span><span class="sxs-lookup"><span data-stu-id="cdd68-299">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-300">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-300">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-301">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-301">3600</span></span>  <br/> |<span data-ttu-id="cdd68-302">SRV</span><span class="sxs-lookup"><span data-stu-id="cdd68-302">SRV</span></span>  <br/> |<span data-ttu-id="cdd68-303">100</span><span class="sxs-lookup"><span data-stu-id="cdd68-303">100</span></span>  <br/> |<span data-ttu-id="cdd68-304">1-d</span><span class="sxs-lookup"><span data-stu-id="cdd68-304">1</span></span>  <br/> |<span data-ttu-id="cdd68-305">443</span><span class="sxs-lookup"><span data-stu-id="cdd68-305">443</span></span>  <br/> |<span data-ttu-id="cdd68-306">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-306">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="cdd68-307">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="cdd68-307">_sipfederationtls._tcp.</span></span> <span data-ttu-id="cdd68-308">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-308">*domain_name*.</span></span> <span data-ttu-id="cdd68-309">(たとえば、_sipfederationtls. _tcp] など)。</span><span class="sxs-lookup"><span data-stu-id="cdd68-309">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="cdd68-310">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="cdd68-310">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="cdd68-311">3600</span><span class="sxs-lookup"><span data-stu-id="cdd68-311">3600</span></span>  <br/> |<span data-ttu-id="cdd68-312">SRV</span><span class="sxs-lookup"><span data-stu-id="cdd68-312">SRV</span></span>  <br/> |<span data-ttu-id="cdd68-313">100</span><span class="sxs-lookup"><span data-stu-id="cdd68-313">100</span></span>  <br/> |<span data-ttu-id="cdd68-314">1-d</span><span class="sxs-lookup"><span data-stu-id="cdd68-314">1</span></span>  <br/> |<span data-ttu-id="cdd68-315">5061</span><span class="sxs-lookup"><span data-stu-id="cdd68-315">5061</span></span>  <br/> |<span data-ttu-id="cdd68-316">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd68-316">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="cdd68-317">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-317">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="cdd68-318">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cdd68-318">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cdd68-319">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="cdd68-319">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cdd68-320">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cdd68-320">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cdd68-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cdd68-321">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cdd68-322">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd68-322">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
