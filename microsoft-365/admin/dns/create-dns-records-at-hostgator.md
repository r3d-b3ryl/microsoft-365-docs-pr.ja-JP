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
ms.openlocfilehash: fb510bcdcdefb141535e9a1099e18b63adffd2ab
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049001"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="79ac7-103">Microsoft の Hostgator で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="79ac7-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="79ac7-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79ac7-105">使用している DNS ホスティング プロバイダーが Hostgator の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="79ac7-106">この記事に記載されている他の手順のいずれかを使用して DNS レコードを追加する前に、最初の procedurebelow を実行して、[ドメインをホスティングアカウントにする](#point-your-domain-to-your-hosting-account)必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="79ac7-107">Hostgator でこれらの変更をすべて行った後、ドメインは Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="79ac7-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="79ac7-111">ドメインがホスティング アカウントを指すようにする</span><span class="sxs-lookup"><span data-stu-id="79ac7-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="79ac7-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-113">この手順どおりに行ってから、この記事のその他の手順どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="79ac7-114">この手順に従って、ドメインとホスティング アカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="79ac7-p102">まず、[このリンク](https://portal.hostgator.com/)を使って Hostgator でドメイン管理ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="79ac7-117">左側の [ **Domains** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="79ac7-118">[**ドメインの管理**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="79ac7-119">左側の [ポップアップ] メニューで、[**ネームサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="79ac7-120">自分のドメインの [**ネームサーバー** ] ページで、[**自動的にこのドメインをホスティングアカウントにポイントする**] ドロップダウンリストで、ドメインに関連付けられているホスティングアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="79ac7-121">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="79ac7-122">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="79ac7-122">Add a TXT record for verification</span></span>
<span data-ttu-id="79ac7-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-124">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="79ac7-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79ac7-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="79ac7-129">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-129">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="79ac7-130">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="79ac7-130">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="79ac7-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="79ac7-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="79ac7-132">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="79ac7-133">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="79ac7-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="79ac7-135">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="79ac7-136">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="79ac7-137">[**ゾーン編集の詳細**] ページの [ **Add a record** ] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79ac7-138">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="79ac7-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79ac7-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="79ac7-139">**Name**</span></span> <br/> |<span data-ttu-id="79ac7-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79ac7-140">**TTL**</span></span> <br/> |<span data-ttu-id="79ac7-141">**Type**</span><span class="sxs-lookup"><span data-stu-id="79ac7-141">**Type**</span></span> <br/> |<span data-ttu-id="79ac7-142">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="79ac7-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="79ac7-143">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-143">Use your  *domain_name*.</span></span> <span data-ttu-id="79ac7-144">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="79ac7-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-145">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="79ac7-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-146">1-d</span><span class="sxs-lookup"><span data-stu-id="79ac7-146">1</span></span>  <br/> |<span data-ttu-id="79ac7-147">TXT</span><span class="sxs-lookup"><span data-stu-id="79ac7-147">TXT</span></span>  <br/> |<span data-ttu-id="79ac7-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="79ac7-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="79ac7-149">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="79ac7-149">**Note:** This is an example.</span></span> <span data-ttu-id="79ac7-150">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="79ac7-151">確認する方法</span><span class="sxs-lookup"><span data-stu-id="79ac7-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="79ac7-152">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="79ac7-153">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="79ac7-154">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="79ac7-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="79ac7-155">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="79ac7-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="79ac7-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="79ac7-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="79ac7-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79ac7-p110">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="79ac7-163">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="79ac7-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="79ac7-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-165">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="79ac7-p111">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="79ac7-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="79ac7-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="79ac7-169">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="79ac7-170">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="79ac7-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="79ac7-172">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="79ac7-173">[**コントロールパネル**] ページの [**電子メール**] 領域で、[ **MX Entry**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="79ac7-174">[ **Email Routing**] 領域で、[ **Remote Mail Exchanger**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="79ac7-175">[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="79ac7-176">[**新しいレコードの追加**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="79ac7-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="79ac7-177">**Priority**</span></span>|<span data-ttu-id="79ac7-178">**Destination**</span><span class="sxs-lookup"><span data-stu-id="79ac7-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="79ac7-179">.0</span><span class="sxs-lookup"><span data-stu-id="79ac7-179">0</span></span>  <br/> <span data-ttu-id="79ac7-180">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-180">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="79ac7-181">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="79ac7-182">**注:**\< Microsoft アカウントから*ドメインキー* \>を取得します。  </span><span class="sxs-lookup"><span data-stu-id="79ac7-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="79ac7-183">確認する方法</span><span class="sxs-lookup"><span data-stu-id="79ac7-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="79ac7-184">[ **Add New Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="79ac7-185">その他の MX レコードが [ **MX Records**] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="79ac7-186">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="79ac7-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="79ac7-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-188">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="79ac7-p115">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="79ac7-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="79ac7-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="79ac7-192">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="79ac7-193">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="79ac7-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="79ac7-195">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="79ac7-196">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="79ac7-197">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="79ac7-198">[ **Advanced Zone Editor** ] ページの [ **Add a record** ] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="79ac7-199">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="79ac7-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79ac7-200">**Name**</span><span class="sxs-lookup"><span data-stu-id="79ac7-200">**Name**</span></span>|<span data-ttu-id="79ac7-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79ac7-201">**TTL**</span></span>|<span data-ttu-id="79ac7-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="79ac7-202">**Type**</span></span>|<span data-ttu-id="79ac7-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="79ac7-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79ac7-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="79ac7-204">autodiscover.</span></span> <span data-ttu-id="79ac7-205">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-205">*domain_name*.</span></span> <span data-ttu-id="79ac7-206">(たとえば、autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="79ac7-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-207">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-208">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-208">3600</span></span>  <br/> |<span data-ttu-id="79ac7-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="79ac7-209">CNAME</span></span>  <br/> |<span data-ttu-id="79ac7-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="79ac7-211">sip.</span><span class="sxs-lookup"><span data-stu-id="79ac7-211">sip.</span></span> <span data-ttu-id="79ac7-212">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-212">*domain_name*.</span></span> <span data-ttu-id="79ac7-213">(たとえば、sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="79ac7-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-214">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-215">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-215">3600</span></span>  <br/> |<span data-ttu-id="79ac7-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="79ac7-216">CNAME</span></span>  <br/> |<span data-ttu-id="79ac7-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79ac7-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="79ac7-218">lyncdiscover.</span></span> <span data-ttu-id="79ac7-219">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-219">*domain_name*.</span></span> <span data-ttu-id="79ac7-220">(たとえば、lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="79ac7-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-221">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-222">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-222">3600</span></span>  <br/> |<span data-ttu-id="79ac7-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="79ac7-223">CNAME</span></span>  <br/> |<span data-ttu-id="79ac7-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79ac7-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="79ac7-225">enterpriseregistration.</span></span> <span data-ttu-id="79ac7-226">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-226">*domain_name*.</span></span> <span data-ttu-id="79ac7-227">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="79ac7-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-228">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-229">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-229">3600</span></span>  <br/> |<span data-ttu-id="79ac7-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="79ac7-230">CNAME</span></span>  <br/> |<span data-ttu-id="79ac7-231">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="79ac7-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="79ac7-232">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="79ac7-232">enterpriseenrollment.</span></span> <span data-ttu-id="79ac7-233">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-233">*domain_name*.</span></span> <span data-ttu-id="79ac7-234">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="79ac7-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-235">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-236">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-236">3600</span></span>  <br/> |<span data-ttu-id="79ac7-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="79ac7-237">CNAME</span></span>  <br/> |<span data-ttu-id="79ac7-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="79ac7-239">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="79ac7-240">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="79ac7-241">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="79ac7-242">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="79ac7-243">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="79ac7-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="79ac7-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-245">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="79ac7-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="79ac7-246">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="79ac7-247">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="79ac7-248">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="79ac7-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="79ac7-249">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-249">Need examples?</span></span> <span data-ttu-id="79ac7-250">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-250">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="79ac7-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="79ac7-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="79ac7-252">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="79ac7-p124">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="79ac7-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="79ac7-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="79ac7-256">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="79ac7-257">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="79ac7-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="79ac7-259">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="79ac7-260">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="79ac7-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79ac7-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79ac7-262">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="79ac7-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79ac7-263">**Name**</span><span class="sxs-lookup"><span data-stu-id="79ac7-263">**Name**</span></span>|<span data-ttu-id="79ac7-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79ac7-264">**TTL**</span></span>|<span data-ttu-id="79ac7-265">**Type**</span><span class="sxs-lookup"><span data-stu-id="79ac7-265">**Type**</span></span>|<span data-ttu-id="79ac7-266">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="79ac7-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79ac7-267">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-267">Use your  *domain_name*.</span></span> <span data-ttu-id="79ac7-268">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="79ac7-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-269">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-270">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-270">3600</span></span>  <br/> |<span data-ttu-id="79ac7-271">TXT</span><span class="sxs-lookup"><span data-stu-id="79ac7-271">TXT</span></span>  <br/> |<span data-ttu-id="79ac7-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="79ac7-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="79ac7-273">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="79ac7-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="79ac7-274">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="79ac7-275">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="79ac7-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="79ac7-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="79ac7-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79ac7-277">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="79ac7-p128">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="79ac7-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="79ac7-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="79ac7-281">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="79ac7-282">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="79ac7-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="79ac7-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="79ac7-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="79ac7-284">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="79ac7-285">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="79ac7-286">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="79ac7-287">[ **Advanced DNS Zone Editor**] ページの [ **Add a Record**] 領域で、新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="79ac7-288">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="79ac7-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="79ac7-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="79ac7-289">**Name**</span></span>|<span data-ttu-id="79ac7-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="79ac7-290">**TTL**</span></span>|<span data-ttu-id="79ac7-291">**Type**</span><span class="sxs-lookup"><span data-stu-id="79ac7-291">**Type**</span></span>|<span data-ttu-id="79ac7-292">**Priority**</span><span class="sxs-lookup"><span data-stu-id="79ac7-292">**Priority**</span></span>|<span data-ttu-id="79ac7-293">**Weight**</span><span class="sxs-lookup"><span data-stu-id="79ac7-293">**Weight**</span></span>|<span data-ttu-id="79ac7-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="79ac7-294">**Port**</span></span>|<span data-ttu-id="79ac7-295">**対象**</span><span class="sxs-lookup"><span data-stu-id="79ac7-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79ac7-296">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="79ac7-296">_sip._tls.</span></span> <span data-ttu-id="79ac7-297">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-297">*domain_name*.</span></span> <span data-ttu-id="79ac7-298">(たとえば、_sip. _tls] など)。</span><span class="sxs-lookup"><span data-stu-id="79ac7-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-299">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-300">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-300">3600</span></span>  <br/> |<span data-ttu-id="79ac7-301">SRV</span><span class="sxs-lookup"><span data-stu-id="79ac7-301">SRV</span></span>  <br/> |<span data-ttu-id="79ac7-302">100</span><span class="sxs-lookup"><span data-stu-id="79ac7-302">100</span></span>  <br/> |<span data-ttu-id="79ac7-303">1-d</span><span class="sxs-lookup"><span data-stu-id="79ac7-303">1</span></span>  <br/> |<span data-ttu-id="79ac7-304">443</span><span class="sxs-lookup"><span data-stu-id="79ac7-304">443</span></span>  <br/> |<span data-ttu-id="79ac7-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79ac7-306">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="79ac7-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="79ac7-307">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-307">*domain_name*.</span></span> <span data-ttu-id="79ac7-308">(たとえば、_sipfederationtls. _tcp] など)。</span><span class="sxs-lookup"><span data-stu-id="79ac7-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="79ac7-309">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="79ac7-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="79ac7-310">3600</span><span class="sxs-lookup"><span data-stu-id="79ac7-310">3600</span></span>  <br/> |<span data-ttu-id="79ac7-311">SRV</span><span class="sxs-lookup"><span data-stu-id="79ac7-311">SRV</span></span>  <br/> |<span data-ttu-id="79ac7-312">100</span><span class="sxs-lookup"><span data-stu-id="79ac7-312">100</span></span>  <br/> |<span data-ttu-id="79ac7-313">1-d</span><span class="sxs-lookup"><span data-stu-id="79ac7-313">1</span></span>  <br/> |<span data-ttu-id="79ac7-314">5061</span><span class="sxs-lookup"><span data-stu-id="79ac7-314">5061</span></span>  <br/> |<span data-ttu-id="79ac7-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79ac7-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="79ac7-316">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="79ac7-317">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="79ac7-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="79ac7-318">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="79ac7-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="79ac7-p133">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79ac7-p133">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
