---
title: Azure DNS ゾーンの DNS レコードを作成する
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: ドメインを確認して、Microsoft の Azure DNS ゾーンで、電子メール、Skype for Business Online、その他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 40fadb81ebd0ae5385bbbdad727b1c579142b227
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645673"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="9e721-103">Azure DNS ゾーンの DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="9e721-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="9e721-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9e721-105">Azure が DNS ホスティングプロバイダーである場合は、この記事の手順に従って、ドメインを確認し、電子メール、Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9e721-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9e721-106">追加する主なレコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e721-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="9e721-107">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="9e721-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="9e721-108">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="9e721-109">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9e721-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="9e721-110">Microsoft に必要な4つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="9e721-111">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="9e721-112">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="9e721-113">これらのレコードを Azure で追加すると、使用しているドメインが Microsoft サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e721-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e721-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9e721-117">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="9e721-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9e721-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e721-119">この手順は、ドメインを購入して登録したドメイン レジストラーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9e721-120">Azure にサインアップしたときに、DNS ゾーン内にリソースグループを作成し、そのリソースグループにドメイン名を割り当てました。</span><span class="sxs-lookup"><span data-stu-id="9e721-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="9e721-121">そのドメイン名は、外部ドメインレジストラーに登録されています。Azure では、ドメイン登録サービスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="9e721-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="9e721-122">Microsoft でドメインの DNS レコードを確認および作成するには、まず、ドメインレジストラーでネームサーバーを変更して、リソースグループに割り当てられている Azure ネームサーバーを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="9e721-123">ドメイン レジストラーの Web サイトで、自分でドメインのネーム サーバーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9e721-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9e721-124">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="9e721-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9e721-125">次の表の値を使用して、2 つのネーム サーバー レコードを作成するか、またはこれらの値と一致するように、既存のネーム サーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="9e721-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="9e721-126">Azure に割り当てられたネームサーバーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9e721-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="9e721-127">**最初のネームサーバー:** Azure によって割り当てられた名前サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e721-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="9e721-128">**2 番目のネームサーバー:** Azure によって割り当てられた名前サーバーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e721-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="9e721-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="9e721-130">You should use at least two name server records.</span></span> <span data-ttu-id="9e721-131">ドメインレジストラーの web サイトに他のネームサーバーが表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="9e721-132">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="9e721-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e721-133">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e721-134">その後、自分のドメインで使用できるように、Microsoft メールとその他のサービスがすべて設定されます。</span><span class="sxs-lookup"><span data-stu-id="9e721-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e721-135">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-135">Add a TXT record for verification</span></span>
<span data-ttu-id="9e721-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9e721-p106">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="9e721-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e721-p107">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9e721-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9e721-141">まず、 [このリンク](https://portal.azure.com )を使用して Azure でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e721-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="9e721-142">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e721-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-構成-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="9e721-144">**ダッシュボード**ページの**検索バー**を使用して、[ **DNS ゾーン**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="9e721-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="9e721-145">結果の表示で、[**サービス**] の下にある [ **DNS zones** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="9e721-146">リダイレクトされたら、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-構成-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="9e721-148">ドメインの [ **設定** ] ページの [ **DNS ゾーン** ] 領域で、[ **+ Record set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-構成-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="9e721-150">[ **Add record set** ] 領域の新規レコードセットのボックスで、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="9e721-151">(ドロップダウンリストから [ **Type** ] と [ **TTL の単位** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e721-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="9e721-152">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-152">**Name**</span></span>|<span data-ttu-id="9e721-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-153">**Type**</span></span>|<span data-ttu-id="9e721-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-154">**TTL**</span></span>|<span data-ttu-id="9e721-155">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-155">**TTL unit**</span></span>|<span data-ttu-id="9e721-156">**値**</span><span class="sxs-lookup"><span data-stu-id="9e721-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9e721-157">TXT</span><span class="sxs-lookup"><span data-stu-id="9e721-157">TXT</span></span>  <br/> |<span data-ttu-id="9e721-158">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-158">1</span></span>  <br/> |<span data-ttu-id="9e721-159">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-159">Hours</span></span>  <br/> |<span data-ttu-id="9e721-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e721-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e721-161">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="9e721-161">**Note:** This is an example.</span></span> <span data-ttu-id="9e721-162">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9e721-163">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9e721-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-検証-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="9e721-165">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="9e721-166">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9e721-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e721-167">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。</span><span class="sxs-lookup"><span data-stu-id="9e721-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9e721-168">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="9e721-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e721-169">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e721-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9e721-170">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9e721-171">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9e721-172">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9e721-p111">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9e721-176">MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする</span><span class="sxs-lookup"><span data-stu-id="9e721-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9e721-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9e721-178">まず、 [このリンク](https://portal.azure.com )を使用して Azure でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e721-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="9e721-179">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e721-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-構成-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="9e721-181">[ **ダッシュボード** ] ページの [ **すべてのリソース** ] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-構成-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="9e721-183">ドメインの [ **設定** ] ページの [ **DNS ゾーン** ] 領域で、[ **+ Record set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-構成-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="9e721-185">[ **Add record set** ] 領域の新規レコードセットのボックスで、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="9e721-186">(ドロップダウンリストから [ **Type** ] と [ **TTL の単位** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e721-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="9e721-187">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-187">**Name**</span></span>|<span data-ttu-id="9e721-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-188">**Type**</span></span>|<span data-ttu-id="9e721-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-189">**TTL**</span></span>|<span data-ttu-id="9e721-190">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-190">**TTL unit**</span></span>|<span data-ttu-id="9e721-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="9e721-191">**Preference**</span></span>|<span data-ttu-id="9e721-192">**メール交換**</span><span class="sxs-lookup"><span data-stu-id="9e721-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9e721-193">MX</span><span class="sxs-lookup"><span data-stu-id="9e721-193">MX</span></span>  <br/> |<span data-ttu-id="9e721-194">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-194">1</span></span>  <br/> |<span data-ttu-id="9e721-195">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-195">Hours</span></span>  <br/> |<span data-ttu-id="9e721-196">10  </span><span class="sxs-lookup"><span data-stu-id="9e721-196">10</span></span>  <br/> <span data-ttu-id="9e721-197">優先度の詳細については、「[MX 優先度とは何ですか?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="9e721-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e721-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9e721-199">\**注:\*\*\*\<domain-key\>* Microsoft アカウントからを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e721-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="9e721-200">確認する方法</span><span class="sxs-lookup"><span data-stu-id="9e721-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-構成-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="9e721-202">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-202">Select **OK**.</span></span>
    
    ![Azure-BP-構成-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="9e721-204">その他の MX レコードが [ **Mx records** ] セクションに一覧表示されている場合は、それらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="9e721-205">最初に、[ **DNS ゾーン** ] 領域で **MX レコードセット**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-構成-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="9e721-207">次に、削除する MX レコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-構成-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="9e721-209">**コンテキストメニュー (...)** を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-構成-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="9e721-211">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-211">Select **Save**.</span></span>
    
    ![Azure-BP-構成-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e721-213">Microsoft に必要な4つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9e721-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9e721-215">まず、 [このリンク](https://portal.azure.com )を使用して Azure でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e721-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="9e721-216">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e721-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-構成-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="9e721-218">[ **ダッシュボード** ] ページの [ **すべてのリソース** ] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-構成-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="9e721-220">ドメインの [ **設定** ] ページの [ **DNS ゾーン** ] 領域で、[ **+ Record set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-構成-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="9e721-222">4 つのレコードの最初の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="9e721-223">[ **Add record set** ] 領域にある新規レコードセットのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e721-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="9e721-224">(ドロップダウンリストから [ **Type** ] と [ **TTL の単位** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e721-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="9e721-225">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-225">**Name**</span></span>|<span data-ttu-id="9e721-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-226">**Type**</span></span>|<span data-ttu-id="9e721-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-227">**TTL**</span></span>|<span data-ttu-id="9e721-228">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-228">**TTL unit**</span></span>|<span data-ttu-id="9e721-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e721-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e721-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9e721-230">autodiscover</span></span>  <br/> |<span data-ttu-id="9e721-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e721-231">CNAME</span></span>  <br/> |<span data-ttu-id="9e721-232">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-232">1</span></span>  <br/> |<span data-ttu-id="9e721-233">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-233">Hours</span></span>  <br/> |<span data-ttu-id="9e721-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e721-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="9e721-235">sip</span><span class="sxs-lookup"><span data-stu-id="9e721-235">sip</span></span>  <br/> |<span data-ttu-id="9e721-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e721-236">CNAME</span></span>  <br/> |<span data-ttu-id="9e721-237">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-237">1</span></span>  <br/> |<span data-ttu-id="9e721-238">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-238">Hours</span></span>  <br/> |<span data-ttu-id="9e721-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e721-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9e721-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e721-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e721-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e721-241">CNAME</span></span>  <br/> |<span data-ttu-id="9e721-242">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-242">1</span></span>  <br/> |<span data-ttu-id="9e721-243">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-243">Hours</span></span>  <br/> |<span data-ttu-id="9e721-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e721-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-構成-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="9e721-246">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-246">Select **OK**.</span></span>
    
    ![Azure-BP-構成-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="9e721-248">他の 3 つの CNAME レコードをそれぞれ追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="9e721-249">[ **DNS zone** ] 領域で、[ **+ Record set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="9e721-250">空のレコードセットで、表の次の行の値を使用してレコードを作成し、もう一度 [ **OK** ] を選択してそのレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="9e721-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="9e721-251">4 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9e721-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="9e721-252">オプションMDM に2つの CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e721-253">Microsoft 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e721-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="9e721-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e721-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="9e721-255">(MDM を持っていない場合は、この手順を省略できます)。</span><span class="sxs-lookup"><span data-stu-id="9e721-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="9e721-256">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-256">**Name**</span></span>|<span data-ttu-id="9e721-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-257">**Type**</span></span>|<span data-ttu-id="9e721-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-258">**TTL**</span></span>|<span data-ttu-id="9e721-259">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-259">**TTL unit**</span></span>|<span data-ttu-id="9e721-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="9e721-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e721-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e721-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e721-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e721-262">CNAME</span></span>  <br/> |<span data-ttu-id="9e721-263">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-263">1</span></span>  <br/> |<span data-ttu-id="9e721-264">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-264">Hours</span></span>  <br/> |<span data-ttu-id="9e721-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9e721-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="9e721-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e721-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e721-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="9e721-267">CNAME</span></span>  <br/> |<span data-ttu-id="9e721-268">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-268">1</span></span>  <br/> |<span data-ttu-id="9e721-269">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-269">Hours</span></span>  <br/> |<span data-ttu-id="9e721-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e721-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e721-271">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9e721-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e721-273">1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e721-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e721-274">1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9e721-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e721-275">使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="9e721-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9e721-276">代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9e721-277">まず、 [このリンク](https://portal.azure.com )を使用して Azure でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e721-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="9e721-278">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e721-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-構成-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="9e721-280">[ **ダッシュボード** ] ページの [ **すべてのリソース** ] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-構成-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="9e721-282">[ **DNS zone** ] 領域で、 **TXT レコードセット**を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-構成-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="9e721-284">[ **レコードセットのプロパティ** ] 領域の新規レコードセットのボックスで、次の表の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="9e721-285">(ドロップダウンリストから [ **Type** ] と [ **TTL の単位** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e721-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="9e721-286">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-286">**Name**</span></span>|<span data-ttu-id="9e721-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-287">**Type**</span></span>|<span data-ttu-id="9e721-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-288">**TTL**</span></span>|<span data-ttu-id="9e721-289">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-289">**TTL unit**</span></span>|<span data-ttu-id="9e721-290">**値**</span><span class="sxs-lookup"><span data-stu-id="9e721-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9e721-291">TXT</span><span class="sxs-lookup"><span data-stu-id="9e721-291">TXT</span></span>  <br/> |<span data-ttu-id="9e721-292">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-292">1</span></span>  <br/> |<span data-ttu-id="9e721-293">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-293">Hours</span></span>  <br/> |<span data-ttu-id="9e721-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e721-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e721-295">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e721-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-構成-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="9e721-297">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-297">Select **Save**.</span></span>
    
    ![Azure-BP-構成-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e721-299">Microsoft で必要な 2 つの SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="9e721-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9e721-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9e721-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9e721-301">まず、 [このリンク](https://portal.azure.com )を使用して Azure でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e721-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="9e721-302">最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="9e721-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-構成-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="9e721-304">[ **ダッシュボード** ] ページの [ **すべてのリソース** ] 領域で、更新するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-構成-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="9e721-306">ドメインの [ **設定** ] ページの [ **DNS ゾーン** ] 領域で、[ **+ Record set**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-構成-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="9e721-308">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9e721-309">[ **Add record set** ] 領域の新規レコードセットのボックスで、次の表の最初の行の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="9e721-310">(ドロップダウンリストから [ **Type** ] と [ **TTL の単位** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="9e721-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="9e721-311">**名前**</span><span class="sxs-lookup"><span data-stu-id="9e721-311">**Name**</span></span>|<span data-ttu-id="9e721-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="9e721-312">**Type**</span></span>|<span data-ttu-id="9e721-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e721-313">**TTL**</span></span>|<span data-ttu-id="9e721-314">**TTL 単位**</span><span class="sxs-lookup"><span data-stu-id="9e721-314">**TTL unit**</span></span>|<span data-ttu-id="9e721-315">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9e721-315">**Priority**</span></span>|<span data-ttu-id="9e721-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9e721-316">**Weight**</span></span>|<span data-ttu-id="9e721-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="9e721-317">**Port**</span></span>|<span data-ttu-id="9e721-318">**対象**</span><span class="sxs-lookup"><span data-stu-id="9e721-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e721-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9e721-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="9e721-320">SRV</span><span class="sxs-lookup"><span data-stu-id="9e721-320">SRV</span></span>  <br/> |<span data-ttu-id="9e721-321">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-321">1</span></span>  <br/> |<span data-ttu-id="9e721-322">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-322">Hours</span></span>  <br/> |<span data-ttu-id="9e721-323">100</span><span class="sxs-lookup"><span data-stu-id="9e721-323">100</span></span>  <br/> |<span data-ttu-id="9e721-324">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-324">1</span></span>  <br/> |<span data-ttu-id="9e721-325">443</span><span class="sxs-lookup"><span data-stu-id="9e721-325">443</span></span>  <br/> |<span data-ttu-id="9e721-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e721-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="9e721-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9e721-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9e721-328">SRV</span><span class="sxs-lookup"><span data-stu-id="9e721-328">SRV</span></span>  <br/> |<span data-ttu-id="9e721-329">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-329">1</span></span>  <br/> |<span data-ttu-id="9e721-330">時間</span><span class="sxs-lookup"><span data-stu-id="9e721-330">Hours</span></span>  <br/> |<span data-ttu-id="9e721-331">100</span><span class="sxs-lookup"><span data-stu-id="9e721-331">100</span></span>  <br/> |<span data-ttu-id="9e721-332">1-d</span><span class="sxs-lookup"><span data-stu-id="9e721-332">1</span></span>  <br/> |<span data-ttu-id="9e721-333">5061</span><span class="sxs-lookup"><span data-stu-id="9e721-333">5061</span></span>  <br/> |<span data-ttu-id="9e721-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e721-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-構成-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="9e721-336">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e721-336">Select **OK**.</span></span>
    
    ![Azure-BP-構成-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="9e721-338">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e721-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9e721-339">新規レコードのボックスに、表の2行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9e721-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e721-p120">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e721-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
