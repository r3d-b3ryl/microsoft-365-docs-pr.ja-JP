---
title: Bluehost で Office 365 用の DNS レコードを作成する
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: ドメインを確認し、電子メール、Skype for Business Online、および Bluehost for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 9a5cad6778cb66958539a324befee43ddb2dd8b9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247218"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="75a69-103">Bluehost で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="75a69-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="75a69-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="75a69-105">使用している DNS ホスティング プロバイダーが Bluehost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="75a69-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="75a69-106">これらのレコードを Bluehost で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="75a69-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="75a69-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="75a69-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="75a69-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="75a69-111">Add a TXT record for verification</span></span>
<span data-ttu-id="75a69-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="75a69-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="75a69-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="75a69-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="75a69-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="75a69-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="75a69-117">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75a69-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="75a69-118">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="75a69-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="75a69-119">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a69-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="75a69-120">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="75a69-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="75a69-121">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="75a69-122">[\* \* DNS ゾーンエディター \* \*] ページの [ **Dns レコードの追加**] 領域で、新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="75a69-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="75a69-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="75a69-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75a69-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="75a69-124">**Host Record**</span></span> <br/> |<span data-ttu-id="75a69-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75a69-125">**TTL**</span></span> <br/> |<span data-ttu-id="75a69-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="75a69-126">**Type**</span></span> <br/> |<span data-ttu-id="75a69-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="75a69-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="75a69-128">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-128">14400</span></span>  <br/> |<span data-ttu-id="75a69-129">TXT</span><span class="sxs-lookup"><span data-stu-id="75a69-129">TXT</span></span>  <br/> |<span data-ttu-id="75a69-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="75a69-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="75a69-131">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="75a69-131">**Note:** This is an example.</span></span> <span data-ttu-id="75a69-132">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="75a69-133">確認する方法</span><span class="sxs-lookup"><span data-stu-id="75a69-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="75a69-134">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="75a69-135">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="75a69-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="75a69-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="75a69-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="75a69-137">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="75a69-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="75a69-138">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="75a69-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="75a69-139">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="75a69-140">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="75a69-141">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="75a69-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="75a69-145">MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする</span><span class="sxs-lookup"><span data-stu-id="75a69-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="75a69-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="75a69-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="75a69-147">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75a69-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="75a69-148">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="75a69-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="75a69-149">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a69-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="75a69-150">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="75a69-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="75a69-151">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="75a69-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="75a69-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="75a69-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="75a69-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="75a69-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="75a69-154">**Host Record**</span></span>|<span data-ttu-id="75a69-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75a69-155">**TTL**</span></span>|<span data-ttu-id="75a69-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="75a69-156">**Type**</span></span>|<span data-ttu-id="75a69-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="75a69-157">**Points To**</span></span>|<span data-ttu-id="75a69-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="75a69-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="75a69-159">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-159">14400</span></span>  <br/> |<span data-ttu-id="75a69-160">MX</span><span class="sxs-lookup"><span data-stu-id="75a69-160">MX</span></span>  <br/> | <span data-ttu-id="75a69-161">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="75a69-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="75a69-162">**注:**\<Office 365 アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="75a69-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="75a69-163">確認する方法</span><span class="sxs-lookup"><span data-stu-id="75a69-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="75a69-164">.0</span><span class="sxs-lookup"><span data-stu-id="75a69-164">0</span></span>  <br/> <span data-ttu-id="75a69-165">優先度の詳細については、「[MX 優先度とは](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![ドロップダウンリストから [種類] を選択する](../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="75a69-167">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-167">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="75a69-169">その他の MX レコードが [ **MX (Mail Exchanger)** ] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="75a69-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="75a69-170">その他の MX レコードのいずれかで、[削除] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="75a69-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![追加の MX レコードごとに [削除] を選択します。](../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="75a69-172">確認ダイアログボックスで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![[OK] を選択します。](../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="75a69-174">同じ手順に従って、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="75a69-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="75a69-175">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="75a69-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="75a69-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="75a69-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="75a69-177">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75a69-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="75a69-178">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="75a69-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="75a69-179">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a69-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="75a69-180">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="75a69-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="75a69-181">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="75a69-182">[ **A (ホスト)** レコード] セクションで、**自動検出**レコードの行を見つけて、その行に対して [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="75a69-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="75a69-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![[削除] を選択します。](../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="75a69-186">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75a69-186">Select **OK**.</span></span>
    
    ![[OK] を選択します。](../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="75a69-188">6 つの CNAME レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="75a69-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="75a69-189">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="75a69-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="75a69-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="75a69-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="75a69-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="75a69-191">**Host Record**</span></span>|<span data-ttu-id="75a69-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75a69-192">**TTL**</span></span>|<span data-ttu-id="75a69-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="75a69-193">**Type**</span></span>|<span data-ttu-id="75a69-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="75a69-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75a69-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="75a69-195">autodiscover</span></span>  <br/> |<span data-ttu-id="75a69-196">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-196">14400</span></span>  <br/> |<span data-ttu-id="75a69-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="75a69-197">CNAME</span></span>  <br/> |<span data-ttu-id="75a69-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="75a69-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="75a69-199">sip</span><span class="sxs-lookup"><span data-stu-id="75a69-199">sip</span></span>  <br/> |<span data-ttu-id="75a69-200">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-200">14400</span></span>  <br/> |<span data-ttu-id="75a69-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="75a69-201">CNAME</span></span>  <br/> |<span data-ttu-id="75a69-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75a69-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="75a69-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="75a69-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="75a69-204">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-204">14400</span></span>  <br/> |<span data-ttu-id="75a69-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="75a69-205">CNAME</span></span>  <br/> |<span data-ttu-id="75a69-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75a69-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="75a69-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="75a69-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="75a69-208">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-208">14400</span></span>  <br/> |<span data-ttu-id="75a69-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="75a69-209">CNAME</span></span>  <br/> |<span data-ttu-id="75a69-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="75a69-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="75a69-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="75a69-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="75a69-212">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-212">14400</span></span>  <br/> |<span data-ttu-id="75a69-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="75a69-213">CNAME</span></span>  <br/> |<span data-ttu-id="75a69-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="75a69-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![最初の CNAME レコードを作成する](../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="75a69-216">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-216">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="75a69-218">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="75a69-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="75a69-219">引き続き [ **DNS レコードの追加**] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="75a69-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="75a69-220">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="75a69-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="75a69-221">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="75a69-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="75a69-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="75a69-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="75a69-223">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="75a69-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="75a69-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="75a69-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="75a69-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="75a69-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="75a69-226">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="75a69-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="75a69-227">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="75a69-227">Need examples?</span></span> <span data-ttu-id="75a69-228">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="75a69-228">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="75a69-229">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75a69-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="75a69-230">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75a69-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="75a69-231">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="75a69-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="75a69-232">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a69-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="75a69-233">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="75a69-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="75a69-234">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="75a69-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="75a69-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="75a69-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="75a69-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="75a69-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="75a69-237">**Host Record**</span></span>|<span data-ttu-id="75a69-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75a69-238">**TTL**</span></span>|<span data-ttu-id="75a69-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="75a69-239">**Type**</span></span>|<span data-ttu-id="75a69-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="75a69-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="75a69-241">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-241">14400</span></span>  <br/> |<span data-ttu-id="75a69-242">TXT</span><span class="sxs-lookup"><span data-stu-id="75a69-242">TXT</span></span>  <br/> |<span data-ttu-id="75a69-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="75a69-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="75a69-244">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75a69-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![TXT 値をコピーする](../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="75a69-246">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-246">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="75a69-248">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="75a69-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="75a69-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="75a69-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="75a69-250">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75a69-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="75a69-251">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="75a69-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="75a69-252">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a69-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="75a69-253">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="75a69-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="75a69-254">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="75a69-255">2 つの SRV レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="75a69-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="75a69-256">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="75a69-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="75a69-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="75a69-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="75a69-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="75a69-258">**Service**</span></span>|<span data-ttu-id="75a69-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="75a69-259">**Protocol**</span></span>|<span data-ttu-id="75a69-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="75a69-260">**Host**</span></span>|<span data-ttu-id="75a69-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="75a69-261">**TTL**</span></span>|<span data-ttu-id="75a69-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="75a69-262">**Type**</span></span>|<span data-ttu-id="75a69-263">**Priority**</span><span class="sxs-lookup"><span data-stu-id="75a69-263">**Priority**</span></span>|<span data-ttu-id="75a69-264">**Weight**</span><span class="sxs-lookup"><span data-stu-id="75a69-264">**Weight**</span></span>|<span data-ttu-id="75a69-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="75a69-265">**Port**</span></span>|<span data-ttu-id="75a69-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="75a69-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="75a69-267">_sip</span><span class="sxs-lookup"><span data-stu-id="75a69-267">_sip</span></span>  <br/> |<span data-ttu-id="75a69-268">_tls</span><span class="sxs-lookup"><span data-stu-id="75a69-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="75a69-269">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-269">14400</span></span>  <br/> |<span data-ttu-id="75a69-270">SRV</span><span class="sxs-lookup"><span data-stu-id="75a69-270">SRV</span></span>  <br/> |<span data-ttu-id="75a69-271">100</span><span class="sxs-lookup"><span data-stu-id="75a69-271">100</span></span>  <br/> |<span data-ttu-id="75a69-272">1-d</span><span class="sxs-lookup"><span data-stu-id="75a69-272">1</span></span>  <br/> |<span data-ttu-id="75a69-273">443</span><span class="sxs-lookup"><span data-stu-id="75a69-273">443</span></span>  <br/> |<span data-ttu-id="75a69-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75a69-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="75a69-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="75a69-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="75a69-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="75a69-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="75a69-277">14400</span><span class="sxs-lookup"><span data-stu-id="75a69-277">14400</span></span>  <br/> |<span data-ttu-id="75a69-278">SRV</span><span class="sxs-lookup"><span data-stu-id="75a69-278">SRV</span></span>  <br/> |<span data-ttu-id="75a69-279">100</span><span class="sxs-lookup"><span data-stu-id="75a69-279">100</span></span>  <br/> |<span data-ttu-id="75a69-280">1-d</span><span class="sxs-lookup"><span data-stu-id="75a69-280">1</span></span>  <br/> |<span data-ttu-id="75a69-281">5061</span><span class="sxs-lookup"><span data-stu-id="75a69-281">5061</span></span>  <br/> |<span data-ttu-id="75a69-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="75a69-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![新しいレコードの値をコピーする](../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="75a69-284">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75a69-284">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="75a69-286">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="75a69-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="75a69-287">引き続き [ **DNS レコードの追加**] セクションで、表の他の行の値を使用してレコードを作成し、[ **Add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="75a69-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="75a69-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75a69-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

