---
title: ネームサーバーを変更して、ドメイン レジストラー Microsoft 365をセットアップする
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 電子メールやオンラインのようなサービスが独自のドメインMicrosoft 365使用するために、Skype for Businessドメインを追加して設定する方法について説明します。
ms.openlocfilehash: c6394b505e025c565713aae753879601f5a6aecf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635440"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="4846f-103">ネームサーバーを変更して、ドメイン レジストラー Microsoft 365をセットアップする</span><span class="sxs-lookup"><span data-stu-id="4846f-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="4846f-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4846f-105">次の手順に従って、メールやメールMicrosoft 365サービスが独自のドメイン名を使用Teamsドメインを追加および設定します。</span><span class="sxs-lookup"><span data-stu-id="4846f-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="4846f-106">これを行うには、ドメインを確認し、ドメインのネームサーバーを Microsoft 365 に変更して、正しい DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="4846f-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="4846f-107">次のステートメントで状況が説明されている場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4846f-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="4846f-108">独自のドメインを持ち、このドメインを設定してドメインを使用Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="4846f-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="4846f-109">DNS レコードMicrosoft 365管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="4846f-110">(必要に応じて、独自 [の DNS レコードを管理できます](../setup/add-domain.md)。)</span><span class="sxs-lookup"><span data-stu-id="4846f-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="4846f-111">確認のため TXT レコードまたは MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="4846f-111">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="4846f-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4846f-112"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="4846f-p103">これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="4846f-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="4846f-p104">Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4846f-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4846f-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4846f-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="4846f-119">DNS ホスティング プロバイダーの Web サイトで、新しいレコードを作成できる領域を見つける</span><span class="sxs-lookup"><span data-stu-id="4846f-119">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="4846f-120">DNS ホスティング プロバイダーの Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4846f-120">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="4846f-121">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="4846f-121">Choose your domain.</span></span>
    
3. <span data-ttu-id="4846f-122">ドメインに関する DNS レコードを編集可能なページを探します。</span><span class="sxs-lookup"><span data-stu-id="4846f-122">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="4846f-123">レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="4846f-123">Create the record</span></span>

<span data-ttu-id="4846f-124">TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="4846f-124">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="4846f-125">**TXT レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="4846f-125">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4846f-126">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4846f-126">**Record Type**</span></span> <br/> |<span data-ttu-id="4846f-127">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="4846f-127">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="4846f-128">**Value**</span><span class="sxs-lookup"><span data-stu-id="4846f-128">**Value**</span></span> <br/> |<span data-ttu-id="4846f-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4846f-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="4846f-130">TXT</span><span class="sxs-lookup"><span data-stu-id="4846f-130">TXT</span></span>  <br/> |<span data-ttu-id="4846f-131">次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。  </span><span class="sxs-lookup"><span data-stu-id="4846f-131">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="4846f-132">> [!NOTE]> このフィールドの要件は、DNS ホストによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4846f-132">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="4846f-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4846f-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4846f-134">> [!NOTE]> これは例です。</span><span class="sxs-lookup"><span data-stu-id="4846f-134">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="4846f-135">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-135">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="4846f-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4846f-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4846f-137">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="4846f-137">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="4846f-138">**MX レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="4846f-138">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4846f-139">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="4846f-139">**Record Type**</span></span>|<span data-ttu-id="4846f-140">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="4846f-140">**Alias** or **Host Name**</span></span>|<span data-ttu-id="4846f-141">**Value**</span><span class="sxs-lookup"><span data-stu-id="4846f-141">**Value**</span></span>|<span data-ttu-id="4846f-142">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4846f-142">**Priority**</span></span>|<span data-ttu-id="4846f-143">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4846f-143">**TTL**</span></span>|
|<span data-ttu-id="4846f-144">MX</span><span class="sxs-lookup"><span data-stu-id="4846f-144">MX</span></span>|<span data-ttu-id="4846f-145">**@** か自分のドメインの名前のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="4846f-145">Type either **@** or your domain name.</span></span> |<span data-ttu-id="4846f-146">MS=ms *XXXXXXXX* > [!NOTE]> これは例です。</span><span class="sxs-lookup"><span data-stu-id="4846f-146">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="4846f-147">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-147">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="4846f-148">確認する方法</span><span class="sxs-lookup"><span data-stu-id="4846f-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4846f-149">**Priority** には、メール フローに使われる MX レコードとの競合を避けるために、既存の MX レコードよりも低い優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="4846f-149">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="4846f-150">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-150">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="4846f-151">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="4846f-151">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="4846f-152">レコードを保存する</span><span class="sxs-lookup"><span data-stu-id="4846f-152">Save the record</span></span>

