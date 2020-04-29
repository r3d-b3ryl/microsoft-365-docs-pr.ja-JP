---
title: Microsoft の Bluehost で DNS レコードを作成する
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: ドメインを確認し、電子メール、Skype for Business Online、および Bluehost のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 1608aebdf984e22e45d7a2469acb0a8002fca2a1
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919553"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="df782-103">Microsoft の Bluehost で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="df782-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="df782-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="df782-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df782-105">使用している DNS ホスティング プロバイダーが Bluehost の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="df782-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df782-106">これらのレコードを Bluehost で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="df782-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="df782-107">Microsoft での Web サイト向け Web ホスティングと DNS の詳細については、「[Microsoft での一般向け Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="df782-p101">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df782-111">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="df782-111">Add a TXT record for verification</span></span>
<span data-ttu-id="df782-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="df782-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="df782-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="df782-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df782-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="df782-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="df782-117">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df782-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="df782-118">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="df782-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="df782-119">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df782-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="df782-120">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="df782-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="df782-121">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="df782-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="df782-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="df782-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="df782-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df782-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="df782-124">**Host Record**</span></span> <br/> |<span data-ttu-id="df782-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df782-125">**TTL**</span></span> <br/> |<span data-ttu-id="df782-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="df782-126">**Type**</span></span> <br/> |<span data-ttu-id="df782-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="df782-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="df782-128">14400</span><span class="sxs-lookup"><span data-stu-id="df782-128">14400</span></span>  <br/> |<span data-ttu-id="df782-129">TXT</span><span class="sxs-lookup"><span data-stu-id="df782-129">TXT</span></span>  <br/> |<span data-ttu-id="df782-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="df782-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="df782-131">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="df782-131">**Note:** This is an example.</span></span> <span data-ttu-id="df782-132">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="df782-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="df782-133">確認する方法</span><span class="sxs-lookup"><span data-stu-id="df782-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="df782-134">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="df782-135">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="df782-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="df782-136">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="df782-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="df782-137">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="df782-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="df782-138">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="df782-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="df782-139">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="df782-140">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="df782-141">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="df782-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df782-145">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="df782-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="df782-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="df782-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="df782-147">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df782-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="df782-148">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="df782-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="df782-149">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df782-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="df782-150">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="df782-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="df782-151">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="df782-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="df782-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="df782-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="df782-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="df782-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="df782-154">**Host Record**</span></span>|<span data-ttu-id="df782-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df782-155">**TTL**</span></span>|<span data-ttu-id="df782-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="df782-156">**Type**</span></span>|<span data-ttu-id="df782-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="df782-157">**Points To**</span></span>|<span data-ttu-id="df782-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="df782-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="df782-159">14400</span><span class="sxs-lookup"><span data-stu-id="df782-159">14400</span></span>  <br/> |<span data-ttu-id="df782-160">MX</span><span class="sxs-lookup"><span data-stu-id="df782-160">MX</span></span>  <br/> | <span data-ttu-id="df782-161">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df782-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="df782-162">**注:** Microsoft アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="df782-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="df782-163">確認する方法</span><span class="sxs-lookup"><span data-stu-id="df782-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="df782-164">.0</span><span class="sxs-lookup"><span data-stu-id="df782-164">0</span></span>  <br/> <span data-ttu-id="df782-165">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![ドロップダウンリストから [種類] を選択する](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="df782-167">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-167">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="df782-169">その他の MX レコードが [ **MX (Mail Exchanger)** ] セクションにある場合は、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="df782-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="df782-170">その他の MX レコードのいずれかで、[削除] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="df782-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![追加の MX レコードごとに [削除] を選択します。](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="df782-172">確認ダイアログボックスで、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![[OK] を選択します。](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="df782-174">同じ手順に従って、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="df782-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="df782-175">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="df782-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="df782-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="df782-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="df782-177">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df782-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="df782-178">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="df782-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="df782-179">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df782-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="df782-180">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="df782-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="df782-181">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="df782-182">[ **A (ホスト)** レコード] セクションで、**自動検出**レコードの行を見つけて、その行に対して [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="df782-183">Microsoft によって必要とされる**自動検出**レコードを追加する*前に*、既存の**自動検出**レコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df782-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="df782-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span><span class="sxs-lookup"><span data-stu-id="df782-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![[削除] を選択します。](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="df782-186">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-186">Select **OK**.</span></span>
    
    ![[OK] を選択します。](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="df782-188">6 つの CNAME レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="df782-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="df782-189">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="df782-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="df782-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="df782-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="df782-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="df782-191">**Host Record**</span></span>|<span data-ttu-id="df782-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df782-192">**TTL**</span></span>|<span data-ttu-id="df782-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="df782-193">**Type**</span></span>|<span data-ttu-id="df782-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="df782-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df782-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df782-195">autodiscover</span></span>  <br/> |<span data-ttu-id="df782-196">14400</span><span class="sxs-lookup"><span data-stu-id="df782-196">14400</span></span>  <br/> |<span data-ttu-id="df782-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="df782-197">CNAME</span></span>  <br/> |<span data-ttu-id="df782-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="df782-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="df782-199">sip</span><span class="sxs-lookup"><span data-stu-id="df782-199">sip</span></span>  <br/> |<span data-ttu-id="df782-200">14400</span><span class="sxs-lookup"><span data-stu-id="df782-200">14400</span></span>  <br/> |<span data-ttu-id="df782-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="df782-201">CNAME</span></span>  <br/> |<span data-ttu-id="df782-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df782-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df782-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df782-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df782-204">14400</span><span class="sxs-lookup"><span data-stu-id="df782-204">14400</span></span>  <br/> |<span data-ttu-id="df782-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="df782-205">CNAME</span></span>  <br/> |<span data-ttu-id="df782-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df782-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df782-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df782-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df782-208">14400</span><span class="sxs-lookup"><span data-stu-id="df782-208">14400</span></span>  <br/> |<span data-ttu-id="df782-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="df782-209">CNAME</span></span>  <br/> |<span data-ttu-id="df782-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df782-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="df782-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df782-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df782-212">14400</span><span class="sxs-lookup"><span data-stu-id="df782-212">14400</span></span>  <br/> |<span data-ttu-id="df782-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="df782-213">CNAME</span></span>  <br/> |<span data-ttu-id="df782-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df782-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![最初の CNAME レコードを作成する](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="df782-216">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-216">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="df782-218">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="df782-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="df782-219">引き続き [ **DNS レコードの追加**] セクションで、表の次の行の値を使用してレコードを作成し、[ **add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="df782-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="df782-220">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="df782-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df782-221">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="df782-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df782-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="df782-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df782-223">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="df782-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df782-224">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="df782-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df782-225">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="df782-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="df782-226">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="df782-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="df782-227">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df782-227">Need examples?</span></span> <span data-ttu-id="df782-228">こちらの[Microsoft の外部ドメイン ネーム システムのレコード](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="df782-229">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df782-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="df782-230">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df782-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="df782-231">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="df782-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="df782-232">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df782-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="df782-233">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="df782-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="df782-234">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="df782-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="df782-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="df782-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="df782-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="df782-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="df782-237">**Host Record**</span></span>|<span data-ttu-id="df782-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df782-238">**TTL**</span></span>|<span data-ttu-id="df782-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="df782-239">**Type**</span></span>|<span data-ttu-id="df782-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="df782-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="df782-241">14400</span><span class="sxs-lookup"><span data-stu-id="df782-241">14400</span></span>  <br/> |<span data-ttu-id="df782-242">TXT</span><span class="sxs-lookup"><span data-stu-id="df782-242">TXT</span></span>  <br/> |<span data-ttu-id="df782-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="df782-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="df782-244">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df782-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![TXT 値をコピーする](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="df782-246">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-246">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="df782-248">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="df782-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="df782-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="df782-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="df782-250">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="df782-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="df782-251">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="df782-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="df782-252">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df782-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="df782-253">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="df782-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="df782-254">[ ***Domain_name*** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="df782-255">2 つの SRV レコードの最初のレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="df782-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="df782-256">[ **DNS Zone Editor**] ページの [ **Add DNS Record**] 領域で、新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="df782-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="df782-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="df782-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="df782-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="df782-258">**Service**</span></span>|<span data-ttu-id="df782-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="df782-259">**Protocol**</span></span>|<span data-ttu-id="df782-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="df782-260">**Host**</span></span>|<span data-ttu-id="df782-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df782-261">**TTL**</span></span>|<span data-ttu-id="df782-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="df782-262">**Type**</span></span>|<span data-ttu-id="df782-263">**Priority**</span><span class="sxs-lookup"><span data-stu-id="df782-263">**Priority**</span></span>|<span data-ttu-id="df782-264">**Weight**</span><span class="sxs-lookup"><span data-stu-id="df782-264">**Weight**</span></span>|<span data-ttu-id="df782-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="df782-265">**Port**</span></span>|<span data-ttu-id="df782-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="df782-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df782-267">_sip</span><span class="sxs-lookup"><span data-stu-id="df782-267">_sip</span></span>  <br/> |<span data-ttu-id="df782-268">_tls</span><span class="sxs-lookup"><span data-stu-id="df782-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="df782-269">14400</span><span class="sxs-lookup"><span data-stu-id="df782-269">14400</span></span>  <br/> |<span data-ttu-id="df782-270">SRV</span><span class="sxs-lookup"><span data-stu-id="df782-270">SRV</span></span>  <br/> |<span data-ttu-id="df782-271">100</span><span class="sxs-lookup"><span data-stu-id="df782-271">100</span></span>  <br/> |<span data-ttu-id="df782-272">1-d</span><span class="sxs-lookup"><span data-stu-id="df782-272">1</span></span>  <br/> |<span data-ttu-id="df782-273">443</span><span class="sxs-lookup"><span data-stu-id="df782-273">443</span></span>  <br/> |<span data-ttu-id="df782-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df782-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="df782-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="df782-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="df782-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="df782-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="df782-277">14400</span><span class="sxs-lookup"><span data-stu-id="df782-277">14400</span></span>  <br/> |<span data-ttu-id="df782-278">SRV</span><span class="sxs-lookup"><span data-stu-id="df782-278">SRV</span></span>  <br/> |<span data-ttu-id="df782-279">100</span><span class="sxs-lookup"><span data-stu-id="df782-279">100</span></span>  <br/> |<span data-ttu-id="df782-280">1-d</span><span class="sxs-lookup"><span data-stu-id="df782-280">1</span></span>  <br/> |<span data-ttu-id="df782-281">5061</span><span class="sxs-lookup"><span data-stu-id="df782-281">5061</span></span>  <br/> |<span data-ttu-id="df782-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="df782-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![新しいレコードの値をコピーする](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="df782-284">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df782-284">Select **add record**.</span></span>
    
    ![[Add Record] を選択します。](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="df782-286">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="df782-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="df782-287">引き続き [ **DNS レコードの追加**] セクションで、表の他の行の値を使用してレコードを作成し、[ **Add record** ] をもう一度選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="df782-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="df782-p114">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df782-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

