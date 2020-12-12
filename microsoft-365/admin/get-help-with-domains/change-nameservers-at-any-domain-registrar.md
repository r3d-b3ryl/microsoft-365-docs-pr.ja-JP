---
title: 任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する
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
description: メールや Skype for Business Online のようなサービスで独自のドメイン名を使用するために、Microsoft 365 でドメインを追加して設定する方法について説明します。
ms.openlocfilehash: a4218b03e3f23ba8bc39c5eb84b42f87a71b9a65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658601"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="6c02d-103">任意のドメイン レジストラーで Microsoft 365 をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="6c02d-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="6c02d-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6c02d-105">最初 [にドメインのセットアップ (ホスト固有](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) の手順) を確認し、レジストラーの手順がインストールされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="6c02d-106">Microsoft 365 でドメインを追加および設定するには、次の手順に従って、メールや Teams のようなサービスで独自のドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="6c02d-107">これを行うには、ドメインを確認し、ドメインのネームサーバーを Microsoft 365 に変更して、正しい DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="6c02d-108">次のステートメントで状況が説明されている場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6c02d-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="6c02d-109">独自のドメインを所有し、Microsoft 365 で動作するドメインを設定する場合。</span><span class="sxs-lookup"><span data-stu-id="6c02d-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="6c02d-110">Microsoft 365 で DNS レコードを管理する場合。</span><span class="sxs-lookup"><span data-stu-id="6c02d-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="6c02d-111">(必要に応じて、独自 [の DNS レコードを管理できます](../setup/add-domain.md))。</span><span class="sxs-lookup"><span data-stu-id="6c02d-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="6c02d-112">確認のため TXT レコードまたは MX レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="6c02d-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="6c02d-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6c02d-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="6c02d-p103">これらのレコードのいずれか一方を作成します。推奨されるレコードの種類は TXT ですが、一部の DNS ホスティング プロバイダーではサポートしていないため、代わりに MX レコードを作成してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="6c02d-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="6c02d-p104">Microsoft 365 のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c02d-p105">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="6c02d-120">DNS ホスティング プロバイダーの Web サイトで、新しいレコードを作成できる領域を見つける</span><span class="sxs-lookup"><span data-stu-id="6c02d-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="6c02d-121">DNS ホスティング プロバイダーの Web サイトにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6c02d-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="6c02d-122">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="6c02d-123">ドメインに関する DNS レコードを編集可能なページを探します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="6c02d-124">レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="6c02d-124">Create the record</span></span>

<span data-ttu-id="6c02d-125">TXT レコードと MX レコードのどちらを作成しているかに応じて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="6c02d-126">**TXT レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="6c02d-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c02d-127">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6c02d-127">**Record Type**</span></span> <br/> |<span data-ttu-id="6c02d-128">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="6c02d-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="6c02d-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="6c02d-129">**Value**</span></span> <br/> |<span data-ttu-id="6c02d-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c02d-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="6c02d-131">TXT</span><span class="sxs-lookup"><span data-stu-id="6c02d-131">TXT</span></span>  <br/> |<span data-ttu-id="6c02d-132">次のいずれかを実行します。「 **@** 」と入力するか、フィールドを空白のままにするか、ドメイン名を入力します。  </span><span class="sxs-lookup"><span data-stu-id="6c02d-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="6c02d-133">> [!NOTE]> このフィールドの要件は、DNS ホストによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="6c02d-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6c02d-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6c02d-135">> [!NOTE]> これは例です。</span><span class="sxs-lookup"><span data-stu-id="6c02d-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="6c02d-136">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="6c02d-137">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6c02d-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6c02d-138">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="6c02d-139">**MX レコードを作成する場合は、以下の値を使います。**</span><span class="sxs-lookup"><span data-stu-id="6c02d-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c02d-140">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="6c02d-140">**Record Type**</span></span>|<span data-ttu-id="6c02d-141">**Alias** または **Host Name**</span><span class="sxs-lookup"><span data-stu-id="6c02d-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="6c02d-142">**Value**</span><span class="sxs-lookup"><span data-stu-id="6c02d-142">**Value**</span></span>|<span data-ttu-id="6c02d-143">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6c02d-143">**Priority**</span></span>|<span data-ttu-id="6c02d-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6c02d-144">**TTL**</span></span>|
|<span data-ttu-id="6c02d-145">MX</span><span class="sxs-lookup"><span data-stu-id="6c02d-145">MX</span></span>|<span data-ttu-id="6c02d-146">**@** か自分のドメインの名前のいずれかを入力します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="6c02d-147">MS=ms *XXXXXXXX* > [!NOTE]> これは例です。</span><span class="sxs-lookup"><span data-stu-id="6c02d-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="6c02d-148">Microsoft 365 の表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="6c02d-149">確認する方法</span><span class="sxs-lookup"><span data-stu-id="6c02d-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6c02d-150">**Priority** には、メール フローに使われる MX レコードとの競合を避けるために、既存の MX レコードよりも低い優先度を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="6c02d-151">優先度の詳細については、「[MX 優先度とは何ですか?](../setup/domains-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="6c02d-152">この値は、 **1 hour** 、または 1 時間に相当する分数 ( **60** ) や秒数 ( **3600** ) などに設定します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="6c02d-153">レコードを保存する</span><span class="sxs-lookup"><span data-stu-id="6c02d-153">Save the record</span></span>

