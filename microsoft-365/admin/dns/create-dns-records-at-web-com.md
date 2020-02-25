---
title: Web.com for Office 365 で DNS レコードを作成する
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および web.com for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249457"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="955f5-103">Web.com for Office 365 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="955f5-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="955f5-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="955f5-105">DNS ホスティングプロバイダーが web.com の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="955f5-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="955f5-106">これらのレコードを web.com で追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="955f5-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="955f5-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="955f5-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="955f5-111">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="955f5-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="955f5-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="955f5-113">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="955f5-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="955f5-114">Web.com にサインアップしたときに、web.com**セットアップ**プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="955f5-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="955f5-115">Office 365 でドメインの DNS レコードを確認および作成するには、最初にドメインレジストラーでネームサーバーを変更して、web .com のネームサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="955f5-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="955f5-116">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="955f5-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="955f5-117">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="955f5-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="955f5-118">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="955f5-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="955f5-119">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="955f5-119">First nameserver</span></span>  <br/> |<span data-ttu-id="955f5-120">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="955f5-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="955f5-121">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="955f5-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="955f5-122">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="955f5-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="955f5-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="955f5-123">You should use at least two name server records.</span></span> <span data-ttu-id="955f5-124">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="955f5-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="955f5-125">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="955f5-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="955f5-p103">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="955f5-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="955f5-128">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="955f5-128">Add a TXT record for verification</span></span>
<span data-ttu-id="955f5-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="955f5-p104">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="955f5-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="955f5-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="955f5-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="955f5-134">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="955f5-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="955f5-135">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="955f5-135">Log in first.</span></span>
  
2. <span data-ttu-id="955f5-136">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="955f5-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="955f5-137">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="955f5-138">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="955f5-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="955f5-139">**Host**</span></span>|<span data-ttu-id="955f5-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="955f5-140">**TTL**</span></span>|<span data-ttu-id="955f5-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="955f5-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="955f5-142">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-142">3600</span></span>  <br/> |<span data-ttu-id="955f5-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="955f5-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="955f5-p107">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="955f5-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="955f5-147">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="955f5-148">新しい TXT レコードが確認されるまで数分待ってから、作成したレコードがインターネットを介して更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="955f5-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="955f5-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="955f5-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="955f5-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="955f5-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="955f5-151">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="955f5-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="955f5-152">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="955f5-153">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="955f5-154">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="955f5-p108">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="955f5-158">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="955f5-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="955f5-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="955f5-160">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="955f5-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="955f5-161">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="955f5-161">Log in first.</span></span>
  
2. <span data-ttu-id="955f5-162">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="955f5-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="955f5-163">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="955f5-164">[**メールサーバー (Mx records)**] で、[ **Mx レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="955f5-165">**優先度**</span><span class="sxs-lookup"><span data-stu-id="955f5-165">**Priority**</span></span>|<span data-ttu-id="955f5-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="955f5-166">**TTL**</span></span>|<span data-ttu-id="955f5-167">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="955f5-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="955f5-168">1-d</span><span class="sxs-lookup"><span data-stu-id="955f5-168">1</span></span>  <br/> <span data-ttu-id="955f5-169">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="955f5-170">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-170">3600</span></span>  <br/> |<span data-ttu-id="955f5-171">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="955f5-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="955f5-172">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="955f5-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="955f5-173">確認する方法</span><span class="sxs-lookup"><span data-stu-id="955f5-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="955f5-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="955f5-175">その他の MX レコードが [ **Mx records** ] セクションに表示されている場合は、[**削除**] でそのレコードの横にあるチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="955f5-176">確認画面で、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="955f5-177">Office 365 に必要な6つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="955f5-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="955f5-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="955f5-179">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="955f5-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="955f5-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="955f5-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="955f5-181">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="955f5-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="955f5-182">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="955f5-183">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="955f5-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="955f5-184">[ **Host alias (Cname records)**] で [ **Cname レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="955f5-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="955f5-185">**Alias**</span></span>|<span data-ttu-id="955f5-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="955f5-186">**TTL**</span></span>|<span data-ttu-id="955f5-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="955f5-187">**Refers to Host Name**</span></span>|<span data-ttu-id="955f5-188">**その他のホスト**</span><span class="sxs-lookup"><span data-stu-id="955f5-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="955f5-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="955f5-189">autodiscover</span></span>  <br/> |<span data-ttu-id="955f5-190">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-190">3600</span></span>  <br/> |<span data-ttu-id="955f5-191">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-191">@ (none)</span></span>  <br/> |<span data-ttu-id="955f5-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="955f5-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="955f5-193">sip</span><span class="sxs-lookup"><span data-stu-id="955f5-193">sip</span></span>  <br/> |<span data-ttu-id="955f5-194">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-194">3600</span></span>  <br/> |<span data-ttu-id="955f5-195">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-195">@ (none)</span></span>  <br/> |<span data-ttu-id="955f5-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="955f5-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="955f5-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="955f5-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="955f5-198">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-198">3600</span></span>  <br/> |<span data-ttu-id="955f5-199">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-199">@ (none)</span></span>  <br/> | <span data-ttu-id="955f5-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="955f5-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="955f5-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="955f5-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="955f5-202">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-202">3600</span></span>  <br/> |<span data-ttu-id="955f5-203">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-203">@ (none)</span></span>  <br/> |<span data-ttu-id="955f5-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="955f5-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="955f5-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="955f5-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="955f5-206">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-206">3600</span></span>  <br/> |<span data-ttu-id="955f5-207">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-207">@ (none)</span></span>  <br/> |<span data-ttu-id="955f5-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="955f5-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="955f5-209">msoid</span><span class="sxs-lookup"><span data-stu-id="955f5-209">msoid</span></span>  <br/> |<span data-ttu-id="955f5-210">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-210">3600</span></span>  <br/> |<span data-ttu-id="955f5-211">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="955f5-211">@ (none)</span></span>  <br/> |<span data-ttu-id="955f5-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="955f5-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="955f5-213">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="955f5-214">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="955f5-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="955f5-215">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="955f5-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="955f5-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="955f5-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="955f5-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="955f5-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="955f5-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="955f5-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="955f5-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="955f5-220">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="955f5-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="955f5-221">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="955f5-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="955f5-222">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="955f5-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="955f5-223">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="955f5-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="955f5-224">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="955f5-225">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="955f5-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="955f5-226">**Host**</span></span>|<span data-ttu-id="955f5-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="955f5-227">**TTL**</span></span>|<span data-ttu-id="955f5-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="955f5-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="955f5-229">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-229">3600</span></span>  <br/> |<span data-ttu-id="955f5-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="955f5-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="955f5-231">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="955f5-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="955f5-232">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-232">Select **Continue**.</span></span>

