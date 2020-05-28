---
title: Microsoft の Namecheap で DNS レコードを作成する
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Namecheap の他のサービスの DNS レコードをセットアップする方法について説明します。
ms.openlocfilehash: 2aae667428aba5ea22ab210c47aa9c994a9acf14
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400390"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="c6976-103">Microsoft の Namecheap で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="c6976-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="c6976-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c6976-105">使用している DNS ホスティング プロバイダーが Namecheap の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="c6976-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c6976-106">これらのレコードを Namecheap で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6976-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c6976-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c6976-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c6976-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c6976-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c6976-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6976-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="c6976-116">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c6976-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c6976-p104">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="c6976-120">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="c6976-122">[**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="c6976-124">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="c6976-126">[**ホストレコード**] セクションで、[**新しいレコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="c6976-128">[ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c6976-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6976-129">[**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="c6976-131">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c6976-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c6976-132">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="c6976-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c6976-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="c6976-133">**Type**</span></span>|<span data-ttu-id="c6976-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="c6976-134">**Host**</span></span>|<span data-ttu-id="c6976-135">**値**</span><span class="sxs-lookup"><span data-stu-id="c6976-135">**Value**</span></span>|<span data-ttu-id="c6976-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6976-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6976-137">TXT</span><span class="sxs-lookup"><span data-stu-id="c6976-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="c6976-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c6976-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="c6976-139">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="c6976-139">**Note:** This is an example.</span></span> <span data-ttu-id="c6976-140">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="c6976-141">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c6976-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c6976-142">30 分</span><span class="sxs-lookup"><span data-stu-id="c6976-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-検証-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="c6976-144">[**変更の保存**] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="c6976-146">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c6976-147">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="c6976-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c6976-148">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="c6976-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c6976-149">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6976-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c6976-150">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c6976-151">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c6976-152">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="c6976-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c6976-156">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c6976-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c6976-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c6976-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c6976-158">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c6976-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c6976-p107">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="c6976-162">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="c6976-164">[**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="c6976-166">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="c6976-168">[ **MAIL SETTINGS**] セクションで、[ **Email Forwarding**] ドロップダウン リストから [ **Custom MX**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c6976-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="c6976-169">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="c6976-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="c6976-171">[ **Add New Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="c6976-173">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="c6976-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="c6976-174">([ **Priority**] ボックスは、[ **Value**] ボックスの右側にある名前のないボックスです。</span><span class="sxs-lookup"><span data-stu-id="c6976-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="c6976-175">ドロップダウンリストから [ **TTL** ] 値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="c6976-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c6976-176">**Type**</span><span class="sxs-lookup"><span data-stu-id="c6976-176">**Type**</span></span>|<span data-ttu-id="c6976-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="c6976-177">**Host**</span></span>|<span data-ttu-id="c6976-178">**Value**</span><span class="sxs-lookup"><span data-stu-id="c6976-178">**Value**</span></span>|<span data-ttu-id="c6976-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c6976-179">**Priority**</span></span>|<span data-ttu-id="c6976-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6976-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6976-181">MX レコード</span><span class="sxs-lookup"><span data-stu-id="c6976-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="c6976-182">\<*domain-key*\>. mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="c6976-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="c6976-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="c6976-184">\**注:\*\*\*\<domain-key\>* Microsoft アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6976-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="c6976-185">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c6976-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c6976-186">.0</span><span class="sxs-lookup"><span data-stu-id="c6976-186">0</span></span>  <br/> <span data-ttu-id="c6976-187">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-187">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="c6976-188">30 分</span><span class="sxs-lookup"><span data-stu-id="c6976-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="c6976-190">[**変更の保存**] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="c6976-192">これ以外の MX レコードがある場合は、次の 2 段階のプロセスに従って、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6976-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="c6976-193">最初に、削除するレコードの [**削除] アイコン**(ごみ箱) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="c6976-195">次に、[**はい]** を選択して削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6976-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="c6976-197">この手順の最初に追加した MX レコード以外の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="c6976-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c6976-198">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c6976-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c6976-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c6976-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c6976-200">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c6976-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c6976-p110">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="c6976-204">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="c6976-206">[**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="c6976-208">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="c6976-210">[**ホストレコード**] セクションで、[**新しいレコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="c6976-212">[ **Type**] ドロップダウンで、[ **CNAME Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c6976-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6976-213">[**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="c6976-215">新しいレコードの空のボックスで、[ **Record Type**] に [ **CNAME**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c6976-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="c6976-216">**種類**</span><span class="sxs-lookup"><span data-stu-id="c6976-216">**Type**</span></span>|<span data-ttu-id="c6976-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="c6976-217">**Host**</span></span>|<span data-ttu-id="c6976-218">**値**</span><span class="sxs-lookup"><span data-stu-id="c6976-218">**Value**</span></span>|<span data-ttu-id="c6976-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6976-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6976-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6976-220">CNAME</span></span>  <br/> |<span data-ttu-id="c6976-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c6976-221">autodiscover</span></span>  <br/> |<span data-ttu-id="c6976-222">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="c6976-223">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-224">3600</span><span class="sxs-lookup"><span data-stu-id="c6976-224">3600</span></span>  <br/> |
    |<span data-ttu-id="c6976-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6976-225">CNAME</span></span>  <br/> |<span data-ttu-id="c6976-226">sip</span><span class="sxs-lookup"><span data-stu-id="c6976-226">sip</span></span>  <br/> |<span data-ttu-id="c6976-227">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c6976-228">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-229">3600</span><span class="sxs-lookup"><span data-stu-id="c6976-229">3600</span></span>  <br/> |
    |<span data-ttu-id="c6976-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6976-230">CNAME</span></span>  <br/> |<span data-ttu-id="c6976-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c6976-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c6976-232">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c6976-233">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-234">3600</span><span class="sxs-lookup"><span data-stu-id="c6976-234">3600</span></span>  <br/> |
    |<span data-ttu-id="c6976-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6976-235">CNAME</span></span>  <br/> |<span data-ttu-id="c6976-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c6976-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c6976-237">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="c6976-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="c6976-238">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-239">3600</span><span class="sxs-lookup"><span data-stu-id="c6976-239">3600</span></span>  <br/> |
    |<span data-ttu-id="c6976-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="c6976-240">CNAME</span></span>  <br/> |<span data-ttu-id="c6976-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c6976-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c6976-242">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="c6976-243">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-244">3600</span><span class="sxs-lookup"><span data-stu-id="c6976-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="c6976-246">[**変更の保存**] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="c6976-248">上記の4つの手順と、表の他の5つの行の値を使用して、残りの5つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="c6976-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c6976-249">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c6976-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c6976-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c6976-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6976-251">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6976-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c6976-252">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c6976-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c6976-253">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c6976-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c6976-254">代わりに、値のセットを含む*1 つ*の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6976-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="c6976-255">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c6976-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="c6976-p112">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="c6976-258">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="c6976-260">[**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="c6976-262">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="c6976-264">[**ホストレコード**] セクションで、[**新しいレコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="c6976-266">[ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c6976-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6976-267">[**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="c6976-269">新規レコードのボックスに、次の値を入力するか、次の表から値をコピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="c6976-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="c6976-270">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="c6976-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c6976-271">**Type**</span><span class="sxs-lookup"><span data-stu-id="c6976-271">**Type**</span></span>|<span data-ttu-id="c6976-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="c6976-272">**Host**</span></span>|<span data-ttu-id="c6976-273">**Value**</span><span class="sxs-lookup"><span data-stu-id="c6976-273">**Value**</span></span>|<span data-ttu-id="c6976-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6976-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6976-275">TXT</span><span class="sxs-lookup"><span data-stu-id="c6976-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="c6976-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c6976-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c6976-277">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6976-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c6976-278">30 分</span><span class="sxs-lookup"><span data-stu-id="c6976-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="c6976-280">[**変更の保存**] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c6976-282">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c6976-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c6976-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c6976-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c6976-p113">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c6976-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="c6976-287">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="c6976-289">[**ドメインリスト**] ページで、編集するドメインの名前を見つけて、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="c6976-291">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="c6976-293">[**ホストレコード**] セクションで、[**新しいレコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="c6976-295">[ **Type**] ドロップダウンで、[ **SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c6976-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6976-296">[**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6976-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="c6976-298">新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c6976-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="c6976-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="c6976-299">**Service**</span></span>|<span data-ttu-id="c6976-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="c6976-300">**Protocol**</span></span>|<span data-ttu-id="c6976-301">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c6976-301">**Priority**</span></span>|<span data-ttu-id="c6976-302">**Weight**</span><span class="sxs-lookup"><span data-stu-id="c6976-302">**Weight**</span></span>|<span data-ttu-id="c6976-303">**Port**</span><span class="sxs-lookup"><span data-stu-id="c6976-303">**Port**</span></span>|<span data-ttu-id="c6976-304">**対象**</span><span class="sxs-lookup"><span data-stu-id="c6976-304">**Target**</span></span>|<span data-ttu-id="c6976-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6976-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c6976-306">_sip</span><span class="sxs-lookup"><span data-stu-id="c6976-306">_sip</span></span>  <br/> |<span data-ttu-id="c6976-307">_tls</span><span class="sxs-lookup"><span data-stu-id="c6976-307">_tls</span></span>  <br/> |<span data-ttu-id="c6976-308">100</span><span class="sxs-lookup"><span data-stu-id="c6976-308">100</span></span>  <br/> |<span data-ttu-id="c6976-309">1 </span><span class="sxs-lookup"><span data-stu-id="c6976-309">1</span></span>  <br/> |<span data-ttu-id="c6976-310">443</span><span class="sxs-lookup"><span data-stu-id="c6976-310">443</span></span>  <br/> |<span data-ttu-id="c6976-311">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="c6976-312">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-313">30 分</span><span class="sxs-lookup"><span data-stu-id="c6976-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="c6976-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c6976-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c6976-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="c6976-315">_tcp</span></span>  <br/> |<span data-ttu-id="c6976-316">100</span><span class="sxs-lookup"><span data-stu-id="c6976-316">100</span></span>  <br/> |<span data-ttu-id="c6976-317">1 </span><span class="sxs-lookup"><span data-stu-id="c6976-317">1</span></span>  <br/> |<span data-ttu-id="c6976-318">5061</span><span class="sxs-lookup"><span data-stu-id="c6976-318">5061</span></span>  <br/> |<span data-ttu-id="c6976-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="c6976-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="c6976-320">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="c6976-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="c6976-321">30 分</span><span class="sxs-lookup"><span data-stu-id="c6976-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="c6976-323">[**変更の保存**] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6976-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="c6976-325">上の 4 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6976-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6976-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6976-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
