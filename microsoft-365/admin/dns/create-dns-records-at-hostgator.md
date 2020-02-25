---
title: Hostgator で Office 365 用の DNS レコードを作成する
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: ドメインを確認して、電子メール、Skype for Business Online、および Office 365 用のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: cb0b26081e5946ed2558d090c976847197ed7eb8
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249146"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a><span data-ttu-id="e7112-103">Hostgator で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="e7112-103">Create DNS records at Hostgator for Office 365</span></span>

 <span data-ttu-id="e7112-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e7112-105">使用している DNS ホスティング プロバイダーが Hostgator の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7112-105">If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e7112-106">この記事に記載されている他の手順のいずれかを使用して DNS レコードを追加する前に、最初の procedurebelow を実行して、[ドメインをホスティングアカウントにする](#point-your-domain-to-your-hosting-account)必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-106">You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article.</span></span> 

<span data-ttu-id="e7112-107">これらの変更のすべてを Hostgator で行うと、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="e7112-107">After you make all of these changes at Hostgator, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="e7112-108">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-108">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7112-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="e7112-112">ドメインがホスティング アカウントを指すようにする</span><span class="sxs-lookup"><span data-stu-id="e7112-112">Point your domain to your hosting account</span></span>
<span data-ttu-id="e7112-113"><a name="BKMK_PointDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-113"><a name="BKMK_PointDomain"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-114">この手順どおりに行ってから、この記事のその他の手順どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-114">You must perform this procedure before you perform any of the other procedures in this article.</span></span> 
  
<span data-ttu-id="e7112-115">この手順に従って、ドメインとホスティング アカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e7112-115">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="e7112-p102">まず、[このリンク](https://portal.hostgator.com/)を使って Hostgator でドメイン管理ページにアクセスします。 ログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p102">To get started, go to your domain management page at Hostgator by using [this link](https://portal.hostgator.com/). You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="e7112-118">左側の [ **Domains** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e7112-118">Select **Domains** on the left.</span></span>
  
3. <span data-ttu-id="e7112-119">[**ドメインの管理**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-119">On the **Manage Domains** page, select the domain you want to update.</span></span> 
  
4. <span data-ttu-id="e7112-120">左側の [ポップアップ] メニューで、[**ネームサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-120">On the pop-out menu on the left, select **Name Servers**.</span></span>
  
5. <span data-ttu-id="e7112-121">自分のドメインの [**ネームサーバー** ] ページで、[**自動的にこのドメインをホスティングアカウントにポイントする**] ドロップダウンリストで、ドメインに関連付けられているホスティングアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-121">On the **Name Servers** page for your domain, in the **Automatically point this domain to my hosting account** drop-down list, choose the hosting account that is associated with your domain.</span></span> 
  
6. <span data-ttu-id="e7112-122">[ **Save Name Servers**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e7112-122">Select **Save Name Servers**.</span></span>
    
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e7112-123">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e7112-123">Add a TXT record for verification</span></span>
<span data-ttu-id="e7112-124"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-124"><a name="BKMK_verify"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-125">この手順の前に、まず、この記事の最初のセクション「[ドメインをホスティング アカウントにポイントする](#point-your-domain-to-your-hosting-account)」の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-125">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
<span data-ttu-id="e7112-p103">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7112-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e7112-130">To get started, go to your cPanel page at Hostgator.</span><span class="sxs-lookup"><span data-stu-id="e7112-130">To get started, go to your cPanel page at Hostgator.</span></span> <span data-ttu-id="e7112-131">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="e7112-131">You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="e7112-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="e7112-132">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="e7112-133">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="e7112-133">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="e7112-134">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e7112-134">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7112-p107">cPanel をドメインに関連付けるには、Hostgator でのホスティング アカウントが必要です。 Office 365 を使い始めるには、Hostgator からホスティング アカウントを購入するか、[ネームサーバーの再委任を行ってポイント先を Office 365 にします](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="e7112-p107">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="e7112-137">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-137">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="e7112-138">[**ゾーン編集の詳細**] ページの [ **Add a record** ] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e7112-138">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7112-139">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="e7112-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7112-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7112-140">**Name**</span></span> <br/> |<span data-ttu-id="e7112-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7112-141">**TTL**</span></span> <br/> |<span data-ttu-id="e7112-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7112-142">**Type**</span></span> <br/> |<span data-ttu-id="e7112-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="e7112-143">**TXT Data**</span></span> <br/> |
    |<span data-ttu-id="e7112-144">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7112-144">Use your  *domain_name*.</span></span> <span data-ttu-id="e7112-145">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="e7112-145">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-146">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="e7112-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-147">1-d</span><span class="sxs-lookup"><span data-stu-id="e7112-147">1</span></span>  <br/> |<span data-ttu-id="e7112-148">TXT</span><span class="sxs-lookup"><span data-stu-id="e7112-148">TXT</span></span>  <br/> |<span data-ttu-id="e7112-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e7112-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e7112-150">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="e7112-150">**Note:** This is an example.</span></span> <span data-ttu-id="e7112-151">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-151">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="e7112-152">確認する方法</span><span class="sxs-lookup"><span data-stu-id="e7112-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="e7112-153">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="e7112-154">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="e7112-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e7112-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="e7112-155">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="e7112-156">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="e7112-156">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e7112-157">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7112-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e7112-158">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e7112-159">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e7112-160">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e7112-p110">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="e7112-164">MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする</span><span class="sxs-lookup"><span data-stu-id="e7112-164">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="e7112-165"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-165"><a name="BKMK_add_MX"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-166">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-166">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="e7112-p111">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p111">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="e7112-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="e7112-169">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="e7112-170">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="e7112-170">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="e7112-171">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e7112-171">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7112-p113">cPanel をドメインに関連付けるには、Hostgator でのホスティング アカウントが必要です。 Office 365 を使い始めるには、Hostgator からホスティング アカウントを購入するか、[ネームサーバーの再委任を行ってポイント先を Office 365 にします](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="e7112-p113">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="e7112-174">[**コントロールパネル**] ページの [**電子メール**] 領域で、[ **MX Entry**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-174">On the **Control Panel** page, in the **Email** area, select **MX Entry**.</span></span>
    
 
3. <span data-ttu-id="e7112-175">[ **Email Routing**] 領域で、[ **Remote Mail Exchanger**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e7112-175">In the **Email Routing** area, select **Remote Mail Exchanger**.</span></span>

4. <span data-ttu-id="e7112-176">[**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-176">Select **Change**.</span></span>
  
5. <span data-ttu-id="e7112-177">[**新しいレコードの追加**] 領域にある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e7112-177">In the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="e7112-178">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e7112-178">**Priority**</span></span>|<span data-ttu-id="e7112-179">**Destination**</span><span class="sxs-lookup"><span data-stu-id="e7112-179">**Destination**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="e7112-180">.0</span><span class="sxs-lookup"><span data-stu-id="e7112-180">0</span></span>  <br/> <span data-ttu-id="e7112-181">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-181">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="e7112-182">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7112-182">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e7112-183">**注:**\< Office 365 アカウントから*ドメインキー* \>を取得します。  </span><span class="sxs-lookup"><span data-stu-id="e7112-183">**Note:** Get your \< *domain-key*  \> from your Office 365 account.</span></span>  [<span data-ttu-id="e7112-184">確認する方法</span><span class="sxs-lookup"><span data-stu-id="e7112-184">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
  
6. <span data-ttu-id="e7112-185">[ **Add New Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-185">Select **Add New Record**.</span></span>
   
 
7. <span data-ttu-id="e7112-186">その他の MX レコードが [ **MX Records**] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7112-186">If there are any other MX records in the **MX Records** section, remove each of them.</span></span> 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="e7112-187">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e7112-187">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="e7112-188"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-188"><a name="BKMK_add_CNAME"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-189">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-189">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="e7112-p115">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p115">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="e7112-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="e7112-192">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="e7112-193">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="e7112-193">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="e7112-194">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e7112-194">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7112-p117">cPanel をドメインに関連付けるには、Hostgator でのホスティング アカウントが必要です。 Office 365 を使い始めるには、Hostgator からホスティング アカウントを購入するか、[ネームサーバーの再委任を行ってポイント先を Office 365 にします](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="e7112-p117">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="e7112-197">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-197">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="e7112-198">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7112-198">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="e7112-199">[ **Advanced Zone Editor** ] ページの [ **Add a record** ] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e7112-199">On the **Advanced Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e7112-200">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="e7112-200">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7112-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7112-201">**Name**</span></span>|<span data-ttu-id="e7112-202">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7112-202">**TTL**</span></span>|<span data-ttu-id="e7112-203">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7112-203">**Type**</span></span>|<span data-ttu-id="e7112-204">**CNAME**</span><span class="sxs-lookup"><span data-stu-id="e7112-204">**CNAME**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7112-205">autodiscover.</span><span class="sxs-lookup"><span data-stu-id="e7112-205">autodiscover.</span></span> <span data-ttu-id="e7112-206">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-206">*domain_name*.</span></span> <span data-ttu-id="e7112-207">(たとえば、autodiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="e7112-207">(for example, autodiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-208">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-208">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-209">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-209">3600</span></span>  <br/> |<span data-ttu-id="e7112-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7112-210">CNAME</span></span>  <br/> |<span data-ttu-id="e7112-211">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e7112-211">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e7112-212">sip.</span><span class="sxs-lookup"><span data-stu-id="e7112-212">sip.</span></span> <span data-ttu-id="e7112-213">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-213">*domain_name*.</span></span> <span data-ttu-id="e7112-214">(たとえば、sip.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="e7112-214">(for example, sip.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-215">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-215">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-216">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-216">3600</span></span>  <br/> |<span data-ttu-id="e7112-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7112-217">CNAME</span></span>  <br/> |<span data-ttu-id="e7112-218">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7112-218">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e7112-219">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="e7112-219">lyncdiscover.</span></span> <span data-ttu-id="e7112-220">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-220">*domain_name*.</span></span> <span data-ttu-id="e7112-221">(たとえば、lyncdiscover.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="e7112-221">(for example, lyncdiscover.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-222">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-222">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-223">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-223">3600</span></span>  <br/> |<span data-ttu-id="e7112-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7112-224">CNAME</span></span>  <br/> |<span data-ttu-id="e7112-225">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7112-225">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e7112-226">enterpriseregistration.</span><span class="sxs-lookup"><span data-stu-id="e7112-226">enterpriseregistration.</span></span> <span data-ttu-id="e7112-227">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-227">*domain_name*.</span></span> <span data-ttu-id="e7112-228">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="e7112-228">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-229">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-229">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-230">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-230">3600</span></span>  <br/> |<span data-ttu-id="e7112-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7112-231">CNAME</span></span>  <br/> |<span data-ttu-id="e7112-232">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e7112-232">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="e7112-233">enterpriseenrollment.</span><span class="sxs-lookup"><span data-stu-id="e7112-233">enterpriseenrollment.</span></span> <span data-ttu-id="e7112-234">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-234">*domain_name*.</span></span> <span data-ttu-id="e7112-235">(たとえば、enterpriseregistration.fourthcoffee.com)</span><span class="sxs-lookup"><span data-stu-id="e7112-235">(for example, enterpriseregistration.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-236">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-236">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-237">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-237">3600</span></span>  <br/> |<span data-ttu-id="e7112-238">CNAME</span><span class="sxs-lookup"><span data-stu-id="e7112-238">CNAME</span></span>  <br/> |<span data-ttu-id="e7112-239">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e7112-239">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |

  
4. <span data-ttu-id="e7112-240">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-240">Select **Add Record**.</span></span>

5. <span data-ttu-id="e7112-241">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="e7112-241">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="e7112-242">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="e7112-242">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
    <span data-ttu-id="e7112-243">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e7112-243">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e7112-244">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e7112-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e7112-245"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-245"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-246">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="e7112-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e7112-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="e7112-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e7112-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7112-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="e7112-249">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="e7112-249">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="e7112-250">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e7112-250">Need examples?</span></span> <span data-ttu-id="e7112-251">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="e7112-251">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="e7112-252">SPF レコードを確認するには、[SPF の検証ツール](../setup/domains-faq.md)を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e7112-252">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e7112-253">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-253">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="e7112-p124">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p124">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="e7112-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="e7112-256">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="e7112-257">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="e7112-257">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="e7112-258">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e7112-258">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7112-p126">cPanel をドメインに関連付けるには、Hostgator でのホスティング アカウントが必要です。 Office 365 を使い始めるには、Hostgator からホスティング アカウントを購入するか、[ネームサーバーの再委任を行ってポイント先を Office 365 にします](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="e7112-p126">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="e7112-261">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-261">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>
    
3. <span data-ttu-id="e7112-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e7112-262">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e7112-263">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="e7112-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7112-264">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7112-264">**Name**</span></span>|<span data-ttu-id="e7112-265">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7112-265">**TTL**</span></span>|<span data-ttu-id="e7112-266">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7112-266">**Type**</span></span>|<span data-ttu-id="e7112-267">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="e7112-267">**TXT Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7112-268">*Domain_name*を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7112-268">Use your  *domain_name*.</span></span> <span data-ttu-id="e7112-269">(for example, fourthcoffee.com.)</span><span class="sxs-lookup"><span data-stu-id="e7112-269">(for example, fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-270">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-270">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-271">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-271">3600</span></span>  <br/> |<span data-ttu-id="e7112-272">TXT</span><span class="sxs-lookup"><span data-stu-id="e7112-272">TXT</span></span>  <br/> |<span data-ttu-id="e7112-273">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e7112-273">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e7112-274">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7112-274">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
  
4. <span data-ttu-id="e7112-275">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-275">Select **Add Record**.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="e7112-276">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="e7112-276">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="e7112-277"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e7112-277"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7112-278">この手順を進める前に、この記事の最初のセクション「[ドメインがホスティング アカウントを指すようにする](#point-your-domain-to-your-hosting-account)」に記載されている手順の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7112-278">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account).</span></span> 
  
1. <span data-ttu-id="e7112-p128">開始するには、Hostgator で自分の cPanel ページに移動します。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="e7112-p128">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="e7112-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span><span class="sxs-lookup"><span data-stu-id="e7112-281">(Each hosted account at Hostgator is assigned a unique cPanel address.</span></span> <span data-ttu-id="e7112-282">CPanel アドレスは、次https://YourSiteAddress:secure-port-numberのようになります。</span><span class="sxs-lookup"><span data-stu-id="e7112-282">Your cPanel address should look like this: https://YourSiteAddress:secure-port-number.</span></span> <span data-ttu-id="e7112-283">Hostgator から受信したサインアップ電子メールでは、そのアドレスが指定され、**ホスト**ページでも cpanel リンクが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e7112-283">The sign-up email you received from Hostgator will specify that address, and a cPanel link is also available on the **Hosting** page.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7112-p130">cPanel をドメインに関連付けるには、Hostgator でのホスティング アカウントが必要です。 Office 365 を使い始めるには、Hostgator からホスティング アカウントを購入するか、[ネームサーバーの再委任を行ってポイント先を Office 365 にします](change-nameservers-at-hostgator.md)。</span><span class="sxs-lookup"><span data-stu-id="e7112-p130">To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md).</span></span> 
  
2. <span data-ttu-id="e7112-286">[**コントロールパネル**] ページの [**ドメイン**] 領域で、[ **Advanced Zone Editor**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-286">On the **Control Panel** page, in the **Domains** area, select **Advanced Zone Editor**.</span></span>

    
3. <span data-ttu-id="e7112-287">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7112-287">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e7112-288">[ **Advanced DNS Zone Editor**] ページの [ **Add a Record**] 領域で、新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e7112-288">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e7112-289">(ドロップダウン リストから [ **Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="e7112-289">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e7112-290">**Name**</span><span class="sxs-lookup"><span data-stu-id="e7112-290">**Name**</span></span>|<span data-ttu-id="e7112-291">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e7112-291">**TTL**</span></span>|<span data-ttu-id="e7112-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7112-292">**Type**</span></span>|<span data-ttu-id="e7112-293">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e7112-293">**Priority**</span></span>|<span data-ttu-id="e7112-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="e7112-294">**Weight**</span></span>|<span data-ttu-id="e7112-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="e7112-295">**Port**</span></span>|<span data-ttu-id="e7112-296">**対象**</span><span class="sxs-lookup"><span data-stu-id="e7112-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e7112-297">_sip _tls。</span><span class="sxs-lookup"><span data-stu-id="e7112-297">_sip._tls.</span></span> <span data-ttu-id="e7112-298">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-298">*domain_name*.</span></span> <span data-ttu-id="e7112-299">(たとえば、_sip. _tls] など)。</span><span class="sxs-lookup"><span data-stu-id="e7112-299">(for example, _sip._tls.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-300">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-300">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-301">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-301">3600</span></span>  <br/> |<span data-ttu-id="e7112-302">SRV</span><span class="sxs-lookup"><span data-stu-id="e7112-302">SRV</span></span>  <br/> |<span data-ttu-id="e7112-303">100</span><span class="sxs-lookup"><span data-stu-id="e7112-303">100</span></span>  <br/> |<span data-ttu-id="e7112-304">1-d</span><span class="sxs-lookup"><span data-stu-id="e7112-304">1</span></span>  <br/> |<span data-ttu-id="e7112-305">443</span><span class="sxs-lookup"><span data-stu-id="e7112-305">443</span></span>  <br/> |<span data-ttu-id="e7112-306">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7112-306">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e7112-307">_sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="e7112-307">_sipfederationtls._tcp.</span></span> <span data-ttu-id="e7112-308">*domain_name*します。</span><span class="sxs-lookup"><span data-stu-id="e7112-308">*domain_name*.</span></span> <span data-ttu-id="e7112-309">(たとえば、_sipfederationtls. _tcp] など)。</span><span class="sxs-lookup"><span data-stu-id="e7112-309">(for example, _sipfederationtls._tcp.fourthcoffee.com.)</span></span>  <br/> <span data-ttu-id="e7112-310">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="e7112-310">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="e7112-311">3600</span><span class="sxs-lookup"><span data-stu-id="e7112-311">3600</span></span>  <br/> |<span data-ttu-id="e7112-312">SRV</span><span class="sxs-lookup"><span data-stu-id="e7112-312">SRV</span></span>  <br/> |<span data-ttu-id="e7112-313">100</span><span class="sxs-lookup"><span data-stu-id="e7112-313">100</span></span>  <br/> |<span data-ttu-id="e7112-314">1-d</span><span class="sxs-lookup"><span data-stu-id="e7112-314">1</span></span>  <br/> |<span data-ttu-id="e7112-315">5061</span><span class="sxs-lookup"><span data-stu-id="e7112-315">5061</span></span>  <br/> |<span data-ttu-id="e7112-316">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e7112-316">sipfed.online.lync.com</span></span>  <br/> |
   

4. <span data-ttu-id="e7112-317">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7112-317">Select **Add Record**.</span></span>

  
5. <span data-ttu-id="e7112-318">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7112-318">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e7112-319">[ **Add a record** ] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="e7112-319">In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e7112-p133">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7112-p133">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
