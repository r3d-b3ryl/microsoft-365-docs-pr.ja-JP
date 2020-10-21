---
title: Namecheap を使用して Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'DNS レコードを管理する場合は、Namecheap を使用して Microsoft カスタムドメインをセットアップする方法について説明します。 '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646453"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="60e4e-103">Namecheap を使用して Microsoft をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="60e4e-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="60e4e-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60e4e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="60e4e-105">Microsoft が DNS レコードを管理する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="60e4e-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="60e4e-106">(必要に応じ [て、すべての MICROSOFT DNS レコードを Namecheap で管理](create-dns-records-at-namecheap.md)することができます)。</span><span class="sxs-lookup"><span data-stu-id="60e4e-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="60e4e-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="60e4e-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="60e4e-p102">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="60e4e-111">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="60e4e-113">[ **ドメインリスト** ] ページで、編集するドメインの名前を見つけて、[ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="60e4e-115">[ **ADVANCED DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="60e4e-117">[ **ホストレコード** ] セクションで、[ **新しいレコードの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="60e4e-119">[ **Type**] ドロップダウンで、[ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="60e4e-120">[**新しいレコードの追加**] を選択すると、[**種類**] ドロップダウンが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="60e4e-122">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="60e4e-123">(ドロップダウンリストから [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="60e4e-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="60e4e-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="60e4e-124">**Type**</span></span>|<span data-ttu-id="60e4e-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="60e4e-125">**Host**</span></span>|<span data-ttu-id="60e4e-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="60e4e-126">**Value**</span></span>|<span data-ttu-id="60e4e-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="60e4e-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60e4e-128">TXT</span><span class="sxs-lookup"><span data-stu-id="60e4e-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="60e4e-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="60e4e-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="60e4e-130">**注**: これは例です。</span><span class="sxs-lookup"><span data-stu-id="60e4e-130">**Note**: This is an example.</span></span> <span data-ttu-id="60e4e-131">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="60e4e-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="60e4e-132">確認する方法</span><span class="sxs-lookup"><span data-stu-id="60e4e-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="60e4e-133">30 分</span><span class="sxs-lookup"><span data-stu-id="60e4e-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-検証-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="60e4e-135">[ **変更の保存** ] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="60e4e-137">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="60e4e-138">これで、ドメインレジストラーのサイトでレコードが追加されました。 Microsoft に戻って、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="60e4e-139">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="60e4e-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="60e4e-140">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="60e4e-141">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="60e4e-142">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="60e4e-143">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="60e4e-p104">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60e4e-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="60e4e-147">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="60e4e-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="60e4e-148">Microsoft によるドメインの設定を完了するには、ドメインレジストラーでドメインの NS レコードを変更して、Microsoft プライマリネームサーバーとセカンダリネームサーバーをポイントするようにします。</span><span class="sxs-lookup"><span data-stu-id="60e4e-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="60e4e-149">これにより、ドメインの DNS レコードが更新されるように Microsoft が設定されます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="60e4e-150">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="60e4e-151">ドメインの NS レコードを変更して Microsoft ネームサーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="60e4e-152">たとえば、ドメインに送信されるすべての電子メール (rob@ *your_domain*  など) は、この変更を行った後に Microsoft に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="60e4e-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="60e4e-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="60e4e-p107">まず、[このリンク](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)を使って Namecheap でドメイン ページにアクセスします。サインインして続行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="60e4e-157">**ランディング**ページの [**アカウント**] で、ドロップダウンリストから [**ドメインリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="60e4e-159">[ **ドメインリスト** ] ページで、編集するドメインの名前を見つけて、[ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="60e4e-161">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="60e4e-163">[ **NAMESERVERS**] セクションを探し、[ **Namecheap Default**] ドロップダウン リストから [ **Custom**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="60e4e-165">現在表示されているページに既にネームサーバーが表示されているかどうかに応じて、次の2つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="60e4e-166">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="60e4e-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="60e4e-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="60e4e-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="60e4e-168">[ **ADD NAMESERVER** ] を2回選択して、2つの新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="60e4e-170">[ **Nameserver**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="60e4e-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="60e4e-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="60e4e-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="60e4e-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="60e4e-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="60e4e-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="60e4e-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="60e4e-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="60e4e-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="60e4e-180">[ **保存** ] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="60e4e-182">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60e4e-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="60e4e-183">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="60e4e-184">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="60e4e-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="60e4e-p109">これらの手順は、前途した 4 件の *正しい*  ネームサーバー以外にも既存のネームサーバーがある場合に  *のみ*  行ってください (つまり、現在のネームサーバーのうち *ns1.bdm.microsoftonline.com* 、 *ns2.bdm.microsoftonline.com* 、 **ns3.bdm.microsoftonline.com** 、 **ns4.bdm.microsoftonline.com** のいずれでも  **ない**  もの  **だけ**  を削除します)。</span><span class="sxs-lookup"><span data-stu-id="60e4e-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="60e4e-187">[ **Nameserver**] ボックスに他のネーム サーバーが表示されている場合は、各ネームサーバーを選び、キーボードの **Delete** キーを押して、ネーム サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="60e4e-189">[ **ADD NAMESERVER** ] を2回選択して、2つの新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="60e4e-191">[ **Nameserver**] ボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="60e4e-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="60e4e-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="60e4e-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="60e4e-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="60e4e-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="60e4e-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="60e4e-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="60e4e-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="60e4e-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="60e4e-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="60e4e-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="60e4e-201">[ **保存** ] (チェックマーク) コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="60e4e-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="60e4e-203">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60e4e-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="60e4e-204">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="60e4e-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