<span data-ttu-id="4846f-153">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="4846f-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="4846f-154">Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="4846f-154">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="4846f-155">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4846f-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4846f-156">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="4846f-157">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-157">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="4846f-158">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4846f-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4846f-162">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="4846f-162">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="4846f-163"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="4846f-163"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="4846f-164">ドメイン セットアップ ウィザードの最後の手順に進み、Microsoft 365タスクが 1 つ残っています。</span><span class="sxs-lookup"><span data-stu-id="4846f-164">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="4846f-165">メールなど、Microsoft 365 サービスを使用してドメインを設定するには、ドメイン レジストラーでドメインのネームサーバー (または NS) レコードを変更して、Microsoft 365 プライマリ ネームサーバーとセカンダリ ネームサーバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="4846f-165">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="4846f-166">次に、DNS Microsoft 365ホストしている場合、サービスに必要な DNS レコードが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4846f-166">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="4846f-167">ネーム サーバー レコード自体は、ドメイン レジストラーが Web サイトのヘルプで説明している手順に従って更新できます。</span><span class="sxs-lookup"><span data-stu-id="4846f-167">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="4846f-168">DNS が不明である場合は、ドメイン レジストラーのサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="4846f-168">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="4846f-169">ドメイン レジストラーの Web サイトでドメインのネームサーバーを自分で変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4846f-169">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="4846f-170">ドメインレジストラーの Web サイトで、ドメインのネームサーバーまたはカスタム ネームサーバーを使用できる領域を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4846f-170">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="4846f-171">ネーム サーバー レコードを作成するか、既存のネーム サーバー レコードを編集して、次の値に一致します。</span><span class="sxs-lookup"><span data-stu-id="4846f-171">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4846f-172">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-172">First nameserver</span></span>  <br/> |<span data-ttu-id="4846f-173">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4846f-173">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4846f-174">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-174">Second nameserver</span></span>  <br/> |<span data-ttu-id="4846f-175">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4846f-175">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4846f-176">3 番目のネームサーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-176">Third nameserver</span></span>  <br/> |<span data-ttu-id="4846f-177">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4846f-177">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="4846f-178">4 番目のネームサーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-178">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="4846f-179">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="4846f-179">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="4846f-180">4 つのレコードすべてが追加されるのが最善ですが、レジストラーが 2 つのみサポートしている場合は、ns1.bdm.microsoftonline.com **を\*\*\*\*追加** ns2.bdm.microsoftonline.com。</span><span class="sxs-lookup"><span data-stu-id="4846f-180">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="4846f-181">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="4846f-181">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="4846f-182">ドメインの NS レコードを変更して Microsoft 365 ネーム サーバーをポイントすると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="4846f-182">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4846f-183">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-183">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="4846f-184">それ以外の場合、この変更により、メール アクセスの不足や現在の Web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-184">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="4846f-185">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="4846f-185">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="4846f-186">2 つのネーム サーバー レコードを作成するか、既存のネーム サーバー レコードを編集して、次の値に一致します。</span><span class="sxs-lookup"><span data-stu-id="4846f-186">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4846f-187">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-187">First nameserver</span></span>  <br/> |<span data-ttu-id="4846f-188">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="4846f-188">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="4846f-189">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="4846f-189">Second nameserver</span></span>  <br/> |<span data-ttu-id="4846f-190">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="4846f-190">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="4846f-191">少なくとも 2 つのネーム サーバー レコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-191">You should use at least two nameserver records.</span></span> <span data-ttu-id="4846f-192">その他のネームサーバーが一覧表示されている場合は、それらを削除するか、または名前を **[ns3.dns.partner.microsoftonline.cn]** **ns4.dns.partner.microsoftonline.cn。**</span><span class="sxs-lookup"><span data-stu-id="4846f-192">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="4846f-193">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="4846f-193">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="4846f-194">ドメインの NS レコードを 21Vianet ネームサーバーが運用する Office 365 を指す値に変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="4846f-194">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="4846f-195">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-195">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="4846f-196">それ以外の場合、この変更により、メール アクセスの不足や現在の Web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-196">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="4846f-197">たとえば、電子メールと Web サイトのホスティングには、次のような追加の手順が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-197">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="4846f-198">NS レコードを変更する前に、ドメインを使用Microsoft 365メール アドレスを移動します。</span><span class="sxs-lookup"><span data-stu-id="4846f-198">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="4846f-199">www.fourthcoffee.com などの Web サイト アドレスで現在使用されているドメインを追加する場合は、ドメインの追加中に、サイトが現在ホストされている場所でこの Web サイトをホストし続けるための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4846f-199">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="4846f-200">ドメインの NS レコードを Microsoft 365 に変更した後も、ユーザーが Web サイトにアクセスできるよう、サイトがホストされている場所にドメインを追加する場合は、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4846f-200">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="4846f-201">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4846f-201">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="4846f-202">[**ドメイン**] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="4846f-202">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="4846f-203">[ドメインの詳細] ページで、[DNS レコード] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="4846f-203">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="4846f-204">[レコード **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4846f-204">Select **Add record**.</span></span>

