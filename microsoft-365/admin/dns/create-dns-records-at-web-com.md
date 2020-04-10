---
title: Web.com for Office 365 で DNS レコードを作成する
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および web.com for Office 365 のその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: d5546b55392849aac9049613bd860f937ffb7618
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211076"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="3993b-103">Web.com for Office 365 で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="3993b-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="3993b-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3993b-105">DNS ホスティングプロバイダーが web.com の場合は、この記事に記載されている手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="3993b-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3993b-106">これらのレコードを web.com で追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="3993b-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="3993b-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3993b-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="3993b-111">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="3993b-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="3993b-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3993b-113">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3993b-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="3993b-114">Web.com にサインアップしたときに、web.com**セットアップ**プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="3993b-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="3993b-115">Office 365 でドメインの DNS レコードを確認および作成するには、最初にドメインレジストラーでネームサーバーを変更して、web .com のネームサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3993b-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="3993b-116">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3993b-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="3993b-117">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3993b-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="3993b-118">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="3993b-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="3993b-119">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="3993b-119">First nameserver</span></span>  <br/> |<span data-ttu-id="3993b-120">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="3993b-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="3993b-121">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="3993b-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="3993b-122">Web.com によって提供される nameserver 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="3993b-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="3993b-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="3993b-123">You should use at least two name server records.</span></span> <span data-ttu-id="3993b-124">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3993b-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="3993b-125">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="3993b-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3993b-p103">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3993b-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3993b-128">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3993b-128">Add a TXT record for verification</span></span>
<span data-ttu-id="3993b-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3993b-p104">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3993b-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3993b-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3993b-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3993b-134">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3993b-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3993b-135">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="3993b-135">Log in first.</span></span>
  
2. <span data-ttu-id="3993b-136">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3993b-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3993b-137">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="3993b-138">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="3993b-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="3993b-139">**Host**</span></span>|<span data-ttu-id="3993b-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3993b-140">**TTL**</span></span>|<span data-ttu-id="3993b-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="3993b-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="3993b-142">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-142">3600</span></span>  <br/> |<span data-ttu-id="3993b-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3993b-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3993b-p107">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="3993b-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="3993b-147">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="3993b-148">新しい TXT レコードが確認されるまで数分待ってから、作成したレコードがインターネットを介して更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3993b-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3993b-149">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="3993b-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="3993b-150">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="3993b-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3993b-151">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3993b-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3993b-152">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3993b-153">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="3993b-154">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="3993b-p108">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="3993b-158">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="3993b-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="3993b-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3993b-160">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3993b-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3993b-161">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="3993b-161">Log in first.</span></span>
  
