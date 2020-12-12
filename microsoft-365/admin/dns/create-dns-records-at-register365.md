---
title: Register365 for Microsoft で DNS レコードを作成する
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Register365 for Microsoft でドメインを確認し、メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 6cefdeff3da1256911d80066b55b00f5bef24055
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656917"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="305f3-103">Register365 for Microsoft で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="305f3-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="305f3-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="305f3-105">使用している DNS ホスティング プロバイダーが Register365 の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="305f3-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="305f3-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="305f3-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="305f3-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="305f3-108">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="305f3-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="305f3-109">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="305f3-110">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="305f3-111">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="305f3-112">これらのレコードを Microsoft で追加すると、ドメインは Microsoft サービスで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="305f3-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="305f3-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="305f3-116">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-116">Add a TXT record for verification</span></span>
<span data-ttu-id="305f3-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="305f3-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="305f3-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="305f3-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="305f3-p104">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="305f3-125">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="305f3-126">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-126">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="305f3-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="305f3-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="305f3-129">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="305f3-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="305f3-130">(行を追加する必要がある場合は **、[A/CNAME レコードの追加 (+)**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="305f3-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="305f3-131">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="305f3-132">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="305f3-132">**Host name**</span></span>|<span data-ttu-id="305f3-133">**種類**</span><span class="sxs-lookup"><span data-stu-id="305f3-133">**Type**</span></span>|<span data-ttu-id="305f3-134">**結果**</span><span class="sxs-lookup"><span data-stu-id="305f3-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="305f3-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="305f3-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="305f3-136">TXT</span><span class="sxs-lookup"><span data-stu-id="305f3-136">TXT</span></span>  <br/> |<span data-ttu-id="305f3-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="305f3-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="305f3-138">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="305f3-138">**Note:** This is an example.</span></span> <span data-ttu-id="305f3-139">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="305f3-140">確認する方法</span><span class="sxs-lookup"><span data-stu-id="305f3-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="305f3-142">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-142">Select **Save**.</span></span>
    
    <span data-ttu-id="305f3-143">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-143">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="305f3-145">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="305f3-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="305f3-146">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="305f3-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="305f3-147">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="305f3-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="305f3-148">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="305f3-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="305f3-149">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="305f3-150">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="305f3-151">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="305f3-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="305f3-155">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="305f3-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="305f3-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="305f3-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="305f3-p107">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="305f3-160">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="305f3-161">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-161">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="305f3-163">[ **Add/Modify DNS Zone**] ページの [ **Mail exchange records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="305f3-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="305f3-164">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="305f3-165">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="305f3-165">**Host name**</span></span>|<span data-ttu-id="305f3-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="305f3-166">**Priority**</span></span>|<span data-ttu-id="305f3-167">**Result**</span><span class="sxs-lookup"><span data-stu-id="305f3-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="305f3-168">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="305f3-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="305f3-169">1 </span><span class="sxs-lookup"><span data-stu-id="305f3-169">1</span></span>  <br/> <span data-ttu-id="305f3-170">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="305f3-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="305f3-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="305f3-172">**注:** Microsoft アカウント  *\<domain-key\>*  からユーザーを取得します。</span><span class="sxs-lookup"><span data-stu-id="305f3-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="305f3-173">確認する方法</span><span class="sxs-lookup"><span data-stu-id="305f3-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="305f3-175">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-175">Select **Save**.</span></span>
    
    <span data-ttu-id="305f3-176">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-176">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="305f3-178">他の MX レコードがある場合は、[ **Mail exchange records**] セクションで各レコードを選び、キーボードの **Delete** キーを押して、レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="305f3-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="305f3-180">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-180">Select **Save**.</span></span>
    
    <span data-ttu-id="305f3-181">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-181">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="305f3-183">Microsoft に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="305f3-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="305f3-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="305f3-p109">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="305f3-188">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="305f3-189">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-189">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="305f3-191">[ **Add/Modify DNS Zone**] ページの [ **A, CNAME, AAAA, TXT and NS records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="305f3-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="305f3-192">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="305f3-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="305f3-193">(行を追加する必要がある場合は **、[A/CNAME レコードの追加 (+)**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="305f3-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="305f3-194">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="305f3-195">\*\*\*\*Host name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="305f3-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="305f3-196">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="305f3-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="305f3-197">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="305f3-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="305f3-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="305f3-198">autodiscover</span></span>  <br/> |<span data-ttu-id="305f3-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="305f3-199">CNAME</span></span>  <br/> |<span data-ttu-id="305f3-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="305f3-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="305f3-201">sip</span><span class="sxs-lookup"><span data-stu-id="305f3-201">sip</span></span>  <br/> |<span data-ttu-id="305f3-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="305f3-202">CNAME</span></span>  <br/> |<span data-ttu-id="305f3-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="305f3-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="305f3-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="305f3-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="305f3-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="305f3-205">CNAME</span></span>  <br/> |<span data-ttu-id="305f3-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="305f3-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="305f3-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="305f3-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="305f3-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="305f3-208">CNAME</span></span>  <br/> |<span data-ttu-id="305f3-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="305f3-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="305f3-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="305f3-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="305f3-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="305f3-211">CNAME</span></span>  <br/> |<span data-ttu-id="305f3-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="305f3-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="305f3-214">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-214">Select **Save**.</span></span>
    
    ![[保存] を選択します。](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="305f3-216">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="305f3-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="305f3-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="305f3-218">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="305f3-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="305f3-219">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="305f3-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="305f3-220">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="305f3-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="305f3-221">代わりに、必要な Microsoft の値を現在のレコードに追加して、両方の値のセットを含む  *1*  つの SPF レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="305f3-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="305f3-p111">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="305f3-225">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="305f3-226">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-226">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="305f3-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="305f3-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="305f3-229">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="305f3-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="305f3-230">(行を追加する必要がある場合は **、[A/CNAME レコードの追加 (+)**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="305f3-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="305f3-231">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="305f3-232">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="305f3-232">**Host name**</span></span>|<span data-ttu-id="305f3-233">**種類**</span><span class="sxs-lookup"><span data-stu-id="305f3-233">**Type**</span></span>|<span data-ttu-id="305f3-234">**結果**</span><span class="sxs-lookup"><span data-stu-id="305f3-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="305f3-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="305f3-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="305f3-236">TXT</span><span class="sxs-lookup"><span data-stu-id="305f3-236">TXT</span></span>  <br/> |<span data-ttu-id="305f3-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="305f3-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="305f3-238">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="305f3-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![[DNS ゾーンの追加/変更] ページで値を入力する](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="305f3-240">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-240">Select **Save**.</span></span>
    
    <span data-ttu-id="305f3-241">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-241">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="305f3-243">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="305f3-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="305f3-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="305f3-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="305f3-p112">まず、[このリンク](https://admin.register365.com/dns/)を使って Register365 でドメイン ページにアクセスします。 最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="305f3-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![コントロール パネルの [Log in] ページ](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="305f3-248">[ **ダッシュボード**] ページで、更新しているドメインの名前を見つけ、ドロップダウン リストで [ **DNS Settings**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="305f3-249">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-249">(You may have to scroll down.)</span></span>
    
    ![一覧で DNS 設定を選択する](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="305f3-251">[ **Add/Modify DNS Zone**] ページの [ **Service records**] セクションにある新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="305f3-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="305f3-252">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="305f3-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="305f3-253">**Name**</span></span>|<span data-ttu-id="305f3-254">**Priority**</span><span class="sxs-lookup"><span data-stu-id="305f3-254">**Priority**</span></span>|<span data-ttu-id="305f3-255">**Weight**</span><span class="sxs-lookup"><span data-stu-id="305f3-255">**Weight**</span></span>|<span data-ttu-id="305f3-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="305f3-256">**Port**</span></span>|<span data-ttu-id="305f3-257">**Result**</span><span class="sxs-lookup"><span data-stu-id="305f3-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="305f3-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="305f3-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="305f3-259">100</span><span class="sxs-lookup"><span data-stu-id="305f3-259">100</span></span>  <br/> |<span data-ttu-id="305f3-260">1 </span><span class="sxs-lookup"><span data-stu-id="305f3-260">1</span></span>  <br/> |<span data-ttu-id="305f3-261">443</span><span class="sxs-lookup"><span data-stu-id="305f3-261">443</span></span>  <br/> |<span data-ttu-id="305f3-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="305f3-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="305f3-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="305f3-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="305f3-264">100</span><span class="sxs-lookup"><span data-stu-id="305f3-264">100</span></span>  <br/> |<span data-ttu-id="305f3-265">1 </span><span class="sxs-lookup"><span data-stu-id="305f3-265">1</span></span>  <br/> |<span data-ttu-id="305f3-266">5061</span><span class="sxs-lookup"><span data-stu-id="305f3-266">5061</span></span>  <br/> |<span data-ttu-id="305f3-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="305f3-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![[サービス レコード] セクションに値を入力する](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="305f3-269">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="305f3-269">Select **Save**.</span></span>
    
    <span data-ttu-id="305f3-270">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="305f3-270">(You may have to scroll down.)</span></span>
    
    ![[保存] を選択します。](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="305f3-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="305f3-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
