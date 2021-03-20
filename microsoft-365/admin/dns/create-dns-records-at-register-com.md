---
title: Microsoft 向け DNS レコード Register.com 作成する
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: ドメインを確認し、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法については、Microsoft Register.com 説明します。
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910056"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="c8df7-103">Microsoft 向け DNS レコード Register.com 作成する</span><span class="sxs-lookup"><span data-stu-id="c8df7-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="c8df7-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.yml)** してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c8df7-105">使用している DNS ホスティング プロバイダーが Register.com の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="c8df7-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c8df7-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8df7-106">These are the main records to add.</span></span> <span data-ttu-id="c8df7-107">次の手順を実行するか、[ビデオを参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="c8df7-108">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="c8df7-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="c8df7-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c8df7-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="c8df7-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="c8df7-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="c8df7-112">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="c8df7-113">これらのレコードを追加すると、Register.com Microsoft サービスを使用するためにドメインが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="c8df7-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="c8df7-117">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="c8df7-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="c8df7-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c8df7-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c8df7-p103">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8df7-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="c8df7-123">次の手順を実行するか、[ビデオ (44 秒から開始) を参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c8df7-p105">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c8df7-126">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c8df7-127">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c8df7-128">変更するドメインの名前を含む行を検索します。次に、その行で [管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c8df7-129">[高度な技術設定 **] セクションまで下にスクロール** し、[TXT レコードの編集 **(SPF) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="c8df7-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c8df7-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="c8df7-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="c8df7-131">**Host Name**</span></span> <br/> |<span data-ttu-id="c8df7-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="c8df7-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="c8df7-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c8df7-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c8df7-134">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="c8df7-134">**Note:** This is an example.</span></span> <span data-ttu-id="c8df7-135">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="c8df7-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c8df7-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c8df7-137">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="c8df7-138">次のページで、[続行] を **再度選択** して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="c8df7-139">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c8df7-140">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="c8df7-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c8df7-141">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="c8df7-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c8df7-142">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c8df7-143">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c8df7-144">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c8df7-145">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c8df7-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c8df7-149">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="c8df7-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c8df7-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c8df7-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c8df7-151">次の手順を実行するか、[ビデオ (3 分 32 秒から開始) を参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c8df7-p108">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c8df7-154">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c8df7-155">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c8df7-156">変更するドメインの名前を含む行を検索します。次に、その行で [管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c8df7-157">[高度な技術 **設定] セクションまでスクロール** し、[メール エクスチェンジャー レコードの **編集] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![[メール エクスチェンジャー レコードの編集] を選択する](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="c8df7-159">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c8df7-160">(ドロップダウン リスト **から [優先度** ] の値を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c8df7-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c8df7-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c8df7-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c8df7-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c8df7-164">High</span><span class="sxs-lookup"><span data-stu-id="c8df7-164">High</span></span>  <br/> <span data-ttu-id="c8df7-165">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="c8df7-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="c8df7-167">**注: Microsoft アカウントから** 取得\<*domain-key*\> します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="c8df7-168">確認する方法</span><span class="sxs-lookup"><span data-stu-id="c8df7-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルから値をコピーして貼り付ける](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="c8df7-170">MX レコードが他にもリストされている場合は、レコードを 1 つずつ選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="c8df7-172">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-172">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="c8df7-174">次のページで、[続行] を **再度選択** して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択します。](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c8df7-176">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c8df7-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c8df7-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c8df7-178">次の手順を実行するか、[ビデオ (4 分 23 秒から開始) を参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c8df7-p109">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c8df7-181">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c8df7-182">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c8df7-183">変更するドメインの名前を含む行を検索します。次に、その行で [管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c8df7-184">[高度な技術 **設定] セクションまでスクロール** し、[ドメイン エイリアス レコードの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![[ドメイン エイリアス レコードの編集] を選択します。](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="c8df7-186">[ドメイン **エイリアスの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-186">Select **Add more domain aliases**.</span></span>
    
    ![[追加のドメイン エイリアスを追加する] を選択します。](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="c8df7-188">必要な CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="c8df7-189">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="c8df7-190">\*\*\*\*最初のフィールド (ラベルなし)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="c8df7-191">\*\*\*\*points to\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c8df7-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c8df7-192">autodiscover</span></span>  <br/> |<span data-ttu-id="c8df7-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c8df7-194">sip</span><span class="sxs-lookup"><span data-stu-id="c8df7-194">sip</span></span>  <br/> |<span data-ttu-id="c8df7-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c8df7-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c8df7-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c8df7-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="c8df7-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c8df7-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c8df7-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c8df7-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c8df7-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c8df7-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c8df7-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![テーブルから DNS 値をコピーして貼り付ける](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="c8df7-203">必要なすべての CNAME レコードを追加した場合は、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="c8df7-205">次のページで、[続行] を **再度選択** して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択します。](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c8df7-207">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c8df7-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c8df7-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8df7-209">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8df7-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c8df7-210">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="c8df7-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c8df7-211">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c8df7-212">代わりに、現在のレコードに Microsoft で必要になる値を追加して、元々の値と追加する値の組み合わせが 1 つの SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="c8df7-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="c8df7-213">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c8df7-p111">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c8df7-216">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c8df7-217">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c8df7-218">変更するドメインの名前を含む行を検索します。次に、その行で [管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c8df7-219">[高度な技術 **設定] セクションまでスクロール** し、[TXT レコードの編集 **(SPF) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![[TXT レコードの編集] (SPF) を選択します。](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="c8df7-221">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="c8df7-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c8df7-223">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c8df7-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c8df7-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c8df7-225">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8df7-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![テーブルから値をコピーして貼り付ける](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="c8df7-227">[続行 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-227">Select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="c8df7-229">次のページで、[続行] を **再度選択** して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択します。](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c8df7-231">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="c8df7-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c8df7-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c8df7-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c8df7-233">次の手順を実行するか、[ビデオ (5 分 55 秒から開始) を参照](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4)してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="c8df7-p112">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c8df7-236">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c8df7-237">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c8df7-238">変更するドメインの名前を含む行を検索します。次に、その行で [管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c8df7-239">[高度な技術 **設定] セクションまでスクロール** し **、[SRV** レコードの編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![[SRV レコードの編集] を選択する](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="c8df7-241">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="c8df7-242">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c8df7-243">(ドロップダウン リスト **から [優先度** ] の値を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c8df7-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c8df7-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="c8df7-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="c8df7-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="c8df7-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c8df7-248">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="c8df7-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="c8df7-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c8df7-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c8df7-251">_sip</span><span class="sxs-lookup"><span data-stu-id="c8df7-251">_sip</span></span>  <br/> |<span data-ttu-id="c8df7-252">_tls</span><span class="sxs-lookup"><span data-stu-id="c8df7-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="c8df7-253">High</span><span class="sxs-lookup"><span data-stu-id="c8df7-253">High</span></span>  <br/> |<span data-ttu-id="c8df7-254">1</span><span class="sxs-lookup"><span data-stu-id="c8df7-254">1</span></span>  <br/> |<span data-ttu-id="c8df7-255">443</span><span class="sxs-lookup"><span data-stu-id="c8df7-255">443</span></span>  <br/> |<span data-ttu-id="c8df7-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c8df7-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c8df7-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c8df7-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="c8df7-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="c8df7-259">High</span><span class="sxs-lookup"><span data-stu-id="c8df7-259">High</span></span>  <br/> |<span data-ttu-id="c8df7-260">1</span><span class="sxs-lookup"><span data-stu-id="c8df7-260">1</span></span>  <br/> |<span data-ttu-id="c8df7-261">5061</span><span class="sxs-lookup"><span data-stu-id="c8df7-261">5061</span></span>  <br/> |<span data-ttu-id="c8df7-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c8df7-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![テーブルから値をコピーして貼り付ける](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="c8df7-264">**[SRV レコードの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-264">Select **Add more SRV records**.</span></span>
    
    ![[SRV レコードの追加] を選択します。](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="c8df7-266">2 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="c8df7-267">上の表の 2 行目の値を 2 つ目のレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c8df7-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="c8df7-268">両方の SRV レコードを追加した場合は、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8df7-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![[続行] を選択します。](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="c8df7-270">次のページで、[続行] を **再度選択** して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="c8df7-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択します。](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="c8df7-p113">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8df7-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
