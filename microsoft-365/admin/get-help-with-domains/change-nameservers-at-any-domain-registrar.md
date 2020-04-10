---
title: 任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更する
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: メールや Skype for Business Online などのサービスが独自のドメイン名を使用するように、Office 365 でドメインを追加してセットアップする方法について説明します。
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210494"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="f0197-103">任意のドメイン レジストラーで Office 365 をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="f0197-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="f0197-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0197-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f0197-105">最初に[ドメイン (ホスト固有の指示) を設定](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)し、レジストラーに関する指示があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0197-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="f0197-106">次の手順に従って、Office 365 にドメインを追加してセットアップします。これにより、電子メールや Skype for Business Online などのサービスが独自のドメイン名を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="f0197-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="f0197-107">これを行うには、ドメインを確認してから、ドメインのネームサーバーを Office 365 に変更して、適切な DNS レコードをセットアップできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0197-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="f0197-108">次のステートメントで状況を説明する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0197-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="f0197-109">独自のドメインがあり、Office 365 と連携するようにセットアップしたい。</span><span class="sxs-lookup"><span data-stu-id="f0197-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="f0197-p102">Office 365 で DNS レコードを管理したい ([独自の DNS レコードを管理することもできます](../setup/add-domain.md))。</span><span class="sxs-lookup"><span data-stu-id="f0197-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="f0197-112">確認のため TXT レコードまたは MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="f0197-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="f0197-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f0197-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="f0197-p103">これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="f0197-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="f0197-p104">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f0197-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0197-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f0197-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="f0197-120">DNS ホスティングプロバイダーの web サイトで、新しいレコードを作成できる領域を検索する</span><span class="sxs-lookup"><span data-stu-id="f0197-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="f0197-121">DNS ホスティング プロバイダーの Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f0197-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="f0197-122">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="f0197-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="f0197-123">ドメインに関する DNS レコードを編集可能なページを探します。</span><span class="sxs-lookup"><span data-stu-id="f0197-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="f0197-124">レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="f0197-124">Create the record</span></span>