2. <span data-ttu-id="3993b-162">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3993b-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3993b-163">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="3993b-164">[**メールサーバー (Mx records)**] で、[ **Mx レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="3993b-165">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3993b-165">**Priority**</span></span>|<span data-ttu-id="3993b-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3993b-166">**TTL**</span></span>|<span data-ttu-id="3993b-167">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="3993b-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3993b-168">1-d</span><span class="sxs-lookup"><span data-stu-id="3993b-168">1</span></span>  <br/> <span data-ttu-id="3993b-169">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="3993b-170">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-170">3600</span></span>  <br/> |<span data-ttu-id="3993b-171">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3993b-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3993b-172">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="3993b-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="3993b-173">確認する方法</span><span class="sxs-lookup"><span data-stu-id="3993b-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="3993b-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="3993b-175">その他の MX レコードが [ **Mx records** ] セクションに表示されている場合は、[**削除**] でそのレコードの横にあるチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="3993b-176">確認画面で、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="3993b-177">Office 365 に必要な6つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3993b-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="3993b-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3993b-179">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3993b-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3993b-180">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3993b-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="3993b-181">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3993b-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3993b-182">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="3993b-183">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3993b-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3993b-184">[ **Host alias (Cname records)**] で [ **Cname レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="3993b-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="3993b-185">**Alias**</span></span>|<span data-ttu-id="3993b-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3993b-186">**TTL**</span></span>|<span data-ttu-id="3993b-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="3993b-187">**Refers to Host Name**</span></span>|<span data-ttu-id="3993b-188">**その他のホスト**</span><span class="sxs-lookup"><span data-stu-id="3993b-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3993b-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3993b-189">autodiscover</span></span>  <br/> |<span data-ttu-id="3993b-190">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-190">3600</span></span>  <br/> |<span data-ttu-id="3993b-191">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-191">@ (none)</span></span>  <br/> |<span data-ttu-id="3993b-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3993b-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="3993b-193">sip</span><span class="sxs-lookup"><span data-stu-id="3993b-193">sip</span></span>  <br/> |<span data-ttu-id="3993b-194">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-194">3600</span></span>  <br/> |<span data-ttu-id="3993b-195">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-195">@ (none)</span></span>  <br/> |<span data-ttu-id="3993b-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3993b-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3993b-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3993b-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3993b-198">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-198">3600</span></span>  <br/> |<span data-ttu-id="3993b-199">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-199">@ (none)</span></span>  <br/> | <span data-ttu-id="3993b-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3993b-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="3993b-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3993b-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3993b-202">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-202">3600</span></span>  <br/> |<span data-ttu-id="3993b-203">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-203">@ (none)</span></span>  <br/> |<span data-ttu-id="3993b-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3993b-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="3993b-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3993b-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3993b-206">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-206">3600</span></span>  <br/> |<span data-ttu-id="3993b-207">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-207">@ (none)</span></span>  <br/> |<span data-ttu-id="3993b-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3993b-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="3993b-209">msoid</span><span class="sxs-lookup"><span data-stu-id="3993b-209">msoid</span></span>  <br/> |<span data-ttu-id="3993b-210">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-210">3600</span></span>  <br/> |<span data-ttu-id="3993b-211">@ (なし)</span><span class="sxs-lookup"><span data-stu-id="3993b-211">@ (none)</span></span>  <br/> |<span data-ttu-id="3993b-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="3993b-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="3993b-213">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="3993b-214">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="3993b-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3993b-215">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3993b-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3993b-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3993b-217">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3993b-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3993b-218">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="3993b-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3993b-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="3993b-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="3993b-220">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="3993b-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="3993b-221">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3993b-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3993b-222">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="3993b-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="3993b-223">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3993b-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3993b-224">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="3993b-225">[ **Domain Names** ] ページの [ **Text (txt records)**] で、[ **txt レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="3993b-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="3993b-226">**Host**</span></span>|<span data-ttu-id="3993b-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3993b-227">**TTL**</span></span>|<span data-ttu-id="3993b-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="3993b-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3993b-229">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-229">3600</span></span>  <br/> |<span data-ttu-id="3993b-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3993b-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3993b-231">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3993b-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="3993b-232">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-232">Select **Continue**.</span></span>

6. <span data-ttu-id="3993b-233">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="3993b-234">Office 365 に必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="3993b-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="3993b-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3993b-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3993b-236">Web.com は、この機能を使用できるようにする責任があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="3993b-237">次の手順と現在の web.com GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Web.com コミュニティ](https://community.web.com.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="3993b-238">まず、[このリンク](https://checkout.web.com/manage-it/index.jsp)を使って web.com でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3993b-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="3993b-239">最初にログインします。</span><span class="sxs-lookup"><span data-stu-id="3993b-239">Log in first.</span></span>
      
2. <span data-ttu-id="3993b-240">[**アカウントマネージャー** ] ページで、[ **My Domain Names**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3993b-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="3993b-241">[\* \* Manage \* my domain \* \* \*] で、[ **ADVANCED DNS レコードの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="3993b-242">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3993b-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="3993b-243">[**サービス (Srv レコード)**] で、[ **Srv レコードの編集**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="3993b-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="3993b-244">**Service**</span></span>|<span data-ttu-id="3993b-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="3993b-245">**Protocol**</span></span>|<span data-ttu-id="3993b-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3993b-246">**TTL**</span></span>|<span data-ttu-id="3993b-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3993b-247">**Priority**</span></span>|<span data-ttu-id="3993b-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="3993b-248">**Weight**</span></span>|<span data-ttu-id="3993b-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="3993b-249">**Port**</span></span>|<span data-ttu-id="3993b-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="3993b-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3993b-251">_sip</span><span class="sxs-lookup"><span data-stu-id="3993b-251">_sip</span></span> |<span data-ttu-id="3993b-252">_tls</span><span class="sxs-lookup"><span data-stu-id="3993b-252">_tls</span></span> |<span data-ttu-id="3993b-253">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-253">3600</span></span> | <span data-ttu-id="3993b-254">100</span><span class="sxs-lookup"><span data-stu-id="3993b-254">100</span></span>|<span data-ttu-id="3993b-255">1-d</span><span class="sxs-lookup"><span data-stu-id="3993b-255">1</span></span> |<span data-ttu-id="3993b-256">443</span><span class="sxs-lookup"><span data-stu-id="3993b-256">443</span></span> |<span data-ttu-id="3993b-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3993b-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="3993b-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3993b-258">_sipfederationtls</span></span> |<span data-ttu-id="3993b-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="3993b-259">_tcp</span></span> |<span data-ttu-id="3993b-260">3600</span><span class="sxs-lookup"><span data-stu-id="3993b-260">3600</span></span> |<span data-ttu-id="3993b-261">100</span><span class="sxs-lookup"><span data-stu-id="3993b-261">100</span></span> |<span data-ttu-id="3993b-262">1-d</span><span class="sxs-lookup"><span data-stu-id="3993b-262">1</span></span> |<span data-ttu-id="3993b-263">5061</span><span class="sxs-lookup"><span data-stu-id="3993b-263">5061</span></span> | <span data-ttu-id="3993b-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3993b-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="3993b-265">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3993b-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="3993b-266">[**続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-266">Select **Continue**.</span></span>

7. <span data-ttu-id="3993b-267">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3993b-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="3993b-p116">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3993b-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
