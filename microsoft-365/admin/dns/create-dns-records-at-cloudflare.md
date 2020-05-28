---
title: Cloudflare で Microsoft 用の DNS レコードを作成する
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および Cloudflare for Microsoft の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 9b717ddedaf6435f6599f4f75cc0fa7c4e618d59
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400547"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="bf657-103">Cloudflare で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="bf657-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="bf657-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bf657-105">使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="bf657-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bf657-106">Cloudflare でこれらのレコードを追加すると、使用しているドメインが、Microsoft 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="bf657-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="bf657-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="bf657-110">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="bf657-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="bf657-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf657-112">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf657-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="bf657-113">Cloudflare にサインアップしたときに、Cloudflare の [ **Setup**] プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="bf657-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="bf657-114">追加したドメインは、Cloudflare または別のドメインレジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="bf657-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="bf657-115">Microsoft 365 でドメインの DNS レコードを確認および作成するには、まず、Cloudflare のネームサーバーを使用するようにドメインレジストラーでネームサーバーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf657-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="bf657-116">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bf657-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="bf657-117">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="bf657-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="bf657-118">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="bf657-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="bf657-119">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="bf657-119">First nameserver</span></span>  <br/> |<span data-ttu-id="bf657-120">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf657-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="bf657-121">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="bf657-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="bf657-122">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf657-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="bf657-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="bf657-123">You should use at least two name server records.</span></span> <span data-ttu-id="bf657-124">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf657-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="bf657-125">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="bf657-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bf657-126">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf657-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="bf657-127">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="bf657-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="bf657-128">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bf657-128">Add a TXT record for verification</span></span>
<span data-ttu-id="bf657-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bf657-p105">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bf657-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf657-p106">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bf657-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="bf657-134">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bf657-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="bf657-135">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf657-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="bf657-136">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="bf657-137">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="bf657-138">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="bf657-139">**型**</span><span class="sxs-lookup"><span data-stu-id="bf657-139">**Type**</span></span>|<span data-ttu-id="bf657-140">**名前**</span><span class="sxs-lookup"><span data-stu-id="bf657-140">**Name**</span></span>|<span data-ttu-id="bf657-141">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="bf657-141">**Automatic TTL**</span></span>|<span data-ttu-id="bf657-142">**Content**</span><span class="sxs-lookup"><span data-stu-id="bf657-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="bf657-143">TXT</span><span class="sxs-lookup"><span data-stu-id="bf657-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="bf657-144">30 分</span><span class="sxs-lookup"><span data-stu-id="bf657-144">30 minutes</span></span>  <br/> |<span data-ttu-id="bf657-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bf657-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bf657-146">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="bf657-146">**Note:** This is an example.</span></span> <span data-ttu-id="bf657-147">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="bf657-148">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bf657-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="bf657-149">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="bf657-150">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="bf657-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bf657-151">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="bf657-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="bf657-152">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="bf657-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bf657-153">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bf657-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="bf657-154">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="bf657-155">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="bf657-156">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="bf657-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="bf657-160">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="bf657-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="bf657-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="bf657-p110">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf657-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="bf657-164">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="bf657-165">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="bf657-166">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="bf657-167">**型**</span><span class="sxs-lookup"><span data-stu-id="bf657-167">**Type**</span></span>|<span data-ttu-id="bf657-168">**名前**</span><span class="sxs-lookup"><span data-stu-id="bf657-168">**Name**</span></span>|<span data-ttu-id="bf657-169">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="bf657-169">**Mail server**</span></span>|<span data-ttu-id="bf657-170">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bf657-170">**Priority**</span></span>|<span data-ttu-id="bf657-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf657-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf657-172">MX</span><span class="sxs-lookup"><span data-stu-id="bf657-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="bf657-173">*\<domain-key\>*. mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bf657-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="bf657-174">\**注:\*\*\*\<domain-key\>* Microsoft 365 アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf657-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="bf657-175">確認する方法</span><span class="sxs-lookup"><span data-stu-id="bf657-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="bf657-176">1 </span><span class="sxs-lookup"><span data-stu-id="bf657-176">1</span></span>  <br/> <span data-ttu-id="bf657-177">優先度の詳細については、「[MX 優先度とは何か](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="bf657-178">30 分</span><span class="sxs-lookup"><span data-stu-id="bf657-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="bf657-179">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="bf657-180">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、[ **Delete (X)**] アイコンを選択してそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf657-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="bf657-181">確認ダイアログボックスで、[**削除**] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="bf657-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="bf657-182">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bf657-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="bf657-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="bf657-p112">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf657-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="bf657-186">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="bf657-187">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="bf657-188">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf657-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="bf657-189">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="bf657-190">**型**</span><span class="sxs-lookup"><span data-stu-id="bf657-190">**Type**</span></span>|<span data-ttu-id="bf657-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="bf657-191">**Name**</span></span>|<span data-ttu-id="bf657-192">**Target**</span><span class="sxs-lookup"><span data-stu-id="bf657-192">**Target**</span></span>|<span data-ttu-id="bf657-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf657-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf657-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-194">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bf657-195">autodiscover</span></span>  <br/> |<span data-ttu-id="bf657-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bf657-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="bf657-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="bf657-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-198">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-199">sip</span><span class="sxs-lookup"><span data-stu-id="bf657-199">sip</span></span>  <br/> |<span data-ttu-id="bf657-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bf657-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="bf657-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="bf657-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-202">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bf657-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bf657-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bf657-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="bf657-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="bf657-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-206">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bf657-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bf657-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="bf657-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="bf657-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="bf657-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-210">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bf657-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bf657-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bf657-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="bf657-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="bf657-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="bf657-214">CNAME</span></span>  <br/> |<span data-ttu-id="bf657-215">msoid</span><span class="sxs-lookup"><span data-stu-id="bf657-215">msoid</span></span>  <br/> |<span data-ttu-id="bf657-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="bf657-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="bf657-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="bf657-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="bf657-218">[ **DNS トラフィック**] アイコン (オレンジのクラウド) を選択して、cloudflare サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="bf657-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="bf657-219">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="bf657-220">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="bf657-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bf657-221">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bf657-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bf657-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf657-223">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf657-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bf657-224">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf657-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bf657-225">使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="bf657-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="bf657-226">代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="bf657-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="bf657-227">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bf657-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="bf657-228">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf657-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="bf657-229">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="bf657-230">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="bf657-231">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="bf657-232">**型**</span><span class="sxs-lookup"><span data-stu-id="bf657-232">**Type**</span></span>|<span data-ttu-id="bf657-233">**名前**</span><span class="sxs-lookup"><span data-stu-id="bf657-233">**Name**</span></span>|<span data-ttu-id="bf657-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf657-234">**TTL**</span></span>|<span data-ttu-id="bf657-235">**Content**</span><span class="sxs-lookup"><span data-stu-id="bf657-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf657-236">TXT</span><span class="sxs-lookup"><span data-stu-id="bf657-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="bf657-237">30 分</span><span class="sxs-lookup"><span data-stu-id="bf657-237">30 minutes</span></span>  <br/> |<span data-ttu-id="bf657-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bf657-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bf657-239">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf657-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="bf657-240">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="bf657-241">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="bf657-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="bf657-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bf657-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf657-243">Cloudflare は、この機能を使用できるようにする必要があることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="bf657-244">次の手順と現在の Cloudflare GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Cloudflare コミュニティ](https://community.cloudflare.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="bf657-245">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bf657-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="bf657-246">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf657-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="bf657-247">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="bf657-248">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="bf657-249">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf657-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="bf657-250">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の1行目の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="bf657-251">**Type**</span><span class="sxs-lookup"><span data-stu-id="bf657-251">**Type**</span></span>|<span data-ttu-id="bf657-252">**Service**</span><span class="sxs-lookup"><span data-stu-id="bf657-252">**Service**</span></span>|<span data-ttu-id="bf657-253">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="bf657-253">**Protocol**</span></span>|<span data-ttu-id="bf657-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="bf657-254">**Name**</span></span>|<span data-ttu-id="bf657-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="bf657-255">**TTL**</span></span>|<span data-ttu-id="bf657-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="bf657-256">**Priority**</span></span>|<span data-ttu-id="bf657-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="bf657-257">**Weight**</span></span>|<span data-ttu-id="bf657-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="bf657-258">**Port**</span></span>|<span data-ttu-id="bf657-259">**Target**</span><span class="sxs-lookup"><span data-stu-id="bf657-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bf657-260">SRV</span><span class="sxs-lookup"><span data-stu-id="bf657-260">SRV</span></span>|<span data-ttu-id="bf657-261">_sip</span><span class="sxs-lookup"><span data-stu-id="bf657-261">_sip</span></span> |<span data-ttu-id="bf657-262">TLS</span><span class="sxs-lookup"><span data-stu-id="bf657-262">TLS</span></span> |<span data-ttu-id="bf657-263">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf657-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="bf657-264">30 分</span><span class="sxs-lookup"><span data-stu-id="bf657-264">30 minutes</span></span> | <span data-ttu-id="bf657-265">100</span><span class="sxs-lookup"><span data-stu-id="bf657-265">100</span></span>|<span data-ttu-id="bf657-266">1 </span><span class="sxs-lookup"><span data-stu-id="bf657-266">1</span></span> |<span data-ttu-id="bf657-267">443</span><span class="sxs-lookup"><span data-stu-id="bf657-267">443</span></span> |<span data-ttu-id="bf657-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bf657-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="bf657-269">SRV</span><span class="sxs-lookup"><span data-stu-id="bf657-269">SRV</span></span>|<span data-ttu-id="bf657-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bf657-270">_sipfederationtls</span></span> | <span data-ttu-id="bf657-271">TCP</span><span class="sxs-lookup"><span data-stu-id="bf657-271">TCP</span></span>|<span data-ttu-id="bf657-272">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf657-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="bf657-273">30 分</span><span class="sxs-lookup"><span data-stu-id="bf657-273">30 minutes</span></span> |<span data-ttu-id="bf657-274">100</span><span class="sxs-lookup"><span data-stu-id="bf657-274">100</span></span> |<span data-ttu-id="bf657-275">1 </span><span class="sxs-lookup"><span data-stu-id="bf657-275">1</span></span> |<span data-ttu-id="bf657-276">5061</span><span class="sxs-lookup"><span data-stu-id="bf657-276">5061</span></span> | <span data-ttu-id="bf657-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bf657-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="bf657-278">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf657-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="bf657-279">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf657-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="bf657-p117">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf657-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
