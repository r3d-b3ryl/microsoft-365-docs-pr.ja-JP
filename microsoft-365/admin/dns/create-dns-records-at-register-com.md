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
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629277"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="cfbf4-103">Microsoft の Register.com で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="cfbf4-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cfbf4-105">使用している DNS ホスティング プロバイダーが Register.com の場合は、この記事に示す手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cfbf4-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-106">These are the main records to add.</span></span> <span data-ttu-id="cfbf4-107">次の手順を実行するか、[ビデオを参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="cfbf4-108">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="cfbf4-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cfbf4-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="cfbf4-110">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="cfbf4-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="cfbf4-112">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="cfbf4-113">これらのレコードを Register.com で追加すると、使用しているドメインが、Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="cfbf4-114">Microsoft を使用した web サイトのホストと DNS の詳細については、「 [microsoft とのパブリック web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfbf4-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cfbf4-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cfbf4-117">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="cfbf4-118">Register.com で TXT レコードを追加して、ドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="cfbf4-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cfbf4-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cfbf4-120">ドメインを Microsoft で使用する前に、必ずそのドメインを所有していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="cfbf4-121">ドメインレジストラーで自分のアカウントにログインし、DNS レコードを作成することにより、そのドメインを所有していることが Microsoft に証明されます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfbf4-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="cfbf4-124">次の手順を実行するか、[ビデオ (44 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cfbf4-125">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cfbf4-126">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cfbf4-127">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cfbf4-128">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cfbf4-129">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cfbf4-130">[**高度な技術設定**] セクションまで下にスクロールしてから、[ **TXT レコードの編集 (SPF)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="cfbf4-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="cfbf4-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="cfbf4-132">**Host Name**</span></span> <br/> |<span data-ttu-id="cfbf4-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="cfbf4-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="cfbf4-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cfbf4-135">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-135">**Note:** This is an example.</span></span> <span data-ttu-id="cfbf4-136">この表では、特定の**宛先またはポイントを**使用して、ここにアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="cfbf4-137">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cfbf4-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="cfbf4-138">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="cfbf4-139">次のページで、[**続行**] をもう一度選択して、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="cfbf4-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cfbf4-141">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを要求します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cfbf4-142">Microsoft が正しい TXT レコードを見つけると、ドメインが確認されます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cfbf4-143">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cfbf4-144">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="cfbf4-145">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="cfbf4-146">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cfbf4-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cfbf4-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cfbf4-149">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cfbf4-150">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="cfbf4-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cfbf4-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cfbf4-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cfbf4-152">次の手順を実行するか、[ビデオ (3 分 32 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cfbf4-153">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cfbf4-154">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cfbf4-155">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cfbf4-156">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cfbf4-157">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cfbf4-158">[**高度な技術設定**] セクションまでスクロールし、[**メールエクスチェンジャーレコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![[メールエクスチェンジャーレコードの編集] を選択する](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="cfbf4-160">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cfbf4-161">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="cfbf4-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cfbf4-162">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-164">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="cfbf4-165">High</span><span class="sxs-lookup"><span data-stu-id="cfbf4-165">High</span></span>  <br/> <span data-ttu-id="cfbf4-166">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="cfbf4-167">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="cfbf4-168">**注:**\<Microsoft アカウントから*ドメインキー* \>を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="cfbf4-169">確認する方法</span><span class="sxs-lookup"><span data-stu-id="cfbf4-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="cfbf4-171">MX レコードが他にもリストされている場合は、レコードを 1 つずつ選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="cfbf4-173">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-173">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="cfbf4-175">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cfbf4-177">Microsoft に必要な CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cfbf4-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cfbf4-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cfbf4-179">次の手順を実行するか、[ビデオ (4 分 23 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cfbf4-180">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cfbf4-181">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cfbf4-182">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cfbf4-183">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cfbf4-184">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cfbf4-185">[**高度な技術設定**] セクションまでスクロールし、[**ドメインエイリアスレコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![[ドメインエイリアスレコードの編集] を選択する](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="cfbf4-187">[**追加するドメインエイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-187">Select **Add more domain aliases**.</span></span>
    
    ![[その他のドメインエイリアスの追加] を選択します。](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="cfbf4-189">必要な CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="cfbf4-190">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="cfbf4-191">\*\*\*\*最初のフィールド (ラベルなし)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-192">\*\*\*\*points to\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="cfbf4-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cfbf4-193">autodiscover</span></span>  <br/> |<span data-ttu-id="cfbf4-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cfbf4-195">sip</span><span class="sxs-lookup"><span data-stu-id="cfbf4-195">sip</span></span>  <br/> |<span data-ttu-id="cfbf4-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cfbf4-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cfbf4-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cfbf4-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="cfbf4-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cfbf4-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cfbf4-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cfbf4-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cfbf4-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cfbf4-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cfbf4-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![テーブルから DNS の値をコピーして貼り付けます。](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="cfbf4-204">必要な CNAME レコードをすべて追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="cfbf4-206">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cfbf4-208">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cfbf4-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cfbf4-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfbf4-210">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cfbf4-211">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cfbf4-212">ドメインに対して既に SPF レコードがある場合は、Microsoft 用に新しいを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cfbf4-213">代わりに、値のセットを含む1つの SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="cfbf4-214">次の手順を実行するか、[ビデオ (5 分 12 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cfbf4-215">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="cfbf4-216">サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cfbf4-217">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cfbf4-218">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cfbf4-219">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cfbf4-220">[**高度な技術設定**] セクションまでスクロールして、[ **TXT レコードの編集 (SPF)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![[Edit TXT Records (SPF)] を選択します。](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="cfbf4-222">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="cfbf4-223">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-224">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="cfbf4-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cfbf4-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cfbf4-226">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![テーブルから値をコピーして貼り付けます。](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="cfbf4-228">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-228">Select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="cfbf4-230">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cfbf4-232">Microsoft に必要な2つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cfbf4-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cfbf4-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cfbf4-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cfbf4-234">次の手順を実行するか、[ビデオ (5 分 55 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="cfbf4-p112">まず、[このリンク](https://www.register.com/myaccount/)を使って Register.com でドメイン ページにアクセスします。 サインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="cfbf4-237">[ **ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="cfbf4-238">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="cfbf4-239">変更するドメインの名前を含む行を検索します。その行で、[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="cfbf4-240">[**高度な技術設定**] セクションまでスクロールして、[ **SRV レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![[SRV レコードの編集] を選択する](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="cfbf4-242">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="cfbf4-243">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="cfbf4-244">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="cfbf4-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cfbf4-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-249">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="cfbf4-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cfbf4-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cfbf4-252">_sip</span><span class="sxs-lookup"><span data-stu-id="cfbf4-252">_sip</span></span>  <br/> |<span data-ttu-id="cfbf4-253">_tls</span><span class="sxs-lookup"><span data-stu-id="cfbf4-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="cfbf4-254">High</span><span class="sxs-lookup"><span data-stu-id="cfbf4-254">High</span></span>  <br/> |<span data-ttu-id="cfbf4-255">1-d</span><span class="sxs-lookup"><span data-stu-id="cfbf4-255">1</span></span>  <br/> |<span data-ttu-id="cfbf4-256">443</span><span class="sxs-lookup"><span data-stu-id="cfbf4-256">443</span></span>  <br/> |<span data-ttu-id="cfbf4-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="cfbf4-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cfbf4-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="cfbf4-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="cfbf4-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="cfbf4-260">High</span><span class="sxs-lookup"><span data-stu-id="cfbf4-260">High</span></span>  <br/> |<span data-ttu-id="cfbf4-261">1-d</span><span class="sxs-lookup"><span data-stu-id="cfbf4-261">1</span></span>  <br/> |<span data-ttu-id="cfbf4-262">5061</span><span class="sxs-lookup"><span data-stu-id="cfbf4-262">5061</span></span>  <br/> |<span data-ttu-id="cfbf4-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cfbf4-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![テーブルから値をコピーして貼り付けます。](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="cfbf4-265">[ **Add MORE SRV records**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-265">Select **Add more SRV records**.</span></span>
    
    ![[追加する SRV レコードの追加] を選択する](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="cfbf4-267">2 番目の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="cfbf4-268">上の表の 2 行目の値を 2 つ目のレコードのボックスに入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="cfbf4-269">両方の SRV レコードを追加したら、[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![[続行] を選択する](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="cfbf4-271">次のページで [**続行**] を選択して、変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![[続行] を選択する](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="cfbf4-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="cfbf4-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="cfbf4-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="cfbf4-275">DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメインまたは DNS レコードの追加後に問題を特定して解決](../get-help-with-domains/find-and-fix-issues.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfbf4-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
