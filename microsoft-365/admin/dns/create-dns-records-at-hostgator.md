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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Hostgator にあるその他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 8adfc4b6154dad0da7dd2fe037c73fcfc4f84d58
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400439"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a><span data-ttu-id="65ef9-103">Microsoft の Hostgator で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="65ef9-103">Create DNS records at Hostgator for Microsoft</span></span>

 <span data-ttu-id="65ef9-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="65ef9-105">使用している DNS ホスティング プロバイダーが Hostgator の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65ef9-106">この記事に記載されている他の手順のいずれかを使用して DNS レコードを追加する前に、最初の procedurebelow を実行して、[ドメインをホスティングアカウントにする](#point-your-domain-to-your-hosting-account)必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="65ef9-107">Hostgator でこれらの変更をすべて行った後、ドメインは Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-107">After you make all of these changes at Hostgator, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="65ef9-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="65ef9-111">ドメインがホスティング アカウントを指すようにする</span><span class="sxs-lookup"><span data-stu-id="65ef9-111">Point your domain to your hosting account</span></span>
<span data-ttu-id="65ef9-112"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-112"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-113">この手順どおりに行ってから、この記事のその他の手順どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-113">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="65ef9-114">この手順に従って、ドメインとホスティング アカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-114">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="65ef9-p102">まず、[このリンク](https://portal.hostgator.com/)を使って Hostgator でドメイン管理ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="65ef9-117">左側の [ **Domains** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-117">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="65ef9-118">[**ドメインの管理**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-118">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="65ef9-119">左側の [ポップアップ] メニューで、[**ネームサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-119">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="65ef9-120">自分のドメインの [**ネームサーバー** ] ページで、[**自動的にこのドメインをホスティングアカウントにポイントする**] ドロップダウンリストで、ドメインに関連付けられているホスティングアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-120">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="65ef9-121">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-121">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="65ef9-122">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="65ef9-122">Add a TXT record for verification</span></span>
<span data-ttu-id="65ef9-123"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-123"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-124">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="65ef9-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="65ef9-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="65ef9-129">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-129">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="65ef9-130">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="65ef9-130">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="65ef9-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="65ef9-131">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="65ef9-132">CPanel アドレスは、次のようになり https://YourSiteAddress:secure-port-number ます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-132">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="65ef9-133">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-133">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65ef9-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="65ef9-135">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-135">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="65ef9-136">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-136">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="65ef9-137">[**ゾーン編集の詳細**] ページの [ **Add a record** ] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-137">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="65ef9-138">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="65ef9-138">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="65ef9-139">**Name**</span><span class="sxs-lookup"><span data-stu-id="65ef9-139">**Name**</span></span> <br/> |<span data-ttu-id="65ef9-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="65ef9-140">**TTL**</span></span> <br/> |<span data-ttu-id="65ef9-141">**Type**</span><span class="sxs-lookup"><span data-stu-id="65ef9-141">**Type**</span></span> <br/> |<span data-ttu-id="65ef9-142">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="65ef9-142">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="65ef9-143">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-143">Use your  *domain_name*.</span></span> <span data-ttu-id="65ef9-144">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="65ef9-144">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-145">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="65ef9-145">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-146">1 </span><span class="sxs-lookup"><span data-stu-id="65ef9-146">1</span></span>  <br/> |<span data-ttu-id="65ef9-147">TXT</span><span class="sxs-lookup"><span data-stu-id="65ef9-147">TXT</span></span>  <br/> |<span data-ttu-id="65ef9-148">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="65ef9-148">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="65ef9-149">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="65ef9-149">**Note:** This is an example.</span></span> <span data-ttu-id="65ef9-150">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-150">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="65ef9-151">確認する方法</span><span class="sxs-lookup"><span data-stu-id="65ef9-151">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="65ef9-152">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-152">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="65ef9-153">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="65ef9-154">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="65ef9-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="65ef9-155">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="65ef9-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="65ef9-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="65ef9-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-158">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="65ef9-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-159">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="65ef9-p110">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="65ef9-163">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="65ef9-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="65ef9-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-164"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-165">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-165">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="65ef9-p111">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="65ef9-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="65ef9-168">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="65ef9-169">CPanel アドレスは、次のようになり https://YourSiteAddress:secure-port-number ます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-169">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="65ef9-170">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-170">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65ef9-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-171">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="65ef9-172">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-172">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="65ef9-173">[**コントロールパネル**] ページの [**電子メール**] 領域で、[ **MX Entry**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-173">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="65ef9-174">[ **Email Routing**] 領域で、[ **Remote Mail Exchanger**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-174">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="65ef9-175">[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-175">Select **Change**.</span></span>
  
5. <span data-ttu-id="65ef9-176">[**新しいレコードの追加**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-176">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="65ef9-177">**Priority**</span><span class="sxs-lookup"><span data-stu-id="65ef9-177">**Priority**</span></span>|<span data-ttu-id="65ef9-178">**Destination**</span><span class="sxs-lookup"><span data-stu-id="65ef9-178">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="65ef9-179">.0</span><span class="sxs-lookup"><span data-stu-id="65ef9-179">0</span></span>  <br/> <span data-ttu-id="65ef9-180">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-180">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="65ef9-181">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-181">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="65ef9-182">**注:**\< *domain-key*  \>Microsoft アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-182">**Note:** Get your \< *domain-key*  \> from your Microsoft account.</span></span>  [<span data-ttu-id="65ef9-183">確認する方法</span><span class="sxs-lookup"><span data-stu-id="65ef9-183">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="65ef9-184">[ **Add New Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-184">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="65ef9-185">その他の MX レコードが [ **MX Records**] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-185">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="65ef9-186">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="65ef9-186">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="65ef9-187"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-187"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-188">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-188">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="65ef9-p115">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="65ef9-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="65ef9-191">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="65ef9-192">CPanel アドレスは、次のようになり https://YourSiteAddress:secure-port-number ます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-192">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="65ef9-193">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-193">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65ef9-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-194">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="65ef9-195">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-195">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="65ef9-196">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-196">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="65ef9-197">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-197">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="65ef9-198">[ **Advanced Zone Editor** ] ページの [ **Add a record** ] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-198">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="65ef9-199">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="65ef9-199">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="65ef9-200">**Name**</span><span class="sxs-lookup"><span data-stu-id="65ef9-200">**Name**</span></span>|<span data-ttu-id="65ef9-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="65ef9-201">**TTL**</span></span>|<span data-ttu-id="65ef9-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="65ef9-202">**Type**</span></span>|<span data-ttu-id="65ef9-203">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="65ef9-203">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="65ef9-204">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="65ef9-204">autodiscover.</span></span> <span data-ttu-id="65ef9-205">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-205">*domain_name*.</span></span> <span data-ttu-id="65ef9-206">(たとえば、autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="65ef9-206">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-207">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-207">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-208">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-208">3600</span></span>  <br/> |<span data-ttu-id="65ef9-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="65ef9-209">CNAME</span></span>  <br/> |<span data-ttu-id="65ef9-210">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-210">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="65ef9-211">sip.</span><span class="sxs-lookup"><span data-stu-id="65ef9-211">sip.</span></span> <span data-ttu-id="65ef9-212">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-212">*domain_name*.</span></span> <span data-ttu-id="65ef9-213">(たとえば、sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="65ef9-213">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-214">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-214">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-215">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-215">3600</span></span>  <br/> |<span data-ttu-id="65ef9-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="65ef9-216">CNAME</span></span>  <br/> |<span data-ttu-id="65ef9-217">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-217">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="65ef9-218">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="65ef9-218">lyncdiscover.</span></span> <span data-ttu-id="65ef9-219">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-219">*domain_name*.</span></span> <span data-ttu-id="65ef9-220">(たとえば、lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="65ef9-220">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-221">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-221">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-222">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-222">3600</span></span>  <br/> |<span data-ttu-id="65ef9-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="65ef9-223">CNAME</span></span>  <br/> |<span data-ttu-id="65ef9-224">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-224">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="65ef9-225">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="65ef9-225">enterpriseregistration.</span></span> <span data-ttu-id="65ef9-226">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-226">*domain_name*.</span></span> <span data-ttu-id="65ef9-227">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="65ef9-227">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-228">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-229">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-229">3600</span></span>  <br/> |<span data-ttu-id="65ef9-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="65ef9-230">CNAME</span></span>  <br/> |<span data-ttu-id="65ef9-231">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="65ef9-231">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="65ef9-232">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="65ef9-232">enterpriseenrollment.</span></span> <span data-ttu-id="65ef9-233">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-233">*domain_name*.</span></span> <span data-ttu-id="65ef9-234">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="65ef9-234">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-235">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-235">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-236">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-236">3600</span></span>  <br/> |<span data-ttu-id="65ef9-237">CNAME</span><span class="sxs-lookup"><span data-stu-id="65ef9-237">CNAME</span></span>  <br/> |<span data-ttu-id="65ef9-238">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-238">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="65ef9-239">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-239">Select **Add Record**.</span></span>

5. <span data-ttu-id="65ef9-240">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-240">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="65ef9-241">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-241">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="65ef9-242">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-242">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="65ef9-243">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="65ef9-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="65ef9-244"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-244"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-245">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="65ef9-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="65ef9-246">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="65ef9-247">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="65ef9-248">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="65ef9-248">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="65ef9-249">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-249">Need examples?</span></span> <span data-ttu-id="65ef9-250">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-250">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="65ef9-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="65ef9-251">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="65ef9-252">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-252">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="65ef9-p124">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="65ef9-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="65ef9-255">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="65ef9-256">CPanel アドレスは、次のようになり https://YourSiteAddress:secure-port-number ます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-256">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="65ef9-257">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-257">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65ef9-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-258">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="65ef9-259">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-259">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="65ef9-260">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-260">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="65ef9-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="65ef9-261">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="65ef9-262">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="65ef9-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="65ef9-263">**Name**</span><span class="sxs-lookup"><span data-stu-id="65ef9-263">**Name**</span></span>|<span data-ttu-id="65ef9-264">**TTL**</span><span class="sxs-lookup"><span data-stu-id="65ef9-264">**TTL**</span></span>|<span data-ttu-id="65ef9-265">**Type**</span><span class="sxs-lookup"><span data-stu-id="65ef9-265">**Type**</span></span>|<span data-ttu-id="65ef9-266">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="65ef9-266">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="65ef9-267">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-267">Use your  *domain_name*.</span></span> <span data-ttu-id="65ef9-268">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="65ef9-268">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-269">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-269">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-270">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-270">3600</span></span>  <br/> |<span data-ttu-id="65ef9-271">TXT</span><span class="sxs-lookup"><span data-stu-id="65ef9-271">TXT</span></span>  <br/> |<span data-ttu-id="65ef9-272">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="65ef9-272">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="65ef9-273">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65ef9-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="65ef9-274">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-274">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="65ef9-275">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="65ef9-275">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="65ef9-276"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="65ef9-276"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ef9-277">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-277">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="65ef9-p128">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="65ef9-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="65ef9-280">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="65ef9-281">CPanel アドレスは、次のようになり https://YourSiteAddress:secure-port-number ます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-281">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="65ef9-282">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65ef9-282">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="65ef9-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="65ef9-283">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="65ef9-284">Microsoft を使用して作業を開始するには、ホストアカウントを Hostgator から購入するか、ネームサーバーを再[委任して microsoft をポイントする](change-nameservers-at-hostgator.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-284">To get started with Microsoft, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Microsoft](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="65ef9-285">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-285">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="65ef9-286">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-286">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="65ef9-287">[ **Advanced DNS Zone Editor**] ページの [ **Add a Record**] 領域で、新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-287">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="65ef9-288">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="65ef9-288">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="65ef9-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="65ef9-289">**Name**</span></span>|<span data-ttu-id="65ef9-290">**TTL**</span><span class="sxs-lookup"><span data-stu-id="65ef9-290">**TTL**</span></span>|<span data-ttu-id="65ef9-291">**Type**</span><span class="sxs-lookup"><span data-stu-id="65ef9-291">**Type**</span></span>|<span data-ttu-id="65ef9-292">**Priority**</span><span class="sxs-lookup"><span data-stu-id="65ef9-292">**Priority**</span></span>|<span data-ttu-id="65ef9-293">**Weight**</span><span class="sxs-lookup"><span data-stu-id="65ef9-293">**Weight**</span></span>|<span data-ttu-id="65ef9-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="65ef9-294">**Port**</span></span>|<span data-ttu-id="65ef9-295">**対象**</span><span class="sxs-lookup"><span data-stu-id="65ef9-295">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="65ef9-296">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="65ef9-296">_sip._tls.</span></span> <span data-ttu-id="65ef9-297">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-297">*domain_name*.</span></span> <span data-ttu-id="65ef9-298">(たとえば、_sip. _tls] など)。</span><span class="sxs-lookup"><span data-stu-id="65ef9-298">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-299">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-299">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-300">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-300">3600</span></span>  <br/> |<span data-ttu-id="65ef9-301">SRV</span><span class="sxs-lookup"><span data-stu-id="65ef9-301">SRV</span></span>  <br/> |<span data-ttu-id="65ef9-302">100</span><span class="sxs-lookup"><span data-stu-id="65ef9-302">100</span></span>  <br/> |<span data-ttu-id="65ef9-303">1 </span><span class="sxs-lookup"><span data-stu-id="65ef9-303">1</span></span>  <br/> |<span data-ttu-id="65ef9-304">443</span><span class="sxs-lookup"><span data-stu-id="65ef9-304">443</span></span>  <br/> |<span data-ttu-id="65ef9-305">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-305">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="65ef9-306">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="65ef9-306">_sipfederationtls._tcp.</span></span> <span data-ttu-id="65ef9-307">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-307">*domain_name*.</span></span> <span data-ttu-id="65ef9-308">(たとえば、_sipfederationtls. _tcp] など)。</span><span class="sxs-lookup"><span data-stu-id="65ef9-308">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="65ef9-309">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="65ef9-309">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="65ef9-310">3600</span><span class="sxs-lookup"><span data-stu-id="65ef9-310">3600</span></span>  <br/> |<span data-ttu-id="65ef9-311">SRV</span><span class="sxs-lookup"><span data-stu-id="65ef9-311">SRV</span></span>  <br/> |<span data-ttu-id="65ef9-312">100</span><span class="sxs-lookup"><span data-stu-id="65ef9-312">100</span></span>  <br/> |<span data-ttu-id="65ef9-313">1 </span><span class="sxs-lookup"><span data-stu-id="65ef9-313">1</span></span>  <br/> |<span data-ttu-id="65ef9-314">5061</span><span class="sxs-lookup"><span data-stu-id="65ef9-314">5061</span></span>  <br/> |<span data-ttu-id="65ef9-315">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="65ef9-315">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="65ef9-316">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-316">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="65ef9-317">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="65ef9-317">Add the other SRV record.</span></span>
    
    <span data-ttu-id="65ef9-318">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="65ef9-318">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="65ef9-p133">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65ef9-p133">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
