---
title: Google Domains で Office 365 をセットアップするためにネームサーバーを変更する
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Google Domains でカスタムドメインの DNS レコードを管理するように Office 365 をセットアップする方法について説明します。
ms.openlocfilehash: f6faaa4a7b6540086752e88da2051a73450f4455
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351968"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="de7ec-103">Google Domains で Office 365 をセットアップするためにネームサーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="de7ec-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="de7ec-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="de7ec-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="de7ec-p101">Office 365 に Office 365 DNS レコードを管理させる場合は、次の手順に従います ([Google Domains で Office 365 のすべての DNS レコードを管理することもできます](create-dns-records-at-google-domains.md))。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="de7ec-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="de7ec-107">Add a TXT record for verification</span></span>

<span data-ttu-id="de7ec-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="de7ec-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="de7ec-112">開始するには、[このリンク](https://domains.google.com/registrar)を使用して Google domains のドメインページにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="de7ec-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="de7ec-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="de7ec-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="de7ec-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="de7ec-114">To do so:</span></span>
    
1. <span data-ttu-id="de7ec-115">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="de7ec-116">ログイン資格情報を入力して、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="de7ec-117">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="de7ec-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="de7ec-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="de7ec-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="de7ec-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="de7ec-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="de7ec-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de7ec-121">**名前**</span><span class="sxs-lookup"><span data-stu-id="de7ec-121">**Name**</span></span> <br/> |<span data-ttu-id="de7ec-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="de7ec-122">**Type**</span></span> <br/> |<span data-ttu-id="de7ec-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="de7ec-123">**TTL**</span></span> <br/> |<span data-ttu-id="de7ec-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="de7ec-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="de7ec-125">TXT</span><span class="sxs-lookup"><span data-stu-id="de7ec-125">TXT</span></span>  <br/> |<span data-ttu-id="de7ec-126">1H</span><span class="sxs-lookup"><span data-stu-id="de7ec-126">1H</span></span>  <br/> |<span data-ttu-id="de7ec-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="de7ec-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="de7ec-128">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="de7ec-128">**Note:** This is an example.</span></span> <span data-ttu-id="de7ec-129">Office 365 の表から [**宛先またはポイント先のアドレス**] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="de7ec-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="de7ec-130">確認する方法</span><span class="sxs-lookup"><span data-stu-id="de7ec-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="de7ec-131">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="de7ec-132">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="de7ec-133">これで、ドメイン レジストラーのサイトでレコードが追加されました。Office 365 に戻り、Office 365 にレコードの検索をリクエストします。</span><span class="sxs-lookup"><span data-stu-id="de7ec-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="de7ec-134">Office 365 で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。</span><span class="sxs-lookup"><span data-stu-id="de7ec-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="de7ec-135">管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="de7ec-136">**[ドメイン]** ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="de7ec-137">**[セットアップ]** ページで、**[セットアップの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="de7ec-138">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="de7ec-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="de7ec-142">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="de7ec-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="de7ec-p107">Office 365 でドメインをセットアップするには、Office 365 のプライマリ ネーム サーバーとセカンダリ ネーム サーバーを参照するように、ドメインの NS レコードをドメイン レジストラーで変更します。これで、ドメインの DNS レコードを更新するように Office 365 で設定されます。メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="de7ec-146">ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="de7ec-147">たとえば、ドメインに送信されるすべての電子メール (rob@ など*your_domain。*</span><span class="sxs-lookup"><span data-stu-id="de7ec-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="de7ec-148">この変更を行った後、com) は Office 365 に送られ始めます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="de7ec-149">次の手順では、他の不要なネームサーバーを一覧から削除する方法、および上記のネームサーバーが一覧に表示されていない場合に、正しいネームサーバーを追加する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="de7ec-150">> このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="de7ec-p110">まず、[このリンク](https://domains.google.com/registrar)を使って Google Domains でドメイン ページにアクセスします。 サインインするように求められます。 そのためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="de7ec-154">[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="de7ec-155">ログイン資格情報を入力してから、もう一度 [**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="de7ec-156">[ドメイン **] ページの**[**ドメイン**] セクションで、編集するドメインの [ **DNS の構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="de7ec-157">[ **ドメイン**] ページの [ **ネームサーバー**] セクションで、[ **カスタム ネームサーバーを使用**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="de7ec-159">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="de7ec-160">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="de7ec-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="de7ec-161">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="de7ec-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="de7ec-162">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="de7ec-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="de7ec-163">最初のネームサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="de7ec-164">[ **ネームサーバー**] セクションにある [ **ネームサーバー**] ボックスに、次の表の最初の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="de7ec-165">**1 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-165">**First name server**</span></span> <br/> |<span data-ttu-id="de7ec-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-167">**2 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-167">**Second name server**</span></span> <br/> |<span data-ttu-id="de7ec-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-169">**3 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-169">**Third name server**</span></span> <br/> |<span data-ttu-id="de7ec-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-171">**4 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="de7ec-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-ドメイン-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="de7ec-174">空の行を作成するには、[ **+ (追加)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="de7ec-176">他の 3 つのネームサーバー レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="de7ec-177">[**カスタムの名前サーバーを使用**する] セクションで、表の次の行の値を使用してレコードを作成し、[ **+ (追加)** ] コントロールを選択して別の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="de7ec-178">4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="de7ec-179">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="de7ec-p111">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="de7ec-183">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="de7ec-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="de7ec-184">他のネームサーバーが表示されている場合は、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="de7ec-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="de7ec-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="de7ec-186">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="de7ec-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="de7ec-188">ネームサーバーを選んで、キーボードの **Delete** キーを押して、1 つずつ削除します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="de7ec-190">[ **ネームサーバー**] セクションの [ **ネームサーバー**] 行に、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="de7ec-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="de7ec-191">**1 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-191">**First name server**</span></span> <br/> |<span data-ttu-id="de7ec-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-193">**2 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-193">**Second name server**</span></span> <br/> |<span data-ttu-id="de7ec-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-195">**3 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-195">**Third name server**</span></span> <br/> |<span data-ttu-id="de7ec-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="de7ec-197">**4 番目のネーム サーバー**</span><span class="sxs-lookup"><span data-stu-id="de7ec-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="de7ec-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="de7ec-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-ドメイン-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="de7ec-200">空の行を作成するには、[ **+ (追加)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="de7ec-202">他の 2 つのネームサーバー レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="de7ec-203">[**カスタムの名前サーバーを使用**する] セクションで、表の次の行の値を使用してレコードを作成し、[ **+ (追加)** ] コントロールを選択して別の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="de7ec-204">4 つのネームサーバー レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="de7ec-205">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de7ec-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="de7ec-p113">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de7ec-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
