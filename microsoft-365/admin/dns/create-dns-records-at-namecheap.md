---
title: Namecheap で Microsoft 用の DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Namecheap for Microsoft でドメインを確認し、メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 1e0fa8839e4ceae5074059d6ae05e3c7456611c2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657841"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="a601f-103">Namecheap で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a601f-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="a601f-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a601f-105">使用している DNS ホスティング プロバイダーが Namecheap の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="a601f-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a601f-106">Namecheap でこれらのレコードを追加すると、ドメインは Microsoft サービスで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a601f-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a601f-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a601f-110">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a601f-110">Add a TXT record for verification</span></span>
<span data-ttu-id="a601f-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a601f-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a601f-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a601f-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a601f-116">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a601f-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a601f-p104">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a601f-120">ランディング ページ **の [** アカウント] **で**、ドロップダウン **リストから** [ドメイン一覧] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a601f-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span><span class="sxs-lookup"><span data-stu-id="a601f-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a601f-124">Select **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="a601f-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a601f-126">[HOST **RECORDS] セクションで** 、[ADD **NEW RECORD] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a601f-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a601f-128">[ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a601f-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a601f-129">[ **新しいレコード** の追加] を選択すると、[種類] ドロップダウン **が自動的に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a601f-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="a601f-131">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a601f-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a601f-132">(ドロップダウン リスト **から TTL** 値を選択します)。</span><span class="sxs-lookup"><span data-stu-id="a601f-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a601f-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="a601f-133">**Type**</span></span>|<span data-ttu-id="a601f-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="a601f-134">**Host**</span></span>|<span data-ttu-id="a601f-135">**Value**</span><span class="sxs-lookup"><span data-stu-id="a601f-135">**Value**</span></span>|<span data-ttu-id="a601f-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a601f-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a601f-137">TXT</span><span class="sxs-lookup"><span data-stu-id="a601f-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a601f-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a601f-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="a601f-139">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="a601f-139">**Note:** This is an example.</span></span> <span data-ttu-id="a601f-140">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="a601f-141">確認する方法</span><span class="sxs-lookup"><span data-stu-id="a601f-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a601f-142">30 分</span><span class="sxs-lookup"><span data-stu-id="a601f-142">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="a601f-144">[変更 **の保存]** (チェック マーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="a601f-146">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="a601f-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a601f-147">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="a601f-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a601f-148">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="a601f-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a601f-149">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a601f-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a601f-150">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a601f-151">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a601f-152">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="a601f-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a601f-156">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="a601f-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a601f-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a601f-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="a601f-158">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a601f-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a601f-p107">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a601f-162">ランディング ページ **の [** アカウント] **で**、ドロップダウン **リストから** [ドメイン一覧] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a601f-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span><span class="sxs-lookup"><span data-stu-id="a601f-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a601f-166">Select **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="a601f-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a601f-168">[ **MAIL SETTINGS**] セクションで、[ **Email Forwarding**] ドロップダウン リストから [ **Custom MX**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a601f-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="a601f-169">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="a601f-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="a601f-171">[新しい **レコードの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a601f-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-BP-Configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="a601f-173">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="a601f-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="a601f-174">([ **Priority**] ボックスは、[ **Value**] ボックスの右側にある名前のないボックスです。</span><span class="sxs-lookup"><span data-stu-id="a601f-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="a601f-175">ドロップダウン リスト **から TTL** 値を選択します)。</span><span class="sxs-lookup"><span data-stu-id="a601f-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a601f-176">**Type**</span><span class="sxs-lookup"><span data-stu-id="a601f-176">**Type**</span></span>|<span data-ttu-id="a601f-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="a601f-177">**Host**</span></span>|<span data-ttu-id="a601f-178">**Value**</span><span class="sxs-lookup"><span data-stu-id="a601f-178">**Value**</span></span>|<span data-ttu-id="a601f-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a601f-179">**Priority**</span></span>|<span data-ttu-id="a601f-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a601f-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a601f-181">MX レコード</span><span class="sxs-lookup"><span data-stu-id="a601f-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="a601f-182">\<*domain-key*\>.mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="a601f-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a601f-183">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="a601f-184">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a601f-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="a601f-185">確認する方法</span><span class="sxs-lookup"><span data-stu-id="a601f-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a601f-186">0</span><span class="sxs-lookup"><span data-stu-id="a601f-186">0</span></span>  <br/> <span data-ttu-id="a601f-187">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-187">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="a601f-188">30 分</span><span class="sxs-lookup"><span data-stu-id="a601f-188">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="a601f-190">[変更 **の保存]** (チェック マーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="a601f-192">これ以外の MX レコードがある場合は、次の 2 段階のプロセスに従って、それぞれのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="a601f-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="a601f-193">最初に、 **削除するレコードの** [削除] アイコン (ごみ箱) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="a601f-195">次に、[ **はい] を** 選択して削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="a601f-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="a601f-197">この手順の最初に追加した MX レコード以外の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="a601f-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a601f-198">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a601f-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a601f-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a601f-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="a601f-200">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a601f-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a601f-p110">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a601f-204">ランディング ページ **の [** アカウント] **で**、ドロップダウン **リストから** [ドメイン一覧] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a601f-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span><span class="sxs-lookup"><span data-stu-id="a601f-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a601f-208">Select **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="a601f-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a601f-210">[HOST **RECORDS] セクションで** 、[ADD **NEW RECORD] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a601f-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a601f-212">[ **Type**] ドロップダウンで、[ **CNAME Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a601f-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a601f-213">[ **新しいレコード** の追加] を選択すると、[種類] ドロップダウン **が自動的に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a601f-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="a601f-215">新しいレコードの空のボックスで、[ **Record Type**] に [ **CNAME**] を選び、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a601f-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a601f-216">**種類**</span><span class="sxs-lookup"><span data-stu-id="a601f-216">**Type**</span></span>|<span data-ttu-id="a601f-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="a601f-217">**Host**</span></span>|<span data-ttu-id="a601f-218">**Value**</span><span class="sxs-lookup"><span data-stu-id="a601f-218">**Value**</span></span>|<span data-ttu-id="a601f-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a601f-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a601f-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="a601f-220">CNAME</span></span>  <br/> |<span data-ttu-id="a601f-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a601f-221">autodiscover</span></span>  <br/> |<span data-ttu-id="a601f-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a601f-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="a601f-223">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-224">3600</span><span class="sxs-lookup"><span data-stu-id="a601f-224">3600</span></span>  <br/> |
    |<span data-ttu-id="a601f-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="a601f-225">CNAME</span></span>  <br/> |<span data-ttu-id="a601f-226">sip</span><span class="sxs-lookup"><span data-stu-id="a601f-226">sip</span></span>  <br/> |<span data-ttu-id="a601f-227">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a601f-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a601f-228">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-229">3600</span><span class="sxs-lookup"><span data-stu-id="a601f-229">3600</span></span>  <br/> |
    |<span data-ttu-id="a601f-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="a601f-230">CNAME</span></span>  <br/> |<span data-ttu-id="a601f-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a601f-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a601f-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a601f-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a601f-233">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-234">3600</span><span class="sxs-lookup"><span data-stu-id="a601f-234">3600</span></span>  <br/> |
    |<span data-ttu-id="a601f-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="a601f-235">CNAME</span></span>  <br/> |<span data-ttu-id="a601f-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a601f-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a601f-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a601f-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="a601f-238">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-239">3600</span><span class="sxs-lookup"><span data-stu-id="a601f-239">3600</span></span>  <br/> |
    |<span data-ttu-id="a601f-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="a601f-240">CNAME</span></span>  <br/> |<span data-ttu-id="a601f-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a601f-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a601f-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a601f-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="a601f-243">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-244">3600</span><span class="sxs-lookup"><span data-stu-id="a601f-244">3600</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="a601f-246">[変更 **の保存]** (チェック マーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="a601f-248">前の 4 つの手順と表の他の 5 行の値を使用して、他の 5 つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a601f-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a601f-249">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a601f-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a601f-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a601f-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a601f-251">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a601f-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a601f-252">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a601f-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a601f-253">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="a601f-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a601f-254">代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a601f-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="a601f-255">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a601f-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="a601f-p112">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="a601f-258">ランディング ページ **の [** アカウント] **で**、ドロップダウン **リストから** [ドメイン一覧] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a601f-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span><span class="sxs-lookup"><span data-stu-id="a601f-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a601f-262">Select **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="a601f-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a601f-264">[HOST **RECORDS] セクションで** 、[ADD **NEW RECORD] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a601f-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a601f-266">[ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a601f-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a601f-267">[ **新しいレコード** の追加] を選択すると、[種類] ドロップダウン **が自動的に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a601f-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="a601f-269">新規レコードのボックスに、次の値を入力するか、次の表から値をコピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="a601f-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="a601f-270">(ドロップダウン リスト **から TTL** 値を選択します)。</span><span class="sxs-lookup"><span data-stu-id="a601f-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a601f-271">**Type**</span><span class="sxs-lookup"><span data-stu-id="a601f-271">**Type**</span></span>|<span data-ttu-id="a601f-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="a601f-272">**Host**</span></span>|<span data-ttu-id="a601f-273">**Value**</span><span class="sxs-lookup"><span data-stu-id="a601f-273">**Value**</span></span>|<span data-ttu-id="a601f-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a601f-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a601f-275">TXT</span><span class="sxs-lookup"><span data-stu-id="a601f-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a601f-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a601f-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a601f-277">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a601f-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="a601f-278">30 分</span><span class="sxs-lookup"><span data-stu-id="a601f-278">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="a601f-280">[変更 **の保存]** (チェック マーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a601f-282">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a601f-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a601f-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a601f-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a601f-p113">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a601f-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a601f-287">ランディング ページ **の [** アカウント] **で**、ドロップダウン **リストから** [ドメイン一覧] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a601f-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span><span class="sxs-lookup"><span data-stu-id="a601f-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a601f-291">Select **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="a601f-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a601f-293">[HOST **RECORDS] セクションで** 、[ADD **NEW RECORD] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a601f-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a601f-295">[ **Type**] ドロップダウンで、[ **SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a601f-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a601f-296">[ **新しいレコード** の追加] を選択すると、[種類] ドロップダウン **が自動的に表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a601f-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="a601f-298">新規レコードの空のボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a601f-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="a601f-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="a601f-299">**Service**</span></span>|<span data-ttu-id="a601f-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a601f-300">**Protocol**</span></span>|<span data-ttu-id="a601f-301">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a601f-301">**Priority**</span></span>|<span data-ttu-id="a601f-302">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a601f-302">**Weight**</span></span>|<span data-ttu-id="a601f-303">**Port**</span><span class="sxs-lookup"><span data-stu-id="a601f-303">**Port**</span></span>|<span data-ttu-id="a601f-304">**対象**</span><span class="sxs-lookup"><span data-stu-id="a601f-304">**Target**</span></span>|<span data-ttu-id="a601f-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a601f-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a601f-306">_sip</span><span class="sxs-lookup"><span data-stu-id="a601f-306">_sip</span></span>  <br/> |<span data-ttu-id="a601f-307">_tls</span><span class="sxs-lookup"><span data-stu-id="a601f-307">_tls</span></span>  <br/> |<span data-ttu-id="a601f-308">100</span><span class="sxs-lookup"><span data-stu-id="a601f-308">100</span></span>  <br/> |<span data-ttu-id="a601f-309">1 </span><span class="sxs-lookup"><span data-stu-id="a601f-309">1</span></span>  <br/> |<span data-ttu-id="a601f-310">443</span><span class="sxs-lookup"><span data-stu-id="a601f-310">443</span></span>  <br/> |<span data-ttu-id="a601f-311">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a601f-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="a601f-312">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-313">30 分</span><span class="sxs-lookup"><span data-stu-id="a601f-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="a601f-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a601f-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="a601f-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="a601f-315">_tcp</span></span>  <br/> |<span data-ttu-id="a601f-316">100</span><span class="sxs-lookup"><span data-stu-id="a601f-316">100</span></span>  <br/> |<span data-ttu-id="a601f-317">1 </span><span class="sxs-lookup"><span data-stu-id="a601f-317">1</span></span>  <br/> |<span data-ttu-id="a601f-318">5061</span><span class="sxs-lookup"><span data-stu-id="a601f-318">5061</span></span>  <br/> |<span data-ttu-id="a601f-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a601f-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="a601f-320">**この値は、末尾がピリオド (.) でなければなりません**</span><span class="sxs-lookup"><span data-stu-id="a601f-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="a601f-321">30 分</span><span class="sxs-lookup"><span data-stu-id="a601f-321">30 min</span></span>  <br/> |
       
    ![Namecheap-BP-Configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="a601f-323">[変更 **の保存]** (チェック マーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a601f-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="a601f-325">上の 4 つの手順に従って、表の 2 行目の値を使って、別の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a601f-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a601f-p114">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a601f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