6. <span data-ttu-id="955f5-233">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="955f5-234">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="955f5-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="955f5-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="955f5-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="955f5-236">Web.com は、この機能を使用できるようにする責任があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="955f5-237">次の手順と現在の web.com GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Web.com コミュニティ](https://community.web.com.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="955f5-238">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="955f5-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="955f5-239">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="955f5-239">Log in first.</span></span>
      
2. <span data-ttu-id="955f5-240">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="955f5-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="955f5-241">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="955f5-242">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="955f5-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="955f5-243">[**サービス (Srv レコード)**] で、[ **Srv レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="955f5-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="955f5-244">**Service**</span></span>|<span data-ttu-id="955f5-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="955f5-245">**Protocol**</span></span>|<span data-ttu-id="955f5-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="955f5-246">**TTL**</span></span>|<span data-ttu-id="955f5-247">**優先度**</span><span class="sxs-lookup"><span data-stu-id="955f5-247">**Priority**</span></span>|<span data-ttu-id="955f5-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="955f5-248">**Weight**</span></span>|<span data-ttu-id="955f5-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="955f5-249">**Port**</span></span>|<span data-ttu-id="955f5-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="955f5-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="955f5-251">_sip</span><span class="sxs-lookup"><span data-stu-id="955f5-251">_sip</span></span> |<span data-ttu-id="955f5-252">_tls</span><span class="sxs-lookup"><span data-stu-id="955f5-252">_tls</span></span> |<span data-ttu-id="955f5-253">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-253">3600</span></span> | <span data-ttu-id="955f5-254">100</span><span class="sxs-lookup"><span data-stu-id="955f5-254">100</span></span>|<span data-ttu-id="955f5-255">1-d</span><span class="sxs-lookup"><span data-stu-id="955f5-255">1</span></span> |<span data-ttu-id="955f5-256">443</span><span class="sxs-lookup"><span data-stu-id="955f5-256">443</span></span> |<span data-ttu-id="955f5-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="955f5-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="955f5-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="955f5-258">_sipfederationtls</span></span> |<span data-ttu-id="955f5-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="955f5-259">_tcp</span></span> |<span data-ttu-id="955f5-260">3600</span><span class="sxs-lookup"><span data-stu-id="955f5-260">3600</span></span> |<span data-ttu-id="955f5-261">100</span><span class="sxs-lookup"><span data-stu-id="955f5-261">100</span></span> |<span data-ttu-id="955f5-262">1-d</span><span class="sxs-lookup"><span data-stu-id="955f5-262">1</span></span> |<span data-ttu-id="955f5-263">5061</span><span class="sxs-lookup"><span data-stu-id="955f5-263">5061</span></span> | <span data-ttu-id="955f5-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="955f5-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="955f5-265">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="955f5-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="955f5-266">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-266">Select **Continue**.</span></span>

7. <span data-ttu-id="955f5-267">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="955f5-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="955f5-p116">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="955f5-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
