---
title: Google Domains で Microsoft をセットアップするためにネームサーバーを変更する
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google Domains でカスタム ドメインの DNS レコードを管理するために Microsoft をセットアップする方法について説明します。
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658442"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="8d9f3-103">Google Domains で Microsoft をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="8d9f3-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="8d9f3-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8d9f3-105">Microsoft が DNS レコードを管理する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="8d9f3-106">(必要に応じて [、Google Domains ですべての DNS レコードを管理できます](create-dns-records-at-google-domains.md))。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8d9f3-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8d9f3-107">Add a TXT record for verification</span></span>

<span data-ttu-id="8d9f3-p102">Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8d9f3-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8d9f3-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="8d9f3-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="8d9f3-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="8d9f3-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="8d9f3-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="8d9f3-114">To do so:</span></span>
    
1. <span data-ttu-id="8d9f3-115">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="8d9f3-116">ログイン資格情報を入力し、もう一度 [サインイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="8d9f3-117">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8d9f3-118">[**Custom resource records**] セクションにある新規レコードのボックスに、次の表の値を入力するかコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8d9f3-119">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="8d9f3-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="8d9f3-120">(ドロップダウン リストから [**Type**] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="8d9f3-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d9f3-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-121">**Name**</span></span> <br/> |<span data-ttu-id="8d9f3-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-122">**Type**</span></span> <br/> |<span data-ttu-id="8d9f3-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-123">**TTL**</span></span> <br/> |<span data-ttu-id="8d9f3-124">**データ**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="8d9f3-125">TXT</span><span class="sxs-lookup"><span data-stu-id="8d9f3-125">TXT</span></span>  <br/> |<span data-ttu-id="8d9f3-126">1H</span><span class="sxs-lookup"><span data-stu-id="8d9f3-126">1H</span></span>  <br/> |<span data-ttu-id="8d9f3-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8d9f3-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="8d9f3-128">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-128">**Note:** This is an example.</span></span> <span data-ttu-id="8d9f3-129">この表から **[宛先またはポイント先のアドレス]** の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="8d9f3-130">確認する方法</span><span class="sxs-lookup"><span data-stu-id="8d9f3-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="8d9f3-131">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="8d9f3-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8d9f3-133">ドメイン レジストラーのサイトでレコードを追加したので、Microsoft に戻り、レコードの検索を要求します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="8d9f3-134">Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8d9f3-135">Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8d9f3-136">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8d9f3-137">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8d9f3-138">**[ドメインの確認]** ページで、**[確認]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d9f3-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[ドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8d9f3-142">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="8d9f3-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8d9f3-143">Microsoft でドメインのセットアップを完了するには、ドメイン レジストラーでドメインの NS レコードを変更して、Microsoft のプライマリ ネーム サーバーとセカンダリ ネーム サーバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="8d9f3-144">これにより、ドメインの DNS レコードを更新する Microsoft がセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="8d9f3-145">メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8d9f3-146">Microsoft ネーム サーバーを指すドメインの NS レコードを変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8d9f3-147">たとえば、ドメインに送信されたメール (たとえば *、rob@your_domain。*</span><span class="sxs-lookup"><span data-stu-id="8d9f3-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="8d9f3-148">com) は、この変更を行った後に Microsoft に公開されます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8d9f3-149">次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="8d9f3-150">>このセクションの手順を完了すると、以下の 4 つのネームサーバーだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="8d9f3-p110">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="8d9f3-154">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="8d9f3-155">ログイン資格情報を入力してから、[**サインイン**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="8d9f3-156">[**ドメイン**] ページの [**ドメイン**] セクションで、編集するドメインの [**DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="8d9f3-157">[ **ドメイン**] ページの [ **ネームサーバー**] セクションで、[ **カスタム ネームサーバーを使用**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="8d9f3-159">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="8d9f3-160">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="8d9f3-161">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="8d9f3-162">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="8d9f3-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="8d9f3-163">最初のネームサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="8d9f3-164">[ **ネームサーバー**] セクションにある [ **ネームサーバー**] ボックスに、次の表の最初の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="8d9f3-165">**1 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-165">**First name server**</span></span> <br/> |<span data-ttu-id="8d9f3-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-167">**2 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-167">**Second name server**</span></span> <br/> |<span data-ttu-id="8d9f3-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-169">**3 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-169">**Third name server**</span></span> <br/> |<span data-ttu-id="8d9f3-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-171">**4 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="8d9f3-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="8d9f3-174">+ **(追加) コントロールを選択** して空の行を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="8d9f3-176">他の 3 つのネームサーバー レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="8d9f3-177">[カスタム ネーム **サーバーの** 使用] セクションで、表の次の行の値を使用してレコードを作成し、+ **(追加)** コントロールを選択して別の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="8d9f3-178">4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="8d9f3-179">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="8d9f3-181">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8d9f3-182">その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="8d9f3-183">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="8d9f3-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="8d9f3-184">他のネームサーバーが一覧表示されている場合は、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8d9f3-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="8d9f3-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="8d9f3-186">(つまり、名前が **ns1.bdm.microsoftonline.com**、ns2.bdm.microsoftonline.com、ns3.bdm.microsoftonline.com、または ns4.bdm.microsoftonline.com **))**  </span><span class="sxs-lookup"><span data-stu-id="8d9f3-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="8d9f3-188">ネームサーバーを選んで、キーボードの **Delete** キーを押して、1 つずつ削除します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="8d9f3-190">[ **ネームサーバー**] セクションの [ **ネームサーバー**] 行に、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="8d9f3-191">**1 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-191">**First name server**</span></span> <br/> |<span data-ttu-id="8d9f3-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-193">**2 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-193">**Second name server**</span></span> <br/> |<span data-ttu-id="8d9f3-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-195">**3 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-195">**Third name server**</span></span> <br/> |<span data-ttu-id="8d9f3-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8d9f3-197">**4 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="8d9f3-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="8d9f3-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d9f3-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="8d9f3-200">**+(add) コントロールを選択** して空の行を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="8d9f3-202">他の 2 つのネームサーバー レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="8d9f3-203">[カスタムネーム サーバーの使用] セクションで、表の次の行の値を使用してレコードを作成し **、+(add)** コントロールを選択して別の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="8d9f3-204">4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="8d9f3-205">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="8d9f3-207">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8d9f3-208">その後、Microsoft のメールと他のサービスはすべて、ドメインで動作する設定に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8d9f3-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
