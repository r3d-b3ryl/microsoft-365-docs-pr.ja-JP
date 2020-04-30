---
title: Microsoft の Register.com で DNS レコードを作成する
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: ドメインを確認し、電子メール、Skype for Business Online、および Register.com のその他のサービスの DNS レコードを Microsoft 用にセットアップする方法について説明します。
ms.openlocfilehash: 7d1293368a9a7ab94a5556ca266c716280ae85f5
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939121"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="8ec10-103">Microsoft の Register.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="8ec10-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="8ec10-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8ec10-105">使用している DNS ホスティング プロバイダーが Register.com の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="8ec10-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8ec10-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ec10-106">These are the main records to add.</span></span> <span data-ttu-id="8ec10-107">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="8ec10-108">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="8ec10-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="8ec10-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="8ec10-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="8ec10-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="8ec10-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="8ec10-112">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="8ec10-113">これらのレコードを Register.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="8ec10-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="8ec10-117">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="8ec10-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="8ec10-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8ec10-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8ec10-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ec10-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8ec10-123">次の手順を実行するか、[ビデオ (44 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-123">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ec10-124">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="8ec10-125">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="8ec10-126">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="8ec10-127">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="8ec10-128">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="8ec10-129">[**高度な技術設定**] セクションまで下にスクロールしてから、[ **TXT レコードの編集 (SPF)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="8ec10-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8ec10-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="8ec10-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="8ec10-131">**Host Name**</span></span> <br/> |<span data-ttu-id="8ec10-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="8ec10-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="8ec10-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8ec10-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8ec10-134">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="8ec10-134">**Note:** This is an example.</span></span> <span data-ttu-id="8ec10-135">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="8ec10-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="8ec10-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="8ec10-137">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="8ec10-138">次のページで、[**続行**] をもう一度選択して、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="8ec10-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8ec10-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8ec10-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="8ec10-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8ec10-142">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8ec10-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8ec10-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8ec10-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8ec10-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8ec10-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="8ec10-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8ec10-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8ec10-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="8ec10-151">次の手順を実行するか、[ビデオ (3 分 32 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-151">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ec10-152">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="8ec10-153">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="8ec10-154">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="8ec10-155">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="8ec10-156">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="8ec10-157">[**高度な技術設定**] セクションまでスクロールし、[**メールエクスチェンジャーレコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![[メールエクスチェンジャーレコードの編集] を選択する](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="8ec10-159">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8ec10-160">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="8ec10-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8ec10-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="8ec10-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="8ec10-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8ec10-164">高</span><span class="sxs-lookup"><span data-stu-id="8ec10-164">High</span></span>  <br/> <span data-ttu-id="8ec10-165">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="8ec10-166">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="8ec10-167">**注:** Microsoft アカウントから自分の\<*ドメイン キー*\>を取得します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="8ec10-168">確認する方法</span><span class="sxs-lookup"><span data-stu-id="8ec10-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="8ec10-170">MX レコードが他にもリストされている場合は、レコードを 1 つずつ選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="8ec10-172">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-172">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="8ec10-174">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ec10-176">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8ec10-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8ec10-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="8ec10-178">次の手順を実行するか、[ビデオ (4 分 23 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-178">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ec10-179">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="8ec10-180">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="8ec10-181">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="8ec10-182">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="8ec10-183">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="8ec10-184">[**高度な技術設定**] セクションまでスクロールし、[**ドメインエイリアスレコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![[ドメインエイリアスレコードの編集] を選択する](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="8ec10-186">[**追加するドメインエイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-186">Select **Add more domain aliases**.</span></span>
    
    ![[その他のドメインエイリアスの追加] を選択します。](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="8ec10-188">必要な CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="8ec10-189">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="8ec10-190">\*\*\*\*最初のフィールド (ラベルなし)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="8ec10-191">\*\*\*\*points to\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="8ec10-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8ec10-192">autodiscover</span></span>  <br/> |<span data-ttu-id="8ec10-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="8ec10-194">sip</span><span class="sxs-lookup"><span data-stu-id="8ec10-194">sip</span></span>  <br/> |<span data-ttu-id="8ec10-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="8ec10-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8ec10-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8ec10-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="8ec10-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8ec10-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8ec10-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8ec10-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="8ec10-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8ec10-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8ec10-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![テーブルから DNS の値をコピーして貼り付けます。](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="8ec10-203">必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="8ec10-205">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8ec10-207">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8ec10-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8ec10-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec10-209">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ec10-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8ec10-210">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8ec10-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8ec10-211">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8ec10-212">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="8ec10-213">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-213">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ec10-214">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="8ec10-215">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="8ec10-216">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="8ec10-217">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="8ec10-218">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="8ec10-219">[**高度な技術設定**] セクションまでスクロールして、[ **TXT レコードの編集 (SPF)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![[Edit TXT Records (SPF)] を選択します。](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="8ec10-221">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="8ec10-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="8ec10-223">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="8ec10-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8ec10-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8ec10-225">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ec10-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![テーブルから値をコピーして貼り付けます。](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="8ec10-227">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-227">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="8ec10-229">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8ec10-231">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8ec10-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8ec10-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8ec10-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="8ec10-233">次の手順を実行するか、[ビデオ (5 分 55 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-233">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="8ec10-p112">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="8ec10-236">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="8ec10-237">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="8ec10-238">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="8ec10-239">[**高度な技術設定**] セクションまでスクロールして、[ **SRV レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![[SRV レコードの編集] を選択する](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="8ec10-241">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="8ec10-242">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="8ec10-243">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="8ec10-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="8ec10-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="8ec10-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="8ec10-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="8ec10-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="8ec10-248">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="8ec10-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="8ec10-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ec10-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8ec10-251">_sip</span><span class="sxs-lookup"><span data-stu-id="8ec10-251">_sip</span></span>  <br/> |<span data-ttu-id="8ec10-252">_tls</span><span class="sxs-lookup"><span data-stu-id="8ec10-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="8ec10-253">High</span><span class="sxs-lookup"><span data-stu-id="8ec10-253">High</span></span>  <br/> |<span data-ttu-id="8ec10-254">1-d</span><span class="sxs-lookup"><span data-stu-id="8ec10-254">1</span></span>  <br/> |<span data-ttu-id="8ec10-255">443</span><span class="sxs-lookup"><span data-stu-id="8ec10-255">443</span></span>  <br/> |<span data-ttu-id="8ec10-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="8ec10-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8ec10-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="8ec10-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="8ec10-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="8ec10-259">High</span><span class="sxs-lookup"><span data-stu-id="8ec10-259">High</span></span>  <br/> |<span data-ttu-id="8ec10-260">1-d</span><span class="sxs-lookup"><span data-stu-id="8ec10-260">1</span></span>  <br/> |<span data-ttu-id="8ec10-261">5061</span><span class="sxs-lookup"><span data-stu-id="8ec10-261">5061</span></span>  <br/> |<span data-ttu-id="8ec10-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8ec10-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="8ec10-264">[ **Add MORE SRV records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-264">Select **Add more SRV records**.</span></span>
    
    ![[追加する SRV レコードの追加] を選択する](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="8ec10-266">2 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="8ec10-267">上の表の 2 行目の値を 2 つ目のレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8ec10-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="8ec10-268">両方の SRV レコードを追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="8ec10-270">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec10-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="8ec10-p113">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec10-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