<span data-ttu-id="f0197-125">TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0197-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="f0197-126">**TXT レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="f0197-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0197-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f0197-127">**Record Type**</span></span> <br/> |<span data-ttu-id="f0197-128">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="f0197-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="f0197-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="f0197-129">**Value**</span></span> <br/> |<span data-ttu-id="f0197-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0197-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="f0197-131">TXT</span><span class="sxs-lookup"><span data-stu-id="f0197-131">TXT</span></span>  <br/> |<span data-ttu-id="f0197-132">次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。  </span><span class="sxs-lookup"><span data-stu-id="f0197-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="f0197-133">> [!NOTE]> このフィールドの要件は、DNS ホストによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0197-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="f0197-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f0197-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f0197-p106">> [!NOTE]> これは例です。Office 365 の表にある [ **宛先またはポイント先のアドレス**] の値を指定してください。          [確認する方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f0197-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="f0197-138">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="f0197-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="f0197-139">**MX レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="f0197-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0197-140">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="f0197-140">**Record Type**</span></span>|<span data-ttu-id="f0197-141">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="f0197-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="f0197-142">**Value**</span><span class="sxs-lookup"><span data-stu-id="f0197-142">**Value**</span></span>|<span data-ttu-id="f0197-143">**Priority**</span><span class="sxs-lookup"><span data-stu-id="f0197-143">**Priority**</span></span>|<span data-ttu-id="f0197-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0197-144">**TTL**</span></span>|
|<span data-ttu-id="f0197-145">MX</span><span class="sxs-lookup"><span data-stu-id="f0197-145">MX</span></span>|<span data-ttu-id="f0197-146">**@** か自分のドメインの名前のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="f0197-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="f0197-p107">MS=ms *XXXXXXXX* > [!NOTE]> これは例です。Office 365 の表にある [ **宛先またはポイント先のアドレス**] の値を指定してください。          [確認する方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f0197-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="f0197-150">**Priority** には、メール フローに使われる MX レコードとの競合を避けるために、既存の MX レコードよりも低い優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0197-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="f0197-151">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.md#what-is-mx-priority)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0197-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="f0197-152">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="f0197-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="f0197-153">レコードを保存する</span><span class="sxs-lookup"><span data-stu-id="f0197-153">Save the record</span></span>

<span data-ttu-id="f0197-154">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="f0197-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f0197-155">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="f0197-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="f0197-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0197-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f0197-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0197-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="f0197-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0197-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="f0197-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0197-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f0197-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0197-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f0197-163">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="f0197-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f0197-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f0197-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="f0197-165">Office 365 のドメインのセットアップウィザードの最後の手順に戻ると、1つのタスクが残っています。</span><span class="sxs-lookup"><span data-stu-id="f0197-165">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining.</span></span> <span data-ttu-id="f0197-166">Office 365 サービスを使用してドメインをセットアップするには、メールのように、ドメインレジストラーでドメインのネームサーバー (NS) レコードを変更して、Office 365 プライマリネームサーバーとセカンダリネームサーバーを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="f0197-166">To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers.</span></span> <span data-ttu-id="f0197-167">その後、Office 365 が DNS をホストするため、サービスに必要な DNS レコードが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f0197-167">Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="f0197-168">ネーム サーバー レコード自体は、ドメイン レジストラーが Web サイトのヘルプで説明している手順に従って更新できます。</span><span class="sxs-lookup"><span data-stu-id="f0197-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="f0197-169">DNS が不明である場合は、ドメイン レジストラーのサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f0197-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="f0197-170">ドメインレジストラーの web サイトで、自分でドメインのネームサーバーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0197-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="f0197-171">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f0197-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f0197-172">2つのネームサーバーレコードを作成するか、または次の値に一致するように既存のネームサーバーレコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="f0197-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f0197-173">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f0197-173">First nameserver</span></span>  <br/> |<span data-ttu-id="f0197-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f0197-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f0197-175">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f0197-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="f0197-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f0197-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f0197-177">少なくとも2つのネームサーバーレコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="f0197-178">他のネームサーバーが表示されている場合は、それらを削除するか、 **ns3.bdm.microsoftonline.com**および**ns4.bdm.microsoftonline.com**に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0197-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="f0197-179">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f0197-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f0197-180">Office 365 ネームサーバーを参照するようにドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f0197-180">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f0197-181">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f0197-182">そうしないと、この変更により、メールのアクセスが不足している、現在の web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="f0197-183">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f0197-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f0197-184">2つのネームサーバーレコードを作成するか、または次の値に一致するように既存のネームサーバーレコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="f0197-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f0197-185">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f0197-185">First nameserver</span></span>  <br/> |<span data-ttu-id="f0197-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f0197-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="f0197-187">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="f0197-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="f0197-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f0197-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f0197-189">少なくとも2つのネームサーバーレコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="f0197-190">他のネームサーバーが表示されている場合は、それらを削除するか、 **ns3.dns.partner.microsoftonline.cn**および**ns4.dns.partner.microsoftonline.cn**に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0197-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="f0197-191">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f0197-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f0197-192">21Vianet のネームサーバーが運用している Office 365 をポイントするようにドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="f0197-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f0197-193">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f0197-194">そうしないと、この変更により、メールのアクセスが不足している、現在の web サイトにアクセスできないなど、サービスのダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="f0197-195">たとえば、電子メールと Web サイトのホスティングには、次のような追加の手順が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0197-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="f0197-196">NS レコードを変更する前に、ドメインを使うすべてのメール アドレスを Office 365 に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0197-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="f0197-197">www.fourthcoffee.com などの Web サイト アドレスで現在使用されているドメインを追加する場合は、ドメインの追加中に、サイトが現在ホストされている場所でこの Web サイトをホストし続けるための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0197-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="f0197-198">ドメインを追加して、サイトがホストされている場所に web サイトをホストしている場合は、次の手順を実行して、Office 365 をポイントするようにドメインの NS レコードを変更した後も、ユーザーが web サイトにアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0197-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="f0197-199">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0197-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="f0197-200">[ ドメイン] ページで、ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="f0197-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="f0197-201">[ **DNS 設定**] で [**カスタムレコード**] を選択し、[**新しいカスタムレコード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0197-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="f0197-202">追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0197-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="f0197-203">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0197-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f0197-p116">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0197-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