5. <span data-ttu-id="4846f-205">[カスタム **DNS レコードの追加]** ウィンドウの [種類] ドロップダウン リストから **、[A] (アドレス) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4846f-205">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="4846f-206">[ホスト名 **] または [エイリアス] ボックスに「.** **@**</span><span class="sxs-lookup"><span data-stu-id="4846f-206">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="4846f-207">[IP **アドレス] ボックス** に、現在ホストされている Web サイトの静的 IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4846f-207">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="4846f-208">たとえば、172.16.140.1。</span><span class="sxs-lookup"><span data-stu-id="4846f-208">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="4846f-209">これは、動的 _IP_ アドレスではなく、Web サイトの静的 IP アドレス _である_ 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4846f-209">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="4846f-210">パブリック Web サイトの静的 IP アドレスを取得するには、Web サイトをホストするサイトに確認してください。</span><span class="sxs-lookup"><span data-stu-id="4846f-210">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="4846f-211">レコードの TTL 設定を変更する場合は **、TTL** ドロップダウン リストから新しい時間を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-211">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="4846f-212">それ以外の場合は、手順 9 に進みます。</span><span class="sxs-lookup"><span data-stu-id="4846f-212">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="4846f-213">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-213">Select **Save**.</span></span> 
    
<span data-ttu-id="4846f-214">さらに、CNAME レコードを作成して、Web サイトを顧客が簡単に見つけることができるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4846f-214">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="4846f-215">[レコード **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4846f-215">Select **Add record**.</span></span>

3.  <span data-ttu-id="4846f-216">[カスタム **DNS レコードの追加] ウィンドウの**[種類] ドロップダウン **リストから\*\*\*\*、[CNAME (エイリアス**) ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-216">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="4846f-217">[ホスト名 **] または [エイリアス] ボックスに\*\*\*\*「www」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="4846f-217">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="4846f-218">[ポイント **先アドレス] ボックス** に、Web サイトの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4846f-218">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="4846f-219">たとえば **contoso.com** です。</span><span class="sxs-lookup"><span data-stu-id="4846f-219">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="4846f-220">レコードの TTL 設定を変更する場合は **、TTL** ドロップダウン リストから新しい時間を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-220">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="4846f-221">それ以外の場合は、手順 6 に進みます。</span><span class="sxs-lookup"><span data-stu-id="4846f-221">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="4846f-222">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4846f-222">Select **Save**.</span></span>

<span data-ttu-id="4846f-223">ネームサーバー レコードが更新され、Microsoft をポイントすると、ドメインのセットアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="4846f-223">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="4846f-224">メールは Microsoft にルーティングされ、Web サイトアドレスへのトラフィックは現在の Web サイトのホストに引き続き送信されます。</span><span class="sxs-lookup"><span data-stu-id="4846f-224">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="4846f-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="4846f-225">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="4846f-226">その後、Microsoft の電子メールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4846f-226">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="4846f-227">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4846f-227">Related content</span></span>

<span data-ttu-id="4846f-228">[DNS レコードを追加してドメインに接続](create-dns-records-at-any-dns-hosting-provider.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="4846f-228">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="4846f-229">[ドメインまたは DNS レコードを追加した後で問題を](find-and-fix-issues.md) 見つけて修正する (記事)</span><span class="sxs-lookup"><span data-stu-id="4846f-229">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="4846f-230">[ドメインの管理](index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="4846f-230">[Manage domains](index.yml) (link page)</span></span>
