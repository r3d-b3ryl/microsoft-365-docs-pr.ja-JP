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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: ドメインを確認し、電子メール、Skype for Business Online、および Cloudflare for Microsoft の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919629"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="a7e1b-103">Cloudflare で Microsoft 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="a7e1b-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7e1b-105">使用している DNS ホスティング プロバイダーが Cloudflare の場合は、この記事に記載された手順に従って、ドメインの確認とメールや Skype for Business Online などの DNS レコードのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a7e1b-106">Cloudflare でこれらのレコードを追加すると、使用しているドメインが、Microsoft 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="a7e1b-107">Microsoft での Web サイト向け Web ホスティングと DNS の詳細については、「[Microsoft での一般向け Web サイトの使用](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a7e1b-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a7e1b-111">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a7e1b-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e1b-113">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a7e1b-114">Cloudflare にサインアップしたときに、Cloudflare の [ **Setup**] プロセスを使用してドメインを追加しました。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="a7e1b-115">追加したドメインは、Cloudflare または別のドメインレジストラーから購入されました。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="a7e1b-116">Microsoft 365 でドメインの DNS レコードを確認および作成するには、まず、Cloudflare のネームサーバーを使用するようにドメインレジストラーでネームサーバーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="a7e1b-117">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a7e1b-118">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a7e1b-119">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a7e1b-120">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="a7e1b-120">First nameserver</span></span>  <br/> |<span data-ttu-id="a7e1b-121">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-122">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="a7e1b-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="a7e1b-123">Cloudflare によって提供されるネーム サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="a7e1b-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a7e1b-124">You should use at least two name server records.</span></span> <span data-ttu-id="a7e1b-125">他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="a7e1b-126">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7e1b-127">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a7e1b-128">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7e1b-129">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-129">Add a TXT record for verification</span></span>
<span data-ttu-id="a7e1b-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a7e1b-p105">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7e1b-p106">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a7e1b-135">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7e1b-136">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="a7e1b-137">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7e1b-138">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7e1b-139">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7e1b-140">**型**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-140">**Type**</span></span>|<span data-ttu-id="a7e1b-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-141">**Name**</span></span>|<span data-ttu-id="a7e1b-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-142">**Automatic TTL**</span></span>|<span data-ttu-id="a7e1b-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="a7e1b-144">TXT</span><span class="sxs-lookup"><span data-stu-id="a7e1b-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7e1b-145">30 分</span><span class="sxs-lookup"><span data-stu-id="a7e1b-145">30 minutes</span></span>  <br/> |<span data-ttu-id="a7e1b-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7e1b-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7e1b-147">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-147">**Note:** This is an example.</span></span> <span data-ttu-id="a7e1b-148">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a7e1b-149">確認する方法</span><span class="sxs-lookup"><span data-stu-id="a7e1b-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="a7e1b-150">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="a7e1b-151">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7e1b-152">これで、ドメインレジストラーのサイトでレコードが追加されたので、Microsoft に戻ってレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="a7e1b-153">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7e1b-154">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a7e1b-155">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a7e1b-156">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a7e1b-157">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a7e1b-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a7e1b-161">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="a7e1b-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a7e1b-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a7e1b-p110">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="a7e1b-165">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7e1b-166">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7e1b-167">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7e1b-168">**型**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-168">**Type**</span></span>|<span data-ttu-id="a7e1b-169">**名前**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-169">**Name**</span></span>|<span data-ttu-id="a7e1b-170">**メール サーバー**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-170">**Mail server**</span></span>|<span data-ttu-id="a7e1b-171">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-171">**Priority**</span></span>|<span data-ttu-id="a7e1b-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e1b-173">MX</span><span class="sxs-lookup"><span data-stu-id="a7e1b-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7e1b-174">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7e1b-175">**注:** Microsoft 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="a7e1b-176">確認する方法</span><span class="sxs-lookup"><span data-stu-id="a7e1b-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="a7e1b-177">1-d</span><span class="sxs-lookup"><span data-stu-id="a7e1b-177">1</span></span>  <br/> <span data-ttu-id="a7e1b-178">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="a7e1b-179">30 分</span><span class="sxs-lookup"><span data-stu-id="a7e1b-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="a7e1b-180">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="a7e1b-181">[ **MX Records**] セクションに他の MX レコードが一覧表示されている場合は、[ **Delete (X)**] アイコンを選択してそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="a7e1b-182">確認ダイアログボックスで、[**削除**] を選択して変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7e1b-183">Microsoft に必要な6つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a7e1b-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a7e1b-p112">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="a7e1b-187">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7e1b-188">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7e1b-189">5つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="a7e1b-190">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="a7e1b-191">**型**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-191">**Type**</span></span>|<span data-ttu-id="a7e1b-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-192">**Name**</span></span>|<span data-ttu-id="a7e1b-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-193">**Target**</span></span>|<span data-ttu-id="a7e1b-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e1b-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-195">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a7e1b-196">autodiscover</span></span>  <br/> |<span data-ttu-id="a7e1b-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a7e1b-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-199">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-200">sip</span><span class="sxs-lookup"><span data-stu-id="a7e1b-200">sip</span></span>  <br/> |<span data-ttu-id="a7e1b-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a7e1b-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-203">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7e1b-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7e1b-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a7e1b-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-207">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7e1b-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7e1b-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a7e1b-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a7e1b-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-211">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7e1b-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7e1b-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a7e1b-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7e1b-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7e1b-215">CNAME</span></span>  <br/> |<span data-ttu-id="a7e1b-216">msoid</span><span class="sxs-lookup"><span data-stu-id="a7e1b-216">msoid</span></span>  <br/> |<span data-ttu-id="a7e1b-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="a7e1b-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="a7e1b-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="a7e1b-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="a7e1b-219">[ **DNS トラフィック**] アイコン (オレンジのクラウド) を選択して、cloudflare サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="a7e1b-220">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="a7e1b-221">他の 5 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7e1b-222">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7e1b-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e1b-224">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7e1b-225">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7e1b-226">使用しているドメインに既に SPF レコードがある場合は、Microsoft 365 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="a7e1b-227">代わりに、現在のレコードに Microsoft 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが "*1 つ*" の SPF レコードに含まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a7e1b-228">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7e1b-229">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="a7e1b-230">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7e1b-231">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7e1b-232">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="a7e1b-233">**型**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-233">**Type**</span></span>|<span data-ttu-id="a7e1b-234">**名前**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-234">**Name**</span></span>|<span data-ttu-id="a7e1b-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-235">**TTL**</span></span>|<span data-ttu-id="a7e1b-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e1b-237">TXT</span><span class="sxs-lookup"><span data-stu-id="a7e1b-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7e1b-238">30 分</span><span class="sxs-lookup"><span data-stu-id="a7e1b-238">30 minutes</span></span>  <br/> |<span data-ttu-id="a7e1b-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7e1b-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7e1b-240">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="a7e1b-241">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7e1b-242">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a7e1b-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a7e1b-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7e1b-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7e1b-244">Cloudflare は、この機能を使用できるようにする必要があることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="a7e1b-245">次の手順と現在の Cloudflare GUI (グラフィカルユーザーインターフェイス) の間に矛盾がある場合は、 [Cloudflare コミュニティ](https://community.cloudflare.com/)を活用してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="a7e1b-246">まず、[このリンク](https://www.cloudflare.com/a/login)を使って Cloudflare でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7e1b-247">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="a7e1b-248">[**ホーム**] ページで、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7e1b-249">ドメインの [**概要**] ページで、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="a7e1b-250">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="a7e1b-251">[ **DNS の管理**] ページで、[**レコードの追加**] をクリックし、次の表の1行目の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="a7e1b-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-252">**Type**</span></span>|<span data-ttu-id="a7e1b-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-253">**Service**</span></span>|<span data-ttu-id="a7e1b-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-254">**Protocol**</span></span>|<span data-ttu-id="a7e1b-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-255">**Name**</span></span>|<span data-ttu-id="a7e1b-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-256">**TTL**</span></span>|<span data-ttu-id="a7e1b-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-257">**Priority**</span></span>|<span data-ttu-id="a7e1b-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-258">**Weight**</span></span>|<span data-ttu-id="a7e1b-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-259">**Port**</span></span>|<span data-ttu-id="a7e1b-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="a7e1b-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7e1b-261">SRV</span><span class="sxs-lookup"><span data-stu-id="a7e1b-261">SRV</span></span>|<span data-ttu-id="a7e1b-262">_sip</span><span class="sxs-lookup"><span data-stu-id="a7e1b-262">_sip</span></span> |<span data-ttu-id="a7e1b-263">TLS</span><span class="sxs-lookup"><span data-stu-id="a7e1b-263">TLS</span></span> |<span data-ttu-id="a7e1b-264">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="a7e1b-265">30 分</span><span class="sxs-lookup"><span data-stu-id="a7e1b-265">30 minutes</span></span> | <span data-ttu-id="a7e1b-266">100</span><span class="sxs-lookup"><span data-stu-id="a7e1b-266">100</span></span>|<span data-ttu-id="a7e1b-267">1-d</span><span class="sxs-lookup"><span data-stu-id="a7e1b-267">1</span></span> |<span data-ttu-id="a7e1b-268">443</span><span class="sxs-lookup"><span data-stu-id="a7e1b-268">443</span></span> |<span data-ttu-id="a7e1b-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="a7e1b-270">SRV</span><span class="sxs-lookup"><span data-stu-id="a7e1b-270">SRV</span></span>|<span data-ttu-id="a7e1b-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a7e1b-271">_sipfederationtls</span></span> | <span data-ttu-id="a7e1b-272">TCP</span><span class="sxs-lookup"><span data-stu-id="a7e1b-272">TCP</span></span>|<span data-ttu-id="a7e1b-273">*Domain_name*を使用します。たとえば、contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="a7e1b-274">30 分</span><span class="sxs-lookup"><span data-stu-id="a7e1b-274">30 minutes</span></span> |<span data-ttu-id="a7e1b-275">100</span><span class="sxs-lookup"><span data-stu-id="a7e1b-275">100</span></span> |<span data-ttu-id="a7e1b-276">1-d</span><span class="sxs-lookup"><span data-stu-id="a7e1b-276">1</span></span> |<span data-ttu-id="a7e1b-277">5061</span><span class="sxs-lookup"><span data-stu-id="a7e1b-277">5061</span></span> | <span data-ttu-id="a7e1b-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7e1b-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="a7e1b-279">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="a7e1b-280">表の2行目の値を選択して、他の SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="a7e1b-p117">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7e1b-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