<span data-ttu-id="6c02d-154">これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft 365 に戻り、Microsoft 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="6c02d-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="6c02d-155">Microsoft 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="6c02d-156">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6c02d-157">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="6c02d-158">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="6c02d-159">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6c02d-p109">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6c02d-163">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="6c02d-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="6c02d-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="6c02d-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="6c02d-165">Microsoft 365 のドメインセットアップ ウィザードの最後の手順に進むには、残りのタスクが 1 つ残っています。</span><span class="sxs-lookup"><span data-stu-id="6c02d-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="6c02d-166">メールなど、Microsoft 365 サービスでドメインをセットアップするには、ドメイン レジストラーでドメインのネームサーバー (または NS) レコードを変更して、Microsoft 365 プライマリネームサーバーとセカンダリ ネームサーバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="6c02d-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="6c02d-167">その後、Microsoft 365 は DNS をホストします。このため、サービスに必要な DNS レコードが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="6c02d-168">ネーム サーバー レコード自体は、ドメイン レジストラーが Web サイトのヘルプで説明している手順に従って更新できます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="6c02d-169">DNS が不明である場合は、ドメイン レジストラーのサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6c02d-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="6c02d-170">ドメイン レジストラーの Web サイトでドメインのネームサーバーを自分で変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="6c02d-171">ドメイン レジストラーの Web サイトで、ドメインのネームサーバーを変更できる領域、またはカスタム ネームサーバーを使用できる領域を探します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="6c02d-172">ネームサーバー レコードを作成するか、次の値に一致する既存のネームサーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6c02d-173">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-173">First nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6c02d-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6c02d-175">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6c02d-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6c02d-177">3 番目のネームサーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6c02d-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6c02d-179">4 番目のネームサーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6c02d-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6c02d-181">4 つのレコードすべてが追加されるのが最善ですが、レジストラーでサポートされているレコードが 2 つのみである場合は、ns1.bdm.microsoftonline.com **を追加\*\*\*\*ns2.bdm.microsoftonline.com。**</span><span class="sxs-lookup"><span data-stu-id="6c02d-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="6c02d-182">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6c02d-183">Microsoft 365 ネームサーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="6c02d-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6c02d-184">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="6c02d-185">そうしないと、この変更によってサービスのダウンタイムが発生する可能性があります。電子メール へのアクセスが不足したり、現在の Web サイトにアクセスできないなどです。</span><span class="sxs-lookup"><span data-stu-id="6c02d-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="6c02d-186">ドメイン レジストラーの Web サイトで、ドメインのネーム サーバーを編集できる場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="6c02d-187">2 つのネームサーバー レコードを作成するか、次の値に一致する既存のネームサーバー レコードを編集します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="6c02d-188">1 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-188">First nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6c02d-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="6c02d-190">2 番目のネーム サーバー</span><span class="sxs-lookup"><span data-stu-id="6c02d-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="6c02d-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="6c02d-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="6c02d-192">少なくとも 2 つのネームサーバー レコードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="6c02d-193">その他のネームサーバーが一覧表示されている場合は、それらを削除するか、または名前を変更して **ns3.dns.partner.microsoftonline.cn変更\*\*\*\*ns4.dns.partner.microsoftonline.cn。**</span><span class="sxs-lookup"><span data-stu-id="6c02d-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="6c02d-194">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6c02d-195">21Vianet が運用している Office 365 ネームサーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="6c02d-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6c02d-196">メール アドレスの追加など、ウィザードの途中でスキップした手順がある場合、あるいはそのドメインをブログ、ショッピング カートなどのサービスで使用している場合は、さらにいくつかの手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="6c02d-197">そうしないと、この変更によってサービスのダウンタイムが発生する可能性があります。メール へのアクセスが不足したり、現在の Web サイトにアクセスできないなどです。</span><span class="sxs-lookup"><span data-stu-id="6c02d-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="6c02d-198">たとえば、電子メールと Web サイトのホスティングには、次のような追加の手順が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c02d-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="6c02d-199">NS レコードを変更する前に、ドメインを使用しているすべてのメール アドレスを Microsoft 365 に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="6c02d-200">www.fourthcoffee.com などの Web サイト アドレスで現在使用されているドメインを追加する場合は、ドメインの追加中に、サイトが現在ホストされている場所でこの Web サイトをホストし続けるための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="6c02d-201">Microsoft 365 を指すドメインの NS レコードを変更した後も、ユーザーが引き続き Web サイトにアクセスできるよう、ドメインを追加して、サイトがホストされている場所で Web サイトをホストし続ける間、以下の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="6c02d-202">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="6c02d-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="6c02d-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="6c02d-204">[DNS **設定] で**、[カスタム レコード **] を** 選択し、[新しいカスタム レコード] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6c02d-204">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="6c02d-205">追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="6c02d-206">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c02d-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c02d-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6c02d-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6c02d-208">その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6c02d-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
